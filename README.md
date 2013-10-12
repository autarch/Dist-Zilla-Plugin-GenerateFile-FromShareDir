# NAME

Dist::Zilla::Plugin::GenerateFile::ShareDir - Create files in the build, based on a template located in a dist sharedir

# VERSION

version 0.001

# SYNOPSIS

In your `dist.ini`:

    [GenerateFile::ShareDir]
    -dist = Dist::Zilla::PluginBundle::Author::ME
    -source_filename = my_data_template.txt
    -destination_filename = examples/my_data.txt
    key1 = value to pass to template
    key2 = another value to pass to template

# DESCRIPTION

Generates a file in your dist, indicated by `-destination_file`, based on the
[Text::Template](http://search.cpan.org/perldoc?Text::Template) located in the `-source_file` of `-dist`'s
[distribution sharedir](http://search.cpan.org/perldoc?File::ShareDir). Any extra config values are passed
along to the template, in addition to `$zilla` and `$plugin` objects.

I expect that usually the `-dist` that contains the template will be either a
plugin bundle, so you can generate a custom-tailored file in your dist, or a
plugin that subclasses this one.

# OPTIONS

This plugin accepts the following options:

- `-dist`

    The distribution name to use when finding the sharedir (see [File::ShareDir](http://search.cpan.org/perldoc?File::ShareDir)
    and [Dist::Zilla::Plugin::ShareDir](http://search.cpan.org/perldoc?Dist::Zilla::Plugin::ShareDir)). Defaults to the dist corresponding to
    the running plugin.

- `-destination_filename` or `-filename`

    The filename to generate in the distribution being built. Required.

- `-source_filename`

    The filename in the sharedir to use to generate the new file. Defaults to the
    same filename and path as `-destination_file`.

- `arbitrary option`

    All other keys/values provided will be passed to the template as is.

# SUPPORT

Bugs may be submitted through [the RT bug tracker](https://rt.cpan.org/Public/Dist/Display.html?Name=Dist-Zilla-Plugin-GenerateFile-ShareDir)
(or [bug-Dist-Zilla-Plugin-GenerateFile-ShareDir@rt.cpan.org](mailto:bug-Dist-Zilla-Plugin-GenerateFile-ShareDir@rt.cpan.org)).
I am also usually active on irc, as 'ether' at `irc.perl.org`.

# SEE ALSO

- [File::ShareDir](http://search.cpan.org/perldoc?File::ShareDir)
- [Dist::Zilla::Plugin::ShareDir](http://search.cpan.org/perldoc?Dist::Zilla::Plugin::ShareDir)
- [Text::Template](http://search.cpan.org/perldoc?Text::Template)

# AUTHOR

Karen Etheridge <ether@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2013 by Karen Etheridge.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
