
---
title: Programmatic access - Downloading data at every UniProt release
categories: UniProtKB,UniRef,UniParc,Programmatic_access,Download,help
---

The [HTTP header](http://www.w3.org/Protocols/rfc2616/rfc2616%2Dsec14.html) `Last-Modified:` will avoid that you download data more than once per release, if you use a download tool that makes use of this information, e.g. the unix commands `lwp-mirror` or `curl` with the `-z` option. Here are examples of how to do this in Perl:

*   [Download all UniProt sequences for a given organism in FASTA format](http://www.uniprot.org/help/api_downloading#download_perl_example1)  
      
    
    use strict;
    use warnings;
    use LWP::UserAgent;
    use HTTP::Date;
    
    my $taxon = $ARGV\[0\]; # Taxonomy identifier of organism.
    
    my $query = "https://www.uniprot.org/uniprot/?query=organism:$taxon&format=fasta";
    my $file = $taxon . '.fasta';
    
    my $contact = ''; # Please set a contact email address here to help us debug in case of problems (see https://www.uniprot.org/help/privacy).
    my $agent = LWP::UserAgent->new(agent => "libwww-perl $contact");
    my $response = $agent->mirror($query, $file);
    
    if ($response->is\_success) {
      my $results = $response->header('X-Total-Results');
      my $release = $response->header('X-UniProt-Release');
      my $date = sprintf("%4d-%02d-%02d", HTTP::Date::parse\_date($response->header('Last-Modified')));
      print "Downloaded $results entries of UniProt release $release ($date) to file $file\\n";
    }
    elsif ($response->code == HTTP::Status::RC\_NOT\_MODIFIED) {
      print "Data for taxon $taxon is up-to-date.\\n";
    }
    else {
      die 'Failed, got ' . $response->status\_line .
        ' for ' . $response->request->uri . "\\n";
    }
    
*   [Download the UniProt reference proteomes for all organisms below a given taxonomy node in compressed FASTA format](http://www.uniprot.org/help/api_downloading#download_perl_example2)  
      
    
    use strict;
    use warnings;
    use LWP::UserAgent;
    use HTTP::Date;
    
    # Taxonomy identifier of top node for query, e.g. 2 for Bacteria, 2157 for Archea, etc.
    # (see https://www.uniprot.org/taxonomy)
    my $top\_node = $ARGV\[0\];
    
    my $agent = LWP::UserAgent->new;
    
    # Get a list of all reference proteomes of organisms below the given taxonomy node.
    my $query\_list = "https://www.uniprot.org/proteomes/?query=reference:yes+taxonomy:$top\_node&format=list";
    my $response\_list = $agent->get($query\_list);
    die 'Failed, got ' . $response\_list->status\_line .
      ' for ' . $response\_list->request->uri . "\\n"
      unless $response\_list->is\_success;
    
    # For each proteome, mirror its set of UniProt entries in compressed FASTA format.
    for my $proteome (split(/\\n/, $response\_list->content)) {
      my $file = $proteome . '.fasta.gz';
      my $query\_proteome = "https://www.uniprot.org/uniprot/?query=proteome:$proteome&format=fasta&compress=yes";
      my $response\_proteome = $agent->mirror($query\_proteome, $file);
    
      if ($response\_proteome->is\_success) {
        my $results = $response\_proteome->header('X-Total-Results');
        my $release = $response\_proteome->header('X-UniProt-Release');
        my $date = sprintf("%4d-%02d-%02d", HTTP::Date::parse\_date($response\_proteome->header('Last-Modified')));
        print "File $file: downloaded $results entries of UniProt release $release ($date)\\n";
      }
      elsif ($response\_proteome->code == HTTP::Status::RC\_NOT\_MODIFIED) {
        print "File $file: up-to-date\\n";
      }
      else {
        die 'Failed, got ' . $response\_proteome->status\_line .
          ' for ' . $response\_proteome->request->uri . "\\n";
      }
    }
    

#### Release number and date

If you would like to record the UniProt release number and/or date of the data which you retrieve, you can extract this information from the [HTTP header](http://www.w3.org/Protocols/rfc2616/rfc2616%2Dsec14.html) of the response (see this Perl example):

use strict;
use warnings;
use LWP::UserAgent;

my $query = $ARGV\[0\]; # Query URL.

my $contact = ''; # Please set a contact email address here to help us debug in case of problems (see https://www.uniprot.org/help/privacy).
my $agent = LWP::UserAgent->new(agent => "libwww-perl $contact");
my $response = $agent->get($query);

if ($response->is\_success) {
  print 'UniProt release ' . $response->header('X-UniProt-Release') .
  ' of ' . $response->header('Last-Modified') . "\\n";
}
else {
  die 'Failed, got ' . $response->status\_line .
    ' for ' . $response->request->uri . "\\n";
}

*   `X-UniProt-Release:` contains the UniProt release number, e.g. `2010_08`
*   `Last-Modified:` contains the UniProt release date, e.g. `Tue, 13 Jul 2010 00:00:00 GMT`

See also:  
  
[REST API - Access the UniProt website programmatically](http://www.uniprot.org/help/api) - batch retrieval, ID mapping, queries, downloads, etc  
  
[How can I (programmatically) obtain the number of results returned by my query?](http://www.uniprot.org/help/entry%5Fcount)
        