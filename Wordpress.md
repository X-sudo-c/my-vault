for help on how to compromise use  https://book.hacktricks.wiki/en/network-services-pentesting/pentesting-web/wordpress.html?highlight=wp-cron#wp-cronphp-dos

Interesting Finding(s):

[+] Headers
 | Interesting Entries:
 |  - server: nginx
 |  - x-cache-enabled: True
 |  - x-httpd-modphp: 1
 |  - host-header: 8441280b0c35cbc1147f8ba998a563a7
 |  - x-proxy-cache: HIT
 | Found By: Headers (Passive Detection)
 | Confidence: 100%

[+] robots.txt found: https://blog.bpsafrica.com/robots.txt
 | Interesting Entries:
 |  - /wp-admin/
 |  - /wp-admin/admin-ajax.php
 |  - /*blackhole
 |  - /?blackhole
 |  - /wp-content/uploads/wpo/wpo-plugins-tables-list.json
 | Found By: Robots Txt (Aggressive Detection)
 | Confidence: 100%

[+] XML-RPC seems to be enabled: https://blog.bpsafrica.com/xmlrpc.php
 | Found By: Link Tag (Passive Detection)
 | Confidence: 30%
 | References:
 |  - http://codex.wordpress.org/XML-RPC_Pingback_API
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_ghost_scanner/
 |  - https://www.rapid7.com/db/modules/auxiliary/dos/http/wordpress_xmlrpc_dos/
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_xmlrpc_login/
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_pingback_access/

[+] WordPress readme found: https://blog.bpsafrica.com/readme.html
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 100%

[+] This site has 'Must Use Plugins': https://blog.bpsafrica.com/wp-content/mu-plugins/
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 80%
 | Reference: http://codex.wordpress.org/Must_Use_Plugins

[+] The external WP-Cron seems to be enabled: https://blog.bpsafrica.com/wp-cron.php
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 60%
 | References:
 |  - https://www.iplocation.net/defend-wordpress-from-ddos
 |  - https://github.com/wpscanteam/wpscan/issues/1299

[+] WordPress version 6.8.1 identified (Latest, released on 2025-04-30).
 | Found By: Common Wp Includes Query Parameter In Homepage (Passive Detection)
 |  - https://blog.bpsafrica.com/wp-includes/js/mediaelement/mediaelement-migrate.min.js?ver=6.8.1
 |  - https://blog.bpsafrica.com/wp-includes/js/mediaelement/wp-mediaelement.min.js?ver=6.8.1
 | Confirmed By: Query Parameter In Install Page (Aggressive Detection)
 |  - https://blog.bpsafrica.com/wp-includes/css/dashicons.min.css?ver=6.8.1
 |  - https://blog.bpsafrica.com/wp-includes/css/buttons.min.css?ver=6.8.1
 |  - https://blog.bpsafrica.com/wp-admin/css/forms.min.css?ver=6.8.1
 |  - https://blog.bpsafrica.com/wp-admin/css/l10n.min.css?ver=6.8.1
 |  - https://blog.bpsafrica.com/wp-admin/css/install.min.css?ver=6.8.1

[+] WordPress theme in use: Divi
 | Location: https://blog.bpsafrica.com/wp-content/themes/Divi/
 | Last Updated: 2024-11-26T00:00:00.000Z
 | [!] The version is out of date, the latest version is 4.27.4
 | Style URL: https://blog.bpsafrica.com/wp-content/themes/Divi/style.css
 | Style Name: Divi
 | Style URI: http://www.elegantthemes.com/gallery/divi/
 | Description: Smart. Flexible. Beautiful. Divi is the most powerful theme in our collection....
 | Author: Elegant Themes
 | Author URI: http://www.elegantthemes.com
 |
 | Found By: Urls In Homepage (Passive Detection)
 | Confirmed By: Urls In 404 Page (Passive Detection)
 |
 | Version: 4.25.1 (80% confidence)
 | Found By: Style (Passive Detection)
 |  - https://blog.bpsafrica.com/wp-content/themes/Divi/style.css, Match: 'Version: 4.25.1'

[+] Enumerating Most Popular Plugins (via Passive Methods)
[+] Checking Plugin Versions (via Passive and Aggressive Methods)

[i] Plugin(s) Identified:

[+] *
 | Location: https://blog.bpsafrica.com/wp-content/plugins/*/
 |
 | Found By: Urls In Homepage (Passive Detection)
 | Confirmed By: Urls In 404 Page (Passive Detection)
 |
 | The version could not be determined.

[+] google-analytics-for-wordpress
 | Location: https://blog.bpsafrica.com/wp-content/plugins/google-analytics-for-wordpress/
 | Last Updated: 2025-05-06T18:40:00.000Z
 | [!] The version is out of date, the latest version is 9.5.2
 |
 | Found By: Monster Insights Comment (Passive Detection)
 |
 | Version: 9.4.1 (60% confidence)
 | Found By: Monster Insights Comment (Passive Detection)
 |  - https://blog.bpsafrica.com/, Match: 'Google Analytics by MonsterInsights plugin v9.4.1 -'

[+] sg-cachepress
 | Location: https://blog.bpsafrica.com/wp-content/plugins/sg-cachepress/
 | Latest Version: 7.7.2
 | Last Updated: 2025-04-15T07:33:00.000Z
 |
 | Found By: Urls In Homepage (Passive Detection)
 | Confirmed By: Urls In 404 Page (Passive Detection)
 |
 | The version could not be determined.

[+] Enumerating Most Popular Themes (via Passive and Aggressive Methods)
 Checking Known Locations - Time: 00:00:42 <======================================> (400 / 400) 100.00% Time: 00:00:42
[+] Checking Theme Versions (via Passive and Aggressive Methods)

[i] Theme(s) Identified:

[+] Divi
 | Location: https://blog.bpsafrica.com/wp-content/themes/Divi/
 | Last Updated: 2024-11-26T00:00:00.000Z
 | [!] The version is out of date, the latest version is 4.27.4
 | Style URL: https://blog.bpsafrica.com/wp-content/themes/Divi/style.css
 | Style Name: Divi
 | Style URI: http://www.elegantthemes.com/gallery/divi/
 | Description: Smart. Flexible. Beautiful. Divi is the most powerful theme in our collection....
 | Author: Elegant Themes
 | Author URI: http://www.elegantthemes.com
 |
 | Found By: Urls In Homepage (Passive Detection)
 | Confirmed By: Urls In 404 Page (Passive Detection)
 |
 | Version: 4.25.1 (80% confidence)
 | Found By: Style (Passive Detection)
 |  - https://blog.bpsafrica.com/wp-content/themes/Divi/style.css, Match: 'Version: 4.25.1'

[+] Enumerating Users (via Passive and Aggressive Methods)
 Brute Forcing Author IDs - Time: 00:00:01 <========================================> (10 / 10) 100.00% Time: 00:00:01

[[User Identified]]


[+] Finished: Tue May 13 17:39:34 2025
[+] Requests Done: 486
[+] Cached Requests: 21
[+] Data Sent: 110.396 KB
[+] Data Received: 24.467 MB
[+] Memory used: 286.094 MB



[[VULNERABILITIES]]