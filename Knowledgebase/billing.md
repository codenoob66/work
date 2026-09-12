# Billing Knowledge Base

## General Procedures & Policies

### 1. Refund Verification (Orders Caught in Security Filter)
- **Scenario:** Customer requests a refund for domains or services that were suspended or deactivated because the order was caught in a security filter. Support cannot reactivate or restore the inactive order, account access, or hosting files.
- **Verification Prerequisite:** A refund can only be processed once payment has actually been completed and verified.
- **Invoice vs. Payment Proof:** System-generated invoices or order confirmations are *not* sufficient proof of payment. The customer must provide actual transaction proof from their bank or payment provider.
- **Required Verification Information:**
  - A screenshot of the transaction from their bank or payment account showing: payment date, exact amount, and reference/transaction number.
  - **Credit/Debit Card:** If paid by card, ask for the first 6 and last 4 digits of the card used.
  - **PayPal:** If paid by PayPal, ask for the PayPal transaction ID or a screenshot of the transaction details.
- **Resolution Steps:**
  1. Explain that since the order is inactive due to the security filter, manual payment verification is required.
  2. Politely request the customer to provide a bank transaction screenshot, plus credit card digits or PayPal transaction ID.
  3. Once received and verified, forward the case to the billing department to process the refund.

### 2. Hosting Cancellation & Invoice Disputing
- **Scenario:** Customer wants to cancel hosting services to save costs but wants to retain ownership of the domain. Customer may also request the cancellation of specific extra invoices/fees.
- **Resolution Steps:**
  1. Send the customer a cancellation link.
  2. Instruct them to select only the hosting/other add-on services on the cancellation page, but **not** to select the domain registration itself.
  3. For domains managed directly by third parties (e.g., Punktum.dk for `.dk` domains), clarify that they will retain domain ownership as long as they manage and renew it directly with the external registrar.
  4. Cancel any disputed or agreed fees/invoices in the system.

### 3. Downgrading to Email Plan during Website Migration / Domain Retention
- **Scenario:** Customer wants to migrate their website to another hosting provider but keep using their email service with one.com. Customer needs to know how their billing and plan will change.
- **Key Rules & Requirements:**
  - **Webmail / Email Plan Requirement:** Clarify that to continue using email services after moving the website, they must downgrade to an Email-only hosting plan and retain domain registration with one.com (since email cannot function without domain registration).
  - **Pricing Example:**
    - Hosting plan (Email - 12 months): 53.88 USD
    - Domain registration (varies by TLD, e.g., .in - 12 months): 17.99 USD
    - Total: 71.87 USD (excl. VAT)
  - **Migration & Adjustment:** Instruct the customer to notify support once they initiate the migration so that the services and billing can be adjusted in the system.
  - **cPanel Credentials:** If the customer asks for cPanel admin login details for website migration, guide them to use their registered email as username and request a password reset if needed, explaining that cPanel and Webmail can have different passwords.

### 4. Duplicate Payment and Reference Investigation
- **Scenario:** Customer claims to have paid an invoice twice, or bank statement shows two identical charges.
- **Verification Steps:**
  - Ask the customer to provide both payment confirmations / receipts.
  - Review the payment reference/OCR number on both transactions carefully.
  - Check if they are actually for the same invoice, or if they are for different reference numbers/orders (which might have identical amounts, causing customer confusion).
  - If a reference number (e.g., `46907100`) is not found in internal logs, escalate to the Payments Team with transaction details (date, amount, last 4/6 card digits, or Bankgiro reference).
  - If the double payment is confirmed across different payment methods (e.g., card and bankgiro), ask the customer which of the two transactions they prefer to be refunded before processing.

### 5. Downgrading and Invoice Adjustments during Database or Server Outages
- **Scenario:** Customer attempts to downgrade or cancel a service but is prevented from doing so due to active backend or database server issues on our side. The customer has an outstanding invoice and is concerned about being held liable.
- **Key Rules & Procedures:**
  - **Exempt from Liability:** Since the customer attempted the downgrade or cancellation on time, they must not be held liable for the invoice or any delays caused by our system issues.
  - **Document and Hold Case:** Document the customer's request, assign a reference number for their peace of mind, and hold the case.
  - **Execute and Adjust Invoice:** Once the database or system issue is resolved, manually process the downgrade (e.g., removing website files and databases) and adjust the outstanding invoice to reflect the correct new plan pricing.

### 6. Uberall (Local Listings) Missing Dashboard Options
- **Scenario:** Customer has the Uberall (Local Listings) add-on and wants to add another location listing, but "Add location" or other advanced dashboard options are missing.
- **Root Cause & Diagnosis:** To perform these actions (e.g., Excel Bulk Upload or Google Business Profile sync), the customer's account requires Admin permissions on the Uberall platform. If Admin permissions are not active, the customer cannot see these options.
- **Resolution Steps:**
  1. Do not provide guides (like bulk upload) that assume dashboard options are visible without verifying the user's permissions, as this causes frustration.
  2. Explain clearly that the options are hidden because Admin permissions are required on the Uberall platform.
  3. Offer to cancel the Uberall subscription and process a full refund immediately.
  4. Alternatively, escalate the case to the Technical Team (L2) to check if the user account can be upgraded to Admin, or provide the direct support contacts for Uberall support (Email: `support@uberall.com`, UK Phone: `+44 20 3769 3000`).

### 7. B2B VAT Invoices and Reverse Charge Treatment
- **Scenario:** Customer has registered a corporate VAT number on their account and inquires why their invoice total (e.g., 5.99) does not show a VAT breakdown or itemised VAT charge.
- **Root Cause & Tax Treatment:**
  - When a valid B2B VAT number is registered, transactions are processed under the **Reverse Charge Mechanism** (B2B tax rules).
  - Under these rules, one.com applies **0% VAT**. The customer is responsible for reporting and accounting for both input and output VAT on their own local VAT return.
  - Since the VAT rate applied is 0%, the actual VAT amount charged is 0.00, meaning there is no separate VAT amount to itemise.
- **Resolution Steps:**
  1. Confirm that the customer's registered VAT number is visible on the invoice.
  2. Explain that since they provided a corporate VAT number, the invoice is subject to the **Reverse Charge Mechanism** with **0% VAT** applied.
  3. Clarify that the VAT amount included in the total is 0.00, meaning there is no VAT to itemise, and they must account for the VAT locally.

---

## Specific Case Studies & Ticket Takeaways

### Case Study 1: Domain Order Security Filter and Refund Verification
- **Ticket Reference:** Takeaway 9
- **Customer Name:** Cyrus
- **Customer Email:** cyrusm887@gmail.com
- **Domains Discussed:** `farnost-zlate.cz` and `farnostzlate.cz`
- **Context:** Customer's domain registrations were suspended due to being caught in the security filter. Customer submitted order confirmation/invoice screenshots, which were rejected. Support requested actual bank transaction screenshots and credit card details, and processed the refund once verified.

### Case Study 2: Hosting Cancellation & Domain Retention Inquiry
- **Ticket Reference:** Takeaway 3
- **Customer Name:** www.medical-statistics.dk (Email: `wuchunsen@hotmail.com`)
- **Customer Email:** `wuchunsen@hotmail.com`
- **Domain:** `medical-statistics.dk`
- **Context:** Customer wanted to cancel expensive hosting but keep the domain which was managed with Punktum.dk. Sent cancellation link, instructed to cancel other services (Enthusiast, DNS Admin, PHP_extended Support) but NOT the domain. Cancelled the 69 invoice. Service remains active until August 25, 2026.

### Case Study 3: Website Migration, cPanel Credentials & Downgrading to Email Plan
- **Ticket Reference:** Takeaway 12
- **Customer Name:** Harsh
- **Customer Email:** `harsh@hitechfe.in`
- **Domain:** `hitechfe.in`
- **Context:** Customer migrating to another provider but wanted to retain Webmail. Support provided Email-only plan costing 53.88 USD plus domain registration costing 17.99 USD (total 71.87 USD). Instructed customer to reset cPanel password using registered email, and notify support to change billing once migration is active.

### Case Study 4: Identical Payment Amount Confusion & Reference Verification
- **Ticket Reference:** Takeaway 13
- **Customer Name:** Timi (Timea Gódor)
- **Customer Email:** `info@timeasmassage.se`
- **Domain:** `timeasmassage.se`
- **Context:** Customer reported paying invoice 44299114 twice. Provided receipts showing two identical payments of 2,968.75 SEK. Review of receipts showed one was a card payment on June 13 for reference 46907100, and the other was a Bankgiro payment on June 22 for invoice 44299114. Escalated to the Payments Team, who confirmed the double payment. Since the payments were made via different methods, support asked the customer which of the two payments they prefer to have refunded.

### Case Study 5: Downgrade and Invoice Adjustment during Database Server Outage
- **Ticket Reference:** Takeaway 16
- **Customer Name:** Caroline
- **Customer Email:** `caroline@na-yara.com`
- **Domain:** `kandidatbank.se`
- **Context:** Customer was unable to downgrade `kandidatbank.se` to an email-only plan because the control panel page kept loading due to a database outage. She had an outstanding invoice (`10103336`) and was worried about liability. Support documented the request, provided a reference number (`17534382`), assured her she would not be held liable, and promised a new adjusted invoice. Once the database issues were fixed, support successfully completed the downgrade (removing old web files/database) and adjusted the invoice.

### Case Study 6: Uberall Add-On Missing Options and Admin Permission Requirements
- **Ticket Reference:** Ticket #17790252
- **Customer Name:** Richard
- **Customer Email:** `richardsmugagga@gmail.com`
- **Domain:** `acramfoundation.org`
- **Context:** Customer was extremely frustrated after waiting seven days for an update on why he could not add another location to his Uberall dashboard. An L2 agent sent him standard instructions for bulk uploads/Google Sync, which required clicking a non-existent "Add location" button, causing further anger. Support resolved the issue by apologizing without shifting blame, explaining clearly that the missing options were due to a lack of Admin permissions on the Uberall platform, offering an immediate cancellation and refund, and providing Uberall's direct support contact info (email and UK phone).

### Case Study 7: B2B VAT Invoice Reverse Charge Explanation
- **Ticket Reference:** Live Chat / marcin
- **Customer Name:** marcin
- **Customer Email:** office@mbmagicrepairs.com
- **Domain:** `mbmagicrepairs.com` and `mbropeaccess.com`
- **Context:** Customer asked why his invoices showed his VAT number on the left but did not include any VAT breakdown or itemised VAT details for a 5.99 charge. Support explained that since a valid corporate VAT number was provided, B2B Reverse Charge rules applied, resulting in a 0% VAT rate. Consequently, the VAT charged was 0.00 and no itemisation was required, and the customer must account for the VAT locally.

### Case Study 8: one.com Customer Support Contact Information
- **Ticket Reference:** Takeaway 23
- **Customer Name:** N/A
- **Customer Email:** N/A
- **Domain:** N/A
- **Context:** Internal reference discovery. The one.com customer support phone number was not documented in the knowledge base. Direct phone support is available at `+44 20 8106 0910`, weekdays 10am–2pm UTC. Live chat is available every day of the year and is the quickest contact method. Email support is available via `support@one.com` or through the help center contact form at `https://help.one.com/hc/en-us/requests/new`. Note: The Uberall support number (`+44 20 3769 3000`) is separate and only for Uberall-specific issues.

### Case Study 9: Non-EU Customer Charged VAT Due to Incorrect Billing Country
- **Ticket Reference:** Takeaway 27
- **Customer Name:** Gamal
- **Customer Email:** N/A
- **Domain:** `spmarine.net`
- **Context:** Customer in Egypt received a renewal invoice (SEK 2,705.21) with VAT charges applied. Customer questioned why VAT was being added since they are based in Egypt, not in Europe. The root cause is likely that the billing/contact address country on the account was set to an EU country or not properly updated. one.com, being registered in Sweden, must follow EU VAT rules — customers outside the EU should not be charged VAT. Resolution required the customer to verify and update their billing country to Egypt in the Control Panel. Additionally, the customer reported being unable to reply from the billing page ("BC" page). Key lesson: When a non-EU customer disputes VAT charges, always check the billing country setting in the account first, as this is the most common cause.

### Case Study 10: Late Cancellation with Domain Renewal Fee Only
- **Ticket Reference:** Takeaway 28
- **Customer Name:** Matt Russell
- **Customer Email:** matt@matthewrussell.co.uk
- **Domain:** nimbus123123.com
- **Context:** Customer's domain was scheduled for debt collection (£150.24 + £10 reactivation fee). Customer claimed the domain was only used for testing and wanted to cancel. Support offered a late cancellation, waiving hosting and late/reminder fees, reducing the balance to just the £25.19 domain renewal fee (which goes to the registry, not one.com revenue). Customer agreed, paid the £25.19, and requested written confirmation that no further invoices would be issued. After payment was confirmed, the webspace was deleted in the back-office. Key lesson: When a late cancellation is offered and the customer pays only the domain renewal fee (a pass-through cost to the registry), once payment is received, proceed with deleting the webspace in the back-office. The domain remains registered until expiry but no further invoices are generated.

### Case Study 11: Principal Paid to one.com After Case Already with Intrum
- **Ticket Reference:** Takeaway 30
- **Customer Name:** Naureen Nayyar
- **Customer Email:** N/A
- **Domain:** 2055.se
- **Context:** Customer missed the pre-collection warning (was on holiday) for domain renewal invoice 43779594 (SEK 298.75, order 10081908). She paid the principal to one.com after handover; Intrum case 5441059 still claimed SEK 485.13 (capital 298.75 + interest 6.38 + collection costs 180.00). Reminder fee SEK 100 was paid then fully credited (credit note 44750933); one.com balance for 2055.se was 0. Customer wanted help contacting debt collection, a phone number, and ultimately to cancel. Key lesson: Once a claim is with Intrum, paying the principal to one.com does **not** close the Intrum case. Do not tell the customer there is nothing left with collection if Intrum already holds the case. Correct guidance: principal is settled with one.com; customer must settle the **remaining** Intrum amount (interest + collection costs only — here SEK 186.38), not the full Intrum total and not a second capital payment. Apologise if earlier advice said one.com would cancel Intrum on their behalf. Advise using Intrum bankgiro/OCR/Swish/Mina sidor, note capital already paid to one.com, and contact Intrum if their portal still shows the full amount. Separately: non-payment is not cancellation — offer a cancellation link if they still want to stop auto-renew. Phone support: +44 20 8106 0910 (weekdays 10:00–14:00 UTC).

### Case Study 12: Previous Cancellation Request Not Carried Out — Domain Auto-Renewed and Sent to Debt Collection
- **Ticket Reference:** Takeaway 31
- **Customer Name:** André
- **Customer Email:** andre@frydenlund.biz
- **Domain:** launchify.no
- **Context:** Customer contacted support about an Intrum debt collection invoice (1,284.57 NOK) for launchify.no. He claimed he had previously contacted one.com to cancel all active domains and was told everything would be handled. However, launchify.no was never properly cancelled and auto-renewed in May 2026 with a bundled hosting package the customer says he never knowingly ordered. The original order (May 2025) was only 180 NOK for the first year, so the customer did not notice the hosting add-on at the time. The renewal triggered a significant price increase, which went unpaid and was handed to Intrum. During this chat the domain and hosting were cancelled via cancellation link. Key lesson: When a customer requests cancellation of all domains, every domain on the account must be verified and closed — do not assume the request was carried out without checking. Always confirm the full list of active domains/services with the customer before ending the conversation. Also flag that bundled hosting may not be obvious to customers at checkout; when discussing renewal charges, clarify what each line item is. For the Intrum invoice: once a case is with debt collection, the customer must pay Intrum directly and send proof of payment to one.com for record updates.

### Case Study 13: Order Deletion Blocked by Registered Contact Mismatch
- **Ticket Reference:** Takeaway 33
- **Customer Name:** Kanon
- **Customer Email:** kanon210.com@gmail.com
- **Domain:** ascanva.com
- **Context:** Customer contacted support about a pending domain order for ascanva.com. The order was under review (standard process, up to 24 hours). Customer became impatient and requested a refund. Support initially agreed to delete the order and process the refund, but upon attempting to do so discovered the customer's name was not listed as the registered contact on the account. The deletion and refund could not be processed without authorization from the registered account holder. Resolution: advised the customer to wait the full 24 hours for the order to activate. If still not active after that time, they can follow up. For a refund, the registered account holder would need to contact support directly. Key lesson: Before promising order deletions or refunds, verify that the person contacting support is the registered account holder. If they are not, explain the security requirement upfront rather than after attempting the action — this avoids setting false expectations and having to walk back a commitment.

### Case Study 14: EHF Invoicing for Company-Owned Subscriptions
- **Ticket Reference:** Takeaway 42
- **Customer Name:** Galina Manikova
- **Customer Email:** contact@galina.no
- **Domain:** galina.no, atelier-rambergstranda.no, arthouseramberg.no, fremmedart.no
- **Context:** Customer asked for all future invoices to be issued as EHF to Fremmedart as (org. no. 915752071). Support explained that invoice details depend on the webspace/subscription owner, so the customer must change the relevant subscription owner(s) to the company and then activate e-invoicing per domain using the company's EHF/Peppol ID. E-invoicing applies to future invoices only; the existing invoice remains payable through the available payment methods. The customer had not yet confirmed that the owner changes or EHF activation were completed. Key lesson: For an EHF request covering several domains, clarify that both the company billing identity and e-invoicing settings may need to be completed separately for each subscription, and avoid promising changes have been made until they are verified.
