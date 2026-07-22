# Email Knowledge Base

## General Procedures & Policies

### 1. Outbound Email Delivery SSL/TLS Error (MTA Security Policy)
- **Scenario:** Outbound emails to a specific domain (e.g., a government domain like `homeoffice.gov.uk`) are stuck in the mail queue or bouncing with certificate errors.
- **Diagnostic Error:** `STARTTLS error: X.509: self-signed certificate in certificate chain` at the remote MTA.
- **Root Cause:** The recipient's mail server presents a self-signed or invalid SSL/TLS certificate chain. Because one.com enforces secure outbound delivery (strict TLS validation), our MTA cannot establish a secure connection, causing delivery to fail/queue.
- **Resolution Steps:**
  1. Inform the customer that the issue is on the recipient's mail server side due to an invalid or self-signed certificate.
  2. Suggest contacting the recipient via an alternative channel to notify their IT department.
  3. Escalate the case to 2nd Level Technical Support to investigate if an outbound TLS verification bypass or policy adjustment can be configured for that specific recipient domain.

### 2. Outbound Email Blocked by Gmail (Unauthenticated Sender SPF/DKIM on External DNS)
- **Scenario:** Outbound emails to Gmail/Google accounts are bouncing with authentication errors.
- **Diagnostic Error:** `Your email has been blocked because the sender is unauthenticated. Gmail requires all senders to authenticate with either SPF or DKIM.` OR `Unauthenticated email from [domain] is not accepted due to domain's DMARC policy.`
- **Root Cause (External DNS):** The domain's email is hosted at one.com (MX records point to one.com), but its nameservers (DNS) are managed by an external provider (e.g., Wix, Cloudflare, GoDaddy). Because DNS is external, one.com cannot automatically publish SPF or DKIM records. Due to Google's strict email sender authentication requirements, emails sent from an unauthenticated domain are blocked.
- **Root Cause (Combined SPF+DMARC Record):** Even when DNS is hosted at one.com, emails can still bounce if the SPF and DMARC records are incorrectly combined into a single TXT record. Gmail's strict DMARC enforcement requires proper separation of these records.
- **Resolution Steps:**
  1. Check the domain's current nameservers using a DNS lookup or WHOIS.
  2. Check the current DNS TXT records for the domain — look for any combined SPF+DMARC records.
  3. If DNS is hosted externally, explain to the customer that they must add the required TXT/CNAME records in their external registrar's DNS control panel.
  4. If a combined SPF+DMARC record is found, instruct the customer to:
     - Delete the existing combined TXT record
     - Create a separate SPF TXT record: Type TXT, Host: @, Value: `v=spf1 include:_custspf.one.com ~all`
     - Create a separate DMARC TXT record: Type TXT, Host: `_dmarc`, Value: `v=DMARC1; p=none; rua=mailto:[customer's email]`
  5. **SPF Record to Add:**
     - **Type:** TXT
     - **Host/Name:** `@` (or leave blank)
     - **Value:** `v=spf1 include:_custspf.one.com ~all`
  6. **DKIM Records to Add:**
     - Advise that DKIM requires CNAME records (2 for migrated, 4 for non-migrated domains) that support can generate for them.
- **Important Note:** Always check for both scenarios — external DNS AND combined records. DNS propagation may take up to 24-48 hours after changes.

### 3. Changing or Resetting Email Password
- **Scenario:** Customer wants to change their email password or has forgotten it.
- **Resolution Steps:**
  - **Option 1: Via the one.com Control Panel (If password is forgotten or managing multiple accounts)**
    1. Log in to the [one.com Control Panel](https://www.one.com/admin/).
    2. Click the arrow on the **Email and Microsoft 365** tile.
    3. Find the email address to update.
    4. Click the **three dots** (Settings) on the right-hand side.
    5. Select **Change password** from the menu.
    6. Enter and repeat the new password, then click **Save** (it may take up to 5 minutes to become active).
  - **Option 2: Via Webmail (If current password is known)**
    1. Log in to [Webmail](https://www.one.com/webmail/) with the email address and current password.
    2. Click the **Settings icon** in the left-hand menu.
    3. Select **Security** from the menu on the left.
    4. Click **Change password**.
    5. Enter the **current password**, then type and confirm the **new password**.
    6. Click **Save**.

### 4. Managed Exchange / Office 365 Tenant Removal Delay
- **Scenario:** Customer cancelled their Managed Exchange/Office 365 via one.com and wants to set it up directly with Microsoft, but they get an error stating the domain is still in a tenant.
- **Root Cause:** For Managed Exchange, the Microsoft tenant removal is processed automatically *only* after all Exchange accounts associated with the domain are fully cancelled/deleted on our end. However, this automatic process is not instant and can take time (e.g. 24-48 hours) after the accounts were deleted.
- **Resolution Steps:**
  1. Verify that all Exchange accounts for the domain have been cancelled in the control panel.
  2. Inform the customer that the tenant removal happens automatically, but they might have to wait a little longer after the accounts were deleted.
  3. Ask the customer to wait and try adding the domain again later.

---

## Specific Case Studies & Ticket Takeaways

### Case Study 4: Domain stuck in tenant after cancelling Office 365 Management
- **Ticket Reference:** Case QUZ2B
- **Customer Name:** Fee
- **Customer Email:** `feevanda@gmail.com`
- **Domain:** `feeke.be` (`fee@feeke.be`, `marketing@feeke.be`)
- **Context:** Customer cancelled their Office 365 management with one.com yesterday and wanted to set it up directly via Microsoft. Microsoft gave an error that the domain was still in our tenant. Second level support confirmed that for Managed Exchange, the tenant is removed automatically once all accounts are deleted, but the customer needed to wait a bit longer for the automatic removal to process since cancellation just happened.

### Case Study 1: Outbound Email Delivery Issue due to Recipient TLS Misconfiguration
- **Ticket Reference:** Takeaway 4
- **Customer Name:** Martha / Mr. Azhar M Khan
- **Customer Email:** `azhar@wrightjustice.co.uk` (also affects `info@`, `admin@`, `ilyas@`, `sarah@`, `zain@`)
- **Domain:** `wrightjustice.co.uk`
- **Target Recipient:** `fhr16@homeoffice.gov.uk` (UK Home Office)
- **Context:** All emails associated with the domain were pending in the queue due to a STARTTLS certificate error at remote MTA `smtp4.homeoffice.gov.uk`. Advised customer that the issue is on the recipient's end, and escalated to Tier 2 for policy bypass investigation.

### Case Study 2: Outbound Email Blocked by Gmail due to Unauthenticated Sender (External DNS)
- **Ticket Reference:** Takeaway 11
- **Customer Name:** Alice
- **Customer Email:** `info@embelstudio.co.uk`
- **Domain:** `embelstudio.co.uk`
- **Target Recipient:** `alicestewart5tw@gmail.com`
- **Context:** Customer's emails to Gmail were bouncing because the domain's DNS is managed externally by Wix (`ns8.wixdns.net`/`ns9.wixdns.net`). Instructed customer to add the SPF TXT record `v=spf1 include:_custspf.one.com ~all` in Wix DNS and offered to generate DKIM CNAME records.

### Case Study 3: Email Setup and Password Confusion
- **Ticket Reference:** Email Setup and Password Confusion File
- **Case A (Susanne Friese - `support@qinsights.ai` / `qinsights.ai`):** Customer unable to connect after resetting password via `mail.one.com`. Support instructed verification of password via Webmail (`mail.one.com`) and provided standard IMAP (`imap.one.com:993`) and SMTP (`send.one.com:465` with SSL/TLS) settings, using full email as username.
- **Case B (Lara De Peña - `lara.hutmann@gmail.com` / `info@cadalocal.ch` / `cadalocal.ch`):** Customer had setup errors using incorrect server `imap.cadalocal.com`. Support supplied correct settings (`imap.one.com`, `send.one.com`, port/SSL) and guided password reset via the **Email and Microsoft 365** tile in the one.com control panel.

### Case Study 4: one.com Customer Support Contact Information
- **Ticket Reference:** Takeaway 23
- **Customer Name:** N/A
- **Customer Email:** N/A
- **Domain:** N/A
- **Context:** Internal reference discovery. The one.com customer support phone number was not documented in the knowledge base. Direct phone support is available at `+44 20 8106 0910`, weekdays 10am–2pm UTC. Live chat is available every day of the year and is the quickest contact method. Email support is available via `support@one.com` or through the help center contact form at `https://help.one.com/hc/en-us/requests/new`. Note: The Uberall support number (`+44 20 3769 3000`) is separate and only for Uberall-specific issues.

### Case Study 5: Contact Form Failures Across Multiple WordPress Sites (Cache + SMTP)
- **Ticket Reference:** Takeaway 25 (Shared with WordPress)
- **Customer Name:** Åsa
- **Customer Email:** azaboztrom@yahoo.se
- **Domain:** asabostrom.com, parbostrom.com, hypnagogapress.com, writeyourself.com, kammarheit.com (recipient: info@asabostrom.com)
- **Context:** Customer reported contact forms on several WordPress sites not delivering messages (example: https://asabostrom.com/contact/). Support tests were mixed: forms on asabostrom.com and writeyourself.com succeeded after the customer deactivated a caching plugin (common cause: cached pages serving expired WordPress nonces). Customer still saw errors due to browser cache; Incognito/clear cache recommended. Some test mails landed in spam. hypnagogapress.com form accepted submission; writeyourself.com tests arrived. parbostrom.com/contact/ and kammarheit.com/contact/ failed for support with "There was an error trying to send your message. Please try again later." Escalated to engineers; guidance was to install WP SMTP and configure with one.com email host (guide: https://help.one.com/hc/en-us/articles/6949620532113-How-to-send-emails-in-WordPress-using-the-WP-SMTP-Mail-plugin). Also note: customer browser tools (e.g. Norton anti-tracking) can interfere with form submissions client-side; exclude contact pages from cache plugins; SPF/DMARC help deliverability but do not fix form send errors by themselves.

### Case Study 6: Email Restoration from Backup & Restore Service
- **Ticket Reference:** Takeaway 29
- **Customer Name:** N/A
- **Customer Email:** N/A
- **Domain:** N/A
- **Context:** Reference information from one.com's Backup & Restore service (https://www.one.com/en-gb/website-security/backup/). The service provides automatic daily backups for email, websites, and databases with up to 2 weeks retention. To restore email: go to Control Panel, select the email address, choose a date, and set up new credentials — the restore creates a new mail account rather than overwriting the existing one. Email notification is sent upon completion. Backup & Restore is included with Website Builder Premium or larger plans; otherwise available as an add-on from the Control Panel. Note: restoration always creates a new account, not an overwrite of the current one.

### Case Study 7: Exporting Webmail Mailboxes to PST for Microsoft Outlook
- **Ticket Reference:** Takeaway 35
- **Customer Name:** Shahmir Baloch
- **Customer Email:** N/A
- **Domain:** communitycareworker.com
- **Context:** Customer requested backups of all webmail mailboxes as .pst files for import into Microsoft Outlook. one.com does not offer a direct PST download from Webmail or the Control Panel. The correct method is to connect each mailbox to Outlook via IMAP (imap.one.com, port 993, SSL/TLS; send.one.com, port 465, SSL/TLS), let it fully sync, then use Outlook's Import/Export feature (File → Open & Export → Import/Export → Export to a file → Outlook Data File (.pst)) to create the .pst file. This must be repeated for each mailbox. Customer asked whether a Microsoft license is needed per mailbox — the answer is no; only one Outlook desktop installation is required, and all mailboxes can be added to it via IMAP. Key point: clarify upfront that PST creation requires Outlook on the desktop, as one.com has no native PST export. Avoid confirming "yes we can provide PSTs" before explaining the actual method.

### Case Study 8: DMARC Rejection Due to Combined SPF+DMARC TXT Record
- **Ticket Reference:** Takeaway 36
- **Customer Name:** Ahmad Bachir
- **Customer Email:** info@coolmaster.be
- **Domain:** coolmaster.be
- **Context:** Customer's outbound emails from info@coolmaster.be were bouncing with a 550-5.7.26 DMARC rejection error from Gmail: "Unauthenticated email from coolmaster.be is not accepted due to domain's DMARC policy." Customer was sending via Outlook PWA through one.com. Investigation revealed the domain's SPF and DMARC records were incorrectly combined into a single TXT record, causing DMARC authentication to fail. DNS was hosted at one.com (not external). Resolution: customer instructed to delete the combined TXT record and create two separate records — an SPF TXT record (Host: @, Value: v=spf1 include:_custspf.one.com ~all) and a DMARC TXT record (Host: _dmarc, Value: v=DMARC1; p=none; rua=mailto:info@coolmaster.be). DNS propagation may take 24-48 hours. Key lesson: when diagnosing DMARC rejection errors, always check whether SPF and DMARC are properly separated into distinct TXT records, not just whether records exist.
