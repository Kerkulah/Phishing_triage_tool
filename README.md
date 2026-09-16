<h1> Phishing Triage Tool 
</h1>



<h2>Overview</h2>
<br />
Phishing triage is usually the highest volume, lowest leverage task in a SOC. An analyst opens a suspicious email report, manually checks SPF/DKIM/DMARC headers, pulls IOCs by hand, pastes hashes into VirusTotal one at a time, then writes up a verdict. This tool collapses that workflow into a single pipeline: submit a raw email or paste headers, and it returns a scored verdict with the reasoning shown, not just a black box label.
<br />
<br />
Every score is decomposed into the individual detection rules that fired, each one mapped to a MITRE ATT&CK technique, so the output reads like an analyst's reasoning rather than an opaque risk number. This makes it usable both as a triage accelerant and as a teaching tool for junior analysts learning what "suspicious" actually looks like at the header level.

<h2>Design Principles</h2>
<br />

- Each of the 15 detection rules reports its own weight and rationale, so a 63/100 verdict shows exactly which signals (SPF FAIL, DMARC FAIL) drove it.
<br />

- Every rule ties back to a technique ID, keeping the tool consistent with how SOC detections are documented elsewhere.
<br />

- Extracted URLs are defanged and hashes are computed for sharing without re triggering a payload.
<br />

- A CLI for quick one off triage and a Web API for integration into a larger pipeline or SOAR playbook
<br />

<h2> What It Does </h2>
<br />
<br />

(1) Parses the full MIME structure - headers, body, attachments, embedded URLs. 
<br />

(2) Analyzes the email authentication - SPF, DKIM, and DMARC alignment from headers, flagging spoofed senders and envelope mismatches.
<br />

(3) Extracts and defangs IOCs - URLs rendered and formatted with MD5 and SHA256 hashes for safe sharing.
<br />

(4) Scores with explainability - 15 detection rules, each mapped to MITRE ATT&CK, with persignal weight breakdown.
<br />

(5) Enriches with threat intel - VirusTotal, URLhaus, AbuseIPDB, and Shodan lookups.
<br />

(6) Outputs case artifacts - structured JSON case file and a Markdown incident ticket.<h2> Web API </h2>
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
<h1>Markdown incident ticket</h1><br />
<br />
<br />
<img src="https://imgur.com/irHQj1H.jpg"  height="80%" width="80%">
<br />
<br />
