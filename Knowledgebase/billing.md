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
