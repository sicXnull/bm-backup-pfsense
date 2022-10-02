bm-backup-pfsense (blogmotion backup pfsense)
english version below

Description
Presentation➡️ https://blogmotion.fr/systeme/script-backup-pfsense-configuration-16496

This script saves the configuration of a pfSense firewall, by retrieving the XML file remotely via HTTP(S).

3 versions of the script exist :

one based on the wget binary
one based on the cURL binary (faster)
a cURL binary based (faster) multi version
Next if either binary is present, choose the appropriate version.

The multi version allows multiple firewalls to be saved in the same script.

Variables
You must edit the script (nano, vim, etc.) to enter at least:

IP or FQDN name (without trailing slash)
identifier
password
I recommend that you create a dedicated user (System > User Manager) with at least the "WebCfg - Diagnostics: Backup & Restore" privilege. For security reasons, the "admin" account is not recommended (password in clear text in the script).

🚦 Configuration minimale
Need

 shell ou bash
 wget ou cURL
In theory works on any Linux distribution. Tested on Debian, CentOS, pfSense.

Note: modification of the BACKUP_RRD, BACKUP_PKGINFO, BACKUP_PASSWORD variables is currently not supported.

Compatibility
This script is compatible with pfSense:

 2.6.x
 2.5.x
 2.4.x
 2.3.x
 2.2.x
Not tested on lower versions.

Validated with the versions:

 2.6.0
 2.5.2
 2.4.3, 2.4.0
 2.3.4-RELEASE-p1, 2.3.3, 2.3.2, 2.3.1
 2.2.5
🚀 Utilisation
It is recommended to create a dedicated directory to store the script there. XML configurations are stored in a dedicated subdirectory.

Version cURL:

chmod +x pfmotion_curl.sh
./pfmotion_curl.sh
Version cURL multi:

chmod +x pfmotion_curl_multi.sh
./pfmotion_curl_multi.sh
Version wget :

chmod +x pfmotion_curl_wget.sh
./pfmotion_curl_wget.sh
The backup file contains the name of the firewall:

/tmp/conf_backup/config-<nom-hote>_<domaine>-<YYYYmmJJHHMMSS>.xml
Example :

/tmp/conf_backup/config-pf_blogmotion.fr-20171007002812.xml
Description
soon
