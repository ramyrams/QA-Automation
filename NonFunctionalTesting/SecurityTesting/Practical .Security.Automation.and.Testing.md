ReBulk advanced search tool: https://github.com/Toilal/rebulk
Security Development Life cycle (SDLC) banned function calls: https://msdn.microsoft.com/en-us/library/bb288454.aspx
Sensitive information data type: https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/data-loss-prevention/sensitive-information-types?view=exchserver-2019#Taiwan%20National%20ID
Vulnerable API sample project: https://github.com/rahulunair/vulnerable-api
SWAMP: https://www.mir-swamp.org
Sensitive data discovery tool: https://github.com/redglue/redsense
Secrets Search: https://github.com/securing/DumpsterDiver
OWASP deserialization cheat sheet: https://www.owasp.org/index.php/Deserialization_Cheat_Sheet


PII-related information
Examples of regular expression patterns
Credit card number	\d{4}[ -]?\d{4}[ -]?\d{4}[ -]?\d{4}|\d{4}[ -]?\d{6}[ -]?\d{4}\d?
Email address	/([a-z0-9_\-.+]+)@\w+(\.\w+)*
IP address	\b(?:\d{1,3}\.){3}\d{1,3}\b
Credentials	1234 | admin | password | pass | creds | login
Phone number	(\(?\+?[0-9]{1,2}\)?[-. ]?)?(\(?[0-9]{3}\)?|[0-9]{3})[-. ]?([0-9]{3}[-. ]?[0-9]{4}|\b[A-Z0-9]{7}\b)
Address	(street|st|road|rd|avenue|ave|drive|dr|loop|court|ct|circle|cir|lane|ln|boulevard|blvd|way)\.?\b
Social security number	\b\d{3}[ -.]?\d{2}[ -.]?\d{4}\b
ZIP code	\b\d{5}\b(-\d{4})?\b
URL	([^\s:/?#]+):\/\/([^/?#\s]*)([^?#\s]*)(\?([^#\s]*))?(#([^\s]*))?
Dates (MM/DD/YYYY )	\^([1][12]|[0]?[1-9])[\/-]([3][01]|[12]\d|[0]?[1-9])[\/-](\d{4}|\d{2})$
 
# Privacy search tools
The Silver Searcher
This works similarly to Linux GREP for full-text searches in files, but it's much faster. It can support multiple platforms and is easy to use: https://github.com/ggreer/the_silver_searcher.
ReDataSense
This is useful for searching for PII in a MySQL database or in files. It can also define flexible search patterns/rules. It's a Java program but can also support multiple platforms: https://github.com/redglue/redsense.
DumpsterDiver
This is used to search for secrets, API keys, and encrypted passwords by using entropy. It can search logs, files, and compressed archives, and can also customize scanning rules: https://github.com/securing/DumpsterDiver.


For Fuzz data input as security payloads, refer to the following resources:
FuzzDB: https://github.com/fuzzdb-project/fuzzdb
SecLists: https://github.com/danielmiessler/SecLists

Fuzz database
Description
FuzzDB
FuzzDB compressive application security testing dictionary for attack patterns (injection, XSS, directory traversals), discovery (admin directories or sensitive files), response analysis (regular expression patterns), web backdoor samples, and user/pwd list.
https://github.com/fuzzdb-project/fuzzdb
Naughty Strings
The Naughty Strings provides a very long list of strings. There are two formats provided, blns.txt and blns.json.
https://github.com/minimaxir/big-list-of-naughty-strings
 
SecList
This is similar to FuzzDB, which provides various kinds of fuzz data such as command injections, JSON, LDAP, user agents, XSS, char, numeric, Unicode data, and so on
https://github.com/danielmiessler/SecLists
Radamsa
Unlike previous FuzzDB that provides a list of word dictionary, it's a tool that can dynamically generate format-specific based on a given sample
https://github.com/vah13/radamsa


security testing with ZAP Open/SOAP API
import the API definitionZap


ASTRA API Security Testing: https://www.astra-security.info
API Security Checklist: https://github.com/shieldfy/API-Security-Checklist
Python API Security testing by OpenStack Security: https://github.com/openstack/syntribos
Testing your API for Security in Python: https://github.com/BBVA/apitest
Online Vulnerable Web: http://website zero.webappsecurity.com
FuzzDB: https://github.com/fuzzdb-project/fuzzdb
SecList: https://github.com/danielmiessler/SecLists
Web Security Fuzz Testing 0d1n: https://github.com/CoolerVoid/0d1n



Further reading
Fireline Android static analysis: http://magic.360.cn/en/index.html
Android privacy scan (Androwarn): https://github.com/maaaaz/androwarn/
Mobile Security Framework (MobSF): https://github.com/MobSF/Mobile-Security-Framework-MobSF/wiki/1.-documentation
Quick Android review kit: https://github.com/linkedin/qark/
AndroBugs framework: https://github.com/AndroBugs/AndroBugs_Framework
OWASP mobile testing guide: https://legacy.gitbook.com/book/sushi2k/the-owasp-mobile-security-testing-guide
JADX: https://github.com/skylot/jadx
DEX2JAR: https://github.com/pxb1988/dex2jar
Android Cuckoo Sandbox: http://cuckoo-droid.readthedocs.io/en/latest/
Vulnerable APK—GoatDroid.APK: https://github.com/linkedin/qark/blob/master/tests/goatdroid.apk
Vulnerable APK—InSecureBankv2.APK: https://github.com/dineshshetty/Android-InsecureBankv2
Android APK Scan: https://github.com/itsmenaga/apkscan/blob/master/apkscan.py
Android Static Code Analyzer: https://github.com/vincentcox/StaCoAn
Android Security 2017 Year in Review: https://source.android.com/security/reports/Google_Android_Security_2017_Report_Final.pdf
Google App security improvement program: https://developer.android.com/google/play/asi
Mobile Security Framework API docs: https://github.com/MobSF/Mobile-Security-Framework-MobSF/wiki/3.-REST-API-Documentation


Further reading
Automate the secure configuration scanning with OpenSCAP: https://www.open-scap.org/tools/openscap-base/
System Configuration Audit Tools (system, kernel, permissions, services, network, distro, and external): https://github.com/trimstray/otseca
RapidScan: https://github.com/skavngr/rapidscan/ 
Nmap Reference Guide: https://nmap.org/book/man-briefoptions.html
Mozilla SSL Configuration Generator: https://mozilla.github.io/server-side-tls/ssl-config-generator/
OpenSCAP for security configuration scanning: https://www.open-scap.org/
ZMAP network scanner: https://zmap.io/
MASScan for quick port scanning: https://github.com/robertdavidgraham/masscan
Advanced vulnerability scanning with Nmap NSE: https://github.com/scipag/vulscan
Gauntlt BDD Security Testing Framework: https://github.com/gauntlt/gauntlt
OWASP Dependency Track: https://dependencytrack.org/
NMAP NSE (Nmap Scripting Engine): https://nmap.org/nsedoc/
Askalono License Texts Scan: https://github.com/amzn/askalono


Serpico
https://github.com/SerpicoProject/Serpico/releases
RapidScan
This is used to trigger several security testing tools and output the results in the console
sslScan
This is used to scan vulnerable protocols of SSL communication
wfuzz
This is for the fuzz testing of HTTP requests
FuzzDB
This is the security payloads fuzz database
Retire.js
This is used to scan the vulnerable libraries for JavaScript



# Typical use of Nmap for security testing
Fast scan for listening ports	nmap -F --open -Pn
Scan for any missing http security headers such as XSS-Protection	nmap -p80 --script http-security-headers  -Pn
DOS attack with HTTPS Slowloris			nmap -p80,443 --script http-slowloris --max-parallelism 500  -Pn
Scanning for all TCP listening ports	nmap -p1-65535   --open  -Pn
Scanning for all UDP listening ports	nmap -p1-65535 -sU  --open  -Pn
Scanning for common ports	Nmap  -p21, 23,80, 137,138, 443, 445, 1433, 3306, 1521, 3389  --open  -Pn

Security header check	nmap -p80 --script http-security-headers <host>			"X-Frame-Options: DENY"
HTTP slow DOS check		nmap -p80,443 --script http-slowloris-check  <host>		Should not contain "LIKELY VULNERABLE"
SSL ciphers check		nmap --script=ssl-enum-ciphers  <host>					Should not contain "SSL"
XSSed history check		nmap -p80 --script http-xssed.nse <host>				Should return "No previously reported XSS vuln"
SQL injection check		nmap -sV --script=http-sql-injection <host>				Should not return "Possible sqli for"
Stored XSS check		nmap -p80 --script http-stored-xss.nse <host>			Should return "Couldn't find any stored XSS vulnerabilities"


NMAP NSE scripts can be downloaded here: https://svn.nmap.org/nmaps/scripts/<NSE script name>. For example, the security header check NSE is at https://svn.nmap.org/nmap/scripts/http-security-headers.nse.

$ nmap -p80 --script http-security-headers nodegoat.kerokuapp.com  -oX nodeGoat_NmapScan_HTTPheaders.xml

Further reading
RetireJS: https://retirejs.github.io/retire.js/
Security/Server Side TLS:  https://wiki.mozilla.org/Security/Server_Side_TLS
NMAP NSE Index: https://nmap.org/nsedoc/index.html
Robot Framework User Guide: http://robotframework.org/robotframework/latest/libraries/BuiltIn.html#Should%20Be
WebMAP for NMAP reporting: https://github.com/Rev3rseSecurity/WebMap



Further reading
RetireJS: https://retirejs.github.io/retire.js/
Security/Server Side TLS:  https://wiki.mozilla.org/Security/Server_Side_TLS
NMAP NSE Index: https://nmap.org/nsedoc/index.html
Robot Framework User Guide: http://robotframework.org/robotframework/latest/libraries/BuiltIn.html#Should%20Be
WebMAP for NMAP reporting: https://github.com/Rev3rseSecurity/WebMap



Further reading
Web security scanner Arachni: https://github.com/Arachni/arachni
Arachni: https://github.com/Arachni/arachni/wiki/Installation
Archerysec: https://github.com/archerysec/archerysec
DefectDojo Demo Site: https://defectdojo.herokuapp.com (admin / defectdojo@demo#appsec)
Archerysec Demo Site: https://archerysec-test.herokuapp.com/webscanners (Username: archerysec, Password: archerysec@archerysec)
Serpico Report templates: https://github.com/SerpicoProject/Serpico/tree/master/templates
PCI Penetration Testing Guidance: https://www.pcisecuritystandards.org/documents/Penetration_Testing_Guidance_March_2015.pdf
OWASP DefectDojo: https://github.com/DefectDojo/django-DefectDojo

