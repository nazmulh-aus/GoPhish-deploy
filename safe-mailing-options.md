# Email Delivery Method Used in This Lab

This awareness lab used Gmail SMTP as the sending profile inside GoPhish.

Authentication method:

Google Account → 2-Step Verification enabled  
SMTP authentication → Application Password

App Password authentication was required because Gmail blocks direct password login when MFA is enabled.

---

# Gmail SMTP Configuration

SMTP Server:

smtp.gmail.com

Port:

587

Encryption:

STARTTLS

Authentication:

Generated App Password

---

# Security Controls Applied

✔ dedicated training mailbox  
✔ MFA enabled  
✔ App Password authentication  
✔ limited awareness-lab recipients  
✔ no credential harvesting templates  

---

# Gmail Sending Limits

Typical Gmail sending limit:

~500 emails per day

Large enterprise awareness simulations should instead use:

Microsoft 365 relay  
Google Workspace relay  
internal SMTP gateway
