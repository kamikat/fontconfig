fontconfig
==========

This repository contains a set of [fontconfig](http://fontconfig.org) configuration file to
improve CJK display on Linux desktop environment with reasonable font fallback configuration.

Support both Chinese and Japanese.

Prerequisite
------------

You are expected to have following fonts in your fonts path:

* `/usr/share/fonts`
* `/usr/share/X11/fonts/Type1`
* `/usr/share/X11/fonts/TTF`
* `/usr/local/share/fonts`
* `$XDG_DATA_HOME/fonts` defaults to `~/.local/share/fonts`

(`~/.fonts` directory is deprecated, and it's support will be removed in the future)

**ASCII Font Support**

* DejaVu Serif (ASCII Serif)
* STIXGeneral (ASCII Serif)
* DejaVu Sans Condensed (ASCII Sans)
* Courier Typewritter (ASCII Monpspace Courier 10 Pitch modified v2)

  Monospace Font based on "Courier 10 Pitch" modified by @Thynson to get
  better appearance.

**CJK Font Support**

* Droid Sans (CJK Sans including "Droid Sans Fallback"&"Droid Sans Japanese")
* Adobe Song Std (ZH Serif "Adobe 宋体")
* AR PLBaosong2GBK Light (ZH Serif "文鼎报宋")
* Adobe Ming Std (JPN Serif "Adobe 明體")
* IPAMincho (JPN Serif "IPA 明朝")
* IPAexMincho (JPN Serif "IPAex 明朝")

**Optional Font Support**

* Courier X (ASCII Monospace.opt Courier 10 Pitch modified v3)

  Monospace Font based on "Courier 10 Pitch" modified by @Thynson with ASCII
  characters aligned to CJK characters. (Experimental)

* Adobe Fangsong Std (ZH Monospace.opt "Adobe 仿宋")

First, use `fc-list` to check for all available fonts you will need.

`DejaVu` font series are available across most distributions.
You can get Adobe&copy; Fonts from its product granted.

"[Courier X](https://github.com/thynson/Courier-X-Fonts)" and
"[Courier Typewritter](https://github.com/kamikat/Courier-Typewritter-Fonts)"
can be obtained from GitHub.

As for other missing font, refer to font [wiki](http://fedoraproject.org/wiki/Category:Packaged_fonts)
of your distribution to get packages. Or just get font file from Internet.

On Fedora, `yum install stix-fonts ipa-*-fonts google-droid-*-fonts` should install
all fonts required from repository.

Usage
-----

Download the repository to `$XDG_CONFIG_HOME/fontconfig` and
in most cases `$XDG_CONFIG_HOME` refers to `~/.config`.

```sh
cd ~/.config # Default $XDG_CONFIG_HOME
git clone https://github.com/kirisetsz/fontconfig.git
```

If `fontconfig` exists, backup configuration and put them to `conf.d/` folder of current project.

The repository, Chinese configurations are activated by default.
Check `conf.avail` for all avaliable options and pick up your settings.

40-console.conf
---------------

This configuration exposes a font shortcut called `Console`.
It's designed to be used under terminal with
[Courier X](https://github.com/thynson/Courier-X-Fonts) and
Adobe Fangsong Std font family

You may not find the font shortcut from a gtk font chooser.
If you'd like to have a try, enable it from `dconf` for Gnome Terminal:

```sh
# list all profiles
dconf list /org/gnome/terminal/legacy/profiles:/
# set font of profile
dconf write /org/gnome/terminal/legacy/profiles:/$PROFILE_ID/font "'Console 14'"
```

For more information about the configuration detail, see <http://www.freedesktop.org/wiki/Software/fontconfig/>

Contributors
------------

Thynson &lt;thynson&#x2606;dummi.org&gt;

Kamikat &lt;misaka&#x2605;dummi.org&gt;

License
-------

(The MIT License)

