Minecraft-Cydia is a full fletched pastebin based on open Stikked and PHP. Uploads on this will be able to be used on the Cydia Repository Engine. View MCydia for installing Cydia Repository.


Try it out
----------

Coming soon, not ready. 

Installation
------------

**THIS IS NOT SUPPORTED! PLEASE WAIT UNTIL OFFICAL FULL RELEASE!**
1. Download stikked from https://github.com/claudehohl/Stikked/tags
2. Create a user and database for Stikked
3. Copy application/config/stikked.php.default to application/config/stikked.php
4. Edit configuration settings in application/config/stikked.php - everything is described there
5. You're done!

* The database structure will be created automatically if it doesn't exist.
* No special file permissions are needed by default. Optional: If you want to have the JavaScript- and CSS-files minified, the static/asset/ folder has to be writable.
* To ensure that pastes with an expiration set get cleaned up, define the cron key in the config and set up a cronjob, for example:
  * `*/5 * * * * curl --silent http://yoursite.com/cron/[key]`


Changelog
---------

### Version 0.9.0:

* New translations: Japanese, Chinese-Simplified, Chinese-Traditional, Russian
* New themes: Stikkedizr, Cleanwhite
* Display QR code in paste
* Multiline highlighter
* Encrypted pastes (yeah!) - see it in action: http://paste.scratchbook.ch/view/1427473f#iP7p05DRH0BC72qQjxv01BjUeOmNV073
* Added "burn on reading" as expiration
* Search function - search in recent and trending pastes
* Added mockingjay to word list for unknown posters - let the revolution begin!
* Bugfixes and improvements

#### Upgrade instructions

Copy your htdocs/application/stikked.php config file away. Upload the new version. Copy it back.

### Version 0.8.6:

* New translations: Portuguese, Norwegian, Turkish, French
* New theme: Snowkat
* YOURLS support (http://yourls.org/)
* There is now a stikked.php.dist. You may copy that to config.php and have your own settings
* The API has more possibilities, see API doc
* Captcha must be entered only once, no more for further pastes
* Bugfixes and improvements

#### Upgrade instructions

Copy your htdocs/application/stikked.php config file away. Upload the new version. Copy it back.

### Version 0.8.5:

* Themes! Configure a different theme in config/stikked.php - or create your own
* Multilanguage support. Configure a different language in config/stikked.php
* Diff view for paste replies! View differences between the original paste and its reply
 * see it in action: http://paste.scratchbook.ch/view/de81a093/diff
* Possibility to set default expiration time
* Updated GeSHi to version 1.0.8.11
* Updated CodeMirror to version 3.11
* Lots of minor fixes and improvements
* Added guides for troubleshooting, development, translation and creating themes
* Added webserver example configurations
* Added reCaptcha integration for better antispam

#### Upgrade instructions

The following lines must be present config/stikked.php

```php
$config['theme'] = 'default';
```

You can choose between default, bootstrap, gabdark, gabdark3 and a fancy geocities theme ;)

Create you own theme. See doc/CREATING_THEMES.md

```php
$config['language'] = 'english';
```

You can choose between english, german and swissgerman ;)

Help translating Stikked into your language! See doc/TRANSLATING_STIKKED.md

##### reCaptcha

```php
$config['recaptcha_publickey'] = '';
$config['recaptcha_privatekey'] = '';
```

If these lines are filled, reCaptcha will be used.
Get a key from https://www.google.com/recaptcha/admin/create

### Version 0.8.4:

* Trending pastes: http://paste.scratchbook.ch/trends
* LDAP authentication (thanks to Daniel, https://github.com/lightswitch05)
* Blocked words; maintain a comma separated list in your config, e.g. '.es.tl, mycraft.com, yourbadword' - pastes with this words will never get pasted
* Spam trap for bots
* Bugfix: Remove\_invisible\_characters removing legitimate paste content (https://github.com/claudehohl/Stikked/issues/28)
* Possibility to manually set the paste's displayed URL (used with mod\_rewrite configurations)
* Print layout for pastes
* Updated to CodeIgniter version 2.1.3

### Version 0.8.3:

* From now on, IPs get logged in the DB
* Added spamadmin:
  * Enter credentials in config/stikked.php
  * Visit /spamadmin, login
  * Click on an IP to list all pastes belonging to it
  * You can remove all the pastes listed, and optionally block the IP range
* Updated to CodeIgniter version 2.1.2

### Version 0.8.2:

* Database optimizations: Pastes use less space (if you upgrade from a previous version, execute this SQL statement: "ALTER TABLE pastes DROP paste;"
* Anti spam features:
  * Option to disable recent pastes
  * Option to require the user to enter a captcha

### Version 0.8.1:

* Cleaner options
* Valid RSS feed
* Simpler API response (non-JSON)
* Favicon
* gw.gd URL shortener (replaces bit.ly)
* Minor fixes

### Version 0.8:

* Added backup function (yoursite.com/backup; set credentials in stikked.php config)
* Added pagination to the replies table
* Added RSS-Feeds to recent pastes and paste replies
* Embeddable pastes
* GeSHi updated to version 1.0.8.10
* Codemirror turned off by default
* Codemirror: Syntax changes dynamically with selection in language dropdown

### Version 0.7:

* An API (see http://paste.scratchbook.ch/api)
* Integration of Codemirror (http://codemirror.net)

### Version 0.6:

* The language-selection was broken; the dropdown now features all the languages that GeSHi supports
* Updated to CodeIgniter version 2.1.0
* Creation of bit.ly-URLs (instead of snipurl)
* Fixed download link
* Paste downloads as a .txt file
* No need to have PHP short tags enabled
* Automatic creation of all necessary MySQL tables
* Raw-mode is now like the raw-mode on pastebin.com
* Minification and concatenation of CSS and JavaScript files (can be turned on/off)
* Breached the license by removing the nasty copyright footer

### Version 0.5:

* Paste Replies
* Fluid width pastes
* Auto copying paste url to clipboard.
* Paste expiration.
* Fully standards compliant css and xhtml.
* Random generating names for anonymous users
* Paste downloading
