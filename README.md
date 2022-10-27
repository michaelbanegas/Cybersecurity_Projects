# Project 7 - WordPress Pen Testing

Time spent: **8** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pen Testing Report

### 1. Twenty Fifteen Theme <= 1.1 - DOM Cross-Site Scripting (XSS)

- [ ] Summary: 
  - Vulnerability types: (DOM XSS vulnerability) CVE-2015-3429
  - Tested in version: 4.2 
  - Fixed in version: 1.2
- [ ] GIF Walkthrough: ![](https://github.com/michaelbanegas/Codepath_Cybersecurity_HW/blob/Project-7---WordPress-Pen-Testing/exploit2.gif)
- [ ] Steps to recreate: 
1. Looked for xss vulnerability in wpscan results
2. Found article detailing exploit within theme page
3. Link within wpscan redirected to an Invite article that explains exploit command
4. Figured out that you would need to make a post command via making a new post similar to previous XSS exploit.
5. Add exploit command at the end of the url http://wpdistillery/

Exploit: /wordpress/wp-content/themes/twentyfifteen/genericons/example.html#<img/src/onerror=alert(123)>

- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
  - [Link 2](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-3429)
  - [Link 3](https://blog.sucuri.net/2015/05/jetpack-and-twentyfifteen-vulnerable-to-dom-based-xss-millions-of-wordpress-websites-affected-millions-of-wordpress-websites-affected.html)
  - [Link 4](https://packetstormsecurity.com/files/131802/)

  
### 2. WordPress  3.7-4.4 - Authenticated Cross-Site Scripting (XSS)

- [ ] Summary: 
  - Vulnerability types:(XSS vulnerability) CVE-2016-1564
  - Tested in version: 4.2
  - Fixed in version: 4.2.5
- [ ] GIF Walkthrough: ![](https://github.com/michaelbanegas/Codepath_Cybersecurity_HW/blob/Project-7---WordPress-Pen-Testing/exploit1.gif)
- [ ] Steps to recreate:
- 1. Looked for xss vulnerability in wpscan results
- 2. Found article detailing exploit that requires admin permissions
- 3. Link within wpscan redirected to twitter post giving exploit command
- 4. Figured out that you would need to make a post command via making a new post.
- 5. Add exploit command at the end of the url http://wpdistillery/wp-admin 

Exploit: /wp-admin/customize.php?theme=<does not let me paste the rest!>
- [ ] Affected source code:
- [Link 1](https://github.com/WordPress/WordPress/commit/7ab65139c6838910426567849c7abed723932b87)
- [Link 2](https://wpscan.com/vulnerability/09329e59-1871-4eb7-b6ea-fd187cd8db23)
- [Link 3](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-1564)

### 3. WordPress 3.9-5.1 - Comment Cross-Site Scripting (XSS)

- [ ] Summary: 
  - Vulnerability types:(CSRF and XSS) CVE-2019-9787
  - Tested in version: 4.2
  - Fixed in version: 4.2.23
- [ ] GIF Walkthrough:![](https://github.com/michaelbanegas/Codepath_Cybersecurity_HW/blob/Project-7---WordPress-Pen-Testing/exploit3.gif)
- [ ] Steps to recreate: 
- 1. Open post that has been submitted
- 2. Reply to post with exploit shown in gif. Publish it and you will see the line has dissapeared. Due to the WP not having a way to negate it, it is stored in databade. 
- 3. Command is hidden due to it being processed and stored into database. This will allow a user to inject XSS code. 
- [ ] Affected source code:
  - [Link 1](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-9787)
  - [Link 2](https://github.com/WordPress/WordPress/commit/0292de60ec78c5a44956765189403654fe4d080b)
  - [Link 3](https://blog.sonarsource.com/wordpress-csrf-to-rce/?redirect=rips)

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with  ...
<!-- Recommended GIF Tools:
[Kap](https://getkap.co/) for macOS
[ScreenToGif](https://www.screentogif.com/) for Windows
[peek](https://github.com/phw/peek) for Linux. -->

## Notes

When setting up vagrant, I was having trouble connecting to an acceptable IP address. I needed to change my Vagrant file to host IP address 192.168.56.10 instead of 192.168.30.10.

I also had trouble pinging the wpdistillery from kali linux vm. Again needed to reconfigure commands given in instructions to be tailored to new ip address listed above.

Figuring out how to perform the exploits was very difficult as it was a big guessing game.

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
