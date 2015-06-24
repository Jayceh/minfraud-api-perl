# NAME

WebService::MinFraud - Perl API for MaxMind's minFraud web services

# VERSION

version 0.001001

# SYNOPSIS

    use 5.010;
    use WebService::MinFraud::Client;

    my $client = WebService::MinFraud::Client->new(
        user_id     => '42',
        license_key => 'abcdef123456',
    );

    my $request = { device => { ip_address => '24.24.24.24' } }:
    my $score   = $client->score( $request );
    say $score->risk_score;

    my $insights = $client->insights( $request );
    say $insights->shipping_address->is_high_risk;

# DESCRIPTION

This distribution provides an API for the
[MaxMind minFraud Score and Insights web services](http://dev.maxmind.com/minfraud/minfraud-score-and-insights-api-documentation/).

See [WebService::MinFraud::Client](https://metacpan.org/pod/WebService::MinFraud::Client) for details on using the web service client
API.

# VERSIONING POLICY

The minFraud perl API uses [Semantic Versioning](http://semver.org/).

# PERL VERSION SUPPORT

The minimum required perl version for the minFraud perl API is 5.10.0.

The data returned from the minFraud web services includes Unicode characters
in several locales. This may expose bugs in earlier versions of perl.  If
Unicode is important to your work, we recommend that you use the most recent
version of perl available.

# SUPPORT

Please report all issues with this distribution using the GitHub issue tracker
at [https://github.com/maxmind/minfraud-api-perl/issues](https://github.com/maxmind/minfraud-api-perl/issues).

If you are having an issue with a MaxMind service that is not specific to the
client API please visit [http://www.maxmind.com/en/support](http://www.maxmind.com/en/support) for details.

# AUTHOR

Mateu Hunter <mhunter@maxmind.com>

# CONTRIBUTOR

Mateu X Hunter <hunter@missoula.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2015 by MaxMind, Inc..

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
