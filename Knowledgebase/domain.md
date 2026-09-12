# Domain & DNS Knowledge Base

## General Procedures & Policies

### 1. Domain-Specific DNS Access (Guest User)
- **Scenario:** A reseller wants to grant their client DNS administration access (creating and editing records) for a single domain (e.g., `domain.dk`) without giving access to the entire control panel.
- **Key Rules & Requirements:**
  - **Feature Name:** Guest User.
  - **Prerequisite:** Granting DNS management to a guest user is only available with the paid add-on **Domain Protection**.
  - **Trial Policy:** A 1-month free trial can be added as a courtesy.
  - **Auto-Renewal:** Free trial of Domain Protection does not automatically renew and will expire after 1 month.
  - **Data Persistence:** Any DNS records set up during the trial period will remain active and intact after the trial expires.
  - **Access End:** Once the trial expires, the guest user will lose access to edit DNS settings unless Domain Protection is purchased/renewed.
- **Resolution Steps:**
  1. Explain that the "Guest User" feature requires **Domain Protection**.
  2. Guide the customer to the "Guest User" section in their control panel.
  3. Offer a 1-month free trial of Domain Protection as a courtesy, explaining the renewal and access policy.

### 2. Domain Ownership & Control Panel Selection
- **Scenario:** A customer cannot find DNS settings in their one.com control panel for a domain they believe is registered with one.com.
- **Resolution Steps:**
  1. Check WHOIS records first. Often, the domain is registered with an external provider (e.g., GoDaddy).
  2. If the customer has multiple domains, they may simply be looking at the wrong domain in the control panel.
  3. Guide the customer to the domain selection dropdown at the top of the one.com control panel to select their active one.com domain.

### 3. Two Types of Email/Ownership at one.com
- **Registered Email (Subscription/Account Level):**
  - This is the email associated with the one.com subscription or account.
  - It is used for logging into the control panel, receiving invoices, and managing one.com services.
  - Can be updated by the customer directly via **My account > Account settings** in the control panel.
  - Changes apply to all domains under that subscription (or specific ones if linked to multiple accounts).

- **Registrant Email (Domain/Registry Level):**
  - This is the email registered with the domain registry (e.g., ICANN for `.com`, Punktum.dk for `.dk`, Nominet for `.co.uk`).
  - It is used for domain ownership verification, transfer authorization (Auth-ID delivery), and registry-mandated communications.
  - Cannot be updated by the customer directly — requires the **Change Email Form** (PDF) with photo ID to be sent to `support@one.com`.
  - Updating this email in the one.com system does NOT update the subscription/account email, and vice versa.

- **Key Distinction:**
  - Both emails can be the same, but they can also be completely different.
  - A common source of confusion: customers update their contact email in the control panel (subscription level) and assume the registrant email is also updated — it is not.
  - When a customer receives a registry notice about an outdated email, the issue is almost always the **registrant email**, not the subscription email.
  - The registrant email is also where the **Auth-ID** (domain transfer authorization code) is sent when a customer requests to transfer a domain out. If the registrant email is outdated, the customer will not receive the Auth-ID.
  - To check the registrant email: guide the customer to the domain details page in the control panel or use the handover/transfer link `https://www.one.com/admin/handover.do`.

### 4. Domain Owner Change Verification (Company to Company)
- **Scenario:** A customer requests an Owner Change for a company-registered domain.
- **Key Rules & Verification Requirements:**
  - To process an owner change for a company, support must request:
    1. A valid photo ID of the current authorized contact person.
    2. An official company document (e.g., company stamp, letterhead, registry excerpt, or UBO excerpt) confirming the authorized representative.
  - Verify that the documents are valid and that the contact details match the current registration before forwarding to the hostmasters/domain department for final processing.

### 5. Domain Transfer Failure due to Failed Payment
- **Scenario:** A customer is trying to transfer a domain (e.g., from Punktum.dk) to one.com, but the transfer is not proceeding, even if they have an authorization key (transfer key/Auth-ID).
- **Key Rules & Requirements:**
  - **Check Order Logs:** Check the order logs to verify if an order attempt was made and if the payment succeeded.
  - **Failed Payment:** If the payment failed, the transfer cannot proceed automatically.
  - **Resolution Steps:**
    1. Inform the customer that the order attempt was found but the payment failed.
    2. Guide them to submit a new transfer order by going to the homepage, searching for the domain, choosing the transfer option, and completing the payment checkout.
    3. Remind them to enter their authorization code (Auth-ID/transfer key) during or after the checkout to initiate the transfer.

### 6. Domain Order Reactivation (After Refund or Cancellation Request)
- **Scenario:** A customer previously initiated a domain transfer but then requested a cancellation or refund. The transfer order was deleted/cancelled, and hostmasters initially declined reactivation.
- **Key Rules & Requirements:**
  - **Written Consent Requirement:** To reactivate a domain/hosting order that has been cancelled or deleted, the registered contact must send a written request (email) to `support@one.com` stating: "Please proceed with the reactivation for my domain [domain name]".
  - **Verification & Merge:** Once the email is received, support must verify it matches the registered contact email, merge the request into the main chat, and reactivate the order through hostmasters.
- **Resolution Steps:**
  1. Inform the customer that the order was deleted/refunded and hostmasters require explicit written consent.
  2. Ask the customer to send an email from their registered contact address to `support@one.com` requesting reactivation.
  3. Once received and merged, proceed with order reactivation and resume the transfer.

### 7. Registry/ICANN Domain Suspension & Registrant Email Change
- **Scenario:** A domain (especially a `.com` domain) is suspended by the registry due to pending ownership verification, and the customer cannot receive the verification email because the registered email address is outdated or inaccessible.
- **Key Rules & Requirements:**
  - **Suspension Cause:** ICANN/registry requires periodic contact detail verification. If unanswered, the domain is suspended, causing all services (website and email) to stop working.
  - **Identify Registrant Email:** Guide the customer to check the current contact email using the one.com dashboard or the handover/transfer link `https://www.one.com/admin/handover.do` (under domain details) if GDPR policies prevent giving it out.
  - **Contact Email Update Procedure:** If the customer no longer has access to the registered email:
    1. Provide the **Change Email Form** (PDF).
    2. Instruct them to fill it out, selecting "**Domain only**", and sign it (handwritten or digital signatures are accepted).
    3. Request a clear copy of a valid photo ID.
  - **Resolution Steps:**
    1. Once the completed form and valid ID are received, process the change in the system (allow 1-2 hours for processing).
    2. Once updated, a new verification email will be automatically sent by the registry to the new email address.
    3. Instruct the customer to click the verification link in that email to lift the suspension, after which services will resume within a few hours.

### 8. Domain Subscription Cancellation & Termination
- **Scenario:** A customer wishes to cancel their domain subscription to stop auto-renewal, or they want to terminate the service and delete all associated data immediately.
- **Key Distinction:**
  - **Cancellation:** Stops future automatic renewals. The subscription remains active until the end of the current paid period. Data is not immediately deleted.
  - **Termination:** Immediately ends the subscription and deletes all associated files, emails, and databases. This action is irreversible.

- **Resolution Steps (Cancellation via Control Panel):**
  1. Guide the customer to log in to the one.com Control Panel.
  2. Direct them to `My account` → `My products`.
  3. Instruct them to click `Manage` to the right of the relevant domain.
  4. Tell them to click `Cancel`, select the domain/subscription to cancel, and confirm with their Control Panel password.
  5. Inform them they will receive a cancellation confirmation by email, and no new invoices will be generated for that subscription.

- **Resolution Steps (Immediate Termination via Form):**
  1. Provide the customer with the link to the termination form: `https://help.one.com/hc/en-us/articles/7565729769873-Terminate-domain-and-web-space`
  2. Explain the process:
     - Print, fill out, and sign the form.
     - Attach a photo or scan of the signed form.
     - Attach a photo or scan of a valid ID (only full name, date of birth, expiry date, and signature need to be visible).
     - Send both documents as attachments from their registered email address to support.
  3. Clearly state that this action will permanently delete all files, emails, and databases associated with the domain and cannot be undone.
  4. **Alternative for confirmation:** If the customer prefers, they can send the following statement in their email along with the signed form and ID: `"I confirm I understand and accept that all data for [domain name] at one.com will be deleted and the subscription terminated; please proceed with termination and account removal."`

### 9. Subscription Owner vs. Domain Owner (Registrant)
- **Concept & Distinction:** 
  - **Subscription Owner:** The person or entity responsible for the financial and administrative aspects of the hosting account. They pay the subscription fees and invoices, own all files and emails hosted on the web space, and their contact email acts as the username for logging into the one.com Control Panel.
  - **Domain Owner (Registrant):** The legal owner of the domain name itself. They have the sole authority to approve major domain actions, such as transferring the domain to another registrar, changing nameservers, or changing registrant details. Their information is published in WHOIS/RDAP.
- **Key Policies:**
  - In most cases, these are the same, but they can differ (e.g., a web designer managing hosting for a client who owns the domain).
  - Updating the subscription contact email **does not** automatically update the domain owner's email address. They are handled separately in the Control Panel.

### 10. Changing Contact Email Address in the Control Panel
- **Standard Procedure:**
  1. Log in to the [one.com Control Panel](https://login.one.com).
  2. Click **My account** in the top-right corner and select **Account settings**.
  3. If the email is linked to multiple accounts, choose whether to update it for all or specific ones.
  4. Enter the new contact email and click **Update**.
  5. Check the inbox of the **new** email address for a confirmation message with the subject "Change your email address with one.com".
  6. Click the **Change email address** link inside that email to finalize the update.
- **Key Rules:**
  - If domain and subscription have different owners, an **update key** is sent to the *current* registered email address to authorize the change.
  - If the customer lacks access to the current email, they must use the physical **Change Email form**.

### 11. Changing Domain Owner's Contact Details
- **Standard Procedure:**
  1. Log in to the one.com Control Panel.
  2. Go to **My account** > **My products** in the top-right menu.
  3. Click **Manage** for the domain and select **Edit contact details**.
  4. Find the **Domain owner details** section, enter the updated details, and click **Update**.
- **Special Cases:**
  - **gTLDs (.com, .net, .org, etc.):** Changing the email address often triggers a formal "Owner Change" procedure due to ICANN regulations.
  - **Different details:** If subscription and domain details differ, you must click **Request update key** which sends a code to the current domain email. Copy and paste this key into the Control Panel to verify the change.
  - **Inaccessible Email:** If the domain email cannot be accessed, the physical **Domain Owner Form** must be downloaded, signed, and sent with a copy of a valid ID to support.

### 12. Changing Owner of Web Space and Domain (Ownership Change)
- **Standard Procedure (Control Panel):**
  1. **Initiate (Current Owner):** Log in to the Control Panel, go to **My account** > **My products**, and click **Manage** next to the domain.
  2. Select **Change domain owner** (or Change owner of web space, or both) from the menu.
  3. Enter the **new owner's details** (name, email, address).
  4. Copy the on-screen **security code**, check the box to confirm authority, and click **Next**.
  5. Paste the **security code** and click **Next** again to submit.
  6. **Confirm (New Owner):** The new owner receives an email with a link. They must click it, confirm their details, approve the domain registration agreement, and accept the terms of business.
- **Key Rules:**
  - **Fees:** There is usually a fee associated with changing the owner of a web space or domain.
  - **Inaccessible current account:** If the current owner cannot log in or access their email, they must fill out and sign the physical **Domain Owner Form** and send it to support with a copy of their ID.

### 13. Regaining Access & Changing Contact Details when Unable to Log In
- **Scenario:** A customer cannot log in to their Control Panel and needs to update their contact details to regain access.
- **Key Policies & Procedures:**
  - **Forgotten Password (Access to email active):**
    1. Go to the password reset page (`https://login.one.com/recovery`) or refer to the guide [How do I reset my control panel password?](https://help.one.com/hc/en-us/articles/115005592565-How-do-I-reset-my-control-panel-password).
    2. Enter the **domain name** or **registered contact email address** and click **Continue**.
    3. Choose the delivery method for the verification code:
       - **Contact Email:** The primary email address associated with the one.com account.
       - **Recovery Email:** A secondary email address previously added to the account.
       - **Recovery Phone Number:** A mobile number previously added for SMS recovery.
    4. Retrieve the one-time code and enter it on the recovery page, then click **Continue**.
    5. Enter your new password twice and click **Save**.
  - **No Access to Registered Email (Use Change Email Form):**
    1. Support cannot disclose or update contact details directly over phone or chat.
    2. Direct the customer to the online [Change Email form](https://www.one.com/en/support/forms/change-email) (Google Chrome is recommended).
    3. The customer must fill out the details (specifying Subscription, Domain, or both).
    4. They must attach a copy of a valid photo ID and a signed copy of the form.
    5. *Privacy/Safety:* Advise them that they only need to show full name, date of birth, signature, and expiry date. Other sensitive information on the ID can be blacked out.
    6. Send the signed form and ID to the support team for manual verification and processing.

---

## .co.uk TLD Reference

*Source: One.com knowledgebase. Last updated: 3 months ago.*

### Registration
- **Who can register:** Everyone. P.O. Box addresses are **not** permitted.
- **Registrant verification:** Nominet requires accurate registrant name and postal address. If Nominet cannot verify the info, they email the holder to update via Nominet online services. If still unverified, the registrant must send ID (e.g., driving licence and/or utility bill). Domain is **suspended after 30 days** if not resolved, then **deleted after a further 30 days**.

### Transfer In
- **IPS Tag required:** Customer must ask their current provider to change the IPS Tag to **`TJNF-DK`**.
- After the tag is changed, One.com receives automatic notification, updates DNS and billing.
- **Transfer time:** 1–2 working days (Mon–Fri) after the tag is added.
- **If the current provider won't change the tag:** The registrant can change it via [Nominet online services](https://www.nominet.uk) for a fee of **£10 + VAT**.

### Transfer Out
- **Requirements:** The registrant must provide the new provider's IPS Tag.
  - If emailed **from the registered registrant email address**, a message with the domain name, new IPS Tag, and optional new name servers is sufficient.
  - If emailed from **any other address**, the [IPS Tag change form](https://forms.support.one/form/request-to-change-ips-tag.pdf) must be filled out with matching registrant info and signed. Proof of company/organisation is also required (if owner is not private).
- **Transfer time:** Tag changes are usually processed within **24 hours**. Full transfer takes **1–3 working days**. The new provider may require manual approval (handshake); if rejected or not approved within **5 days**, the transfer fails.

### Deletion / Expiration Procedure
| Day | Status |
|-----|--------|
| Day 0 | Expiration date |
| Day 30 | Domain **suspended** (services stop, "Redemption Grace Period") — can still be renewed for a further 60 days |
| Day 90–95 | **Pending Delete Grace Period** — domain can no longer be renewed |
| Drop | Domain becomes available; drop time published daily at [Nominet drop lists](https://registrars.nominet.uk/drop-lists/) |

- .uk domains **cannot** be deleted by One.com — the registrant must use [Nominet Online Services](https://www.nominet.uk).

## Specific Case Studies & Ticket Takeaways

### Case Study: .fi Domain Owner Change and Personal Identity Code (PID) Requirements
- **Context:** A customer submitted a signed owner change form and a driver's license for a `.fi` domain (`oikeustulkit.fi`), but the Personal Identity Code (PID) on the ID was covered by a black bar.
- **Resolution:** The domain operations department requested the new owner's PID because `.fi` domains (managed by Traficom, the Finnish registry) require a valid and visible PID to process owner changes. Support instructed the customer to either provide the PID in text format or submit a new copy of the ID where the field is visible. Once the customer provided the PID in text, a Holder Transfer Key was generated and sent.

### Prices
See the price list or calculator on one.com.

### Domain Status (WHOIS)
| Status | Meaning |
|--------|---------|
| Registered until renewal date | Domain is active and registered |
| No registration status listed | Domain is **reserved** by Nominet |
| Renewal required | Domain is **expired** — registrant has 90 days to reactivate without additional fees |

### Registry & WHOIS
- **Registry:** [Nominet](https://www.nominet.uk)
- .co.uk domains appear in all standard WHOIS databases.

### Owner Change
- Owner changes for .co.uk domains must be done **directly via Nominet**: [https://www.nominet.uk/transferring-your-domain-name/](https://www.nominet.uk/transferring-your-domain-name/)
- One.com only processes the subscription/webspace handover.

---

## Specific Case Studies & Ticket Takeaways

### Case Study 1: Domain Specific DNS Access Inquiry
- **Ticket Reference:** Takeaway 1
- **Customer Name:** Toke (Reseller)
- **Customer Email:** `tkl@icg.dk`
- **Target Domain:** `kiso.dk`
- **Context:** Reseller wanted to grant DNS access to a single domain client. Support activated a 1-month free trial of Domain Protection (normally $9.95 USD/month) to enable the "Guest User" feature. Advised that settings remain active after trial but access ends unless renewed.

### Case Study 2: Domain Ownership & Selection Assistance
- **Ticket Reference:** Takeaway 2
- **Customer Name:** Mohamed
- **Customer Email:** `turathcollegeltd@gmail.com`
- **Domains Discussed:** `turathcollege.com` (registered at GoDaddy) and `turathcollege.co.uk` (registered at one.com)
- **Context:** Customer complained `turathcollege.com` was down and had no DNS option in control panel. Checked WHOIS and showed domain was with GoDaddy. Guided customer to the domain selection dropdown at the top of the control panel to select and manage their active domain, `turathcollege.co.uk`.

### Case Study 3: Domain Owner Change Verification (Company to Company)
- **Ticket Reference:** Takeaway 8
- **Customer Name:** Jinhuang Chen
- **Customer Email:** `frituurpassevite@gmail.com`
- **Domain:** `frituurpassevite.be`
- **Context:** Customer requested owner change from company Passe-Vite to Gui pai BV. Support obtained Chen Jinhuang's photo ID and a Belgian UBO registry excerpt confirming Chen Jinhuang as the authorized representative. Verified and forwarded to hostmasters.

### Case Study 4: Domain Transfer Failure due to Failed Payment
- **Ticket Reference:** Takeaway 13
- **Customer Name:** Vicfaa
- **Customer Email:** N/A (not signed in)
- **Domain:** `goddag.dk`
- **Context:** Customer was unable to transfer domain from Punktum.dk despite providing auth key `OWN-TRANSFER-ce5230639ee6a0b6847e9d3fdf5c84f0`. Log check showed payment failed on the order attempt. Instructed customer to place a new transfer order and checkout/pay on one.com, then enter the auth key.

### Case Study 5: Domain Order Reactivation after Refund Request
- **Ticket Reference:** Takeaway 14
- **Customer Name:** Danielle
- **Customer Email:** `peacebuildersbusiness@gmail.com`
- **Domain:** `peacebuildersunite.com`
- **Context:** Customer's domain transfer order was deleted because she requested a refund. Hostmasters declined automatic reactivation. Support instructed the customer to send an email from her registered email address to `support@one.com` explicitly requesting reactivation. Once received and merged, support reactivated the order and resumed the domain transfer.

### Case Study 6: Registry Domain Suspension and Registrant Email Change
- **Ticket Reference:** Takeaway 16
- **Customer Name:** Caroline
- **Customer Email:** `caroline@na-yara.com`
- **Domain:** `na-yara.com` (suspended) / `kandidatbank.se` (downgraded)
- **Context:** Customer's domain `na-yara.com` was suspended by the registry for pending verification, preventing email from working. The registered contact email was an old, inactive address. Support used the handover link (`https://www.one.com/admin/handover.do`) to let the customer identify the old email, then provided the change-email-form PDF (selecting "Domain only"). Customer submitted the digitally signed form and photo ID, support processed the change, and a new verification email was sent to lift the suspension. Additionally, customer's other domain `kandidatbank.se` was downgraded to email-only and the pending invoice adjusted.

### Case Study 7: .dk Domain Transfer Status Verification
- **Ticket Reference:** Takeaway 17
- **Customer Name:** Kuldip Singh
- **Customer Email:** Kuldipsingh (on platform)
- **Domain:** `upsala.name` (.dk domain, registered directly with Punktum dk)
- **Context:** Customer received one.com promotional email offering free transfer and renewal for .dk domains between 2026-05-22 and 2026-06-22. Customer attempted the transfer but could not confirm whether it completed successfully. The automated virtual assistant responded with general transfer instructions but did not check order logs or account status. Key action for support: check order logs to determine if a transfer order was placed and its current status (pending, failed payment, completed, etc.). If no order exists, guide customer through the transfer process again. If payment failed, refer to Case Study 4 procedure. The deadline for .dk domains to move from Punktum dk to a registrar is June 30, 2028.

### Case Study 8: .dk Domain Registration Failure Due to Missing Punktum dk ID Validation
- **Ticket Reference:** Takeaway 18
- **Customer Name:** Rosemarie Beckman
- **Customer Email:** `rosemarie@samarbetspartnern.se`
- **Domain:** `steel-kamet.dk`
- **Context:** Customer purchased a .dk domain through one.com on February 27, 2025. The order completed successfully, but Punktum dk requires all .dk domain owners to complete a mandatory identity and data validation check directly with them via their self-service portal. Because this validation was not completed within the required timeframe, Punktum dk suspended the domain on March 13, 2025 (log entry: "Failed required ID check. Domain suspended by Punktum dk (with no restore option)"). The domain was subsequently deleted and released back to the open market. Since April 17, 2025, the system has been sending automated "domain is not registered - Action required" emails. Key takeaways: (1) Always check order logs when a customer inquires about an unregistered .dk domain — the registration may have been initiated but failed at the Punktum dk validation step. (2) Punktum dk suspensions due to failed ID checks have **no restore option** — the domain must be re-registered. (3) After re-registration, the customer must be explicitly instructed to log in to the Punktum dk self-service portal (`https://self-service.punktum.dk/`) immediately to complete identity validation to prevent the same issue from recurring. (4) A new registration fee applies for re-registration.

### Case Study 9: .co.uk Domain Registration Failure Due to Customer Type / VAT Mismatch
- **Ticket Reference:** Takeaway 19
- **Customer Name:** Sohail Rehman
- **Customer Email:** (via Rubystone Studio platform account)
- **Domain:** `rubystonestudio.co.uk`
- **Context:** Customer's domain registration request failed because the order was placed with customer type "Association" but company type set to "LTD". One.com requires a valid VAT number for LTD company registrations, and a valid organisation number for association registrations. Since the company is not VAT registered, the simplest resolution was to re-register the domain as a private individual (no VAT or organisation number required). Key takeaways: (1) When a .co.uk domain registration fails, check the customer type and company type combination in the order — mismatches (e.g., Association + LTD) will cause rejection. (2) Private individuals do not need a VAT or organisation number to register a .co.uk domain. (3) Owner change procedure: Control Panel → My account → My products → Manage (next to domain) → Edit contact details → Change domain owner details — enter full name, leave company fields empty. (4) Nominet registrant verification still applies; if the registrant name/address cannot be verified, Nominet will contact the holder and may suspend after 30 days.

### Case Study 10: Domain Cancellation vs. Termination
- **Ticket Reference:** Takeaway from Toomas Kaupmees conversation
- **Customer Name:** Toomas Kaupmees
- **Customer Email:** `funkytoka@gmail.com`
- **Domain:** `guideintallinn.com`
- **Context:** Customer's domain was no longer registered or hosted with one.com, but the subscription was still active and set to auto-renew. The customer was provided with two options: (1) Cancel the subscription via the Control Panel to prevent future renewals, or (2) Use the termination form to have the subscription and all data removed immediately. This case highlights the distinction between a domain's registration status and its billing subscription status.

### Case Study 11: Opting Out of Domain Transfer Reminders
- **Ticket Reference:** WZ0M9
- **Customer Name:** Christian Våge
- **Domain:** `vage.com`
- **Context:** Customer was receiving repeated automated emails encouraging them to transfer their domain to one.com and asked to be opted out. Internal investigation revealed these reminders are part of the "Personal offers" communication track.
- **Resolution:** To stop these specific reminders, go to the customer's Control Panel -> Settings -> Communication preferences and disable the toggle for "Personal offers". This will remove them from that promotional campaign. Inform the customer that this has been done.

### Case Study 12: Disabling Two-Step Verification (2FA) on Migrated GratisDNS Accounts
- **Ticket Reference:** 2FA-GratisDNS-Ownership
- **Customer Name:** Frank Clemen
- **Domain:** `espander.dk`
- **Context:** Customer requested to disable two-step verification (2FA) because they lost access to their registered phone. They submitted the signed disable-form and a copy of their ID. However, the internal Back Office displayed the account owner as "UNKNOWN CUSTOMER" (fclemen), making standard subscriber-to-ID verification impossible.
- **Resolution:** For migrated GratisDNS accounts displaying "UNKNOWN CUSTOMER", support must verify ownership against the domain registrant details (the domain owner) instead of the subscription owner, following historical GratisDNS policy. Since the registrant name and address (Frank Clemen, Roskilde) matched the submitted ID and form, the 2FA removal request was approved and processed.

### Case Study 13: Separate Control Panels and Consolidated .dk Domain Transfer
- **Ticket Reference:** Takeaway from Erik (.dk domains)
- **Customer Name:** Erik
- **Domain:** `visionet.dk` (and `innovadent.dk`)
- **Context:** Customer wanted to transfer two .dk domains from Punktum.dk to one.com and consolidate them under their existing agreement for `innovadent.dk`. Customer got "domain not free" errors when trying to register/transfer them through the public checkout, and couldn't find the .dk transfer banner in their existing active `innovadent.dk` control panel. Analysis showed that `visionet.dk` already had its own separate control panel and subscription set up with us on a different registered email, meaning each domain had its own separate account.
- **Resolution:** Clarified to the customer that since each domain has its own separate control panel and registered contact email, they currently exist as separate accounts (explaining why the transfer banner was missing from the `innovadent.dk` control panel). Offered the option to merge the separate control panels under a single login/profile so they can manage all of them with one login, after which the registrar transfer can be completed using the Auth-IDs from Punktum.dk.

### Case Study 14: DNSSEC Deactivation for Domain Transfer-Out
- **Ticket Reference:** Takeaway 21
- **Customer Name:** Jesse
- **Customer Email:** kazako@aol.com
- **Domain:** customglassmolecules.com
- **Context:** Customer contacted support to unlock their domain `customglassmolecules.com` to transfer it to a different provider. Although the domain was already unlocked on one.com, the transfer was blocked by the new provider due to active DNSSEC. Support directed the customer to log into their control panel and provided the direct link to the DNS settings page (`https://www.one.com/admin/dns.do?route=nameservers`). The customer was instructed to navigate to the DNSSEC section and click "Deactivate". Support informed the customer that DNSSEC deactivation and propagation can take up to 24 hours to complete, after which the transfer would proceed smoothly.

### Case Study 15: Domain Termination Request from Non-Registered Email
- **Ticket Reference:** Takeaway 22
- **Customer Name:** Klein
- **Customer Email:** klein.amoh@herrnhutcorp.com
- **Domain:** olamesbiochar.com
- **Context:** Customer contacted support requesting to completely terminate their domain `olamesbiochar.com`. However, the customer was not contacting from the registered email address associated with the subscription. Support explained that termination cannot proceed without verification from the registered owner. The customer was provided with the termination form (PDF) and informed that the registered owner must fill it out, sign it, and send it to support@one.com along with a copy of a valid picture ID (passport, driver's license, or similar). Key takeaway: Domain termination requests require verification from the registered email address. If the requester is not contacting from the registered email, the termination form and ID verification process must be followed to ensure security and authorization.

### Case Study 16: one.com Customer Support Contact Information
- **Ticket Reference:** Takeaway 23
- **Customer Name:** N/A
- **Customer Email:** N/A
- **Domain:** N/A
- **Context:** Internal reference discovery. The one.com customer support phone number was not documented in the knowledge base. Direct phone support is available at `+44 20 8106 0910`, weekdays 10am–2pm UTC. Live chat is available every day of the year and is the quickest contact method. Email support is available via `support@one.com` or through the help center contact form at `https://help.one.com/hc/en-us/requests/new`. Note: The Uberall support number (`+44 20 3769 3000`) is separate and only for Uberall-specific issues.

### Case Study 17: Web Forward vs Web Alias for Path-Preserving Redirects (Leadpages)
- **Ticket Reference:** Takeaway 26
- **Customer Name:** Elisabeth Andersen
- **Customer Email:** lita_elso@hotmail.com
- **Domain:** helsefysio.no
- **Context:** Customer’s main site was at `www.helsefysio.no` (CNAME to Leadpages) and a landing page lived at path `/bok1` (`www.helsefysio.no/bok1`). Visitors typing `helsefysio.no/bok1` (no www) landed on the homepage because an apex **Web forward** discards the path and only sends users to the target root. Support guided replacing the Web forward with a **Web alias** (empty Hostname → `https://www.helsefysio.no/`) so paths are preserved, and reassured that this only affects bare-domain traffic — the www CNAME/site stays untouched. Customer deleted the Web forward and created the alias correctly; apex `helsefysio.no` then worked, but `/bok1` still dropped to the homepage shortly after change (propagation/cache still in play; follow-up needed). Key lessons: (1) Subfolder paths like `/bok1` are not subdomains — do not treat them as DNS hostnames. (2) Static Web forward often strips paths; Web alias is the usual path-preserving fix for apex → www. (3) Reassure carefully when customers fear “breaking” www — explain www vs bare domain and that only the existing apex redirect is updated. (4) After the change, allow propagation (advised up to ~90 minutes, sometimes longer) and test in a private window; if apex works but a specific path still fails, re-verify alias/forward records, confirm `www.../path` works on the external host (e.g. Leadpages), then consider a true subdomain (e.g. `bok1.helsefysio.no`) if the landing-page platform supports it.

### Case Study 18: Registry Domain Suspension Due to Outdated Registrant Email (Multi-Domain Account)
- **Ticket Reference:** Takeaway 32
- **Customer Name:** Mustafa
- **Customer Email:** onlineboekhoudingzzp@gmail.com
- **Domain:** dimudivloeren.nl (and potentially ~15 other domains on the account)
- **Context:** Customer contacted support after receiving a registry notice that `dimudivloeren.nl` would be suspended on 19-7-2026 due to an unverified registrant email (`k.t*****@******com`). The customer no longer has access to that email — it was closed approximately 6 years ago. The customer’s current contact email (`onlineboekhoudingzzp@gmail.com`) was already updated in the one.com control panel, but the registrant email with the registry remained outdated. Customer was managing ~59 domains and estimated ~15 might have the same issue. Customer was on vacation and unable to process the form immediately, requesting an extension. Support explained the suspension is mandated by the registry (not one.com) and provided the Change Email form (PDF) with instructions to select “Domain only,” sign it, attach a valid photo ID, and send to support@one.com. Support offered to keep the ticket open and work via email. Key lessons: (1) Updating the contact email in the one.com control panel does NOT update the registrant email with the registry — these are separate records. (2) When a customer has many domains, check if multiple domains share the same outdated registrant email — the same form can cover multiple domains. (3) For customers who are on vacation or unable to act immediately, offer to keep the ticket open and communicate via email so they can respond at their convenience. (4) Clarify that registry suspension is different from domain expiry — suspended domains can be restored once verification is completed, while expired domains follow a different reclaim process.

### Case Study 19: Order Deletion Blocked by Registered Contact Mismatch (Shared with Billing)
- **Ticket Reference:** Takeaway 33 (Shared with Billing)
- **Customer Name:** Kanon
- **Customer Email:** kanon210.com@gmail.com
- **Domain:** ascanva.com
- **Context:** Customer contacted support about a pending domain order for ascanva.com. The order was under review (standard process, up to 24 hours). Customer became impatient and requested a refund. Support initially agreed to delete the order and process the refund, but upon attempting discovered the customer’s name was not the registered contact on the account. Deletion and refund could not proceed without the registered account holder’s authorization. Resolution: advised the customer to wait 24 hours; if still not active, follow up. For refund, the registered account holder must contact support directly. Key lesson: Before promising order deletions or refunds, verify that the contacting person is the registered account holder.

### Case Study 20: .UK Domain Ownership Change Must Go Through Nominet
- **Ticket Reference:** Takeaway 34
- **Customer Name:** Belal
- **Customer Email:** belal@zems.org.uk
- **Domain:** zems.org.uk
- **Context:** Customer (Head of IT at Zems Academy Group) contacted support wanting to change the domain registrant/owner from Zeeshan Mirza to Abid Ali for zems.org.uk. The domain was attached to a Guru plan, which prevented ownership changes in the control panel. Support temporarily detached the domain to allow changes, but this did not resolve the issue since the underlying problem was TLD-specific. A Change Domain Ownership form was submitted (initially with both webspace and domain options, later amended to "domain only"), but the domain operations team determined that for .co.uk domains, the registrant change cannot be processed by one.com directly — it must be done through Nominet, the registry for .uk domains. Resolution: Customer was directed to Nominet’s online transfer service (https://www.nominet.uk/transferring-your-domain-name/) where the current registrant initiates the transfer, both parties approve via confirmation emails, and a small fee (£10 + VAT) may apply. The submitted form could still be used for updating subscription/webspace ownership on one.com’s side if needed. Key lessons: (1) For .co.uk (.uk, .org.uk, .me.uk) domains, ownership/registrant changes must go through Nominet — one.com cannot process these directly. Always check TLD-specific requirements before initiating any ownership change process. (2) Detaching a domain from its hosting plan is a valid workaround for control panel-level changes, but it does not address registry-level ownership transfers. (3) When a customer has already submitted forms for an issue that requires a different process, acknowledge the effort and clearly explain what the forms can still be used for vs. what needs to happen separately.

### Case Study 21: Registrant Organization Cannot Be Redacted from WHOIS/RDAP
- **Ticket Reference:** Takeaway 37
- **Customer Name:** Marius
- **Customer Email:** mlanglete@protonmail.com
- **Domain:** peptalitylabs.com
- **Context:** Customer contacted support wanting to transfer peptalitylabs.com, but said they would stay with one.com if the Registrant Organization could be hidden or removed from the public RDAP/WHOIS record. Per one.com’s Domain Registration Data Publication Rules, for gTLDs (.com, .net, etc.) the Registrant Organization is considered non-personal data under NIS2 and is published by legal requirement. It cannot be redacted. The article explicitly states: "We cannot (and will not) redact any of the fields that are published by default." Customer was informed of this limitation. Key lesson: When a customer asks to hide WHOIS/RDAP information, check the Domain Registration Data Publication Rules article — certain fields (Organization, City, State/Province, Country) are mandatory publishes for gTLDs and cannot be removed regardless of customer preference. If the organization field is empty/blank, it won’t display, so clearing it could be a workaround if the customer hasn’t populated it.

### Case Study 22: Attaching Domain to Existing Plan — External Nameservers on Primary Domain Do Not Block Backend Attachment (Shared with Hosting)
- **Ticket Reference:** Takeaway 43 (Shared with Hosting)
- **Customer Name:** Adam
- **Customer Email:** adam@inkwear.co.uk
- **Domain:** inkwear.co.uk (primary, external Cloudflare nameservers), inkwearusa.com (to attach, one.com nameservers)
- **Context:** Customer wanted to attach inkwearusa.com to his existing Enthusiast plan (primary domain inkwear.co.uk) for shared billing and hosting resources. The control panel crashed when trying to add inkwearusa.com because inkwear.co.uk uses external Cloudflare nameservers. However, attaching a domain to an existing plan is a backend billing/subscription operation — it does not require the primary domain to use one.com nameservers. inkwearusa.com was already on one.com nameservers and DNS, so it was fully functional for hosting and WordPress installation independently of the attachment. Key lesson: When a customer with external nameservers on their primary domain cannot add an addon domain through the control panel, this is a known script limitation — the backend attachment can be processed manually by support. Always verify the DNS setup of the domain being attached (not just the primary) to determine whether the customer’s site functionality is actually blocked or just the convenience of the control panel add-on flow.

### Case Study 23: .dk Domain Re-registration After Deletion from Punktum.dk
- **Ticket Reference:** Takeaway 45
- **Customer Name:** Daniel Gallaher
- **Customer Email:** daniel@racetracker.no
- **Domain:** racetracker.dk
- **Context:** Customer contacted support because racetracker.dk showed up in his one.com control panel but had been deleted from his Punktum.dk account (failed to renew properly). The domain showed as available on punktum.dk. Customer could not generate an auth code for a standard transfer since the domain no longer existed under his Punktum.dk account. He initially tried to switch nameservers in the control panel but received the error "Sorry, it is not possible to add custom nameservers for this domain through the Control Panel." Escalated to domain operations (Anders Jørgensen), who confirmed the re-registration procedure should be followed per the internal KB article. Support then contacted the customer to initiate the process: confirm domain fee acceptance, verify contact info in the control panel, and explain the Punktum.dk identity validation requirement. Key lessons: (1) When a .dk domain is deleted from Punktum.dk and shows as available, a standard transfer is not possible — re-registration is required. (2) If an auth code cannot be generated because the domain no longer exists at the losing registrar, do not attempt a transfer; escalate for re-registration. (3) After re-registration of a .dk domain, the customer must complete mandatory identity validation with Punktum.dk via their self-service portal (https://self-service.punktum.dk/) — failure to do so will result in domain suspension with no restore option (see Case Study 8). (4) The nameserver switch error ("not possible to add custom nameservers for this domain") can be a symptom of a domain that exists in the control panel but is not actually registered — check WHOIS to confirm registration status before troubleshooting DNS settings.

