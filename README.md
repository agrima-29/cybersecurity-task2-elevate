# cybersecurity-task2-elevate
Analysis of a phishing email sample to identify common threat indicators such as spoofed sender, failed SPF/DKIM, and suspicious content.
# Phishing Email Analysis - Task 2

## Sample Analyzed:
Filename: 'sample-1005.eml'  (downloaded from GitHub)
Sender: "Mary" <noreply@att.net>  
Subject: '#CRYPTO#'  
Received From IP: '192.232.233.127'  
Originating Domain: 'heritagejewelryandloan.com'

## Phishing Indicators Identified:

1. Spoofed Sender Address  
   - 'noreply@att.net' is a fake or spoofed sender. The email originates from 'heritagejewelryandloan.com' which has no relation to AT&T.

2. Failed Authentication  
   - SPF: None → Sender’s domain did not authorize the sending IP.  
   - DKIM: Ignored due to public key issues.  
   - DMARC: None — domain lacks proper email validation policies.

3. Malicious Hosting Server  
   - Message was routed through a suspicious mail server: 'her.heritagejewelryandloan.com' (IP: '192.232.233.127'), unrelated to the claimed sender (AT&T).

4. Message Body & Content  
   - Subject: '#CRYPTO#' — suspicious, vague, and contextless.  
   - Body contains obfuscated HTML, base64 image, and a placeholder ('#CURL#') indicating possible future link injection or hidden redirection.

5. Spam-Like Structure  
   - Repeated meaningless sequences (e.g., 'xuvvzlfidwwplprrnzkspvpupsmssmrqnrnyisexzvkpeldq...')  
   - Indicates the use of spam generators or obfuscation tools to bypass filters.

6. CompAuth Failures  
   - Microsoft’s 'compauth=fail' flag present, showing the email failed composite authentication checks.

## Tools Used:
- MXToolbox Email Header Analyzer  
- Manual '.eml' file parsing 
- SPF/DKIM/DMARC check via raw headers

## Files Included:
- 'sample-1005.eml'  
- 'README.md'

## Outcome:
- Gained practical experience in analyzing raw '.eml' files  
- Identified header spoofing, IP mismatches, and failed authentication  
- Understood how phishing emails bypass filters and use social engineering
