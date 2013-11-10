fontconfig profile
==================

This repository contains a customized configuration file to
[fontconfig](http://fontconfig.org) with a comfortable look on CJK 
characters. 

The main work on this configuration is to make a font fallback among fonts.

Prerequisite
------------

You are expected to have following fonts in your `$XDG_CONFIG_HOME/fonts`
directory. (`~/.fonts` directory is deprecated, and it's support will be
removed in the future)

* TODO

Refer to font wiki of your linux distribution to find packages.

And for me, it's 
[fedora wiki](http://fedoraproject.org/wiki/Category:Packaged_fonts)

Application
-----------

Typically, the repository is located at `$XDG_CONFIG_HOME/fontconfig` 
in which `$XDG_CONFIG_HOME` refers to `~/.config` if not specified.

Thus, if you have not yet set your fontconfig, use following script to
checkout the repository.

```shell

cd ~/.config # Default $XDG_CONFIG_HOME
git clone https://github.com/shinohane/fontconfig.git

```

Otherwise, you are expected to backup your configuration first and put your
customization into `~/.config/fontconfig/conf.d/` which will be
automatically included to the configuration. 
**Any help from your fork is welcomed :)**

For more information about the configuration detail, see
<http://www.freedesktop.org/wiki/Software/fontconfig/>

Contributor
-----------

shinohane &lt;trinity&#x2605;dummi.org&gt;

License
-------

(The MIT License)

