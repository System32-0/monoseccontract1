<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Selling Collaboration Contract</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        /* Custom scrollbar for better aesthetics */
        .contract-scroll::-webkit-scrollbar {
            width: 8px;
        }
        .contract-scroll::-webkit-scrollbar-track {
            background: #f1f5f9;
            border-radius: 10px;
        }
        .contract-scroll::-webkit-scrollbar-thumb {
            background: #94a3b8;
            border-radius: 10px;
        }
        .contract-scroll::-webkit-scrollbar-thumb:hover {
            background: #64748b;
        }
        h2 {
            font-size: 1.5rem;
            font-weight: 600;
            margin-top: 1.5rem;
            margin-bottom: 0.5rem;
            border-bottom: 1px solid #e2e8f0;
            padding-bottom: 0.5rem;
        }
        h3 {
            font-size: 1.25rem;
            font-weight: 600;
            margin-top: 1.25rem;
            margin-bottom: 0.5rem;
        }
        p, li {
            line-height: 1.6;
            text-align: justify;
        }
        ul {
            list-style-type: none;
            padding-left: 1rem;
        }
        /* Loading Spinner */
        .loader {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #3b82f6;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            margin: 2rem auto;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="bg-slate-100 text-slate-800" oncontextmenu="return false;" onselectstart="return false;">

    <!-- 
        Note on Screen Capture:
        Completely blocking screenshots and screen recordings via a web browser is not technically feasible
        using standard HTML, CSS, or JavaScript. The operating system has ultimate control over screen capture.
        The 'oncontextmenu' and 'onselectstart' attributes on the body tag are added as deterrents 
        to prevent simple right-click saving and text selection.
    -->

    <!-- Header -->
    <header class="bg-white shadow-md sticky top-0 z-20">
        <div class="container mx-auto px-6 py-4 flex justify-between items-center">
            <div class="flex items-center space-x-3">
                <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-slate-600"><path d="M14.5 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7.5L14.5 2z"></path><polyline points="14 2 14 8 20 8"></polyline><line x1="16" y1="13" x2="8" y2="13"></line><line x1="16" y1="17" x2="8" y2="17"></line><line x1="10" y1="9" x2="8" y2="9"></line></svg>
                <h1 class="text-xl md:text-2xl font-bold text-slate-800">Online Selling Collaboration Contract</h1>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto p-4 md:p-8">
        <div class="bg-white p-6 md:p-10 rounded-lg shadow-lg">
            <div class="text-center mb-8">
                <h1 class="text-3xl font-bold text-slate-900">Online Selling Collaboration Contract</h1>
            </div>

            <!-- Contract Scrollable Area -->
            <div id="contract-content" class="h-[70vh] overflow-y-auto contract-scroll pr-4 border border-slate-200 rounded-lg p-6 bg-slate-50">
                <!-- The contract text will be injected here by JavaScript -->
            </div>
        </div>

        <!-- Gemini API Features -->
        <div id="ai-features" class="mt-8 bg-white p-6 md:p-10 rounded-lg shadow-lg">
            <div class="text-center mb-8">
                 <h2 class="text-3xl font-bold text-slate-900 border-b-0 pb-2">Contract Intelligence ✨</h2>
                 <p class="text-slate-500 mt-2">Use AI to better understand this agreement.</p>
            </div>

            <div class="grid md:grid-cols-2 gap-8 max-w-4xl mx-auto">
                <!-- Feature 1: Summarize -->
                <div class="border border-slate-200 rounded-lg p-6 hover:shadow-md transition-shadow">
                    <h3 class="text-xl font-semibold mb-3 text-slate-800">Summarize Contract</h3>
                    <p class="text-slate-600 mb-4">Get a quick, high-level summary of the entire contract.</p>
                    <button id="summarize-btn" class="w-full bg-blue-600 text-white font-bold py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors">
                        ✨ Generate Summary
                    </button>
                </div>

                <!-- Feature 2: Explain Clause -->
                <div class="border border-slate-200 rounded-lg p-6 hover:shadow-md transition-shadow">
                    <h3 class="text-xl font-semibold mb-3 text-slate-800">Explain a Clause</h3>
                    <p class="text-slate-600 mb-4">Enter a clause to get a simple explanation (e.g., "Article 3, Section 1.1").</p>
                    <input type="text" id="clause-input" placeholder="e.g., Article 5, Section 1" class="w-full border-slate-300 rounded-md p-2 mb-3">
                    <button id="explain-btn" class="w-full bg-blue-600 text-white font-bold py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors">
                        ✨ Explain Clause
                    </button>
                </div>
            </div>

            <!-- AI Output Area -->
            <div id="ai-output-container" class="mt-8">
                 <div id="ai-output" class="bg-slate-100 border border-slate-200 rounded-lg p-6 min-h-[100px] whitespace-pre-wrap">
                    <p class="text-slate-500 text-center">AI analysis will appear here.</p>
                 </div>
            </div>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-white mt-8 py-6 border-t border-slate-200">
        <div class="container mx-auto text-center text-slate-500">
            <p>&copy; 2025 Business Collaboration. All Rights Reserved.</p>
            <p class="text-sm mt-1">This document is legally binding upon signature. AI analysis is for informational purposes only.</p>
        </div>
    </footer>

    <script>
        // Full text of the contract
        const contractText = `
This Collaboration Contract Agreement is entered into as of June 19, 2025 (MST), by and between: Party A, Party B, and Party C.

## Definition of Terms:
(a) "Day" means a calendar day unless otherwise specified.
(b) "Majority Decision" means a vote of greater than 50% of the current party members.
(c) "Net Profits" has the meaning given in Article 3, Section 10.
(d) "Material Breach" is defined in Article 6, Section 1.
(e) "IP" means Intellectual Property.
(f) "Publication" means officially putting a product or service on sale.

## Article 1: Purpose
### Section 1: 
The Parties agree to collaborate in selling online products and/or services through various online platforms. Party A will contribute to business leadership and operations management, Party B will contribute creative content and product development, and Party C will contribute financial management and transaction processing. Each party will contribute to the business as described in the articles below.

## Article 2: Roles and Responsibilities
### Section 1: Party A shall be responsible for the following:
(a) Provide overall business direction and strategic leadership
(b) Manage product publication processes and listing coordination with Party C
(c) Handle customer service, marketing, and business operations
(d) Provide all necessary tools, accounts, templates, or systems required for all parties to fulfill their respective roles.
(e) Oversee quality control and product standards
(f) Coordinate with Party C for sales tracking and revenue reporting
(g) Maintain executive authority over business decisions as outlined in Article 13.

### Section 2.1: Party B agrees to:
(a) create original products designs, digital contents, and/or services using platforms as mutually agreed upon for specific project;
(b) submit completed products to Party A for publication and sale;
(c) receive compensation from Party A based on total sales revenue of products containing Party B's work;
(d) adhere to the customized rules and instructions made by Party A, if it adheres to this
(e) submit weekly progress reports detailing work completed, challenges encountered, and estimated completion dates for ongoing projects;
(f) and any additional tasks or responsibilities outside the scope of a specific project, such as assistance with research, marketing, or customer service, shall be mutually agreed upon in writing by both parties and may be subject to additional compensation.

### Section 2.2: Party B shall adhere to specific quality standards for all created products and content, including but not limited to:
(a) originality of design;
(b) adherence to guidelines provided by Party A;

### Section 3: Party C shall be responsible for the following financial execution tasks under Party A's direct supervision and authority. Notwithstanding the foregoing, Party A reserves the unqualified right, at its sole discretion, to directly perform any of these financial management tasks, concurrently with Party C or by assuming full control, at any time and for any reason, prior notice:
(a) Own and operate all online shop(s), marketplace accounts, and e-commerce platforms as directed by Party A;
(b) Execute financial transactions, including payment processing and revenue collection,
(c) Maintain banking relationships, merchant accounts, and payment processor accounts
(d) Process order fulfillment coordination as instructed by Party A;
(e) Track sales and provide financial reporting in formats and schedules specified by Party A;
(f) Calculate and distribute compensation according to Party A's directives and this Agreement's terms;
(g) Maintain financial records as required by Party A and provide statements upon demand;
(h) Execute compliance with financial regulations, tax obligations, and platform requirements under Party A's guidance;
(i) Coordinate with Party A on all business expenses and operational costs, with no independent spending authority.

### Section 4.1: Party B shall adhere to specific, measurable quality standards including:
(a) original design creation;
(b) adherence to written guidelines provided by Party A;
(c) delivery within agreed timeframes;
(d) and technical specifications as outlined in project briefs.
If Party B fails to meet these standards, Party A must provide written notice specifying:
(i) the exact deficiency;
(ii) specific steps required for correction;
(iii) reasonable timeline for correction, with a minimum 2 days for minor issues and 4 days for major revisions;
(iv) and opportunity for Party B to respond and request clarification within 3 days of notice.

### Section 4.2: 
Party A reserves the right to approve, reject, or request revisions on any submitted work based on originality, adherence to guidelines, ethical standards, and quality. Rejection shall be communicated in writing with specific reasons. Upon rejection, Party B shall have a minimum of seven (7) calendar days to revise and resubmit the work. If the revised work still fails to meet standards, Party A may withhold payment for that submission or reassign the task to another Party B member. Any disputes regarding rejection or approval decisions may be subject to Article 13, Section 3.2.

### Section 5: 
All finished works by Party B shall be submitted in a format and through platforms as specified by Party A. Any file not submitted shall be returned or disregarded without obligation.

### Section 6.1: 
Party B must keep backups of submitted work, timestamps, and history as verifiable proof of original authorship. Party A's logs, payment records, and internal communications to of work.

### Section 6.2: 
Party A may request clarification or proof of authorship from Party B. Refusal or failure to provide within seven (7) calendar days may result in payment withholding.

### Section 7: Party C shall adhere to specific financial management standards including:
(a) Accurate and timely processing of all financial transactions;
(b) Maintenance of detailed, auditable financial records;
(c) Prompt distribution of payments according to the schedule outlined in Article 3;
(d) Transparent reporting of all revenue, expenses, and deductions;
(e) Compliance with all applicable financial regulations and platform terms of service;
(f) Secure handling of all financial data and customer payment information;
(g) Coordination with Party A on all business expense approvals over PHP 2,500.

### Section 8: If Party C fails to meet the financial management standards outlined in Section 7, Party A must provide written notice specifying:
(a) The exact financial deficiency or error;
(b) Specific corrective actions required;
(c) Reasonable timeline for correction, with a minimum of 2 days for minor discrepancies and 5 days for major financial issues;
(d) Opportunity for Party C to respond and provide clarification within 3 days of notice. Party C's failure to adequately address financial deficiencies may constitute material breach under Article 6.

## Article 3: Compensation
### Section 1.1: 
Party B shall receive 40% of the net profits from all products they individually created until Party A has recovered a total of $300 in net profits from each Party B member's respective products. Once this individual threshold of $300 has been fully recovered from a Party B member's product sale, that member's share shall increase to 50% for all their future product sales under this Agreement.

### Section 1.2: 
Payment will be made by Party C on a monthly basis, particularly within the last five days of the month, unless otherwise agreed, through Gcash, PayPal, or other secure payment methods that accommodate the available resources of all parties. Late payments owed by Party C shall incur a 5% late fee if delayed beyond 7 days without reasonable, written explanation provided to both Party A and Party B. If Party C provides reasonable, written explanation, then Party C may extend the delay to at most 14 days before any late payment fees shall apply. Late payment fees shall accumulate indefinitely. Party A shall have oversight authority to ensure Party C meets payment obligations.

### Section 1.3: 
Parties agree that 40% means 40.0%, 50% means 50.0%; all calculations shall be rounded to the nearest cent.

### Section 1.4: 
The compensation due to each Party B member shall be calculated individually and separately per product they created or co-created. Net profits from each product shall only be subject to that Party B member's compensation if they directly contributed to its creation. Products made solely by Party A or others outside Party B shall not be included in Party B's compensation. For co-created products involving multiple Party B members, the profit share shall adhere to Article 3, Section 2.1 and/or 2.2, unless a different division is documented in writing and approved by Party A before the product's release.

### Section 1.5: 
Party A shall have the authority to decide the amount of compensation that will be paid to Party B for each month, unless otherwise voted by the majority; however, Party A still has to ensure that all payment owed to Party B shall be paid in full, even if the contract is terminated.

### Section 2.1: 
For products and/or services co-created or co-authored by both parties, the compensation that Party B receives shall depend on the amount of work they individually provide. However, by default, each individual on both parties shall receive an equal percentage of the net income of each service or product sold and shall round up on that Party B's side.

### Section 2.2: 
Providing feedback or insights into a product made by the other party shall not be considered co-ownership or co-authorship.

### Section 3: 
If no sales have been made ninety (90) days after the first product that Party B created has been published, each individual on Party B shall receive PHP1000.00 as compensation. This shall be repeated until the said conditions have been met; however, the compensation amount shall decrease by 50% each time this section is activated. This clause shall not apply more than two (2) times per individual, and the minimum payment shall not fall below PHP 500.00 unless renegotiated in writing.

### Section 4: 
Party A may withhold payment only upon material breach as defined in Article 6, Section 1.1. The withheld amount shall not exceed the reasonable value of non-conforming work. Party A must provide written notice specifying the deficiency and grant Party B at least three (3) days to cure before any withholding takes effect.

### Section 5: 
Party A may withhold payment of any amount due under this agreement if Party B fails to meet the performance milestones or deliverables outlined by Party A. The withheld amount will be paid upon satisfactory completion of the required obligations. Activation of this section shall not affect section 4 of this article.

### Section 6: 
Once Party C has fairly, accurately, and transparently sent the compensation or pay to each of Party B's designated accounts, they shall be deemed to have fulfilled the payment obligations and Party A and Party C shall be released from further liability concerning those payments.

### Section 7.1: Party C shall provide Party B with monthly financial statements including:
(a) Gross sales revenue by product, with clear identification of each Party B member's contributions;
(b) Itemized deductions with supporting documentation (receipts, platform statements, etc.);
(c) Clear calculation methodology showing how each Party B member's compensation was determined;
(d) Bank statements or payment processor statements confirming revenue figures upon request;
(e) Summary report to Party A confirming all payments made and financial obligations met.

### Section 7.2: 
Party B shall have the right to request verification of sales data once per quarter, with reasonable notice to Party A. Reasonable notice shall mean at least five (5) calendar days in advance.

### Section 7.3: 
Party A shall have the right to request verification of Party C's financial management and payment processing at any time with 48 hours written notice. Party C shall provide all requested financial documentation and access to relevant accounts for Party A's review.

### Section 8: 
If Party B's total cumulative earnings from this agreement exceed USD $2,500, Party A may request a renegotiation of the compensation rate. Any reduction in Party B's compensation shall be reasonable, in good faith, and may not fall below 30% of net profits. Party A must provide at least 14 days' written notice with justification, and changes shall be discussed and agreed upon via majority decision, excluding Party A's vote.

### Section 9: 
In the event of a documented financial crisis, defined as a verified 40% or greater decline in total business revenue over a consecutive 30-day, Party A may temporarily reduce Party B's compensation to no lower than 25% of net profits. Such reduction requires:
(a) written documentation of the financial crisis from party A or an independent party;
(b) seven (7) days written notice to Party B with supporting evidence;
(c) good faith consultation with Party B;
(d) and quick restoration to original compensation rates once revenue returns to within 15% of pre-crisis levels for 30 consecutive days.

### Section 10: 
For the purposes of this Agreement, "Net Profits" shall be defined as the gross revenue received by Party A from the sale of products or services created by Party B, less the following specific, documented, and verifiable deductions:
(a) platform fees (e.g., Etsy, Shopify);
(b) payment processing fees (e.g., PayPal, Stripe);
(c) direct advertising and marketing costs associated with the specific products;
(d) costs of returns, refunds, and chargebacks;
(e) payment to Party C;
(f) any other direct costs mutually agreed upon in writing by both parties.
Party A shall provide Party B with a detailed accounting of these deductions on a monthly basis. All deductions must be itemized with supporting receipts. No deduction shall exceed actual documented cost for that line item.

### Section 11.1: 
Party B shall receive an additional 5% bonus from the net profits of any individually created product that achieves a sales milestone of PHP 10,000 or more within 60 days of publication. This bonus shall be paid out with the next regular monthly payment. This bonus is one-time per product per milestone and does not recur for the same product unless a new milestone tier is agreed in writing.

### Section 11.2: 
Party B shall receive an additional 5% bonus from the total net profits of all future products if the cumulative net profits of their products exceed PHP 120,000. This bonus shall apply to all subsequent net profits following the achievement of the threshold and shall be included in the next regular monthly payment cycle. This bonus is ongoing and applies only after the initial PHP 150,000 milestone has been met. Any future adjustments to this threshold or bonus percentage shall require the outlined process under Article 20.

### Section 12: 
In the event Party B disputes any payment calculation, Party A or C shall, within 7 days of receiving the written dispute, provide supporting documentation. Party A shall be copied on all dispute communications and may intervene to resolve the matter. If disagreement remains unresolved, the parties shall engage in mediation as per Article 7. In the event of a tie or abstention by any member, the decision shall default to mediation as defined in Article 7.

### Section 13: Party A or C may deduct up to a maximum of ten percent (10%) from the monthly net profits generated by an individual Party B member's product(s) to fund essential business operating expenses, subject to the following conditions:
(a) The deduction shall be permitted only when reasonably necessary to sustain or operate the business, such as covering critical expenses directly related to sales, marketing platforms, software tools, subscription renewals, or service fees tied to product operations, and must be pre-approved by Party A in writing.
(b) Party A or C must provide a detailed and itemized breakdown of the projected operating expenses to both Party A and Party B at least three (3) calendar days before the deduction is applied. Each deduction must be accompanied by clear and verifiable documentation.
(c) The deduction may not be applied in any month where the individual Party B member's net profit share totals less than PHP 5,000, unless the affected Party B member provides written consent.
(d) Under no circumstance shall this deduction be combined with or used to offset reductions allowed under Article 3, Sections 8 or 9. Deductions shall not exceed 10% of the individual's monthly net profit share, even during financial distress, unless otherwise agreed by all parties in writing.
(e) Party C shall maintain a transparent ledger of all such deductions, available to Party A and Party B members upon request, and subject to review per Article 3, Sections 7.1 and 7.2.
(f) If the total amount deducted for business operations exceeds 100% of the documented and verifiable projected business costs for the upcoming month, the entire surplus shall be refunded proportionally to the affected Party B members in relation to their contributions to the deducted amount. This refund must be issued no later than the end of the following month, and shall be included in the next regular payment.
(g) If cumulative deductions under this section exceed USD $500 per Party B member in a calendar year, continued application shall require majority approval under Article 20, Section 1.

### Section 14: 
In the event that an individual member of Party B is terminated or voluntarily withdraws from this Agreement without material breach or misconduct, they shall be entitled to severance pay equivalent to 10% of the total net profits generated by the products they individually created over the most recent ninety (90) days preceding termination. This severance is subject to the following conditions:
(a) Severance shall not exceed PHP 10,000 unless approved in writing by Party A;
(b) Party A shall issue the payment within fourteen (14) calendar days from final accounting after termination;
(c) No severance shall be paid in cases of termination for material breach as defined in Article 6;
(d) If Party B voluntarily exits with less than 15 days written notice, Party A may reduce the severance by up to 50%.

### Section 15: 
For the purposes of this Agreement, a "Sale" shall be defined as any completed transaction resulting in gross revenue of at least PHP 1.00 received by Party A from the purchase of a product or service that was individually created by a Party B member.

### Section 16: Revenue recognition for Sales shall include:
a) Direct monetary payments received through online platforms, marketplaces, or payment processors
b) Subscription fees, recurring payments, or installment payments attributable to Party B's individual products
c) Licensing agreements, royalty payments, or usage fees generated from Party B's individual creations
d) Refunded or reversed transactions shall not constitute a Sale for compensation calculation purposes.

### Section 17: 
The minimum threshold of PHP 1.00 ensures that nominal or test transactions do not trigger compensation calculations or affect the 90-day no sale compensation clause outlined in Article 3, Section 3.

### Section 18: 
Party B's performance of Services and the timing of all Deliverables under Article 2 shall be scheduled so as not to materially conflict with any Party's school attendance, examinations, or other academic obligations. If either Party's academic schedule changes materially, that Party must provide written notice to the other Party at least seven (7) Calendar Days prior to the intended date of impact, and the Parties shall in good faith adjust Delivery Dates and Milestones accordingly.

### Section 19.1: Notwithstanding any other provision in this Agreement, including but not limited to Article 3, Section 14, Article 5, and any other post-termination benefits, Party A may immediately and unilaterally cease all payments and benefits to a terminated Party B member if that member:
(a) involves, consults with, or discloses confidential information to any third party or independent party regarding this Agreement, business operations, or Party A's proprietary information;
(b) seeks external legal counsel, arbitration, or mediation services without Party A's prior written consent;
(c) discusses the terms, conditions, or circumstances of their termination with parties outside this Agreement.

### Section 19.2: 
This forfeiture provision applies regardless of whether the Party B member was terminated with or without cause, and regardless of any prior entitlements earned under this Agreement.

### Section 19.3: 
Party A's decision to invoke this section shall be final and not subject to the dispute resolution process outlined in Article 7, except for disputes regarding whether the alleged conduct actually occurred.

### Section 19.4: 
This section shall survive termination of this Agreement indefinitely.

### Section 20: 
Party C shall maintain separate business accounts for revenue collection and expense management. Personal funds of Party C shall not be commingled with business funds. Party A shall be designated as a secondary authorized signatory on all business accounts for oversight purposes, with authority to review transactions and approve expenditures exceeding PHP 5,000.

### Section 21: 
In the event Party C becomes unavailable, incapacitated, or fails to perform financial obligations, Party A may assume temporary control of all financial operations and accounts until a replacement is found or Party C's capacity is restored. During such period, Party A shall maintain the same financial standards and reporting requirements outlined in this Article.

### Section 22.1: Party C shall receive compensation for financial management services as follows:
(a) 3% of gross revenue of each product processed through all platforms and payment systems;
(b) This compensation shall be calculated and paid monthly alongside Party B payments;
(c) Party C's compensation is separate from and does not affect Party B's profit-sharing calculations.

### Section 22.2: 
Party C's compensation may be adjusted annually based on business performance and complexity of financial operations, subject to Party A's approval and written agreement from Party C.

### Section 22.3: 
Party C forfeits all right to compensation in any month where material financial errors, unauthorized transactions, or failure to meet reporting deadlines occur, unless such failures are remedied within 7 days of Party A's written notice.

## Article 4: Expenses and Funds
### Section 1: 
Party A and Party C shall be jointly responsible for all expenses related to the business, including but not limited to platform fees, advertising, tools, and account maintenance. Party C shall manage the payment of such expenses, while Party A retains approval authority for expenditures exceeding PHP 2,500. All business expenses shall be documented and reported in the monthly financial statements provided to Party B.

### Section 2.1: 
All compensation and payments under this Agreement shall be calculated based on a fixed exchange rate of One United States Dollar (USD 1.00) to Fifty Philippine Pesos (PHP 50.00). This fixed rate shall be reviewed quarterly. If, at the time of review, the prevailing market exchange rate as determined by a reputable financial institution or central bank average has deviated by more than ±30% from the fixed rate for a continuous period of 60 days, either Party may request a good faith renegotiation of the exchange rate to reflect current market conditions.

### Section 2.2: 
This fixed rate shall apply solely for the purposes of calculation within this agreement, regardless of current market exchange rates.

### Section 3: 
Party C shall be responsible for maintaining accurate records of all business expenses and shall provide itemized expense reports to Party A on a monthly basis. Any unauthorized expenses incurred by Party C without Party A's approval may be deducted from Party C's compensation or result in personal liability for Party C.

## Article 5: Ownership and Intellectual Property
### Section 1: 
All intellectual property, including all copyrights, trademarks, and other proprietary rights in and to the products, designs, and content created by Party B under this Agreement (the 'IP'), shall be co-owned by both parties. However, Party B hereby grants Party A a non-exclusive, revocable, worldwide, royalty-free license to use, reproduce, distribute, display, and create derivative works from the IP for commercial purposes. This license remains valid even after termination; however, this license may be revoked by Party B if Party A fails to pay agreed compensation within 30 days of agreed date, unless a verified, reasonable explanation has been provided, then it shall be increased to 50 days at most. Evocation shall be effective only after written notice and a grace period of 15 days has passed without payment or verified resolution.

### Section 2: 
Party B retains all moral rights to the IP. Party A shall not be obligated to make reasonable efforts to attribute the work to Party B where it is commercially practicable, unless requested upon by Party B in writing. Party B may waive their right to attribution for specific uses upon written request from Party A, provided that such waiver.

### Section 3: 
Pre-existing intellectual property owned by either party prior to this agreement shall remain the sole property of the original owner.

### Section 4: 
Party B retains the right to showcase and sell their original designs independently, provided such use does not indirectly or directly compete with Party A's specific branded platform or violate confidentiality.

### Section 5: 
Party A may not, under any circumstances, modify Party B's products in a way that harms their reputation without written consent.

## Article 6: Term and Termination
### Section 1.1: 
Any party may terminate this agreement with 30 days written notice if any of the parties materially breaches any provision of this contract and fails to cure the breach within the notice period. Material breach shall include, but is not limited to:
(a) repeated failure to deliver products meeting agreed quality standards in a timely manner;
(b) failure to make timely payments without providing valid reasons;
(c) unauthorized disclosure of confidential information;
(d) violation of intellectual property rights;
(e) failure by Party A or C to maintain accurate financial records or fulfill payment obligations;
(f) unauthorized use of business funds by Party A or C for personal purposes.

### Section 1.2: 
Party A shall have the authority to review the material breach committed by either Party and open a discussion and an election for the majority on both parties combined to decide on the best, appropriate approach to handle said matter.

### Section 1.3: 
Either party may terminate this Agreement without cause by providing thirty (30) days' written notice. Final accounting and payment shall be completed within fifteen (15) days of termination date.

### Section 1.4: 
Upon termination of Party B's contract or at any time during the termination processing period, Party A shall have the authority to remove Party B's access to all tools, software, and/or platforms used by them under this agreement.

### Section 2.1: 
Upon termination of this Agreement, Party B waives any and all future claims to earnings, loyalties, or control over the product and/or services that were purchased, created, and published under this collaboration. Notwithstanding Article 3, Section 1.5, this waiver shall become effective automatically upon the effective date of termination, and absolute ownership of the aforementioned items, including all associated intellectual property rights under Article 5, shall be immediately and solely given to Party A, irrespective of any outstanding, pending, or disputed payments. Party B expressly agrees that such waiver and immediate transfer of all rights constitute full and complete consideration for the termination and all prior contributions.

### Section 2.2: 
Party B shall deliver all works-in-progress, source files, and related materials to Party A within 10 days.

### Section 2.3: 
Party A shall make final payment for completed work within 14 days of termination, subject to verification of work quality.

### Section 2.4: 
All products, services, and tools purchased by Party A during the term of this agreement shall solely be his and must be returned to him within seven (7) days of termination, unless agreed otherwise.

### Section 2.5: 
Upon termination of Party C's contract, Party A shall have the authority to assume or assign a different party immediate control of all business accounts, financial records, and payment processing systems. Party C shall provide all necessary account information, passwords, and transfer procedures within 48 hours of termination notice.

### Section 3: 
In the event that Party B commits multiple breaches of this Agreement, Party A shall provide written notice detailing each breach and the cumulative impact. Party A may then, after good faith consultation with Party B, implement appropriate and proportionate consequences as outlined in this Agreement, including but not limited to, temporary suspension of work, reduction in compensation, or termination of this Agreement in accordance with Article 6. Any dispute regarding the proportionality or justification of such actions shall be subject to the dispute resolution process outlined in Article 7.

### Section 4: 
Termination of this agreement shall only affect the target individual(s) on either party provided that the grounds for termination are directly attributable to the individual in question, and a written rationale is given, unless however, both parties unanimously agree to fully terminate this agreement.

### Section 5: 
For a period of nine (9) months after termination, neither party shall knowingly solicit or recruit the other's clients, collaborators, or active team members without prior written consent.

### Section 6: 
Any termination of individual Party B members must be preceded by a 2-day written notice period during which the affected party may request mediation under Article 7. Termination decisions affecting profitable products (those generating over $200 in monthly revenue) require additional justification documenting specific contract violations or performance failures.

### Section 7.1: 
In the event of the death or permanent incapacity of a Party B member, this Agreement shall automatically terminate with respect to that Party B member thirty (30) days after Party A receives written notice of such event.

### Section 7.2: 
For purposes of this Section, "permanent incapacity" means a physical or mental condition that renders the Party B member unable to perform their obligations under this Agreement for a period of thirty-five (35) consecutive days or sixty (60) days in any twelve (12) month period, as certified by a licensed physician.

### Section 7.3: 
Upon termination due to death or permanent incapacity, Party A shall retain all rights to continue selling and marketing the products created by the deceased or incapacitated Party B member in accordance with Article 5.

### Section 7.4: 
Each Party B member shall designate in writing one or more beneficiaries to receive any payments due under this Section in the event of their death or permanent incapacity. In the absence of such designation, payments shall be made to the Party B member's estate or legal guardian.

### Section 7.5: 
The termination of this Agreement with respect to one Party B member shall not affect the rights and obligations of Party A and the remaining Party B members.

### Section 8: 
Should disputes arise under this Article, either party may invoke Article 7, as necessary.

### Section 9.1: 
In the event of the death or permanent incapacity of Party C, this Agreement shall continue with Party A assuming all financial management responsibilities until a suitable replacement is appointed.

### Section 9.2: 
Party C shall designate one or more authorized representatives who may access business accounts and financial systems in case of emergency. Such designation must be approved by Party A and updated annually.

### Section 9.3: 
All business accounts and financial systems shall have Party A as a secondary authorized user to ensure continuity of operations, if possible.

### Section 10: 
Party A may terminate Party C's participation in this Agreement immediately and without cause by providing written notice. Upon such termination, Party C forfeits all rights to compensation for the month in which termination occurs and must immediately transfer all financial systems, accounts, and records to Party A or designated replacement within twenty-four (24) hours. Party C shall be entitled to a severance pay equivalent to 5% of the total sales revenue of the most recent seventy (70) days.

### Section 10.1: 
In the event of the death or permanent incapacity of Party A, this entire Agreement shall immediately terminate without further action from any party. For purposes of this Section, "permanent incapacity" shall mean a physical or mental condition rendering Party A unable to perform their obligations under this Agreement for a period of sixty (60) consecutive days or ninety (90) days in any twelve (12) month period.

### Section 10.2: 
Upon such termination due to Party A's death or permanent incapacity, all current and future pay, including any profit share, accumulated earnings, or uncollected compensation otherwise due to Party B members under this Agreement, shall be immediately voided and forfeited. Furthermore, all rights to severance pay or any post-termination compensation for Party B members shall also be voided, notwithstanding any other provision in this Agreement.

### Section 10.3: 
All current and future pay, profits, and revenue generated from the business operations, products, and services established or derived under this Agreement shall belong solely to Party A's estate or their designated family beneficiaries. Party B shall have no further claim to any income, royalties, or profits from products or services created or co-created under this Agreement upon the activation of this Section.

### Section 10.4: 
Notwithstanding Article 5, Section 1, upon termination due to Party A's death or permanent incapacity, all intellectual property rights, including copyrights and licenses to use products, designs, and content created by Party B under this Agreement, shall immediately and irrevocably transfer solely to Party A's estate or designated family beneficiaries. Party B's revocable license under Article 5, Section 1, shall be deemed immediately non-revocable and fully assigned to Party A's estate, irrespective of any outstanding or voided compensation. Party B shall assist in all necessary transfers of ownership documentation.

## Article 7: Dispute Resolution
### Section 1: 
In the event of any dispute, claim, question, or disagreement arising from or relating to this Agreement or the breach thereof, the parties shall use their best efforts to settle the dispute, claim, question, or disagreement. To this effect, they shall consult and negotiate with each other in good faith and, recognizing their mutual interests, attempt to reach a just and equitable solution satisfactory to both parties.

### Section 2: 
If the parties do not reach such a solution within a period of forty (40) days, then, upon notice by either party to the other, all disputes, claims, questions, or differences shall be submitted to mediation administered by an independent party agreed upon by both sides.

### Section 3: 
In case of deadlock on governance decisions, dispute resolution under this Article 7 shall apply.

## Article 8: Confidentiality
### Section 1.1: 
All details regarding this contract and the operations conduct shall be strictly confidential. Any breach of confidentiality by Party B or Party C shall immediately result in Termination; however, the affected party may still challenge such decisions by evoking Article 13, Section 3.2.

### Section 1.2: 
Involvement of third-parties that arise from this termination shall result in absolute termination of agreement of affected Party B without further consideration.

### Section 1.3: Party B's and Party C's confidentiality obligations extend to:
(a) all business strategies, financial information, and operational methods;
(b) customer lists, supplier relationships, and marketing strategies;
(c) product development plans and unreleased designs;
(d) internal communications, disputes, and management decisions;
(e) the identity and contact information of other party members;
(f) banking information, account details, and financial transaction records;
(g) payment processing systems and merchant account information.

### Section 1.4: 
These obligations remain in effect for an indefinite period.

### Section 1.5: 
Party A shall have the exclusive and unilateral authority to determine whether to disclose the identity, contact information, or signature documentation of any party member to other parties under this Agreement. Party A may, at its sole discretion, maintain the confidentiality of party member identities and is under no obligation to facilitate direct communication or reveal personal information between Party B and Party C members, regardless of their shared participation in this Agreement. This authority extends to all current and future party members and shall survive termination of this Agreement.

## Article 9: Limitation Of Liability
### Section 1: 
Neither party shall be held liable for any indirect, incidental, or consequential damages resulting from this agreement, unless caused by intentional misconduct or gross negligence.

## Article 10: Severability
### Section 1: 
If any provision of this Agreement is held to be invalid, illegal, or unenforceable by a court of competent jurisdiction, such provision shall be severed from this Agreement, and the remaining provisions shall remain in full force and effect. The Parties agree to negotiate in good faith to replace any invalid, illegal, or unenforceable provision with a valid, legal, and enforceable provision that most closely achieves the original intent of the Parties.

## Article 11: Force Majeure
### Section 1: 
Neither Party shall be liable for any failure or delay in performing its obligations under this Agreement if such failure or delay is caused by circumstances beyond its reasonable control, including, but not limited to, acts of God, war, terrorism, riots, embargoes, acts of civil or military authorities, fire, floods, accidents, epidemics, pandemics, or strikes.

### Section 2: 
The Party affected by a Force Majeure Event shall promptly notify the other Party in writing of the occurrence of such event, its anticipated duration, and the extent to which it will affect its ability to perform its obligations. Such notification shall be given within seven (7) business days of the commencement of the Force Majeure Event.

### Section 3: 
The Party affected by a Force Majeure Event shall use all reasonable efforts to mitigate the effects of the Force Majeure Event and to resume performance of its obligations under this Agreement as soon as reasonably practicable.

### Section 4: 
If a Force Majeure Event continues for a period exceeding sixty (60) days, either Party may terminate this Agreement upon written notice to the other Party, without further liability, except for obligations accrued prior to the termination.

## Article 12: Ethics
### Section 1: 
All products and services created under this collaboration shall be strictly original. If an individual from either party is found to have misrepresented or stolen another's work, they shall immediately forfeit all rights to that work, including compensation, and may be subject to contract suspension or termination. Before forfeiture is enforced, the accused individual shall be given at least three (3) days to respond and present evidence in their defense.

### Section 2: 
Topics or themes must avoid content that promotes hate, violence, harassment, misinformation, or material deemed highly political, sexual, or religiously offensive, unless both parties explicitly agree in writing and such content aligns with platform policies and applicable laws.

### Section 3.1: 
Party A may, at its sole discretion, waive any breach or misconduct by Party B that is reasonable in nature and not severe in impact, including but not limited to minor delays, quality issues that can be readily corrected, or procedural oversights.

### Section 3.2: 
Any waiver under this Section shall be communicated in writing to Party B and shall specify the conduct being waived and whether such waiver applies to future similar conduct.

### Section 3.3: 
This waiver authority shall not extend to material breaches as defined in Article 6, Section 1, theft or misappropriation of funds or intellectual property, violations of confidentiality obligations, or any conduct that violates applicable laws or ethical standards.

### Section 3.4: 
Party A's exercise or non-exercise of waiver authority under this Section shall not constitute a waiver of the right to enforce the same or similar provisions in the future, unless explicitly stated in writing.

## Article 13: Governance
### Section 1: 
Party A shall be declared as the Founder and CEO of any businesses or contracts that arise from this agreement. He shall also be the Executive Contract Enforcer and the Head of Ethics. Party C shall serve as the Chief Financial Officer under Party A's authority and supervision.

### Section 2: 
The CEO shall hold the primary executive authority. Final decisions by the CEO which materially impact profit distribution, intellectual property, or termination must be disclosed in writing and may be challenged under Section 3.2 of this Article. Any such decision shall only take effect after a five (5) day notice period during which Party B may request mediation. They shall be responsible for the following:
(a) making final business decisions;
(b) overseeing all operations;
(c) managing finances and profits, setting goals, rules, and direction;
(d) rejecting products and services made by Party B that do not meet personal or provided standards;
(e) final decision-making authority after good faith consultation with Party B;
(f) and represent the business publicly.

### Section 2.1: 
The Chief Financial Officer (Party C) shall hold primary responsibility for financial operations under the CEO's oversight. Party C shall be responsible for:
(a) managing all financial transactions and payment processing;
(b) maintaining accurate financial records and reporting;
(c) ensuring compliance with financial regulations and platform requirements;
(d) coordinating with the CEO on budget approvals and expense management;
(e) providing transparent financial reporting to all parties;
(f) implementing financial controls and security measures.

### Section 2.2: 
Unless otherwise expressly directed by Party A, Party C shall serve as the primary public representative and external face of the business established under this Agreement. This provision directly supersedes Article 13, Section 2(f) of this Agreement solely to the extent that it assigns the primary public representation role from Party A to Party C.

### Section 2.3: 
In this capacity, Party C shall be responsible for the following tasks related to public representation, always in coordination with Party A's strategic direction:
(a) Managing public relations and external communications with customers, partners, and the general public.
(b) Representing the business at public events, online forums, and media engagements as approved by Party A.
(c) Disseminating approved public statements and marketing messages.
(d) Handling customer inquiries and feedback that require public-facing responses.

### Section 2.4: 
Party C's responsibilities under this Section 2.2 are strictly subject to Party A's executive authority and strategic direction, as broadly outlined in Article 13, Section 2. Party A retains the unqualified right to assume direct control over any public representation or external communication at any time and for any reason, without prior notice. All public statements, marketing messages, and significant external communications by Party C must receive prior approval from Party A, unless Party A has provided general guidelines or delegated specific authority in writing. Party C's actions in this public representation role shall not be construed as granting independent decision-making authority regarding business operations or strategic planning, consistent with Article 13, Sections 14 and 16.

### Section 3.1: 
The Executive Contract Officer shall interpret and enforce contract terms using standard legal interpretation principles. Contract disputes shall be resolved through human judgment and, when necessary, professional legal consultation or the dispute resolution process outlined in Article 7. AI tools may be consulted for informational purposes only, but their outputs carry no binding authority. Their responsibilities include the following:
(a) enforcing deadlines, payment rules, and content quality;
(b) handling violations and disputes;
(c) issuing warning or consequences for breaches;
(d) making judgement calls in areas vaguely defined in this contract;
(e) and rejecting products and services made by Party B that do not meet ethical standards.

### Section 3.2: 
Party B retains the right to challenge any decision made by Party A under this Agreement if Party B believes such decision is inconsistent with the express terms of this Agreement. Any such challenge must be submitted in writing to Party A within five days of the decision, clearly stating the basis for the challenge and referencing the specific contractual terms allegedly violated. The parties shall then engage in good faith negotiation, as outlined in Article 7, Section 1, to resolve the challenge. If unresolved, the dispute resolution process outlined in Article 7 shall apply.

### Section 4: 
The Head of Ethics shall be responsible for ensuring that everyone behaves professionally and fairly, as they and the contract deem necessary. They shall set up and uphold the Parties' moral or ethical standards. Their responsibilities include the following:
(a) deciding what is right and wrong;
(b) ensuring fairness and integrity;
(c) protecting parties from being exploited;
(d) mediating professional behaviors between the parties.

### Section 5: 
Regardless of authority and position, all parties to this agreement shall strictly adhere to the provisions of this agreement.

### Section 6: 
In the event of a conflict between this Article and other provisions, the specific clause more favorable to mutual fairness and legality shall prevail. If ambiguity remains, Article 7 shall apply.

### Section 7: 
If Party A makes a decision that affects their own financial benefit directly or indirectly, including but not limited to changes in profit distribution, personal bonuses, or investment redirection, such decisions must be reviewed and approved by either:
(a) an independent third party agreed upon by both parties,
(b) or a majority vote of all Party B members.

### Section 8: 
No waiver of any term or condition of this Agreement shall be deemed a continuing waiver or a waiver of any other term or condition, unless agreed upon in writing.

### Section 9: 
Any provisions of this Agreement which by their nature are intended to survive termination, including but not limited to those relating to confidentiality, IP rights, and dispute resolution, shall survive the termination of this Agreement.

### Section 10: 
Notwithstanding any other provision in this Agreement, all major business decisions affecting either Party's compensation or contract rights must be approved by a majority vote of all parties. Major decisions include but are not limited to:
(a) changes to compensation structure;
(b) business restructuring affecting Party B's rights;
(c) amendments to this Agreement.
Party A's role as CEO does not override this democratic decision-making requirement for matters materially affecting Party B's interests.

### Section 11: 
Party A may grant member(s) of Party B with authority higher than the others. Party A shall not be obligated to disclose such decision(s) to anyone.

### Section 12: 
Party B shall have no authority to demote or inhibit Party A's position or authority under this Agreement, unless otherwise agreed by Party A in writing.

### Section 13.1: Party B members have no right to:
(a) access Party A's financial records beyond what is required under Article 3, Section 7;
(b) make decisions regarding business direction, partnerships, or strategic planning;
(c) form coalitions or unions.

### Section 16: 
Party C shall have no independent decision-making authority regarding business operations, strategic planning, or financial policies. All actions by Party C must be explicitly authorized by Party A in writing or pursuant to routine operational procedures established by Party A. Party C may not enter into agreements, authorize expenditures, or make representations on behalf of the business without Party A's prior written consent. Party C's role is strictly limited to execution of financial tasks under Party A's supervision and direction.

## Article 14: Independent Contractor Relationship
### Section 1: 
Party B is an independent contractor and not an employee, agent, partner, or joint venturer of Party A. This Agreement does not create an employer-employee relationship between the Parties.

### Section 2: 
Party B shall have control over means and methods of work, subject only to quality standards and deadlines.

### Section 3: 
Party B and Party C are each solely responsible for all taxes, social security contributions, unemployment insurance, workers' compensation, and any other employment-related contributions or benefits arising from the compensation paid to them under this Agreement. Party A shall not withhold any taxes or contributions from payments made to Party B or Party C. Party B and Party C may consult their own tax advisors for compliance. Party C shall provide transaction records to Party B if requested for filing purposes, and Party A shall provide transaction records for filing purposes.

### Section 4: 
Party B is free to perform services for other clients, provided such services do not conflict with obligations under this Agreement or involve the use or disclosure of Party A's confidential information.

### Section 5: 
Party B is not entitled to any employee benefits, including but not limited to health insurance, retirement plans, paid time off, or severance pay, from Party A.

### Section 6: To maintain independent contractor status while ensuring quality deliverables:
(a) Party A may establish specific quality standards, deadlines, and deliverable requirements but shall not control the specific methods, tools, or daily schedule by which Party B completes work;
(b) Party A retains the right to review, approve, or reject deliverables based on predetermined quality criteria and may require revisions to meet agreed-upon standards;
(c) Party A may conduct periodic progress reviews focused on milestone achievement and deliverable quality.
(d) Party B retains the right to work for other clients without restriction, provided no confidential information is disclosed;
(e) and both parties acknowledge this relationship is results-oriented project-based collaboration, not employment.

## Article 15: Indemnification
### Section 1: Party B and Party C shall each indemnify, defend, and hold harmless Party A, its officers, directors, employees, and agents from and against any and all claims, demands, losses, damages, liabilities, costs, and expenses (including reasonable attorneys' fees) arising out of or in connection with:
(a) Any breach by Party B or Party C of any representation, warranty, or covenant contained in this Agreement;
(b) Any act or omission by Party B or Party C, their employees, or agents, including negligence or willful misconduct, in the performance of services under this Agreement;
(c) Any claim that the intellectual property or content created by Party B infringes upon or violates the intellectual property rights or other rights of any third party;
(d) Any misrepresentation or inaccuracy in the information provided by Party B or Party C;
(e) Any financial mismanagement, unauthorized transactions, or breach of fiduciary duty by Party C.

### Section 2: Party A shall indemnify, defend, and hold harmless Party B and Party C from and against any and all claims, demands, losses, damages, liabilities, costs, and expenses (including reasonable attorneys' fees) arising out of or in connection with:
(a) any breach by Party A of representations, warranties, or covenants in this Agreement;
(b) any misuse of Party B's intellectual property beyond the scope of the license granted;
(c) any failure by Party A to comply with platform terms of service or applicable laws in marketing or selling Party B's products;
(d) any claims arising from Party A's business operations unrelated to Party B's or Party C's specific contributions;
(e) unauthorized business decisions made by Party A that result in financial liability.

### Section 3: Party C shall additionally indemnify, defend, and hold harmless Party A and Party B from and against any claims arising from:
(a) errors in financial reporting or payment processing;
(b) unauthorized access to or misuse of financial accounts;
(c) failure to comply with payment processor terms or banking regulations;
(d) any data breaches involving customer financial information under Party C's control.

## Article 16: Entire Agreement
### Section 1: 
This Agreement, including any Exhibits or Schedules attached hereto, constitutes the entire agreement between the Parties with respect to the subject matter hereof and supersedes all prior and contemporaneous agreements, understandings, negotiations, and discussions, whether oral or written, of the Parties. No modification, amendment, or waiver of any provision of this Agreement shall be effective unless in writing and signed by both Parties or voted by the majority.

## Article 17: Governing Law
### Section 1: 
This Agreement shall be governed by laws determined in this Agreement or as specified and agreed upon by both Parties in writing.

## Article 18: Notice Delivery
### Section 1: All notices shall be delivered via email and registered mail. Notices are considered delivered:
(a) upon email delivery confirmation;
(b) or three (3) business days after postal mailing.

## Article 19: Additional Signatories and Joinder
### Section 1: Any individual who wishes to join this Agreement as a new member of Party B after its execution may do so by submitting the following to Party A:
(a) a screenshot or digital image of their signature, and
(b) an express written confirmation (via email or text message) of their intent to be bound by all terms and conditions of this Agreement, without modification.

### Section 2: 
Party A shall maintain complete discretion over the disclosure of signatory information, including names, signatures, and contact details of all party members. Party A may choose to provide, withhold, or selectively disclose such information to any party member for any reason or no reason at all. No party member has the right to access information about other signatories unless explicitly authorized by Party A in writing.

### Section 3: 
The inclusion of the new signatory shall be disclosed in writing to Party B within five (5) calendar days. Any objections must be raised within seven (7) days of such notice, after which the addition shall be considered final and binding.

### Section 4: 
All such newly added individuals shall be equally subject to all obligations, rights, and responsibilities as stated for Party B members in this Agreement.

### Section 5: 
Party A shall maintain a record of all added signatories, their consent communications, and timestamped signature submissions for accountability and future reference.

## Article 20: Amendments
### Section 1: 
Any amendment requires majority approval of Party A and B either in writing or using transparent, fair, and accurate voting poll.

### Section 2: 
Both Parties shall ensure that all changes made in this contract does not violate any laws in the United States of America and the Philippines.

### Section 3: 
Notwithstanding any other provision, no Party may unilaterally amend any term of this Agreement that materially affects the rights or obligations of Party B without the prior written consent of Party B. Any proposed amendment shall be circulated in tracked-change format at three (3) days before the effective date and shall only take effect upon execution by both Parties in writing.

## Article 21: Clause Interpretation and Priority
### Section 1: 
In the event of a conflict or ambiguity between two or more provisions in this Agreement, the clause that best promotes mutual fairness, good faith, and legality under applicable law shall prevail. If ambiguity remains, resolution shall follow Article 7.

### Section 2: If a dispute arises regarding the meaning or scope of any clause, the following order shall be used to interpret the provision:
(a) The express written terms of this Agreement;
(b) Relevant definitions and precedent within this document;
(c) Reasonable commercial standards and industry practices;
(d) Supplementary interpretation using AI tools (e.g., ChatGPT, Perplexity.ai) for advisory purposes;
(e) Final authority remains with human arbitration or mediation under Article 7.

## Article 22: Extended Leave for Party B Members
### Section 1: A Party B member may request a temporary suspension of obligations for up to thirty (30) consecutive calendar days due to serious personal circumstances (including but not limited to health issues, family emergencies, or other verifiable personal crises), subject to the following:
(a) The member must submit a written request to Party A with reliable, third-party documentation (e.g., medical certificates, legal affidavits, or government-issued records) verifying the necessity of leave.
(b) Party A reserves the right to audit the evidence through a mutually agreed-upon independent verifier at the requesting member's expense.
(c) Party A may temporarily reassign the member's responsibilities to other Party B members or coordinate with Party C for alternative fulfillment arrangements without penalty.

### Section 2: Activation and Limitations
(a) This provision may be invoked no more than once per individual Party B member within any ninety (90)-day period.
(b) Leave automatically terminates upon the member's submission of any deliverable under Article 2, regardless of remaining days.
(c) Unused leave days expire upon return to work and do not accumulate.

### Section 3: Operational Adjustments
(a) During leave, the member is relieved of all deliverables and deadlines under Article 2.
(b) Compensation for pre-leave work (e.g., royalties from existing product sales under Article 3) continues unaffected.
(c) Party A may temporarily reassign the member's responsibilities to other Party B members without penalty.

### Section 4: 
Party A may not terminate this agreement solely due to a member's use of this leave provision, provided all evidence and notice requirements are satisfied.

### Section 5: 
Party B shall provide at least five (5) business days' advance written notice to Party A prior to the commencement of leave, except in cases of emergency, in which case notice shall be given as soon as reasonably practicable.

### Section 6: 
Party B may, with Party A's written consent, utilize leave on a non-consecutive or part-time basis, provided the total leave taken does not exceed thirty (30) days within the ninety (90)-day period.

### Section 7: 
Party B shall provide a written status update to Party A at least once every ten (10) days during the leave period, confirming ongoing eligibility or anticipated return date.

### Section 8: 
Party A shall treat all documentation and information regarding the reason for leave as confidential and shall not disclose such information except as required for verification or by law.

### Section 9: 
Upon conclusion of leave, Party B shall notify Party A in writing of their intent to resume obligations and may be required to submit updated documentation confirming fitness to work.

### Section 10: 
All deadlines and milestones in Article 2 affected by the leave period shall be automatically extended by the number of leave days taken, unless otherwise agreed in writing by both parties.

### Section 11: 
This provision shall not apply to absences resulting from voluntary travel, recreational activities, or other non-essential personal matters, unless expressly approved in writing by Party A.

### Section 12: 
The granting of leave under this section shall not constitute a waiver of any other contractual obligations or remedies available to either party.

### Section 13: 
If Party A reasonably determines that the leave provision has been misused or that evidence was falsified, Party A may retroactively revoke leave status and pursue remedies under Article 6.

### Section 14: 
In the event of any conflict between this section and other sections of the Agreement, the terms of this section shall prevail with respect to leave-related matters.

### Section 15: 
Party C may request extended leave under the same conditions as Party B members; however, Party C must arrange for qualified temporary financial management coverage approved by Party A, or Party A may assume or assign a temporary replacement to assume temporary financial control during Party C's absence.

## Article 23: Technology Platform Dependency
### Section 1.1: 
The parties acknowledge that the business operations depend on third-party platforms such as Etsy, Shopify, or similar e-commerce platforms, which may change their terms of service, fee structures, content policies, or discontinue their services at any time.

### Section 1.2: 
Party A shall monitor platform policies and notify Party B and Party C of any material changes that may affect the business operations or compensation structure under this Agreement. Party C shall be responsible for implementing any required changes to payment processing or account structures.

### Section 2.1: 
Party A and Party C shall collaboratively maintain contingency plans for migrating the business to alternative platforms in the event that a primary platform becomes unavailable or implements changes that materially affect the business operations. Party C shall handle the technical implementation of platform migrations under Party A's direction.

### Section 2.2: 
In the event that a platform change results in increased fees or costs that materially affect Net Profits as defined in Article 3, Section 10, such increased costs shall be considered legitimate deductions for the purpose of calculating Net Profits.

### Section 3.1: 
Significant disruptions to third-party platforms that are beyond the reasonable control of either party and materially impair the ability to conduct business operations shall be considered Force Majeure events under Article 11.

### Section 3.2: 
In such cases, the parties shall cooperate in good faith to mitigate the effects of such disruptions and may temporarily suspend or modify their obligations under this Agreement until the disruption is resolved.

### Section 4.1: 
Party A shall use reasonable efforts to diversify the business across multiple platforms to reduce dependency on any single platform, subject to the business's operational capabilities and market conditions.

### Section 4.2: 
Party B shall cooperate with Party A in adapting products or services as necessary to comply with platform requirements or to facilitate migration to alternative platforms.

### Section 5.1: Party A shall have exclusive and unilateral authority to select, modify, or change all communication platforms, task management systems, file sharing services, collaboration tools, and any other digital platforms or software applications used in connection with this Agreement, including but not limited to:
(a) messaging platforms (e.g., Discord, Slack, Telegram, WhatsApp);
(b) project management tools (e.g., Trello, Asana, Monday.com, Notion);
(c) file storage and sharing systems (e.g., Google Drive, Dropbox, OneDrive); 
(d) design and creative software platforms;
(e) communication protocols and meeting platforms (e.g., Zoom, Google Meet, Microsoft Teams);
(f) and any other technological tools deemed necessary for business operations.

### Section 5.2: 
Party A's decisions regarding platform selection, configuration, access permissions, user roles, and operational procedures shall be final and binding. Party A may implement changes to platforms, access levels, or usage requirements at any time without prior notice or consultation with Party B, provided that such changes do not materially impair Party B's ability to fulfill their core obligations under Article 2.

### Section 5.3: 
Party B shall have no authority to challenge, override, or revoke Party A's decisions regarding platform selection or management. Party B agrees to adapt to any platform changes and shall be responsible for learning and effectively using any platforms designated by Party A within a reasonable timeframe not to exceed seven (7) calendar days from notification.

### Section 5.4: Party A reserves the right to:
(a) monitor all communications and activities on designated platforms for quality assurance, compliance, and business operational purposes;
(b) establish and modify user permissions, access controls, and usage guidelines;
(c) restrict or terminate Party B's access to any platform for violations of platform terms of service, this Agreement, or business operational requirements;
(d) require Party B to use specific features, templates, or workflows within designated platforms;
(e) and integrate third-party applications or services with existing platforms without Party B consent.

### Section 5.5: 
Party B acknowledges that failure to effectively utilize designated platforms or comply with platform-specific requirements may impact work quality assessments under Article 2, Sections 3 and 4, and may constitute grounds for termination.

### Section 5.6: 
All data, communications, files, and content on platforms designated by Party A shall be subject to the intellectual property provisions of this Agreement. Party A maintains administrative control over all business-related accounts and data.

### Section 5.7: 
In the event of technical difficulties with designated platforms, Party B shall notify Party A within twenty-four (24) hours and make reasonable efforts to resolve the issue. Party A may, at its sole discretion, provide technical support or alternatives but is not obligated to do so. Upon termination, Party B's access to all platforms, data, and communications shall be revoked, and Party A shall retain administrative control over such platforms and data indefinitely.

## Article 24: Business Restructuring and Change of Control
### Section 1: For purposes of this Article, a "Change of Control" means:
(a) the sale or transfer of all or substantially all of Party A's assets;
(b) the merger, consolidation, or reorganization of Party A with or into another entity where Party A is not the surviving entity;
(c) or any transaction or series of related transactions that result in a transfer of more than 50% of the voting control of Party A.

### Section 2.1: 
Party A shall provide written notice to Party B and Party C of any anticipated Change of Control at least thirty (30) days prior to the effective date of such change, or as soon as commercially practicable if earlier notice is not possible due to confidentiality restrictions.

### Section 2.2: 
The notice shall include information regarding the nature of the Change of 'Control and its anticipated effect on the contractual relationship between the parties.

### Section 3.1: 
In the event of a Change of Control, this Agreement shall remain in full force and effect and shall be binding upon Party A's successors and assigns.

### Section 3.2: 
The successor entity shall assume all rights and obligations of Party A under this Agreement without requiring further action from either Party.

### Section 4.1: 
Within thirty (30) days after receiving notice of a Change of Control, Party B shall have the right to terminate this Agreement by providing written notice to Party A or its successor.

### Section 4.2: If Party B or Party C exercises termination rights due to Change of Control, Party A or its successor shall:
(a) Pay the terminating party any compensation due for completed work up to the effective date of termination.
(b) For Party B: Continue to pay the applicable percentage of Net Profits from sales of products created by Party B for a period of six (6) months following the effective date of termination, after which all payment obligations shall cease;
(c) For Party C: Provide transition assistance for transfer of financial management responsibilities and final accounting within thirty (30) days;
(d) Retain all rights to continue business operations in accordance with this Agreement.

### Section 5: 
If Party A restructures its business entity (e.g., converting from sole proprietorship to corporation) without a Change of Control as defined in Section 1 of this Article, Party A shall provide written notice to Party B, and such restructuring shall not affect the rights and obligations of the parties under this Agreement.

## Article 25: Regular Contract Review
### Section 1: 
This contract shall be subject to a mandatory review every six (6) months.

### Section 2: 
During each review, either Party may request modifications to compensation rates, work requirements, or other terms. Such requests shall be considered in good faith by Party A with supporting justification for any denials.

## Article 26: Emergency Fund Protection
### Section 1: 
Party C shall establish and maintain an emergency fund of at least USD $25 and at most USD $1000 per Party A and Party B members to ensure payment obligations can be met even during temporary financial difficulties. This fund shall be managed under Party A's oversight and approval.

### Section 2: 
This fund shall be held by Party C in a separate, interest-bearing account with Party A as secondary authorized signatory and may only be accessed to fulfill payment obligations to Party B members when the primary business accounts are insufficient. Any use of emergency funds requires Party A's written authorization.

### Section 3: 
Upon termination of this Agreement, any unused portion of Party A and Party B's allocated emergency fund shall be returned to them within fifty (50) days. Party C is responsible for processing these returns under Party A's supervision.

## Article 27: Financial Accountability and Audit Rights
### Section 1: 
Party A retains the right to conduct financial audits of Party C's management at any time without notice. Such audits may include review of all business accounts, transaction records, and financial documentation.

### Section 2: 
Party A and C shall maintain detailed transaction logs, expense receipts, and payment records for a minimum of three (3) years. All records shall be made available to Party A upon request within 24 hours.

### Section 3: 
Any discrepancies discovered during audits must be resolved within 7 days. Significant discrepancies (exceeding PHP 1,000 or 5% of monthly revenue) may result in immediate suspension of Party C's access to financial systems pending resolution.

### Section 4: 
Party C agrees to implement financial controls and security measures as specified by Party A, including but not to two-factor authentication, regular password updates, and secure handling of customer payment information.

## Article 28: Party C Succession and Backup
### Section 1: 
Party C shall maintain updated documentation of all financial systems, account access procedures, and operational processes to ensure business continuity in case of absence or incapacity.

### Section 2: 
Party A shall have administrative access to all financial systems and accounts as backup authorization, with full authority to assume financial operations if Party C becomes unavailable.

### Section 3: 
In the event Party C is terminated or withdraws, they must provide complete transfer of all financial systems, accounts, and records to Party A or designated replacement within 48 hours.

## Article 29: Communication Control and Party Isolation
### Section 1: 
Party A reserves the exclusive right to control all inter-party communications and may require that all business communications between Party B and Party C members be conducted through Party A or designated intermediaries.

### Section 2: Party A may, at its sole discretion, implement communication protocols that prevent direct contact between Party B and Party C members, including but not limited to:
(a) Requiring all communications to be routed through Party A;
(b) Prohibiting the exchange of personal contact information between parties;
(c) Establishing separate communication channels for different party members;
(d) Implementing confidentiality barriers between party functions.

### Section 3: 
Neither Party B nor Party C members have the right to demand direct communication with other party members or to bypass Party A's established communication protocols.

### Section 4: 
Violation of communication protocols established under this Article may result in immediate termination without notice or severance benefits.

### Section 5: 
This Article shall survive the termination of this Agreement indefinitely.

## Article 30: Initial Qualification and Product Assessment
### Section 1: 
The Parties agree that the provisions of this Article 30 establish a mandatory initial qualification period for Party B members, during which specific terms regarding product assessment, intellectual property ownership, and termination shall apply. During this Assessment Period, and for all matters specifically addressed herein, the terms of this Article 30 shall prevail over and supersede any conflicting provisions elsewhere in this Agreement, including but not limited to those in Article 3 (Compensation), Article 5 (Ownership and Intellectual Property), Article 6 (Term and Termination), Article 7 (Dispute Resolution), Article 13 (Governance), and Article 20 (Amendments). This Article represents the express agreement of the Parties to grant Party A the specified unilateral authority for the duration and scope of this initial assessment.

### Section 2: 
Upon the signing of this Agreement, each Party B member shall, within a period specified by Party A (not to exceed fourteen (14) calendar days), create and submit one or more original products or digital content as directed by Party A. This period shall be considered an "Assessment Period." Party A shall provide specific guidelines, themes, or requirements for these products.

### Section 3: 
Party A shall have the sole and unilateral authority to set the standards, criteria, and grading methodology for the products created during the Assessment Period. Party A's evaluation of the submitted products, including whether they meet the required standards, shall be final and binding. Notwithstanding Article 7 (Dispute Resolution) and Article 13, Section 3.2 (Party B's right to challenge Party A's decisions), Party A's determination under this Section 2 shall not be subject to mediation, arbitration, or challenge by Party B. The granting of this unilateral authority within this Article 30 is acknowledged by the Parties as an exception to the general decision-making processes outlined in Article 13, Section 10 and Article 20, Section 3, and is effective upon mutual agreement to this Article 30.

### Section 4: 
If, in Party A's sole determination, a Party B member's submitted products fail to meet the standards set for the Assessment Period, Party A may immediately terminate this Agreement with respect to that Party B member. This termination shall be effective immediately upon written notice from Party A, without any requirement for prior notice period, opportunity to cure, or justification beyond the failure of the assessment, notwithstanding any other termination provisions in Article 6.

### Section 5: 
All intellectual property, including all copyrights and other proprietary rights, in and to the products, designs, and content created by Party B during the Assessment Period, shall belong solely and absolutely to Party A upon creation, regardless of whether Party B successfully passes the assessment or is subsequently terminated. Party B hereby irrevocably assigns all such rights to Party A for no additional consideration beyond the opportunity to enter into this Agreement. Party B shall have no claim to any compensation, profit share, royalties, future earnings, or severance pay whatsoever for any products created during this Assessment Period. This complete forfeiture of rights and compensation applies notwithstanding Article 3, Section 1.5 (Full Payment Guarantee on Termination), Article 3, Section 3 (90-day No Sales Compensation), Article 3, Section 14 (Severance Pay), Article 5, Section 1 (IP Co-ownership and Revocable License), Article 5, Section 4 (Party B's Right to Independent Sales), and Article 6, Section 2.1 (Waiver of Claims After Final Payment), all of which are expressly superseded by this Section 4 for products created during the Assessment Period.

### Section 6: 
The provisions of this Article 30, including the ownership and forfeiture provisions in Section 4, shall survive the termination of this Agreement indefinitely.

## Signatures:
By signing this agreement, all parties confirm that they have read, understood, and agreed to the terms stated herein, and shall be legally bound by its provisions without exception or reservation.
<br><br>
Party A: _________________________
<br><br>
Party B: _________________________
<br><br>
Party C: _________________________
`;

        /**
         * A simple parser to convert the semi-markdown text into HTML.
         * It handles headings, paragraphs, and lists.
         */
        function parseContractToHTML(text) {
            const lines = text.trim().split('\n');
            let html = '';
            let inList = false;

            lines.forEach(line => {
                line = line.trim();
                if (line.startsWith('## Article')) {
                    if (inList) {
                        html += '</ul>';
                        inList = false;
                    }
                    html += `<h2>${line.replace('## ', '')}</h2>`;
                } else if (line.startsWith('### Section')) {
                     if (inList) {
                        html += '</ul>';
                        inList = false;
                    }
                    html += `<h3>${line.replace('### ', '')}</h3>`;
                } else if (line.match(/^\(\w+\)/) || line.match(/^\w\)/)) {
                    if (!inList) {
                        html += '<ul>';
                        inList = true;
                    }
                    html += `<li class="ml-4 pl-2 border-l-2 border-slate-300 mb-2">${line}</li>`;
                } else if (line) {
                     if (inList) {
                        html += '</ul>';
                        inList = false;
                    }
                    html += `<p class="mb-4">${line}</p>`;
                }
            });
            
            if (inList) {
                html += '</ul>';
            }

            return html.replace(/<br>/g, '<br />');
        }

        // On document load, parse and inject the contract HTML
        document.addEventListener('DOMContentLoaded', () => {
            const contractContainer = document.getElementById('contract-content');
            if (contractContainer) {
                contractContainer.innerHTML = parseContractToHTML(contractText);
            }

            // --- Gemini API Feature Listeners ---
            const summarizeBtn = document.getElementById('summarize-btn');
            const explainBtn = document.getElementById('explain-btn');
            const riskBtn = document.getElementById('risk-btn');
            const aiOutput = document.getElementById('ai-output');

            summarizeBtn.addEventListener('click', () => {
                const prompt = `Please provide a concise summary of the key points of the following Online Selling Collaboration Contract. Focus on the purpose, the roles of Party A, B, and C, the compensation structure, and intellectual property ownership.\n\n---\n\n${contractText}`;
                callGeminiAPI(prompt);
            });

            explainBtn.addEventListener('click', () => {
                const clauseInput = document.getElementById('clause-input').value;
                if (!clauseInput) {
                    aiOutput.innerHTML = '<p class="text-red-500 text-center">Please enter a clause to explain.</p>';
                    return;
                }
                const clauseText = getClauseText(clauseInput);
                if (!clauseText) {
                    aiOutput.innerHTML = `<p class="text-red-500 text-center">Could not find clause: "${clauseInput}". Please use the format "Article X, Section Y".</p>`;
                    return;
                }
                const prompt = `In simple, easy-to-understand language, please explain the following clause from a legal contract. Explain what it means for the parties involved.\n\n**Clause to Explain:**\n"${clauseInput}"\n\n**Clause Text:**\n"${clauseText}"`;
                callGeminiAPI(prompt);
            });

            riskBtn.addEventListener('click', () => {
                const selectedParty = document.getElementById('party-select').value;
                const prompt = `Analyze the following Online Selling Collaboration Contract from the specific perspective of ${selectedParty}. Identify and explain the top 3-5 potential risks, disadvantages, or unfavorable clauses for ${selectedParty}. For each point, explain why it's a risk and reference the specific article and section.\n\n---\n\n${contractText}`;
                callGeminiAPI(prompt);
            });
        });

        /**
         * Finds the text of a specific article or section in the contract.
         * @param {string} clauseIdentifier - e.g., "Article 3, Section 1.1" or "Article 8"
         * @returns {string|null} The text of the clause or null if not found.
         */
        function getClauseText(clauseIdentifier) {
            // Normalize the input for matching
            const normalizedIdentifier = clauseIdentifier.toLowerCase().replace(/,/g, '');
            const lines = contractText.split('\n');
            let capture = false;
            let content = [];
            
            // Create a regex to match the start of the clause
            // e.g., "article 3 section 1.1" -> /## article 3\n### section 1\.1/i
            const articleMatch = normalizedIdentifier.match(/article\s+(\d+)/);
            const sectionMatch = normalizedIdentifier.match(/section\s+([\d\.]+)/);

            if (!articleMatch) return null;

            const articleNumber = articleMatch[1];
            let searchPattern;

            if (sectionMatch) {
                const sectionNumber = sectionMatch[1].replace('.', '\\.');
                searchPattern = new RegExp(`^### Section ${sectionNumber}`, 'i');
            } else {
                searchPattern = new RegExp(`^## Article ${articleNumber}:`, 'i');
            }
            
            let articleFound = false;
            for (const line of lines) {
                const trimmedLine = line.trim();
                // Find the correct article first
                if (new RegExp(`^## Article ${articleNumber}:`, 'i').test(trimmedLine)) {
                    articleFound = true;
                }

                if (articleFound && searchPattern.test(trimmedLine)) {
                    capture = true;
                    content.push(trimmedLine);
                    continue;
                }

                if (capture) {
                    // Stop capturing when we hit the next section or article
                    if (trimmedLine.startsWith('### Section') || trimmedLine.startsWith('## Article')) {
                        break;
                    }
                    if (trimmedLine) {
                       content.push(trimmedLine);
                    }
                }
            }

            return content.length > 0 ? content.join('\n') : null;
        }

        /**
         * Calls the Gemini API with a given prompt.
         * @param {string} prompt - The prompt to send to the Gemini API.
         */
        async function callGeminiAPI(prompt) {
            const aiOutput = document.getElementById('ai-output');
            aiOutput.innerHTML = '<div class="loader"></div>'; // Show loader

            const apiKey = ""; // API key is handled by the environment
            const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;

            const payload = {
                contents: [{
                    role: "user",
                    parts: [{ text: prompt }]
                }]
            };

            try {
                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                if (!response.ok) {
                    throw new Error(`API request failed with status ${response.status}`);
                }

                const result = await response.json();
                
                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts &&
                    result.candidates[0].content.parts.length > 0) {
                    const text = result.candidates[0].content.parts[0].text;
                    aiOutput.innerHTML = `<p>${text.replace(/\n/g, '<br>')}</p>`; // Display result
                } else {
                    throw new Error("Invalid response structure from API.");
                }

            } catch (error) {
                console.error("Gemini API call failed:", error);
                aiOutput.innerHTML = `<p class="text-red-500 text-center">Error: Could not get a response from the AI. Please check the console for details.</p>`;
            }
        }
    </script>

</body>
</html>

