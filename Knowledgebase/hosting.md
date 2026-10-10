# Hosting & Server Knowledge Base

## General Procedures & Policies

### 1. SSH and Webroot Directory Confusion Post-Migration
- **Scenario:** After server migration, customers might see different directory structures via SSH compared to the control panel's File Manager, leading to confusion about where to upload live files.
- **Key Rules & Root Cause:**
  - SSH/SFTP logins often land the user in their private home directory (e.g., `/customers/.../users/username_ssh`).
  - The live website files served to visitors are located in the main webroot directory (e.g., `/customers/.../webroots/www/`).
  - Subdomains are also served from specific directories inside the main webroot (e.g., `webroots/www/subdomain/`).
- **Resolution Steps:**
  1. Instruct the customer to navigate to `/customers/.../webroots/www/` inside their SSH/SFTP client to manage the live website.
  2. Advise that subdomain folders must reside inside the main `www/` directory to function.
  3. Reassure the customer that old credentials remain active temporarily during the transition.

### 2. FTP/SFTP Access Issue (External Hosting)
- **Scenario:** A customer is unable to access FTP/SFTP via FileZilla using one.com credentials.
- **Key Rules & Diagnosis:**
  - Always check the domain's DNS/Nameservers and IP routing first.
  - If the domain points to external nameservers (e.g., Cloudflare) and the SSH/SFTP hostname points to an IP belonging to an external host (e.g., Combell), then the website and FTP hosting are located externally.
- **Resolution Steps:**
  1. Explain to the customer that their DNS and web hosting are managed externally (e.g., Combell).
  2. Advise them that their one.com FTP credentials do not apply, and they must contact their external host's support or control panel to retrieve the correct credentials.

### 3. Website 500 Internal Server Error vs. DNS Issue
- **Scenario:** Customer reports their website is not loading or shows a "Page not found" error, suspecting a DNS or nameserver issue, and requests a DNS reset.
- **Key Rules & Diagnosis:**
  - Verify nameserver delegation (pointing to one.com) and that DNS A/AAAA records point to one.com default IPs.
  - If DNS is correct but the site returns a **500 Internal Server Error**, it is a server-side code/script issue (e.g., `.htaccess` or PHP errors) rather than a DNS resolution issue.
- **Resolution Steps:**
  1. Reassure the customer that their DNS records are correct and pointing to one.com (DNS reset is not needed).
  2. Explain that the website is encountering a server-side 500 error.
  3. Guide the customer on how to enable PHP error messages in their one.com Control Panel to identify and fix the underlying script error.

### 4. Web Space Exceeded and Root Directory (tmp) Directory Management
- **Scenario:** Customer reports that their web hosting space is completely full/exceeded, despite having a simple website and non-full email accounts. The customer cannot find any large files using the control panel's File Manager.
- **Key Rules & Diagnosis:**
  - The default control panel File Manager only displays files within the public website directory (`httpd.www`).
  - A full disk space issue can often be caused by files accumulating in the root directory (one level above `httpd.www`), such as the `tmp` folder.
  - The `tmp` folder may accumulate a massive number of session files and PHP files over time. Deleting session files in `tmp` is safe and will instantly free up web space, restoring website functionality (e.g., fixing blank/white screen errors caused by a full disk).
- **Resolution Steps:**
  1. Explain to the customer that the `tmp` folder in their root directory (one level above `httpd.www`) is taking up most of the space.
  2. Inform them that they can safely delete the session files inside `tmp` to free up space, but they should review and confirm any PHP files there before removal.
  3. Advise that since the `tmp` folder is located in the root directory, it is not visible in the default File Manager view.
  4. Instruct them to use an FTP client to access and manage the files in their root directory.

### 5. Aida AI Website Builder Domain Connection & File Preservation Limitations
- **Scenario:** A customer builds a website using the Aida AI Website Builder (free trial) and wants to connect an existing domain (or export files/design assets) to it.
- **Key Rules & Limitations:**
  - **No Existing Domain Connection:** Currently, there is no option to connect an existing domain to a website built on the Aida AI Website Builder trial.
  - **Publishing Requirement:** The only way to publish or launch a website built via the Aida AI trial is to purchase a new domain directly through the Aida AI platform.
  - **No Export Option:** There is no option to export or save the website files, nor is there an option to extract color hex codes or uploaded photos directly.
- **Resolution Steps:**
  1. Inform the customer that connecting an existing domain or saving/exporting website files is not supported on the free trial.
  2. Explain that to preserve and publish the website, they must purchase a new domain directly through the Aida AI platform.
  3. Verify the availability of alternative domains (e.g., `.us`, `.com`) if requested.

### 6. NFS (.nfs) Files and Deletion Errors
- **Scenario:** Customer cannot delete hidden files starting with `.nfs` (e.g., `.nfs80d8282e...`) in their root or `tmp` directory via FTP/SFTP (FileZilla returns permission/access error).
- **Key Rules & Diagnosis:**
  - **Root Cause:** A Network File System (NFS) "silly rename" occurs when a file is deleted or modified while still actively held open by a running server process (e.g., a PHP script or web server process). The system renames it to `.nfsXXXX` and keeps it until the process terminates.
  - **Standard Resolution:** These files are usually deleted automatically once the active process terminates or times out.
  - **Manual Removal Policy:** If a customer requests support to manually delete `.nfs` files, **strict security verification is required first**. The request must be sent and verified from the customer's registered administrator email address before escalating to Tier 2/Senior Technical Team for deletion.
- **Resolution Steps:**
  1. Explain that `.nfs` files are created by the server's Network File System (silly rename) because a file is still in use by an active background process. Reassure them it is standard behavior and not malware.
  2. Advise that they will normally disappear automatically once the process stops.
  3. If they want support to manually delete the files, request a confirmation email sent from their registered administrator email address stating: "I confirm and request the removal of the .nfs file from my account for [domain]."
  4. Once verified, escalate the request to the Senior Technical Team (Tier 2) to delete the files.

### 7. Virtual Private Server (VPS) & OpenClaw AI Assistant
- **Scenario:** Customer has questions regarding one.com's VPS plans, features, or how to deploy/use the OpenClaw self-hosted AI assistant.
- **OpenClaw Overview:**
  - OpenClaw is an open-source, self-hosted AI assistant (formerly Moltbot/Clawdbot) designed to run 24/7 on a private server (VPS).
  - It acts as an automated agent that can execute tasks, browse the web, and respond to webhooks.
  - Connects to major messaging apps (WhatsApp, Telegram, Slack, Discord, MS Teams, Signal) for chat-based control.
  - Supports API integration with external models (OpenAI GPT, Anthropic Claude, Google Gemini) or running private local models via Ollama.
  - Published under the MIT license (free to use, no platform fees).
- **VPS Infrastructure Features:**
  - Includes a **1-click automated installer** for OpenClaw.
  - Equipped with NVMe SSD storage and AMD EPYC processors.
  - Guaranteed 99.99% uptime with 1 Gbit/s bandwidth and unlimited traffic.
  - Provides full root access and choice of operating system (Ubuntu, Debian, AlmaLinux, etc.).
  - Powered by 100% green, sustainable energy.
- **VPS Plans and Specifications:**
  - **Cloud Server S ($5.99/mo):** 2 Cores vCPU, 4 GB RAM, 100 GB NVMe SSD, 5,000 IOPS.
  - **Cloud Server M ($9.99/mo - Popular):** 4 Cores vCPU, 8 GB RAM, 200 GB NVMe SSD, 5,000 IOPS.
  - **Cloud Server L ($17.99/mo):** 8 Cores vCPU, 16 GB RAM, 400 GB NVMe SSD, 5,000 IOPS.
  - *All plans feature monthly billing, no setup fees, and 24/7 support.*
- **Common Use Cases:**
  - **Developers:** Running code reviews, background tasks, and debugging.
  - **Freelancers:** Admin tasks, calendar/email summaries (morning briefs), and research.
  - **Agencies:** Segmenting client workflows on a single VPS with isolated configs.
  - **Small Businesses:** Support routing, invoicing automation, and lead qualification.
- **Resolution Steps (Setting up OpenClaw):**
  1. Guide the customer to select a VPS plan matching their resource needs (Cloud Server S, M, or L).
  2. Deploy OpenClaw on the VPS using the 1-click installer in the control panel.
  3. Direct the customer to connect their preferred AI model provider (or set up Ollama for local hosting) via an API key.
  4. Connect the setup to their preferred messaging channel to start interacting with their AI agent.

### 8. Website Builder Plan FTP/SFTP Access Limitations
- **Scenario:** A customer has a Website Builder-only subscription (e.g., Website Builder Business) and wants to find where to configure FTP/SFTP parameters or passwords in their control panel.
- **Key Rules & Limitations:**
  - **No Standard Web Space:** Website Builder-only subscriptions (such as Website Builder Business) do not include standard hosting web space.
  - **No FTP/SFTP/SSH Access:** Because there is no standard web space, these subscriptions do not support FTP, SFTP, or SSH, and there is no option in the control panel to configure an FTP password.
  - **Direct Publishing:** Sites are built, managed, and published directly within the visual Website Builder interface in the control panel.
- **Resolution Steps:**
  1. Explain that their current Website Builder subscription is designed for the visual builder and does not include standard hosting web space or FTP/SFTP access.
  2. Advise that they can design and publish their site directly through the Website Builder editor without needing FTP.
  3. If they have custom files/scripts to upload and require FTP access, advise them to upgrade to a hosting plan that includes web space.

---

## Specific Case Studies & Ticket Takeaways

### Case Study 1: SSH and Webroot Directory Confusion Post-Migration
- **Ticket Reference:** Takeaway 6
- **Customer Name:** Steven
- **Customer Email:** steven@vdks.be
- **Domain:** `wijkteamrodenburg.be`
- **Context:** Customer was confused by directory structure via SSH post-migration. Explained SSH login lands in home directory `/customers/c/0/b/ctb0jryst/users/ctb0jryst_ssh` while live files are in `/customers/c/0/b/ctb0jryst/webroots/www/`. Guided customer to navigate to the webroots directory and move subdomains (`dev`, `prod`) inside `www`.

### Case Study 2: FTP/SFTP Access Issue due to External Hosting (Combell)
- **Ticket Reference:** Takeaway 7
- **Customer Name:** Philippe
- **Customer Email:** `support@pc-matic.be`
- **Domain:** `steakamanger.be`
- **Context:** SFTP failed using one.com settings. Nameservers pointed to Cloudflare and `ssh.steakamanger.be` pointed to Combell IP `185.86.18.198`. Advised customer that hosting is located with Combell, and they must retrieve SFTP details from Combell support.

### Case Study 3: Domain DNS Resolution and 500 Error Troubleshooting
- **Ticket Reference:** Takeaway 5
- **Customer Name:** Tao Jin
- **Customer Email:** `woodyjin415@hotmail.com`
- **Domain:** `xjcc.de`
- **Context:** Customer reported website page not found and wanted a DNS reset. Checked nameservers pointing to one.com and default A/AAAA records correctly pointing to `46.30.213.81`. Found the website was returning a 500 Internal Server Error. Guided customer to enable PHP error messages in control panel to troubleshoot code/scripts.

### Case Study 4: Web Space Exceeded and Root Directory (tmp) Directory Management
- **Ticket Reference:** Takeaway 10
- **Customer Name:** Marcus
- **Customer Email:** `marcus@kronogarden.net` (Alternative: `info@levin-nilsson.se`)
- **Domain:** `levin-nilsson.se`
- **Context:** Disk space was completely full (760 GB of 750 GB used), causing a blank white page. Control Panel File Manager didn't show large files. Support found `tmp` root folder full of session files and PHP files, and the active `wp-content` folder taking up the most space. Advised deleting session files via FTP to immediately restore site functionality.

### Case Study 5: Aida AI Website Builder Limitations and Domain Purchase
- **Ticket Reference:** Takeaway 15
- **Customer Name:** Danielle
- **Customer Email:** `peacebuildersbusiness@gmail.com`
- **Domain:** `generatedemocracy.com` (Existing) / `generatedemocracy.us` (Purchased)
- **Context:** Customer built a website with Aida AI during a trial and wanted to connect her existing domain `generatedemocracy.com`. Support explained that existing domains cannot be connected to the Aida trial and files cannot be exported. To preserve her design, she was guided to purchase a new domain (`generatedemocracy.us`) directly through the Aida platform.

### Case Study 6: NFS (.nfs) Files Deletion and Admin Email Verification
- **Ticket Reference:** Takeaway 16
- **Customer Name:** Lars Bertelsen
- **Customer Email:** `lars@bertelsen.one`
- **Domain:** `denalpinehave.dk`
- **Context:** Customer was cleaning up malware but could not delete a `.nfs` file in the `tmp` directory using FileZilla. Support explained that `.nfs` files are created due to active server processes holding the deleted files open (NFS silly rename) and are normally automatically deleted when the process stops. For support to manually remove the `.nfs` files, security verification was required. The customer sent a confirmation email from his registered administrator address, and the request was escalated to Tier 2 for manual removal.

### Case Study 7: Website Builder Plan FTP/SFTP Access Limitations
- **Ticket Reference:** Takeaway from Diana Monreal (Website Builder FTP limitations)
- **Customer Name:** Diana Monreal
- **Customer Email:** `d.diana.monreal@gmail.com`
- **Domain:** `flordefimo.com`
- **Context:** Customer wanted to connect via FTP to her web space and couldn't find where to configure the FTP password in her control panel. Checked the subscription details and found the customer was on the Website Builder Business package. Explained that Website Builder-only packages do not include standard web space or FTP/SFTP access, as they publish directly via the editor. Guided the customer to use the editor directly or upgrade to a hosting plan if FTP access is required.

### Case Study 8: Website Content Restore using Webspace and Database Backups
- **Ticket Reference:** Takeaway 20
- **Customer Name:** Trisha
- **Customer Email:** info@planticum.com
- **Domain:** planticum.com
- **Context:** Customer reported that their landing page had changed/gone, with only the website header visible and all other content missing. The support robot initially incorrectly suggested that the "index" file was missing and instructed the customer to rename a file to `index.html` or `index.php` via File Manager, which confused the customer. Rafael took over the chat, verified that the customer was in the control panel, and guided them to use the Backup & Restore tool under Hosting Settings. Step-by-step instructions were provided to restore both the Webspace (files) and the Database using a matching, known-good restore date. The customer successfully initiated both restores, and the landing page and database content were restored within minutes. Key takeaways: (1) When website content goes missing or is partially displayed, verify the availability of backups first before manually manipulating files. (2) For websites with databases (such as CMS sites), both the Webspace files and the Database must be restored to the same point in time (matching date) to ensure compatibility. (3) Visual aids and clear step-by-step navigation through the control panel tabs (Webspace and Database) help prevent customer confusion and lead to swift resolutions.

### Case Study 9: Database Connection and Server Host Changes Post-Migration
- **Ticket Reference:** Case ID: Y0U83
- **Customer Name:** Pär Mattsson
- **Customer Email:** parmattsson@yahoo.se
- **Domain:** bjorkstakoren.se
- **Context:** Following a platform migration, the customer reported that their website's database connection was failing with an "Access denied" error. The custom PHP website was using `mysqli_connect` inside `include_db.inc`. Although the database name and username were updated to the new prefix format (`cslhbywgw_bjorkstakoren_sebk`), the script still failed because it used the old database server host address (`bjorkstakoren.se.mysql`). A support engineer resolved the issue by modifying `include_db.inc` directly to use the new server address (`mysql.cslhbywgw.service.one`), which restored the site. However, the customer was upset about files being edited directly without prior coordination, presenting a risk of overwriting active local edits. Additionally, the customer reported that the MariaDB control panel showed confusing host information (e.g., 'localhost' and `cslhbywgw.mysql.service.one.com:3306`) which did not work in remote scripts. Lastly, the customer complained that the migration notification email didn't warn about the changed database server address. We explained that migration notifications are sent only to the registered primary contact email for GDPR compliance, which differed from the customer's support contact email. Key lessons: (1) When database connection fails after a platform migration despite updated credentials, check that the database host is updated to the correct new platform server address. (2) Avoid directly editing customer files without prior coordination/permission to prevent overwriting active customer changes. (3) Platform migration alerts are sent only to the registered subscription contact email to comply with GDPR privacy rules. (4) Ensure the support team is prepared with accurate database server strings, as control panel information can sometimes be misleading or incomplete for custom scripts.

### Case Study 10: one.com Customer Support Contact Information
- **Ticket Reference:** Takeaway 23
- **Customer Name:** N/A
- **Customer Email:** N/A
- **Domain:** N/A
- **Context:** Internal reference discovery. The one.com customer support phone number was not documented in the knowledge base. Direct phone support is available at `+44 20 8106 0910`, weekdays 10am–2pm UTC. Live chat is available every day of the year and is the quickest contact method. Email support is available via `support@one.com` or through the help center contact form at `https://help.one.com/hc/en-us/requests/new`. Note: The Uberall support number (`+44 20 3769 3000`) is separate and only for Uberall-specific issues.

### Case Study 11: Website Stuck on Loading Animation Due to External CDN (GSAP) Failure
- **Ticket Reference:** Takeaway 39
- **Customer Name:** Courcey (Ziggy)
- **Customer Email:** ziggy001@me.com
- **Domain:** ziggysentertainmentgroup.com
- **Context:** Customer reported website stuck on a spinning cross loading animation after upgrading to the Enthusiast Plan. The site loaded fine from the US and Asia but not from the customer's location in West Yorkshire, UK. Issue reproduced on multiple devices (iPhone, laptop, 2 other phones) and different browsers. Initial troubleshooting (cache clear, different browsers/devices/networks) did not resolve it. Escalated to engineers who identified the root cause: the website's theme relies on GSAP (GreenSock Animation Platform) JavaScript files (`gsap.min.js`, `ScrollTrigger.min.js`) and Font Awesome assets loaded externally from `cdnjs.cloudflare.com`. These CDN requests were failing silently from the UK region, preventing the preloader overlay from animating out and hiding the main site content. The fix was for the website designer to download the GSAP and Font Awesome files locally onto the server and update the site to load them locally instead of from the external CDN. Key lessons: (1) When a website loads in some regions but not others, investigate external CDN dependency failures — third-party CDN blocks or outages can cause region-specific loading issues. (2) A hosting plan upgrade is unlikely to cause CDN-related loading failures; the timing was coincidental. (3) Themes relying heavily on external CDN-hosted JavaScript libraries (GSAP, Font Awesome) are vulnerable to silent failures if those CDNs are unreachable from certain regions. Recommending local hosting of critical JS assets is a reliable workaround.

### Case Study 12: Unpublishing a Website Builder Site by Renaming the Index File
- **Ticket Reference:** Takeaway 40
- **Customer Name:** Ann-Charlotte Tennek
- **Customer Email:** ac@tennek.se
- **Domain:** soulhouse.se
- **Context:** Customer wanted to temporarily take her website offline ("unpublish" it). The site was built using the one.com Website Builder, which does not have a built-in "unpublish" button — only "Publish" and "Edit" options are visible. The resolution is to rename the index file (index.php or index.html) via File Manager in the one.com control panel, which immediately makes the start page unavailable while keeping all other pages and content intact. To restore the site, the customer simply renames the file back to its original name. Key lesson: When a Website Builder customer asks to take their site offline temporarily, renaming the index file via File Manager is the standard workaround. Guide the customer through: Control Panel → File Manager → select index file → Rename (e.g., index-1.php). This is a quick self-service solution that avoids needing to delete or unpublish content.

### Case Study 13: Website Unreachable from Specific Customer IP — Blackholed Web Node Diagnosis via Timeout vs. Refused
- **Ticket Reference:** Takeaway 41
- **Customer Name:** Tor Rønnow
- **Customer Email:** N/A
- **Domain:** temperance.dk
- **Context:** Customer reported temperance.dk completely unresponsive from his home network (egress IP 2.110.132.105) — not working in any browser, while FTP and webmail worked fine from the same IP. Support tested from their side and the site loaded normally; no blocks or restrictions in the logs. The customer's own diagnostics were decisive: DNS resolved correctly (temperance.dk → 46.30.215.48), but curl to the web IP on both ports 443 and 80 returned error 28 "Connection timed out after 20001 milliseconds" — not "Connection refused". Meanwhile FTP to the sibling IP 46.30.211.152 connected instantly. Key lessons: (1) Timeout (no SYN-ACK) vs. refused (host up, actively rejecting) is the fast discriminator — a timeout to one IP while a sibling IP on the same account/network answers immediately points to a dead/blackholing web node, not an IP ban or firewall reject. (2) If the customer's source IP is not found in the IP handle block, first-level cannot trace the drop — escalate to 2nd level/network team and request MTR results from the customer's side targeting the customer NAT (here: 193.202.110.22 / customer-nat.pub.webpod15-cph3.one.com; webnode web17.cst.webpod15-cph3.one.com). Ask for at least 100 packets and full hop output. (3) When a customer hands over precise curl output, pass it to engineers verbatim — it shortcuts diagnosis significantly.

### Case Study 14: Attaching Domain to Existing Enthusiast Plan When Primary Domain Uses External Nameservers (Shared with Domain)
- **Ticket Reference:** Takeaway 43
- **Customer Name:** Adam
- **Customer Email:** adam@inkwear.co.uk
- **Domain:** inkwear.co.uk (primary, external Cloudflare nameservers), inkwearusa.com (to attach, one.com nameservers)
- **Context:** Customer needed to attach inkwearusa.com to his existing Enthusiast plan (primary domain inkwear.co.uk) to share hosting resources and avoid paying for a separate plan. The one.com control panel crashed when attempting to add inkwearusa.com because the primary domain inkwear.co.uk uses external Cloudflare nameservers, which caused the add-on domain script to fail. However, this is purely a billing/subscription association — attaching a domain to an existing plan does not require the primary domain to use one.com nameservers. inkwearusa.com was already using one.com nameservers and DNS, so WordPress installation and site setup should have been unaffected regardless of the attachment status. The ticket was significantly delayed because the conversation was derailed by a separate DKIM/email issue for inkwear.co.uk, which had been mixed into the same thread by the customer in a prior chat. Multiple agents and L2 escalations worked on the DKIM issue over several days before the customer clarified his actual need. Key lessons: (1) When a control panel script fails to add an addon domain, check whether the primary domain uses external nameservers — the backend attachment can still be processed manually as it is a billing/subscription matter, not a DNS one. (2) Always confirm with the customer what their actual primary request is, especially when multiple issues have been raised in the same thread — in this case the DKIM issue for inkwear.co.uk was unrelated to the domain attachment for inkwearusa.com. (3) A domain using one.com nameservers can host WordPress independently of whether it is attached to another domain's plan — the attachment is about shared billing/resources, not about DNS or site functionality.

### Case Study 15: Verification Rules Before Giving Out Information (GDPR)
- **Ticket Reference:** Takeaway 46
- **Customer Name:** N/A
- **Customer Email:** N/A
- **Domain:** N/A
- **Context:** Internal policy reference ("Giving out information" article — verification & GDPR). Core rule: never give out or confirm/deny order, customer, or owner details (not even partial, e.g. "sent to p...@one.com"); the only exception is Zendesk's "insert e-mail" feature — the only allowed way to show a masked webspace owner e-mail. Prefer self-service: guide the customer in the control panel, or send a forgot-password/info mail to the registered e-mail so it reaches the verified customer. Verification methods: (1) e-mail from the registered address, (2) phone call from the registered number, (3) copy of the webspace owner's ID, (4) Zendesk Messaging Authentication. A control panel guest user is NOT a verified customer. OK to share without verifying: order type (private/company/association); order active/deleted/cancelled, cancellation deadline, subscription period, hosting plan, active add-ons; outstanding payment and amount, invoice number, bank details, payment methods, whether a case is with Intrum/inkasso, that invoices always go to the webspace owner (never name them) and can be found in the control panel; suspension reasons — spam from connected mail accounts (not which ones), malware/hacked site (malware file list OK), unpaid invoice, missing registrant verification (no owner details); PHP info variables, webspace IP from the zonefile, whether DNS settings are deactivated, whether any personal DNS records exist at all (not which ones — point the customer to https://mxtoolbox.com/SuperTool.aspx); that public owner info is in the WHOIS registry. Verify first: owner name/address/phone, company contact person, registered e-mail (webspace owner and domain owner); CP-visible registrant details (only if the webspace owner is verified AND the domain owner is the same legal entity); order number (only to the registered e-mail or against an ID copy); invoice link, Intrum reference (order-number verification sufficient), credit card number (alternative: written request + ID or company-registry copy), name/e-mail the invoice was sent to; list of mail accounts sending spam, why spam filters flagged a message (order-number verification sufficient — never give this to the sender), zonefile info other than the webspace IP (same), any access/e-mail logs, which personal DNS records are active and where they point, active e-mail forwards and their targets. Card-payment traces: after the payment team traces a card payment, the domain name(s) paid with that card may be given out — anything more (owner name, invoice link) requires verification. One verified order covers other orders ONLY if both the contact e-mail and the owner (legal entity) are identical — always double-check both. "Selected domain:..." in Zendesk does NOT verify anyone (it only means a control panel was used on that computer — could be a guest user or someone else's login). GDPR superusers: Bianca Stommel (bist), Fredrik Nilsson (frni), Ivar Mathiasson (im), Jacob Zwicki (jaz), Martin Erb (me), Nikolay Christensen (ni), Rajsi Hawaldar (rah).

### Case Study 16: Storage Suspension with Mail/Web Separation and One-Week Grace Period
- **Ticket Reference:** Takeaway 47 (Shared with Email)
- **Customer Name:** Ali Issa
- **Customer Email:** N/A
- **Domain:** N/A
- **Context:** Customer's account was suspended for exceeding the allowed storage on the hosting plan. Support offered to lift the suspension and grant a one-week grace period to free up space; the customer agreed to reduce stored emails but noted their total shared disk space was not yet full, and asked for the email storage limit to instruct internally. Key lesson: a hosting storage suspension can be driven by mailboxes rather than web files — mail storage and shared web disk space are tracked separately, so a customer reporting free web space is not a contradiction and does not invalidate the suspension. Quoting the Fair Use Policy (effective 16 September 2026) resolves the confusion: 200 GB mail storage fair-use baseline per contract (growing 100 GB/year if needed, more on request for legitimate business need), 200 GB web storage baseline, effectively 400 GB combined where both apply, and 500 email accounts per contract. Handling pattern: offer to lift the suspension with a one-week window to reduce usage, confirm the mail baseline so the customer can plan internally, and do not rely on the File Manager's web-space view alone when diagnosing storage suspensions.

### Case Study 17: Never Recommend Backup Plugins — Use Backup & Restore or Manual Backup (Shared with WordPress)
- **Ticket Reference:** Takeaway 48 (Shared with WordPress)
- **Customer Name:** Roya
- **Customer Email:** roya.phat@qrut.se
- **Domain:** qrut.se
- **Context:** Customer asked which WordPress plugin to recommend for backing up her database. A draft reply suggesting third-party backup plugins (UpdraftPlus, WP-DB-Backup) was corrected against one.com's "Discouraged WordPress plugins" policy before sending — one.com advises against backup plugins in general (high server load, performance issues, security risk). Correct answer for any backup question: point to the Backup & Restore add-on product (Control Panel → Hosting) for saving/restoring the database and website, offer the manual alternative (phpMyAdmin database export and/or web space backup), and note that one.com takes security backups every night. Key lesson: never recommend backup plugins — for WordPress plugin questions check the Discouraged plugins list first; for backup needs, always steer to Backup & Restore or manual backups.

### Case Study 18: HTTP 500 After Successful WooCommerce Checkout — OOM Kills on Explorer Package (Shared with WordPress)
- **Ticket Reference:** Takeaway 49 (Shared with WordPress)
- **Customer Name:** Patrick
- **Customer Email:** patrick@pokedrop.dk
- **Domain:** pokedrop.dk
- **Context:** Customer's WooCommerce store created order #3404 successfully (confirmation email sent, payment authorised), but the customer was shown an HTTP 500 instead of the order received/thank-you page on 30 September 2026 at ~16:27–16:30 CEST (14:27–14:30 UTC). Customer had already checked WooCommerce logs and File Manager and could not find a historical PHP error log for that request; automated support only offered how to enable PHP error messages going forward. Escalated to 2nd level, who reviewed historical server logs for the exact window and found multiple OOM (out-of-memory) kills of php-cgi-8.3 processes on the account at that timestamp. That explains the partial failure: order creation completed before memory was exhausted, but the thank-you page request was killed mid-execution, so there is no plugin-level PHP stack trace or file in any customer-visible log. Customer was on the Explorer package; 2nd level advised reviewing/optimising the website or upgrading the hosting package for more resources. Key lessons: (1) when a WooCommerce order is created but the thank-you page 500s and no PHP error log exists for that request, suspect OOM kills rather than a plugin fatal error — ask 2nd level for kernel/OOM logs for the exact window. (2) An OOM kill leaves no stack trace, so never promise a plugin-level root cause. (3) Checkout and order-received rendering are memory-intensive; Explorer-level resources can be insufficient for a live WooCommerce store — optimise plugins first, then offer a package upgrade. (4) Enabling PHP error messages helps only for future incidents; historical incidents need a 2nd level log review.

### Case Study 19: SSL Not Secure on External Microsoft Nameservers — ACME Validation Requires 3 DNS Records (Shared with Domain)
- **Ticket Reference:** 19019203 (Shared with Domain)
- **Customer Name:** Carl-Wilhelm
- **Customer Email:** cwjonson@gmail.com
- **Domain:** cwenterprise.se, www.cwenterprise.se
- **Context:** Customer reported www.cwenterprise.se still showing as not secure after the AI assistant suggested an .htaccess HTTPS redirect. Domain was not using one.com nameservers but ns1.bdm.microsoftonline.com etc. A previous supporter had worked on the SSL but it never completed. Escalated to 2nd level (Jerson Complisa Jr) who confirmed www pointed correctly but non-www did not, and required the customer to replace the www A record at their current host with 3 records: A apex to 77.111.240.187, CNAME www to cwenterprise.se.www.service.one.com, CNAME _acme-challenge.cwenterprise.se to cwenterprise.se.acme.service.one.com, then wait for propagation to be checked at their NS host. Customer confirmed the entries in Microsoft DNS and asked to verify ACME and re-activate SSL. DNS checks showed www CNAME and apex A (77.111.240.187) correct, but _acme-challenge CNAME still returned X, blocking issuance — status pending screenshot and propagation with escalation left open. Key lessons: (1) .htaccess redirect cannot fix SSL that cannot issue due to DNS; (2) for external NS verify types separately — apex must be checked as A not CNAME, X for CNAME on apex is expected; (3) in Microsoft DNS use short hostname _acme-challenge to avoid a double-suffix _acme-challenge.cwenterprise.se.cwenterprise.se; (4) confirm propagation at the external host before asking 2nd level to re-trigger SSL.
