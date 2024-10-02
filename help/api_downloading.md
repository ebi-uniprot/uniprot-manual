---
title: Programmatic access - Downloading data at every UniProt release
type: help
categories: UniProtKB,UniRef,UniParc,Programmatic_access,Download,help
---

# Use `X-UniProt-Release-Date` To Avoid Re-Downloading The Same Data Per Release

You can use the [HTTP header](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html) `X-UniProt-Release-Date:`\* to avoid downloading data more than once per release, if you use a download tool that makes use of this information, e.g. the unix commands `lwp-mirror` or `curl` with the `-z` option. Here is an example of how to do this in Perl:

## Download all UniProt sequences for a given organism in FASTA format\*\*

```perl
use strict;
use warnings;
use LWP::UserAgent;
use HTTP::Date;

my $organism_id = $ARGV[0]; # Organism identifier of organism.

my $query = "https://rest.uniprot.org/uniprotkb/stream?query=organism_id:$organism_id&format=fasta";

my $file = $organism_id . '.fasta';

my $contact = ''; # Please set a contact email address here to help us debug in case of problems (see https://www.uniprot.org/help/privacy).
my $agent = LWP::UserAgent->new( agent => "libwww-perl $contact" );
my $response = $agent->mirror( $query, $file );

if ( $response->is_success ) {
    my $results      = $response->header('X-Total-Results');
    my $release      = $response->header('X-UniProt-Release');
    my $release_date = $response->header('X-UniProt-Release-Date');
    print
"Downloaded FASTAs for organism ID: $organism_id from UniProt release $release ($release_date) to file $file\n";
}
elsif ( $response->code == HTTP::Status::RC_NOT_MODIFIED ) {
    print "Data for taxon $organism_id is up-to-date.\n";
}
else {
    die 'Failed, got '
      . $response->status_line . ' for '
      . $response->request->uri . "\n";
}
```

## Download the UniProt reference proteomes for all organisms below a given taxonomy node in compressed FASTA format\*\*

```perl
use strict;
use warnings;
use LWP::UserAgent;
use LWP::Simple;
use HTTP::Date;

# Taxonomy identifier of top node for query, e.g. 2 for Bacteria, 2157 for Archea, etc.
# (see https://www.uniprot.org/taxonomy)
my $top_node = $ARGV[0];

my $agent = LWP::UserAgent->new;

# Get TSV of all reference proteomes of organisms below the given taxonomy node.
my $query_list = "https://rest.uniprot.org/proteomes/stream?&query=reference:true+taxonomy_id:$top_node&fields=upid,lineage,organism_id&format=tsv";

my $response_list = $agent->get($query_list);
if ( $response_list->is_success ) {
    my $release = $response_list->header('x-uniprot-release');
    my $date    = $response_list->header('x-uniprot-release-date');
    print "Fetching FASTAs from UniProt release $release ($date)\n";
}
elsif ( $response_list->code == HTTP::Status::RC_NOT_MODIFIED ) {
    print "Data for taxon $top_node is up-to-date.\n";
}
else {
    die 'Failed, got '
      . $response_list->status_line . ' for '
      . $response_list->request->uri . "\n";
}

# For each proteome, fetch compressed FASTA from FTP.
my @lines = split( /\n/, $response_list->content );
# Skip the TSV header by starting from 1.
for my $index ( 1 .. $#lines ) {
    my @line                     = split( /\t/, $lines[$index] );
    my $upid                     = $line[0];
    my @taxonomic_lineage_column = split( /,\s/, $line[1] );
    my $domain                   = $taxonomic_lineage_column[1]; # first column is "cellular organisms", second is kingdom
    my $organism_id              = $line[2];
    my $url = "https://ftp.ebi.ac.uk/pub/databases/uniprot/current_release/knowledgebase/reference_proteomes/$domain/$upid/$upid\_$organism_id.fasta.gz";
    my $file = "$upid.fasta.gz";
    my $response_ftp = getstore( $url, $file );

    if ( is_success($response_ftp) ) {
        print "Fetched $url\n";
    }
    if ( is_error($response_ftp) ) {
        die "getstore of <$url> failed with $response_ftp";
    }
}
```

# Release number and date

If you would like to record the UniProt release number and/or date of the data which you retrieve, you can extract this information from the [HTTP header](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html) of the response (see this Perl example):

```perl
use strict;
use warnings;
use LWP::UserAgent;

my $query = $ARGV[0];    # Query URL.

my $contact = ''; # Please set a contact email address here to help us debug in case of problems (see https://www.uniprot.org/help/privacy).
my $agent = LWP::UserAgent->new( agent => "libwww-perl $contact" );
my $response = $agent->get($query);

if ( $response->is_success ) {
    print 'UniProt release '
      . $response->header('X-UniProt-Release') . ' of '
      . $response->header('X-UniProt-Release-Date') . "\n";
}
else {
    die 'Failed, got '
      . $response->status_line . ' for '
      . $response->request->uri . "\n";
}
```

- `X-UniProt-Release:` contains the UniProt release number, e.g. `2010_08`
- `X-UniProt-Release-Date:`\* contains the UniProt release date, e.g. `02-January-2022`
- `X-API-Deployment-Date:` contains the API deployment date, can be different from release date (in case of hotfix) e.g. `03-January-2022`

# See also

- [REST API - Access the UniProt website programmatically](https://www.uniprot.org/help/api)
- \- batch retrieval, ID mapping, queries, downloads, etc
- [How can I (programmatically) obtain the number of results returned by my query?](https://www.uniprot.org/help/entry_count)

\* Before July 2022, the "Last-Modified" header was inaccurately used for this.
