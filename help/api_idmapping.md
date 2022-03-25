---
title: Programmatic access - Mapping database identifiers
categories: UniProtKB,UniRef,UniParc,Programmatic_access,Technical,help
---

To use our [database identifier mapping ('Retrieve/ID mapping')](https://www.uniprot.org/help/uploadlists) service programmatically you need to know the abbreviations for the database names. Some databases map only one way. You can find this table below the links to our code examples.

Here are some examples for querying the database mapping service using:

-   Perl

      

        use strict;
        use warnings;
        use LWP::UserAgent;

        my $base = 'https://www.uniprot.org';
        my $tool = 'uploadlists';

        my $params = {
          from => 'ACC',
          to => 'P_REFSEQ_AC',
          format => 'tab',
          query => 'P13368 P20806 Q9UM73 P97793 Q17192'
        };

        my $contact = ''; # Please set a contact email address here to help us debug in case of problems (see https://www.uniprot.org/help/privacy).
        my $agent = LWP::UserAgent->new(agent => "libwww-perl $contact");
        push @{$agent->requests_redirectable}, 'POST';

        my $response = $agent->post("$base/$tool/", $params);

        while (my $wait = $response->header('Retry-After')) {
          print STDERR "Waiting ($wait)...n";
          sleep $wait;
          $response = $agent->get($response->base);
        }

        $response->is_success ?
          print $response->content :
          die 'Failed, got ' . $response->status_line .
            ' for ' . $response->request->uri . "n";

-   Python 2

      

        import urllib,urllib2

        url = 'https://www.uniprot.org/uploadlists/'

        params = {
        'from':'ACC',
        'to':'P_REFSEQ_AC',
        'format':'tab',
        'query':'P13368 P20806 Q9UM73 P97793 Q17192'
        }

        data = urllib.urlencode(params)
        request = urllib2.Request(url, data)
        contact = "" # Please set a contact email address here to help us debug in case of problems (see https://www.uniprot.org/help/privacy).
        request.add_header('User-Agent', 'Python %s' % contact)
        response = urllib2.urlopen(request)
        page = response.read(200000)

-   Python 3

      

        import urllib.parse
        import urllib.request

        url = 'https://www.uniprot.org/uploadlists/'

        params = {
        'from': 'ACC+ID',
        'to': 'ENSEMBL_ID',
        'format': 'tab',
        'query': 'P40925 P40926 O43175 Q9UM73 P97793'
        }

        data = urllib.parse.urlencode(params)
        data = data.encode('utf-8')
        req = urllib.request.Request(url, data)
        with urllib.request.urlopen(req) as f:
           response = f.read()
        print(response.decode('utf-8'))

-   Ruby

      

        ##? tool_example.rb ?##
        require 'net/http'

        base = 'www.uniprot.org'
        tool = 'uploadlists'
        params = {
          'from' => 'ACC', 'to' => 'P_REFSEQ_AC', 'format' => 'tab',
          'query' => 'P13368 P20806 Q9UM73 P97793 Q17192'
        }

        http = Net::HTTP.new base
        $stderr.puts "Submitting...n";
        response = http.request_post '/' + tool + '/',
          params.keys.map {|key| key + '=' + params[key]}.join('&')

        loc = nil
        while response.code == '302'
          loc = response['Location']
          response = http.request_get loc
        end

        while loc
          wait = response['Retry-After'] or break
          $stderr.puts "Waiting (#{wait})...n";
          sleep wait.to_i
          response = http.request_get loc
        end

        response.value # raises http error if not 2xx
        puts response.body

-   Java

      

        package example;

        import java.io.InputStream;
        import java.io.UnsupportedEncodingException;
        import java.net.HttpURLConnection;
        import java.net.URL;
        import java.net.URLConnection;
        import java.net.URLEncoder;
        import java.util.logging.Logger;

        public class Example
        {
          private static final String UNIPROT_SERVER = "https://www.uniprot.org/";
          private static final Logger LOG = Logger.getAnonymousLogger();

          private static void run(String tool, ParameterNameValue[] params)
            throws Exception
          {
            StringBuilder locationBuilder = new StringBuilder(UNIPROT_SERVER + tool + "/?");
            for (int i = 0; i < params.length; i++)
            {
              if (i > 0)
                locationBuilder.append('&');
              locationBuilder.append(params[i].name).append('=').append(params[i].value);
            }
            String location = locationBuilder.toString();
            URL url = new URL(location);
            LOG.info("Submitting...");
            HttpURLConnection conn = (HttpURLConnection) url.openConnection();
            HttpURLConnection.setFollowRedirects(true);
            conn.setDoInput(true);
            conn.connect();

            int status = conn.getResponseCode();
            while (true)
            {
              int wait = 0;
              String header = conn.getHeaderField("Retry-After");
              if (header != null)
                wait = Integer.valueOf(header);
              if (wait == 0)
                break;
              LOG.info("Waiting (" + wait + ")...");
              conn.disconnect();
              Thread.sleep(wait * 1000);
              conn = (HttpURLConnection) new URL(location).openConnection();
              conn.setDoInput(true);
              conn.connect();
              status = conn.getResponseCode();
            }
            if (status == HttpURLConnection.HTTP_OK)
            {
              LOG.info("Got a OK reply");
              InputStream reader = conn.getInputStream();
              URLConnection.guessContentTypeFromStream(reader);
              StringBuilder builder = new StringBuilder();
              int a = 0;
              while ((a = reader.read()) != -1)
              {
                builder.append((char) a);
              }
              System.out.println(builder.toString());
            }
            else
              LOG.severe("Failed, got " + conn.getResponseMessage() + " for "
                + location);
            conn.disconnect();
          }

          public static void main(String[] args)
            throws Exception
          {
            run("uploadlists", new ParameterNameValue[] {
              new ParameterNameValue("from", "ACC"),
              new ParameterNameValue("to", "P_REFSEQ_AC"),
              new ParameterNameValue("format", "tab"),
              new ParameterNameValue("query", "P13368 P20806 Q9UM73 P97793 Q17192"),
            });
          }

          private static class ParameterNameValue
          {
            private final String name;
            private final String value;

            public ParameterNameValue(String name, String value)
              throws UnsupportedEncodingException
            {
              this.name = URLEncoder.encode(name, "UTF-8");
              this.value = URLEncoder.encode(value, "UTF-8");
            }
          }
        }

When mapping between UniProtKB accession numbers and gene names, it is possible (and often advisable) to include a taxonomy filter, as in this PERL example excerpt:

    from => 'GENENAME',
    to => 'ACC',
    format => 'tab',
    columns => 'id,entry_name,reviewed',
    query => 'BRCA1, ALB, TP53',  # list of gene names
    taxon => '9606',              # taxonomy identifier for Homo sapiens (Human).

Alternatively, you can download the data underlying our [database identifier service mapping service](https://www.uniprot.org/uploadlists) from [https://ftp.uniprot.org/pub/databases/uniprot/current\_release/knowledgebase/idmapping/](https://ftp.uniprot.org/pub/databases/uniprot/current%5Frelease/knowledgebase/idmapping/)

See also:

-   [REST API - Access the UniProt website programmatically](https://www.uniprot.org/help/api)
-   \- batch retrieval, ID mapping, queries, downloads, etc

Related terms: programmatic access, program, script, wget, curl, web services, API, uploadlists

Name

Abbreviation

Direction

See also:

-   [REST API - Access the UniProt website programmatically](https://www.uniprot.org/help/api)
-   \- batch retrieval, ID mapping, queries, downloads, etc

Related terms: programmatic access, program, script, wget, curl, web services, API, uploadlists, ID converter, convert identifiers
