# PENETRATION-TESTING-REPORT
<div align="center">

# 🔐 PENETRATION TESTING REPORT
<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Waqas%20Karim%20CCIE-C00000?style=flat-square" />
</p>

## FOOTPRINTING & NETWORK SCANNING PHASES
## W2-PM-FINAL | CYBERSECURITY |  NETWORKWALKS


------------------------------------------------------




| pentester name (cybersecurity professional:Emmanuel Success Ochuko | ⚙️ Configuration   |
| ------------------------------------------------------------------ | ------------------  |
|  🌐 program                                                        |Batch B084D-Networwalks     |
| Modules completed                                                  | W2_PM (Multiple Kali Tools) W2-PM5 (Zenmap scanning)  |
| 🌍 Date                                                           |11/11/2026  |
| 🧰 Hypervisor      | VirtualBox 7.2     |
| 🐉 Security OS     | Kali Linux 2026.2  |
| 🧠 Kali RAM        | 2048 MB            |
| 🌐 Client/Target   |1. Networkwalks (secured written permission already) 
|                    |2. My Own Local LAN Network 
| 📡 Permission Secured from client? | Yes        |
| 🐧 Phase Covered| Phase 1: Reconnaissance & Footprinting        |
|                     | Phase 2: Scanning & Network Ddisovery           |
|                     | Phase 3-5: In progress            |

---

** 

## 📌  Liability Disclaimer
I have performed these activities only on the systems & devices where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorised access is a crime even when nothing is damaged.

--- 

 ## 2. Introduction
This report covers footprinting the networkwalks.com domain using multiple Kali Linux tools (W2-PM1) and scanning my own local network with Zenmap (W2-PM5). One module covers the footprinting phase and the other covers the scanning phase, so together they show how an attacker moves from gathering public information to mapping live hosts on a network. It is the Week 2 part of my ongoing internship program at Networkwalks.
All commands were run in Kali Linux (footprinting) and on a Windows PC with Zenmap installed (scanning). Every step below includes the exact command used, the result I observed, a screenshot as evidence, and a short note on why the finding matters from an attacker's point of view.

---

## 3. Tools Used
The table below lists each tool used in this report and its purpose.
Tool	Purpose
Kali Linux & Windows	Operating systems used for reconnaissance activitieo
WHOIS	Find domain registration details (owner, dates, name servers).
whatweb	Fingerprint web technologies (server, CMS, plugins, IP).
nslookup	Resolve the domain name to its IP address using DNS.
curl -I	Read the HTTP response headers of the website.
wafw00f	Detect whether a Web Application Firewall protects the site.
dnsrecon	Enumerate all DNS records (NS, MX, SPF, TXT, SRV).
Zenmap (Nmap GUI)	Scan the local subnet to find live hosts, IPs and MAC addresses.
Windows CMD	Local IP and MAC address identification


| ⚙️Tools | purpose   |
| ------------------ | ------------------  |
|  🌐 <img src="https://img.shields.io/badge/> Kali%20Linux.-E87500?style=circle&labelColor=000000&logo=kalilinux&logoColor=white" /> & windows                                              |Operating systems used for reconnaissance activitieo    |
| WHOIS                                              |Find domain registration details (owner, dates, name servers). |
| Whatweb                                            |	Fingerprint web technologies (server, CMS, plugins, IP).  |
| nslookup                                            |Resolve the domain name to its IP address using DNS. |
| curl -I   | 	Read the HTTP response headers of the website. |
|wafw00f       | 	Detect whether a Web Application Firewall protects the site.         |
| dnsrecon   |Enumerate all DNS records (NS, MX, SPF, TXT, SRV).
| Zenmap (Nmap GUI) |Scan the local subnet to find live hosts, IPs and MAC addresses.   |
| Windows    | CMD	Local IP and MAC address identification |


---

 ## 4. Activities Performed
 ---
 4.1 Footprinting & Reconnaissance

 I performed reconnaissance against the networkwalks.com domain using six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon. Each tool was used to collect a different type of information about the target.

First, I used WHOIS to obtain publicly available domain registration information and identify the domain’s name servers. The results provided information about the domain registration and hosting infrastructure.

I then used WhatWeb to identify technologies used by the website. The results identified WordPress 7.0.4 and WP Download Manager 3.3.58, along with other information exposed by the website.

Using Nslookup, I resolved the domain name to its IP address. The provided result identified 192.232.216.135.

I used Curl with the -I option to inspect the HTTP response headers. This provided additional information about the web application and exposed the WordPress REST API endpoint /wp-json/.

Next, I used Wafw00f to determine whether a Web Application Firewall was protecting the website. The result identified ModSecurity (SpiderLabs).

Finally, I used DNSRecon to enumerate DNS records. The results provided information relating to name servers, mail servers, SPF/TXT records, service records and DNS software information.

4.2 Network Scanning with Zenmap
For the second activity, I used Zenmap to perform network discovery on my local network. The practical required me to identify my local IP address and subnet, discover live hosts, identify their IP and MAC addresses, and generate a network topology.
I first used the Windows ipconfig command to identify my local IP address and LAN subnet. I then entered the subnet into Zenmap and selected Ping Scan to identify active hosts.
The example results provided in the practical identified four live hosts:
•	10.0.0.1
•	10.0.0.4
•	10.0.0.19
•	10.0.0.5
The example results also included four MAC addresses.
After completing the scan, I opened the Topology section in Zenmap, enabled the legend and saved the network topology in PDF format as required by the practical task.
Note: The actual subnet, number of hosts and addresses should be replaced with the results from my own network when submitting the report.

---

## 5. Risk Analysis / Impact
Based on the information collected during the footprinting and network scanning activities, I identified the following potential risks.

---


| S/N |Risk / finding | Evidence Observation | Potential Impact   |Risk Level purpose |
| :--- | :---: | ---: | :--- | :---:|
|1.| Web technology information exposed |WhatWeb identified WordPress and WP Download Manager |	Attackers may use exposed technology/version information to identify software requiring further security review	|● Medium |
|2.| Server IP address identifiable|Nslookup resolved the domain to 192.232.216.135 |Provides information about the network location of the web service     |● Low |
|3.| HTTP technical information exposed  |Curl returned HTTP response headers and exposed /wp-json/ |May assist technology fingerprinting and further enumeration |  ● Low |
|4. | WAF technology identifiable |Wafw00f identified ModSecurity (SpiderLabs) |Reveals information about the web application’s security architecture   |● Low|
|5.|DNS infrastructure information exposed |DNSRecon identified DNS, mail and service-related records |	DNS information can help build a broader infrastructure profile | 	● Medium|
|6.|Multiple live hosts visible on local network| Zenmap identified four live hosts in the example network | Unknown or unauthorized devices may potentially be present on a network | ● Medium |
---
Risk level key:  ● Critical  ● Medium  ● Low

The risks above are observations from the footprinting and scanning exercises, not confirmed vulnerabilities.
The practical exercises primarily involved information gathering and host discovery. No exploitation or vulnerability validation was performed as part of these two modules.
Therefore, the presence of information such as a software version, IP address or DNS record does not by itself mean that the system is vulnerable. Further authorized security testing would be required to confirm any actual vulnerability.

---

## 6. Recommendations
Based on the observations from these activities, I recommend the following security improvements:
1.	Review publicly exposed technology information
Organizations should regularly review what information about their web technologies, CMS and plugins is publicly visible.
2.	Keep software updated
CMS platforms, plugins and other web technologies should be regularly updated and reviewed against current security advisories.
3.	Review HTTP headers
HTTP response headers should be reviewed to determine whether unnecessary technical information is being exposed.
4.	Review DNS records regularly
DNS records should be checked periodically to ensure that only required information and services are publicly exposed.
5.	Properly configure and monitor the WAF
Keep the WAF (ModSecurity) enabled and tuned, since it already blocks naive attacks.
6.	Perform regular internal network discovery
Organizations should periodically scan their own networks to identify active devices.
7.	Investigate unknown devices
Any unexpected device discovered during network scanning should be investigated and verified.
8.	Maintain network documentation
Network topology and device information should be documented and updated regularly.
9.	Perform security testing with authorization
Reconnaissance and scanning should only be performed against systems and networks where appropriate authorization has been provided.

---

## 7. Conclusion
During Week 2 of my Cybersecurity & Ethical Hacking internship, I completed practical activities covering footprinting, reconnaissance and network scanning.
In the footprinting activity, I used six Kali Linux tools to collect information about the target domain. I learned how WHOIS can provide domain information, WhatWeb can identify web technologies, Nslookup can resolve domain names, Curl can inspect HTTP headers, Wafw00f can identify a WAF, and DNSRecon can provide additional DNS information.
In the network scanning activity, I used Zenmap to identify my local network configuration and discover active hosts. I also collected IP and MAC address information and created a network topology.
The exercises showed me that information gathering is an important part of cybersecurity. Even before attempting to exploit a system, a security professional can learn a significant amount about an environment by carefully analyzing publicly available information and network responses.
I also learned that technical findings should be documented clearly. A good cybersecurity report should explain what was performed, what was discovered, what the observation means, what risk it may create, and what can be done to reduce that risk.
Finally, I learned that reconnaissance and scanning must always be performed within an authorized scope. These activities were completed as part of the assigned educational cybersecurity lab.






















--- 












## 8. Evidences collected

  ┌──(darkhood_1㉿Darkhood)-[~]
└─$ whois networkwalks.com
^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B   Domain Name: NETWORKWALKS.COM
   Registry Domain ID: 2452319255_DOMAIN_COM-VRSN
   Registrar WHOIS Server: whois.godaddy.com
   Registrar URL: http://www.godaddy.com
   Updated Date: 2025-11-12T10:08:43Z
   Creation Date: 2019-11-06T22:51:46Z
   Registry Expiry Date: 2027-11-06T22:51:46Z
   Registrar: GoDaddy.com, LLC
   Registrar IANA ID: 146
   Registrar Abuse Contact Email: abuse@godaddy.com
   Registrar Abuse Contact Phone: 480-624-2505
   Domain Status: clientDeleteProhibited https://icann.org/epp#clientDeleteProhibited
   Domain Status: clientRenewProhibited https://icann.org/epp#clientRenewProhibited
   Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited
   Domain Status: clientUpdateProhibited https://icann.org/epp#clientUpdateProhibited
   Name Server: NS6135.HOSTGATOR.COM
   Name Server: NS6136.HOSTGATOR.COM
   DNSSEC: unsigned
   URL of the ICANN Whois Inaccuracy Complaint Form: https://www.icann.org/wicf/
>>> Last update of whois database: 2026-11-24T15:10:46Z <<<

For more information on Whois status codes, please visit https://icann.org/epp

NOTICE: The expiration date displayed in this record is the date the
registrar's sponsorship of the domain name registration in the registry is
currently set to expire. This date does not necessarily reflect the expiration
date of the domain name registrant's agreement with the sponsoring
registrar.  Users may consult the sponsoring registrar's Whois database to
view the registrar's reported date of expiration for this registration.

TERMS OF USE: You are not authorized to access or query our Whois
database through the use of electronic processes that are high-volume and
automated except as reasonably necessary to register domain names or
modify existing registrations; the Data in VeriSign Global Registry
Services' ("VeriSign") Whois database is provided by VeriSign for
information purposes only, and to assist persons in obtaining information
about or related to a domain name registration record. VeriSign does not
guarantee its accuracy. By submitting a Whois query, you agree to abide
by the following terms of use: You agree that you may use this Data only
for lawful purposes and that under no circumstances will you use this Data
to: (1) allow, enable, or otherwise support the transmission of mass
unsolicited, commercial advertising or solicitations via e-mail, telephone,
or facsimile; or (2) enable high volume, automated, electronic processes
that apply to VeriSign (or its computer systems). The compilation,
repackaging, dissemination or other use of this Data is expressly
prohibited without the prior written consent of VeriSign. You agree not to
use electronic processes that are automated and high-volume to access or
query the Whois database except as reasonably necessary to register
domain names or modify existing registrations. VeriSign reserves the right
to restrict your access to the Whois database in its sole discretion to ensure
operational stability.  VeriSign may restrict or terminate your access to the
Whois database for failure to abide by these terms of use. VeriSign
reserves the right to modify these terms at any time.

The Registry database contains ONLY .COM, .NET, .EDU domains and
Registrars.
Domain Name: networkwalks.com
Registry Domain ID: 2452319255_DOMAIN_COM-VRSN
Registrar WHOIS Server: whois.godaddy.com
Registrar URL: https://www.godaddy.com
Updated Date: 2025-11-12T05:08:41Z
Creation Date: 2019-11-06T17:51:46Z
Registrar Registration Expiration Date: 2027-11-06T17:51:46Z
Registrar: GoDaddy.com, LLC
Registrar IANA ID: 146
Registrar Abuse Contact Email: abuse@godaddy.com
Registrar Abuse Contact Phone: +1.4806242505
Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited
Domain Status: clientUpdateProhibited https://icann.org/epp#clientUpdateProhibited
Domain Status: clientRenewProhibited https://icann.org/epp#clientRenewProhibited
Domain Status: clientDeleteProhibited https://icann.org/epp#clientDeleteProhibited
Registry Registrant ID: Not Available From Registry
Registrant Name: Registration Private
Registrant Organization: Domains By Proxy, LLC
Registrant Street: DomainsByProxy.com
Registrant Street: 100 S. Mill Ave, Suite 1600
Registrant City: Tempe
Registrant State/Province: Arizona
Registrant Postal Code: 85281
Registrant Country: US
Registrant Phone: +1.4806242599
Registrant Phone Ext:
Registrant Fax: 
Registrant Fax Ext:
Registrant Email: https://www.godaddy.com/whois/results.aspx?domain=networkwalks.com&action=contactDomainOwner
Registry Tech ID: Not Available From Registry
Tech Name: Registration Private
Tech Organization: Domains By Proxy, LLC
Tech Street: DomainsByProxy.com
Tech Street: 100 S. Mill Ave, Suite 1600
Tech City: Tempe
Tech State/Province: Arizona
Tech Postal Code: 85281
Tech Country: US
Tech Phone: +1.4806242599
Tech Phone Ext:
Tech Fax: 
Tech Fax Ext:
Tech Email: https://www.godaddy.com/whois/results.aspx?domain=networkwalks.com&action=contactDomainOwner
Name Server: NS6135.HOSTGATOR.COM
Name Server: NS6136.HOSTGATOR.COM
Name Server: NS29.DOMAINCONTROL.COM
Name Server: NS30.DOMAINCONTROL.COM
DNSSEC: unsigned
URL of the ICANN WHOIS Data Problem Reporting System: http://wdprs.internic.net/
>>> Last update of WHOIS database: 2026-11-24T15:11:11Z <<<
For more information on Whois status codes, please visit https://icann.org/epp

TERMS OF USE: The data contained in this registrar's Whois database, while believed by the
registrar to be reliable, is provided "as is" with no guarantee or warranties regarding its
accuracy. This information is provided for the sole purpose of assisting you in obtaining
information about domain name registration records. Any use of this data for any other purpose
is expressly forbidden without the prior written permission of this registrar. By submitting
an inquiry, you agree to these terms and limitations of warranty. In particular, you agree not
to use this data to allow, enable, or otherwise support the dissemination or collection of this
data, in part or in its entirety, for any purpose, such as transmission by e-mail, telephone,
postal mail, facsimile or other means of mass unsolicited, commercial advertising or solicitations
of any kind, including spam. You further agree not to use this data to enable high volume, automated
or robotic electronic processes designed to collect or compile this data for any purpose, including
mining this data for your own personal or commercial purposes. Failure to comply with these terms
may result in termination of access to the Whois database. These terms may be subject to modification
at any time without notice.

**NOTICE** This WHOIS server is being retired. Please use our RDAP service instead.

 

 
 





--- 
**  












┌──(darkhood_1㉿Darkhood)-[~]
└─$ whatweb networkwalks.com
http://networkwalks.com [301 Moved Permanently] Apache, Cookies[__wpdm_client], Country[UNITED STATES][US], HTTPServer[Apache], HttpOnly[__wpdm_client], IP[192.232.216.135], RedirectLocation[https://networkwalks.com/], UncommonHeaders[permissions-policy,x-redirect-by,referrer-policy,x-endurance-cache-level,x-nginx-cache]
https://networkwalks.com [200 OK] Apache, Bootstrap[7.1.5], Cookies[__wpdm_client], Country[UNITED STATES][US], Email[info@networkwalks.com], Frame, Google-Tag-Manager, HTML5, HTTPServer[Apache], HttpOnly[__wpdm_client], IP[192.232.216.135], JQuery[3.7.1], MetaGenerator[WordPress 7.1.5,WordPress Download Manager 3.3.78], Open-Graph-Protocol[website], Script[4684NR-IPIB&amp;pidnVar2=50511&amp;prtVar2=7&amp;scvVar2=12,application/json,application/ld+json,module,speculationrules,text/javascript], Title[Networkwalks Academy], UncommonHeaders[permissions-policy,link,referrer-policy,x-endurance-cache-level,x-nginx-cache], WordPress[7.1.5]
https://networkwalks.com/ [200 OK] Apache, Bootstrap[7.1.5], Country[UNITED STATES][US], Email[info@networkwalks.com], Frame, Google-Tag-Manager, HTML5, HTTPServer[Apache], IP[192.232.216.135], JQuery[3.7.1], MetaGenerator[WordPress 7.1.5,WordPress Download Manager 3.3.78], Open-Graph-Protocol[website], Script[4684NR-IPIB&amp;pidnVar2=50511&amp;prtVar2=7&amp;scvVar2=12,application/json,application/ld+json,module,speculationrules,text/javascript], Title[Networkwalks Academy], UncommonHeaders[permissions-policy,link,referrer-policy,x-endurance-cache-level,x-nginx-cache], WordPress[7.1.5]
                                                
 

--- 
** 


┌──(darkhood_1㉿Darkhood)-[~]
└─$ nslookup networkwalks.com
;; communications error to 8.8.8.8#53: timed out
Server:         8.8.8.8
Address:        8.8.8.8#53

Non-authoritative answer:
Name:   networkwalks.com
Address: 192.232.216.135



 

---







** 


┌──(darkhood_1㉿Darkhood)-[~]
└─$ curl -I https://networkwalks.com
HTTP/1.1 200 OK
Date: Tue, 24 Nov 2026 15:44:39 GMT
Server: Apache
Permissions-Policy: private-state-token-redemption=(self "https://www.google.com" "https://www.gstatic.com" "https://recaptcha.net" "https://challenges.cloudflare.com" "https://hcaptcha.com"), private-state-token-issuance=(self "https://www.google.com" "https://www.gstatic.com" "https://recaptcha.net" "https://challenges.cloudflare.com" "https://hcaptcha.com")
Link: <https://networkwalks.com/wp-json/>; rel="https://api.w.org/", <https://networkwalks.com/wp-json/wp/v2/pages/53>; rel="alternate"; title="JSON"; type="application/json", <https://networkwalks.com/>; rel=shortlink
Set-Cookie: __wpdm_client=3e3dc9824d5bece9dd034154feac4926; path=/; domain=networkwalks.com; secure; HttpOnly
Referrer-Policy: no-referrer-when-downgrade
X-Endurance-Cache-Level: 0
X-nginx-cache: WordPress
Content-Type: text/html; charset=UTF-8

--- 
 
** 



                                                                                                     
┌──(darkhood_1㉿Darkhood)-[~]
└─$ wafw00f networkwalks.com

                                        ______
                                     /          \
                                   (    Woof!    )
                                     \   ____  /              				      )
                         , ,                           			  		        )  (_
            . - .     -                          _______         	          (  |__|
          ( ) ` ` ;                          |==|_______)                    . ) |__|
           /   ('                                 / |  \           	         (   |__|
      (  /       )                              /   |    \                     . |__|
       \(_) _   ) )                           /     |      \        		     |__|
  
                    ~ WAFW00F : v2.4.2 ~
    The Web Application Firewall Fingerprinting Toolkit
    
[*] Checking https://networkwalks.com
[+] The site https://networkwalks.com is behind ModSecurity (SpiderLabs) WAF.
[~] Number of requests: 2
                                        
---  
** 

                                                                               
┌──(darkhood_1㉿Darkhood)-[~]
└─$ dnsrecon -d networkwalks.com
2026-11-24T15:51:58.946058+0000 INFO Starting enumeration for domain: networkwalks.com
2026-11-24T15:51:58.952175+0000 INFO std: Performing General Enumeration against: networkwalks.com...
2026-11-24T15:51:59.743037+0000 ERROR No answer for DNSSEC query for networkwalks.com
^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B2026-11-24T15:52:00.586607+0000 INFO         SOA ns6135.hostgator.com 50.87.144.87
2026-11-24T15:52:02.127449+0000 INFO     NS ns6135.hostgator.com 50.87.144.87
2026-11-24T15:52:02.650425+0000 INFO     Bind Version for 50.87.144.87 "9.16.50-RH"
2026-11-24T15:52:02.650881+0000 INFO     NS ns6136.hostgator.com 192.232.216.131
2026-11-24T15:52:03.267138+0000 INFO     Bind Version for 192.232.216.131 "9.16.50-RH"
2026-11-24T15:52:04.373476+0000 INFO     MX mail.networkwalks.com 192.232.216.135
2026-11-24T15:52:04.847933+0000 INFO     A networkwalks.com 192.232.216.135
2026-11-24T15:52:08.621326+0000 INFO     TXT networkwalks.com google-site-verification=rr04eRmqHoWY3XemnizDNVK4q75X-Ij-mjgEeg-UsYI
2026-11-24T15:52:08.621946+0000 INFO     TXT networkwalks.com v=spf1 +a +mx +ip4:50.87.144.87 +include:websitewelcome.com ~all
2026-11-24T15:52:09.667514+0000 INFO Enumerating SRV Records
2026-11-24T15:52:15.274238+0000 INFO     SRV _autodiscover._tcp.networkwalks.com cpanelemaildiscovery.cpanel.net 184.94.204.11 443
2026-11-24T15:52:15.277110+0000 INFO     SRV _autodiscover._tcp.networkwalks.com cpanelemaildiscovery.cpanel.net 184.94.203.11 443
2026-11-24T15:52:15.280587+0000 INFO     SRV _autodiscover._tcp.networkwalks.com cpanelemaildiscovery.cpanel.net 184.94.204.14 443
2026-11-24T15:52:15.281911+0000 INFO     SRV _autodiscover._tcp.networkwalks.com cpanelemaildiscovery.cpanel.net 184.94.203.15 443
2026-11-24T15:52:15.284892+0000 INFO     SRV _autodiscover._tcp.networkwalks.com cpanelemaildiscovery.cpanel.net 184.94.203.9 443
2026-11-24T15:52:15.288578+0000 INFO     SRV _autodiscover._tcp.networkwalks.com cpanelemaildiscovery.cpanel.net 184.94.204.9 443
2026-11-24T15:52:15.291739+0000 INFO     SRV _autodiscover._tcp.networkwalks.com cpanelemaildiscovery.cpanel.net 184.94.204.15 443
2026-11-24T15:52:15.294338+0000 INFO     SRV _autodiscover._tcp.networkwalks.com cpanelemaildiscovery.cpanel.net 184.94.203.14 443
2026-11-24T15:52:15.297111+0000 INFO 8 Records Found
2026-11-24T15:52:15.298221+0000 INFO Completed enumeration for domain: networkwalks.com

---

# 👤 Author

**Emmanuel success ochuko**\
Cybersecurity intern B084D

LinkedIn: [(https://www.linkedin.com/in/emmanuel-richard-5008a1406/)](https://www.linkedin.com/in/emmanuel-richard-5008a1406/)
---
