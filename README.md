<h1> Phishing Triage Tool 
</h1>



<h2>Description</h2>
<br />
This open source tool eliminates the manual overhead of phishing triage by automating email authentication analysis, IOC extraction, and threat intel enrichment into a single fast pipeline with every scoring decision explained.
<br />
<br />
<h2> What It Does <h2>
<br />
(1)  Parses the full MIME structure : headers, body, attachments, embedded URLs.
<br />
<br />
(2) Analyzes email authentication : SPF, DKIM, and DMARC alignment from headers, flagging spoofed senders and envelope mismatches.
<br />
<br />
(3) Extracts and defangs IOCs : URLs rendered and format with MD5 and SHA256 hashes for safe sharing.
<br />
<br />
(4) Scores with explainability  : 15 detection rules, each mapped to MITRE ATT&CK, with per signal weight breakdown.
<br />
<br />
(5)  Enriches with threat intel : VirusTotal, URLhaus, AbuseIPDB, and Shodan lookups.
<br />
<br />
(6) Outputs case artifacts : structured JSON case file and a Markdown incident ticket, ready to drop into any ticketing system.
<br />
<br />

<h2> Web API </h2>
<br />
<img src="https://imgur.com/sDVtMoI.jpg"  height="80%" width="80%">
<br />
<br />

<h2> Email Sample </h2>
<img src="https://imgur.com/VN6UvlJ.jpg"  height="80%" width="80%">
<br />
<br />
<img src="https://imgur.com/R2G5cYw.jpg"  height="80%" width="80%">
<br />
<br />
<h2>  [SUSPICIOUS] Score 63/100. 2 high severity indicator(s): SPF FAIL; DMARC FAIL </h2>
<img src="https://imgur.com/Xdn2EmQ.jpg"  height="80%" width="80%">
<br />
<br />
<h2>  [PHISHING] Score 100/100. 5 high severity indicator(s): SPF FAIL; DKIM Invalid / Missing; DMARC FAIL </h2>
<img src="https://imgur.com/iWa1KOr.jpg"  height="80%" width="80%">
<br />
<br />
<h2>  [CLEAN] Score 0/100. No high severity indicators found. </h2>
<img src="https://imgur.com/iy3RH3J.jpg"  height="80%" width="80%">
<br />
<br />
<br />

<p align="center">
<br/>
<h1>CLI Usage</h1>
<br />
<img src="https://imgur.com/wnpvt6t.jpg"  height="80%" width="80%">
<br />
<img src="https://imgur.com/opVWwFD.jpg"  height="80%" width="80%">
<br />
<img src="https://imgur.com/9r6WJ4k.jpg"  height="80%" width="80%">
<br />
<br />
<br />
<br />


