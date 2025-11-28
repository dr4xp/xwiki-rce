<h1>Description:</h1>
<h3>XWiki Platform is a generic wiki platform offering runtime services for applications built on top of it. Any guest can perform arbitrary remote code execution through a request to `SolrSearch`. This impacts the confidentiality, integrity and availability of the whole XWiki installation. To reproduce on an instance, without being logged in, go to `<host>/xwiki/bin/get/Main/SolrSearch?media=rss&text=%7D%7D%7D%7B%7Basync%20async%3Dfalse%7D%7D%7B%7Bgroovy%7D%7Dprintln%28"Hello%20from"%20%2B%20"%20search%20text%3A"%20%2B%20%2823%20%2B%2019%29%29%7B%7B%2Fgroovy%7D%7D%7B%7B%2Fasync%7D%7D%20`. If there is an output, and the title of the RSS feed contains `Hello from search text:42`, then the instance is vulnerable. This vulnerability has been patched in XWiki 15.10.11, 16.4.1 and 16.5.0RC1. Users are advised to upgrade. Users unable to upgrade may edit `Main.SolrSearchMacros` in `SolrSearchMacros.xml` on line 955 to match the `rawResponse` macro in `macros.vm#L2824` with a content type of `application/xml`, instead of simply outputting the content of the feed.</h3>
<h1>Resources:</h1>
  
[NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-24893)<br>
[OFFSEC](https://www.offsec.com/blog/cve-2025-24893/)<br>
[METASPLOIT](https://www.rapid7.com/db/modules/exploit/multi/http/xwiki_unauth_rce_cve_2025_24893/)<br>
[YOUTUBE](https://youtube.com/@fr4nc0x1)
<h2>Remote Code Execution by any user</h2>

<p align="center">
  <img src='https://github.com/user-attachments/assets/666442e5-7ae5-485d-9dff-2667aa8efb7e'/>
</p>
