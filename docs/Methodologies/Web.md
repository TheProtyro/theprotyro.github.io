#### Web methodology

- Visit the website
- Put in Burp target scope
- nikto (-C)
- Start making a wordlist
	- cewl
- View source page - comments
	- link location
	- usernames
	- passwords
	- api
- Enumerate version
	- CMS version -> CHANGELOG.txt
	- Github -> release date, security announcements	
	- Copyright year
- Gobuster directory (at least html,js,txt,php | add asp,aspx if windows)
	- /usr/share/seclists/Discovery/Web-Content/raft-medium-directories-lowercase.txt
	- /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt
	- big.txt or technology related (CMS, apache etc.)
	- use -f option to add "/" after the word
- Try the paths found in other services like ftp, smb... 
- Robots.txt , sitemap.xml, .git, cgi-bin,  cgi-mod,  cgi-sys,(shellshock)
- WebDav ? davtest -> cadaver
- Nmap NSE could help. e.g. nmap -sV --script "http-iis*" -p 80 $IP
- Gobuster subdomains (vhost) or FUZZ
- Search backup files -> bfac
- Check cookies , jwt etc. Js files
- Any files to download ? Check metadata, google images, stegano..
- Wayback machine
- Google dorks
- ./testssl.sh (hearthbleed)
- Search exploit based on version CMS, plugins...Even if its a new one (ex: php 8.1.0-dev)
- Login ?
	- Default credentials
	- Guessable credentials (user/user, admin/admin, default_user/, software_name/software_name, hostname/hostname...)
	- quick win sqli (' or 1=1; -- -)
	- BruteForce (sort the wordlist if big)
	- cewl wordlist
- Identify parameters
	- Test for SQLi / RFI / LFI / XSS / OS injection / XXE etc. -> Use FUZZ and always check proxy request output

