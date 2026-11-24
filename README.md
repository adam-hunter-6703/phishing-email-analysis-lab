# phishing-email-analysis-lab
SOC analyst investigation of a phishing email using VirusTotal, WHOIS, URLScan, and threat intelligence analysis.

Phishing Email Analysis Lab
Executive Summary

A suspicious email claiming to be from p.chambers@sasktel.net was analyzed. Examination of the email headers revealed SPF SoftFail, no DKIM configuration, and no DMARC policy. The message originated from mail.yobow.cn (183.56.179.169) and requested that the recipient contact external Gmail addresses, which is a common phishing indicator. Based on the collected evidence, the email was classified as a phishing attempt.

Objectives
Analyze email headers
Identify Indicators of Compromise (IOCs)
Perform OSINT research
Determine email legitimacy
Document investigative findings
Tools Used
Email Header Analyzer
WHOIS
VirusTotal
Manual OSINT Research
Indicators of Compromise
Type	Value
Sender Email	p.chambers@sasktel.net
Source IP	183.56.179.169
Mail Server	mail.yobow.cn
Domain	yobow.cn
Reply-To	agentcynthiajamescontact01@gmail.com
Additional Contact	dr.philipmaxwell303@gmail.com
Key Findings
SPF Analysis
SPF status: SoftFail
The sending server was not authorized to send mail on behalf of the claimed sender domain.
Authentication Analysis
DKIM: None
DMARC: None
Infrastructure Analysis
Source IP: 183.56.179.169
Sending host: mail.yobow.cn
Root domain: yobow.cn
WHOIS information showed the domain is registered in China.
Social Engineering Indicators
Generic greeting ("Attention Dear Beneficiary")
Requests to communicate through Gmail accounts
Impersonation of a legitimate organization
Conclusion

The email exhibits multiple indicators consistent with phishing activity, including sender impersonation, authentication failures, suspicious infrastructure, and redirection to third-party email accounts. Based on the findings, the message should be treated as malicious and reported to the appropriate security team.

Lessons Learned

This investigation reinforced the importance of examining email authentication results, analyzing sender infrastructure, and validating suspicious domains through OSINT techniques before interacting with potentially malicious messages.



Lab Questions
1)   What is the status of SPF, what does it mean, and why did it occur?
The status currently is set to SPF = SoftFail, it was rejected because the email mail.yobow.cn (183.56.179.169) was the original sender but its pretending to be p.chambers@sasktel.net.

2)   What is the sender’s IP address?
183.56.179.169

3)   Are DKIM and DMARC setup?
No because the header currently has dkim=none and dmarc=none.

4)   What is the domain name of the mail server closest to the sender? (include the subdomain)
Received: from mail.yobow.cn (183.56.179.169)

5)   What is the reported date of this email? (include date/time/time zone)
December 6, 2023, the time was 05:00:12 and the time zone was 0800 pacific standard time. 

6)   What is the email address of the sender and when was the domain created?
p.chambers@sasktel.net was the sender and according to WHOIS the domain itself was created on
2000-04-05T21:33:40Z.

7)   If the recipient were to reply to this email, who would it be sent to?
The option to reply to was agentcynthiajamescontact01@gmail.com.

8)   What is the subject line of this email?
Attention Dear Beneficiary was listed under subject.

9)   If the email failed to deliver, who would receive the error message?
The return path is listed as p.chambers@sasktel.net

10) How many “Content-Type” are there in this email and which format(s) are the mail server going to render this message as? (Example: base64? Html? Plain text?) 
content="text/html; charset=windows-1251" and its using html.  

11) What is the “Message ID” for this email?
The message ID is listed as <20231206125957.6414E20EB5FD@mail.yobow.cn>.

12) The recipient of this email is instructed to email two individuals, what are their names and email addresses? 
Miss Cynthia R. James using Email: agentcynthiajamescontact01@gmail.com. The other is Mr. John Williams
using email dr.philipmaxwell303@gmail.com. 



13) When was the root domain of the mail server created and which country is it located in?
The root domain of the mail server is yobow.cn. It was created on July 18, 2014, and it is located in China.

14) Has the root domain been involved in any other phishing related activity?
Yes, the root domain (yobow.cn) has been involved in phishing/scam-related activity.

15) Has the sender IP been reported for spam previously?
    • Bonus question: Is the sender IP part of a VPN service?
In accordance with OSINT on VirusTotal there were no indication that it was scored as malicious but had some connections to other reported malicious actions also there wasn’t any given info detailing a VPN usage.

16) If you received this email, what would your next steps be?

If I received this email, I would treat it as a phishing scam. I would not respond, click any links, or contact the listed individuals. I would report the message to the security team, analyze the headers, document the IOCs, search for additional recipients within the environment, and then quarantine or delete the email.
