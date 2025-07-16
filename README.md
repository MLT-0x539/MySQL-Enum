# MySQL-Enum
Tool to perform MySQL database mapping/enumartion via Blind SQLi + Boolean Enum

# Usage:
 perl MySQL-Enum.pl -h [hostname] -u [url] [-q [query]]
 
**Example:**  perl sqli-p.pl -h www.target.tld -u http://www.target.tld/vuln.ext?input=24 -q "select system_user()"

# Overview:
-  By default, this script will first determine username, version and database name before enumerating the information_schema information.
-  When the -q flag is applied, a user can supply any query that returns only a single cell
-  If the exploit or vulnerability requires a single quote, simply tack %27 to the end of the URI.
-  This script contains error detection : It will only work on a mysql 5.x database, and knows when its queries have syntax errors.
-  This script uses perl's LibWhisker2 for IDS Evasion (The same as Nikto).
-  This script uses the MD5 algorithm for optimization. There are other optimization methods, and this may not work on all sites.

# To-Do list:
- Update this script so that it works on newer MySQL versions (currently it only works on versions up to 5x)
- Implement functionality for additional rDBMS softwares, rather than it just being limited to MySQL
- Implement more modern WAF/IDS evasion techniques
- Create a GUI version of this for n00bz to use
