# Ledger: Command-Line Accounting

<a name="SEC_Contents"></a>

## Table of Contents

*   [1 Introduction to Ledger](#Introduction-to-Ledger)  
    *   [1.1 Fat-free Accounting](#Fat_002dfree-Accounting)
    *   [1.2 Building the program](#Building-the-program)
    *   [1.3 Getting help](#Getting-help)
*   [2 Ledger Tutorial](#Ledger-Tutorial)
    *   [2.1 Start a Journal File](#Start-a-Journal-File)
    *   [2.2 Run a Few Reports](#Run-a-Few-Reports)
        *   [2.2.1 Balance Report](#Balance-Report)
        *   [2.2.2 Register Report](#Register-Report)
        *   [2.2.3 Cleared Report](#Cleared-Report)
        *   [2.2.4 Using the Windows Command-Line](#Using-the-Windows-Command_002dLine)
*   [3 Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger)
    *   [3.1 Accounting with Ledger](#Accounting-with-Ledger)
    *   [3.2 Stating where money goes](#Stating-where-money-goes)
    *   [3.3 Assets and Liabilities](#Assets-and-Liabilities)
        *   [3.3.1 Tracking reimbursable expenses](#Tracking-reimbursable-expenses)
    *   [3.4 Commodities and Currencies](#Commodities-and-Currencies)
        *   [3.4.1 Commodity price histories](#Commodity-price-histories)
        *   [3.4.2 Commodity equivalences](#Commodity-equivalences)
    *   [3.5 Accounts and Inventories](#Accounts-and-Inventories)
    *   [3.6 Understanding Equity](#Understanding-Equity)
    *   [3.7 Dealing with Petty Cash](#Dealing-with-Petty-Cash)
    *   [3.8 Working with multiple funds and accounts](#Working-with-multiple-funds-and-accounts)
*   [4 Keeping a Journal](#Keeping-a-Journal)
    *   [4.1 The Most Basic Entry](#The-Most-Basic-Entry)
    *   [4.2 Starting up](#Starting-up)
    *   [4.3 Structuring your Accounts](#Structuring-your-Accounts)
    *   [4.4 Commenting on your Journal](#Commenting-on-your-Journal)
    *   [4.5 Currency and Commodities](#Currency-and-Commodities)
        *   [4.5.1 Naming Commodities](#Naming-Commodities)
        *   [4.5.2 Buying and Selling Stock](#Buying-and-Selling-Stock)
        *   [4.5.3 Fixing Lot Prices](#Fixing-Lot-Prices)
        *   [4.5.4 Complete control over commodity pricing](#Complete-control-over-commodity-pricing)
    *   [4.6 Keeping it Consistent](#Keeping-it-Consistent)
    *   [4.7 Journal Format](#Journal-Format)
        *   [4.7.1 Transactions and Comments](#Transactions-and-Comments)
        *   [4.7.2 Command Directives](#Command-Directives)
    *   [4.8 Converting from other formats](#Converting-from-other-formats)
    *   [4.9 Archiving Previous Years](#Archiving-Previous-Years)
*   [5 Transactions](#Transactions)
    *   [5.1 Basic format](#Basic-format)
    *   [5.2 Eliding amounts](#Eliding-amounts)
    *   [5.3 Auxiliary dates](#Auxiliary-dates)
    *   [5.4 Codes](#Codes)
    *   [5.5 Transaction state](#Transaction-state)
    *   [5.6 Transaction notes](#Transaction-notes)
    *   [5.7 Metadata](#Metadata)
        *   [5.7.1 Metadata tags](#Metadata-tags)
            *   [5.7.1.1 Payee metadata tag](#Payee-metadata-tag)
        *   [5.7.2 Metadata values](#Metadata-values)
        *   [5.7.3 Typed metadata](#Typed-metadata)
    *   [5.8 Virtual postings](#Virtual-postings)
    *   [5.9 Expression amounts](#Expression-amounts)
    *   [5.10 Balance verification](#Balance-verification)
        *   [5.10.1 Balance assertions](#Balance-assertions)
        *   [5.10.2 Balance assignments](#Balance-assignments)
        *   [5.10.3 Resetting a balance](#Resetting-a-balance)
        *   [5.10.4 Balancing transactions](#Balancing-transactions)
    *   [5.11 Posting cost](#Posting-cost)
    *   [5.12 Explicit posting costs](#Explicit-posting-costs)
        *   [5.12.1 Primary and secondary commodities](#Primary-and-secondary-commodities)
    *   [5.13 Posting cost expressions](#Posting-cost-expressions)
    *   [5.14 Total posting costs](#Total-posting-costs)
    *   [5.15 Virtual posting costs](#Virtual-posting-costs)
    *   [5.16 Commodity prices](#Commodity-prices)
        *   [5.16.1 Total commodity prices](#Total-commodity-prices)
    *   [5.17 Prices versus costs](#Prices-versus-costs)
    *   [5.18 Fixated prices and costs](#Fixated-prices-and-costs)
    *   [5.19 Lot dates](#Lot-dates)
    *   [5.20 Lot notes](#Lot-notes)
    *   [5.21 Lot value expressions](#Lot-value-expressions)
    *   [5.22 Automated Transactions](#Automated-Transactions)
        *   [5.22.1 Amount multipliers](#Amount-multipliers)
        *   [5.22.2 Accessing the matching posting’s amount](#Accessing-the-matching-posting_0027s-amount)
        *   [5.22.3 Referring to the matching posting’s account](#Referring-to-the-matching-posting_0027s-account)
        *   [5.22.4 Applying metadata to every matched posting](#Applying-metadata-to-every-matched-posting)
        *   [5.22.5 Applying metadata to the generated posting](#Applying-metadata-to-the-generated-posting)
        *   [5.22.6 State flags](#State-flags)
        *   [5.22.7 Effective Dates](#Effective-Dates)
        *   [5.22.8 Periodic Transactions](#Periodic-Transactions)
        *   [5.22.9 Concrete Example of Automated Transactions](#Concrete-Example-of-Automated-Transactions)
*   [6 Building Reports](#Building-Reports)
    *   [6.1 Introduction](#Introduction)
    *   [6.2 Balance Reports](#Balance-Reports)
        *   [6.2.1 Controlling the Accounts and Payees](#Controlling-the-Accounts-and-Payees)
        *   [6.2.2 Controlling Formatting](#Controlling-Formatting)
    *   [6.3 Typical queries](#Typical-queries)
        *   [6.3.1 Reporting monthly expenses](#Reporting-monthly-expenses)
    *   [6.4 Advanced Reports](#Advanced-Reports)
        *   [6.4.1 Asset Allocation](#Asset-Allocation)
        *   [6.4.2 Visualizing with Gnuplot](#Visualizing-with-Gnuplot)
*   [7 Reporting Commands](#Reporting-Commands)
    *   [7.1 Primary Financial Reports](#Primary-Financial-Reports)
        *   [7.1.1 The `balance` command](#The-balance-command)
        *   [7.1.2 The `equity` command](#The-equity-command)
        *   [7.1.3 The `register` command](#The-register-command)
        *   [7.1.4 The `print` command](#The-print-command)
    *   [7.2 Reports in other Formats](#Reports-in-other-Formats)
        *   [7.2.1 Comma Separated Values files](#Comma-Separated-Values-files)
            *   [7.2.1.1 The `csv` command](#The-csv-command)
            *   [7.2.1.2 The `convert` command](#The-convert-command)
        *   [7.2.2 The `lisp` command](#The-lisp-command)
        *   [7.2.3 Emacs `org` Mode](#Emacs-org-Mode)
        *   [7.2.4 Org mode with Babel](#Org-mode-with-Babel)
            *   [7.2.4.1 Embedded Ledger example with single source block](#Embedded-Ledger-example-with-single-source-block)
            *   [7.2.4.2 Multiple Ledger source blocks with `noweb`](#Multiple-Ledger-source-blocks-with-noweb)
            *   [7.2.4.3 Income Entries](#Income-Entries)
            *   [7.2.4.4 Expenses](#Expenses)
            *   [7.2.4.5 Financial Summaries](#Financial-Summaries)
            *   [7.2.4.6 An overall balance summary](#An-overall-balance-summary)
            *   [7.2.4.7 Generating a monthly register](#Generating-a-monthly-register)
            *   [7.2.4.8 Summary](#Summary)
        *   [7.2.5 The `pricemap` command](#The-pricemap-command)
        *   [7.2.6 The `xml` command](#The-xml-command)
        *   [7.2.7 `prices` and `pricedb` commands](#prices-and-pricedb-commands)
    *   [7.3 Reports about your Journals](#Reports-about-your-Journals)
        *   [7.3.1 `accounts`](#accounts)
        *   [7.3.2 `payees`](#payees)
        *   [7.3.3 `commodities`](#commodities)
        *   [7.3.4 `tags`](#tags)
        *   [7.3.5 `xact`](#xact)
        *   [7.3.6 `stats`](#stats)
        *   [7.3.7 `select`](#select)
*   [8 Command-Line Syntax](#Command_002dLine-Syntax)
    *   [8.1 Basic Usage](#Basic-Usage)
    *   [8.2 Command-Line Quick Reference](#Command_002dLine-Quick-Reference)
        *   [8.2.1 Basic Reporting Commands](#Basic-Reporting-Commands)
        *   [8.2.2 Basic Options](#Basic-Options)
        *   [8.2.3 Report Filtering](#Report-Filtering)
        *   [8.2.4 Error Checking and Calculation Options](#Error-Checking-and-Calculation-Options)
        *   [8.2.5 Output Customization](#Output-Customization)
        *   [8.2.6 Grouping Options](#Grouping-Options)
        *   [8.2.7 Commodity Reporting](#Commodity-Reporting)
    *   [8.3 Detailed Option Description](#Detailed-Option-Description)
        *   [8.3.1 Global Options](#Global-Options)
        *   [8.3.2 Session Options](#Session-Options)
        *   [8.3.3 Report Options](#Report-Options)
        *   [8.3.4 Basic options](#Basic-options)
        *   [8.3.5 Report filtering](#Report-filtering)
        *   [8.3.6 Output customization](#Output-customization)
        *   [8.3.7 Commodity reporting](#Commodity-reporting)
        *   [8.3.8 Environment variables](#Environment-variables)
    *   [8.4 Period Expressions](#Period-Expressions)
*   [9 Budgeting and Forecasting](#Budgeting-and-Forecasting)
    *   [9.1 Budgeting](#Budgeting)
    *   [9.2 Forecasting](#Forecasting)
*   [10 Time Keeping](#Time-Keeping)
*   [11 Value Expressions](#Value-Expressions)
    *   [11.1 Variables](#Variables)
        *   [11.1.1 Posting/account details](#Posting_002faccount-details)
        *   [11.1.2 Calculated totals](#Calculated-totals)
    *   [11.2 Functions](#Functions)
    *   [11.3 Operators](#Operators)
        *   [11.3.1 Unary Operators](#Unary-Operators)
        *   [11.3.2 Binary Operators](#Binary-Operators)
    *   [11.4 Complex expressions](#Complex-expressions)
        *   [11.4.1 Miscellaneous](#Miscellaneous)
*   [12 Format Strings](#Format-Strings)
    *   [12.1 Format String Basics](#Format-String-Basics)
    *   [12.2 Format String Structure](#Format-String-Structure)
    *   [12.3 Format Expressions](#Format-Expressions)
    *   [12.4 Balance format](#Balance-format)
    *   [12.5 Formatting Functions and Codes](#Formatting-Functions-and-Codes)
        *   [12.5.1 Field Widths](#Field-Widths)
        *   [12.5.2 Colors](#Colors)
        *   [12.5.3 Quantities and Calculations](#Quantities-and-Calculations)
        *   [12.5.4 Date Functions](#Date-Functions)
        *   [12.5.5 Date and Time Format Codes](#Date-and-Time-Format-Codes)
            *   [12.5.5.1 Days](#Days)
            *   [12.5.5.2 Weekdays](#Weekdays)
            *   [12.5.5.3 Month](#Month)
            *   [12.5.5.4 Miscellaneous Date Codes](#Miscellaneous-Date-Codes)
        *   [12.5.6 Text Formatting](#Text-Formatting)
        *   [12.5.7 Data File Parsing Information](#Data-File-Parsing-Information)
*   [15 Major Changes from version 2.6](#Major-Changes-from-version-2_002e6)
*   [Appendix A Example Journal File](#Example-Journal-File)
*   [Appendix B Miscellaneous Notes](#Miscellaneous-Notes)
    *   [B.1 Cookbook](#Cookbook)
        *   [B.1.1 Invoking Ledger](#Invoking-Ledger)
        *   [B.1.2 Ledger Files](#Ledger-Files)
*   [Concepts Index](#Concepts-Index)
*   [Commands & Options Index](#Commands-_0026-Options-Index)

<a name="Top"></a>

<div class="header">

Next: [Introduction to Ledger](#Introduction-to-Ledger), Previous: [(dir)](dir.html#Top), Up: [(dir)](dir.html#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Overview"></a>

# Overview

Ledger is a command-line accounting tool that provides double-entry accounting based on a text journal. It provides no bells or whistles, and returns the user to the days before user interfaces were even a twinkling in their father’s CRT.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Introduction to Ledger](#Introduction-to-Ledger):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Ledger Tutorial](#Ledger-Tutorial):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Keeping a Journal](#Keeping-a-Journal):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Transactions](#Transactions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Building Reports](#Building-Reports):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Reporting Commands](#Reporting-Commands):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Command-Line Syntax](#Command_002dLine-Syntax):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Budgeting and Forecasting](#Budgeting-and-Forecasting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Time Keeping](#Time-Keeping):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Value Expressions](#Value-Expressions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Format Strings](#Format-Strings):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Extending with Python](#Extending-with-Python):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Ledger for Developers](#Ledger-for-Developers):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Major Changes from version 2.6](#Major-Changes-from-version-2_002e6):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Example Journal File](#Example-Journal-File):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Miscellaneous Notes](#Miscellaneous-Notes):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Concepts Index](#Concepts-Index):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Commands & Options Index](#Commands-_0026-Options-Index):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Introduction-to-Ledger"></a>

<div class="header">

Next: [Ledger Tutorial](#Ledger-Tutorial), Previous: [Top](#Top), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Introduction-to-Ledger-1"></a>

## 1 Introduction to Ledger

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Fat-free Accounting](#Fat_002dfree-Accounting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Building the program](#Building-the-program):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Getting help](#Getting-help):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Fat_002dfree-Accounting"></a>

Here is a good place for an aside on the use of the word “account”. Most private people consider an account to be something that holds money at an institution for them. Ledger uses a more general definition of the word. An account is anywhere money can go. Other finance programs use “categories”, Ledger uses accounts. So, for example, if you buy some groceries at Trader Joe’s, then more groceries at Whole Food Market, you might assign the transactions like this

<div class="smallexample">

<pre class="smallexample">2011/03/15   Trader Joe's
    Expenses:Groceries   $100.00
    Assets:Checking
2011/03/15   Whole Food Market
    Expenses:Groceries   $75.00
    Assets:Checking
</pre>

</div>

In both cases the money goes to the ‘<samp>Groceries</samp>’ account, even though the payees were different. You can set up your accounts in any way you choose.


<div class="smallexample">

<pre class="smallexample">2004/09/29 Pacific Bell
    Expenses:Pacific Bell              $23.00
    Assets:Checking
</pre>

</div>

The account balances and registers in this file, if saved as <samp>ledger.dat</samp>, could be reported using:

<div class="smallexample">

<pre class="smallexample">$ ledger -f ledger.dat balance
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">             $-23.00  Assets:Checking
              $23.00  Expenses:Pacific Bell
--------------------
                   0
</pre>

</div>

Or

<div class="smallexample">

<pre class="smallexample">$ ledger -f ledger.dat register checking
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">04-Sep-29 Pacific Bell          Assets:Checking             $-23.00      $-23.00
</pre>

</div>

And even:

<div class="smallexample">

<pre class="smallexample">$ ledger -f ledger.dat register Bell
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">04-Sep-29 Pacific Bell          Expenses:Pacific Bell        $23.00       $23.00
</pre>

</div>

* * *

<a name="Ledger-Tutorial"></a>

<div class="header">

Next: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger), Previous: [Introduction to Ledger](#Introduction-to-Ledger), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Ledger-Tutorial-1"></a>

## 2 Ledger Tutorial

<a name="index-tutorial"></a>

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Start a Journal File](#Start-a-Journal-File):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

* * *

<a name="Start-a-Journal-File"></a>

<div class="header">

Next: [Run a Few Reports](#Run-a-Few-Reports), Previous: [Ledger Tutorial](#Ledger-Tutorial), Up: [Ledger Tutorial](#Ledger-Tutorial)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Start-a-Journal-File-1"></a>

### 2.1 Start a Journal File

<a name="index-journals"></a>

A journal is a record of your financial transactions and will be central to using Ledger. For now we just want to get a taste of what Ledger can do. An example journal is included with the source code distribution, called <samp>drewr3.dat</samp> (see [Example Journal File](#Example-Journal-File)). Copy it someplace convenient and open up a terminal window in that directory.

If you would rather start with your own journal right away please see [Keeping a Journal](#Keeping-a-Journal).

* * *


<a name="Balance-Report"></a>

<div class="header">

Next: [Register Report](#Register-Report), Previous: [Run a Few Reports](#Run-a-Few-Reports), Up: [Run a Few Reports](#Run-a-Few-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Balance-Report-1"></a>

#### 2.2.1 Balance Report

<a name="index-balance-report"></a><a name="index-balance"></a>

To find the balances of all of your accounts, run this command:

<div class="smallexample">

<pre class="smallexample">$ ledger -f drewr3.dat balance
</pre>

</div>

Ledger will generate:

<div class="smallexample">

<pre class="smallexample">         $ -3,804.00  Assets
          $ 1,396.00    Checking
             $ 30.00      Business
         $ -5,200.00    Savings
         $ -1,000.00  Equity:Opening Balances
          $ 6,654.00  Expenses
          $ 5,500.00    Auto
             $ 20.00    Books
            $ 300.00    Escrow
            $ 334.00    Food:Groceries
            $ 500.00    Interest:Mortgage
         $ -2,030.00  Income
         $ -2,000.00    Salary
            $ -30.00    Sales
            $ -63.60  Liabilities
            $ -20.00    MasterCard
            $ 200.00    Mortgage:Principal
           $ -243.60    Tithe
--------------------
           $ -243.60
</pre>

</div>

Showing you the balance of all accounts. Options and search terms can pare this down to show only the accounts you want.

A more useful report is to show only your Assets and Liabilities:

<div class="smallexample">

<pre class="smallexample">$ ledger -f drewr3.dat balance Assets Liabilities
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">         $ -3,804.00  Assets
          $ 1,396.00    Checking
             $ 30.00      Business
         $ -5,200.00    Savings
            $ -63.60  Liabilities
            $ -20.00    MasterCard
            $ 200.00    Mortgage:Principal
           $ -243.60    Tithe
--------------------
         $ -3,867.60
</pre>

</div>

* * *

<a name="Register-Report"></a>

<div class="header">

Next: [Cleared Report](#Cleared-Report), Previous: [Balance Report](#Balance-Report), Up: [Run a Few Reports](#Run-a-Few-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Register-Report-1"></a>

#### 2.2.2 Register Report

<a name="index-register-report"></a><a name="index-register"></a>

To show all transactions and a running total:

<div class="smallexample">

<pre class="smallexample">$ ledger -f drewr3.dat register
</pre>

</div>

Ledger will generate:

<div class="smallexample">

<pre class="smallexample">10-Dec-01 Checking balance      Assets:Checking          $ 1,000.00   $ 1,000.00
                                Equit:Opening Balances  $ -1,000.00            0
10-Dec-20 Organic Co-op         Expense:Food:Groceries      $ 37.50      $ 37.50
                                Expense:Food:Groceries      $ 37.50      $ 75.00
                                Expense:Food:Groceries      $ 37.50     $ 112.50
                                Expense:Food:Groceries      $ 37.50     $ 150.00
                                Expense:Food:Groceries      $ 37.50     $ 187.50
                                Expense:Food:Groceries      $ 37.50     $ 225.00
                                Assets:Checking           $ -225.00            0
10-Dec-28 Acme Mortgage         Lia:Mortgage:Principal     $ 200.00     $ 200.00
                                Expe:Interest:Mortgage     $ 500.00     $ 700.00
                                Expenses:Escrow            $ 300.00   $ 1,000.00
                                Assets:Checking         $ -1,000.00            0
11-Jan-02 Grocery Store         Expense:Food:Groceries      $ 65.00      $ 65.00
                                Assets:Checking            $ -65.00            0
11-Jan-05 Employer              Assets:Checking          $ 2,000.00   $ 2,000.00
                                Income:Salary           $ -2,000.00            0
                                (Liabilities:Tithe)       $ -240.00    $ -240.00
11-Jan-14 Bank                  Assets:Savings             $ 300.00      $ 60.00
                                Assets:Checking           $ -300.00    $ -240.00
11-Jan-19 Grocery Store         Expense:Food:Groceries      $ 44.00    $ -196.00
                                Assets:Checking            $ -44.00    $ -240.00
11-Jan-25 Bank                  Assets:Checking          $ 5,500.00   $ 5,260.00
                                Assets:Savings          $ -5,500.00    $ -240.00
11-Jan-25 Tom's Used Cars       Expenses:Auto            $ 5,500.00   $ 5,260.00
                                Assets:Checking         $ -5,500.00    $ -240.00
11-Jan-27 Book Store            Expenses:Books              $ 20.00    $ -220.00
                                Liabilities:MasterCard     $ -20.00    $ -240.00
11-Dec-01 Sale                  Asse:Checking:Business      $ 30.00    $ -210.00
                                Income:Sales               $ -30.00    $ -240.00
                                (Liabilities:Tithe)         $ -3.60    $ -243.60
</pre>

</div>

To limit this to a more useful subset, simply add the accounts you are interested in seeing transactions for:

<a name="index-accounts_002c-limiting-by"></a><a name="index-limiting-by-accounts"></a>

<div class="smallexample">

<pre class="smallexample">$ ledger -f drewr3.dat register Groceries
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">10-Dec-20 Organic Co-op         Expense:Food:Groceries      $ 37.50      $ 37.50
                                Expense:Food:Groceries      $ 37.50      $ 75.00
                                Expense:Food:Groceries      $ 37.50     $ 112.50
                                Expense:Food:Groceries      $ 37.50     $ 150.00
                                Expense:Food:Groceries      $ 37.50     $ 187.50
                                Expense:Food:Groceries      $ 37.50     $ 225.00
11-Jan-02 Grocery Store         Expense:Food:Groceries      $ 65.00     $ 290.00
11-Jan-19 Grocery Store         Expense:Food:Groceries      $ 44.00     $ 334.00
</pre>

</div>

Which matches the balance reported for the ‘<samp>Groceries</samp>’ account:

<div class="smallexample">

<pre class="smallexample">$ ledger -f drewr3.dat balance Groceries
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">            $ 334.00  Expenses:Food:Groceries
</pre>

</div>

If you would like to find transaction to only a certain payee use ‘<samp>payee</samp>’ or ‘<samp>@</samp>’:

<div class="smallexample">

<pre class="smallexample">$ ledger -f drewr3.dat register payee "Organic"
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">10-Dec-20 Organic Co-op         Expense:Food:Groceries      $ 37.50      $ 37.50
                                Expense:Food:Groceries      $ 37.50      $ 75.00
                                Expense:Food:Groceries      $ 37.50     $ 112.50
                                Expense:Food:Groceries      $ 37.50     $ 150.00
                                Expense:Food:Groceries      $ 37.50     $ 187.50
                                Expense:Food:Groceries      $ 37.50     $ 225.00
                                Assets:Checking           $ -225.00            0
</pre>

</div>

* * *

<a name="Cleared-Report"></a>

<div class="header">

Next: [Using the Windows Command-Line](#Using-the-Windows-Command_002dLine), Previous: [Register Report](#Register-Report), Up: [Run a Few Reports](#Run-a-Few-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Cleared-Report-1"></a>

#### 2.2.3 Cleared Report

<a name="index-cleared-report"></a><a name="index-cleared"></a>

A very useful report is to show what your obligations are versus what expenditures have actually been recorded. It can take several days for a check to clear, but you should treat it as money spent. The `cleared` report shows just that (note that the `cleared` report will not format correctly for accounts that contain multiple commodities):

<div class="smallexample">

<pre class="smallexample">$ ledger -f drewr3.dat cleared
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">     $ -3,804.00            $ 775.00                 Assets
      $ 1,396.00            $ 775.00    10-Dec-20      Checking
         $ 30.00                   0                     Business
     $ -5,200.00                   0                   Savings
     $ -1,000.00         $ -1,000.00    10-Dec-01    Equity:Opening Balances
      $ 6,654.00            $ 225.00                 Expenses
      $ 5,500.00                   0                   Auto
         $ 20.00                   0                   Books
        $ 300.00                   0                   Escrow
        $ 334.00            $ 225.00    10-Dec-20      Food:Groceries
        $ 500.00                   0                   Interest:Mortgage
     $ -2,030.00                   0                 Income
     $ -2,000.00                   0                   Salary
        $ -30.00                   0                   Sales
        $ -63.60                   0                 Liabilities
        $ -20.00                   0                   MasterCard
        $ 200.00                   0                   Mortgage:Principal
       $ -243.60                   0                   Tithe
----------------    ----------------    ---------
       $ -243.60                   0             
</pre>

</div>

The first column shows the outstanding balance, the second column shows the “cleared” balance.

* * *

<a name="Using-the-Windows-Command_002dLine"></a>

<div class="header">

Previous: [Cleared Report](#Cleared-Report), Up: [Run a Few Reports](#Run-a-Few-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Using-the-Windows-Command_002dLine-1"></a>

#### 2.2.4 Using the Windows Command-Line

<a name="index-windows-cmd_002eexe"></a><a name="index-currency-symbol-display-on-windows"></a>

Using ledger under the windows command shell has one significant limitation. CMD.EXE is limited to standard ASCII characters and as such cannot display any currency symbols other than dollar signs ‘<samp>$</samp>’.

* * *

<a name="Principles-of-Accounting-with-Ledger"></a>

<div class="header">

Next: [Keeping a Journal](#Keeping-a-Journal), Previous: [Ledger Tutorial](#Ledger-Tutorial), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Principles-of-Accounting-with-Ledger-1"></a>

## 3 Principles of Accounting with Ledger

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Accounting with Ledger](#Accounting-with-Ledger):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Stating where money goes](#Stating-where-money-goes):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Assets and Liabilities](#Assets-and-Liabilities):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Commodities and Currencies](#Commodities-and-Currencies):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Accounts and Inventories](#Accounts-and-Inventories):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Understanding Equity](#Understanding-Equity):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Dealing with Petty Cash](#Dealing-with-Petty-Cash):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Working with multiple funds and accounts](#Working-with-multiple-funds-and-accounts):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Accounting-with-Ledger"></a>

<div class="header">

Next: [Stating where money goes](#Stating-where-money-goes), Previous: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger), Up: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>


### 3.2 Stating where money goes

<a name="index-credits-and-debits"></a>

Accountants will talk of “credits” and “debits”, but the meaning is often different from the layman’s understanding. To avoid confusion, Ledger uses only subtractions and additions, although the underlying intent is the same as standard accounting principles.

Recall that every posting will involve two or more accounts. Money is transferred from one or more accounts to one or more other accounts. To record the posting, an amount is _subtracted_ from the source accounts, and _added_ to the target accounts.

In order to write a Ledger transaction correctly, you must determine where the money comes from and where it goes to. For example, when you are paid a salary, you must add money to your bank account and also subtract it from an income account:

<div class="smallexample">

<pre class="smallexample">9/29  My Employer
    Assets:Checking                           $500.00
    Income:Salary                            $-500.00
</pre>

</div>

<a name="index-income-is-negative"></a><a name="index-why-is-income-negative"></a>

Why is the Income a negative figure? When you look at the balance totals for your ledger, you may be surprised to see that Expenses are a positive figure, and Income is a negative figure. It may take some getting used to, but to properly use a general ledger you must think in terms of how money moves. Rather than Ledger “fixing” the minus signs, let’s understand why they are there.

When you earn money, the money has to come from somewhere. Let’s call that somewhere “society”. In order for society to give you an income, you must take money away (withdraw) from society in order to put it into (make a payment to) your bank. When you then spend that money, it leaves your bank account (a withdrawal) and goes back to society (a payment). This is why Income will appear negative—it reflects the money you have drawn from society—and why Expenses will be positive—it is the amount you’ve given back. These additions and subtractions will always cancel each other out in the end, because you don’t have the ability to create new money: it must always come from somewhere, and in the end must always leave. This is the beginning of economy, after which the explanation gets terribly difficult.

Based on that explanation, here’s another way to look at your balance report: every negative figure means that that account or person or place has less money now than when you started your ledger; and every positive figure means that that account or person or place has more money now than when you started your ledger. Make sense?

* * *

<a name="Assets-and-Liabilities"></a>

<div class="header">

Next: [Commodities and Currencies](#Commodities-and-Currencies), Previous: [Stating where money goes](#Stating-where-money-goes), Up: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Assets-and-Liabilities-1"></a>

### 3.3 Assets and Liabilities

<a name="index-assets-and-liabilities"></a><a name="index-debts-are-liabilities"></a>

Assets are money that you have, and Liabilities are money that you owe. “Liabilities” is just a more inclusive name for Debts.

An Asset is typically increased by transferring money from an Income account, such as when you get paid. Here is a typical transaction:

<div class="smallexample">

<pre class="smallexample">2004/09/29  My Employer
    Assets:Checking               $500.00
    Income:Salary
</pre>

</div>

Money, here, comes from an Income account belonging to ‘<samp>My Employer</samp>’, and is transferred to your checking account. The money is now yours, which makes it an Asset.

Liabilities track money owed to others. This can happen when you borrow money to buy something, or if you owe someone money. Here is an example of increasing a MasterCard liability by spending money with it:

<div class="smallexample">

<pre class="smallexample">2004/09/30  Restaurant
    Expenses:Dining                $25.00
    Liabilities:MasterCard
</pre>

</div>

The Dining account balance now shows $25 spent on Dining, and a corresponding $25 owed on the MasterCard—and therefore shown as $-25.00\. The MasterCard liability shows up as negative because it offsets the value of your assets.

The combined total of your Assets and Liabilities is your net worth. So to see your current net worth, use this command:

<div class="smallexample">

<pre class="smallexample">$ ledger balance ^assets ^liabilities
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">             $500.00  Assets:Checking
             $-25.00  Liabilities:MasterCard
--------------------
             $475.00
</pre>

</div>

In a similar vein, your Income accounts show up negative, because they transfer money _from_ an account in order to increase your assets. Your Expenses show up positive because that is where the money went to. The combined total of Income and Expenses is your cash flow. A positive cash flow means you are spending more than you make, since income is always a negative figure. To see your current cash flow, use this command:

<div class="smallexample">

<pre class="smallexample">$ ledger balance ^income ^expenses
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">              $25.00  Expenses:Dining
            $-500.00  Income:Salary
--------------------
            $-475.00
</pre>

</div>

Another common question to ask of your expenses is: How much do I spend each month on X? Ledger provides a simple way of displaying monthly totals for any account. Here is an example that summarizes your monthly automobile expenses:

<div class="smallexample">

<pre class="smallexample">$ ledger -M register -f drewr3.dat expenses:auto
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">11-Jan-01 - 11-Jan-31           Expenses:Auto            $ 5,500.00   $ 5,500.00
</pre>

</div>

This assumes, of course, that you use account names like ‘<samp>Expenses:Auto:Gas</samp>’ and ‘<samp>Expenses:Auto:Repair</samp>’.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Tracking reimbursable expenses](#Tracking-reimbursable-expenses):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Tracking-reimbursable-expenses"></a>

<div class="header">

Previous: [Assets and Liabilities](#Assets-and-Liabilities), Up: [Assets and Liabilities](#Assets-and-Liabilities)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Tracking-reimbursable-expenses-1"></a>

#### 3.3.1 Tracking reimbursable expenses

<a name="index-reimbursable-expense-tracking"></a>

Sometimes you will want to spend money on behalf of someone else, which will eventually get repaid. Since the money is still _yours_, it is really an asset. And since the expenditure was for someone else, you don’t want it contaminating your Expenses reports. You will need to keep an account for tracking reimbursements.

This is fairly easy to do in ledger. When spending the money, spend it _to_ your Assets:Reimbursements, using a different account for each person or business that you spend money for. For example:

<div class="smallexample">

<pre class="smallexample">2004/09/29  Circuit City
    Assets:Reimbursements:Company XYZ     $100.00
    Liabilities:MasterCard
</pre>

</div>

This shows $100.00 spent on a MasterCard at Circuit City, with the expense was made on behalf of Company XYZ. Later, when Company XYZ pays the amount back, the money will transfer from that reimbursement account back to a regular asset account:

<div class="smallexample">

<pre class="smallexample">2004/09/29  Company XYZ
    Assets:Checking                       $100.00
    Assets:Reimbursements:Company XYZ
</pre>

</div>

This deposits the money owed from Company XYZ into a checking account, presumably because they paid the amount back with a check.

But what to do if you run your own business, and you want to keep track of expenses made on your own behalf, while still tracking everything in a single ledger file? This is more complex, because you need to track two separate things: 1) The fact that the money should be reimbursed to you, and 2) What the expense account was, so that you can later determine where your company is spending its money.

This kind of posting is best handled with mirrored postings in two different files, one for your personal accounts, and one for your company accounts. But keeping them in one file involves the same kinds of postings, so those are what is shown here. First, the personal transaction, which shows the need for reimbursement:

<div class="smallexample">

<pre class="smallexample">2004/09/29  Circuit City
    Assets:Reimbursements:Company XYZ     $100.00
    Liabilities:MasterCard
</pre>

</div>

This is the same as above, except that you own Company XYZ, and are keeping track of its expenses in the same ledger file. This transaction should be immediately followed by an equivalent transaction, which shows the kind of expense, and also notes the fact that $100.00 is now payable to you:

<div class="smallexample">

<pre class="smallexample">2004/09/29  Circuit City
    Company XYZ:Expenses:Computer:Software      $100.00
    Company XYZ:Accounts Payable:Your Name
</pre>

</div>

This second transaction shows that Company XYZ has just spent $100.00 on software, and that this $100.00 came from Your Name, which must be paid back.

These two transactions can also be merged, to make things a little clearer. Note that all amounts must be specified now:

<div class="smallexample">

<pre class="smallexample">2004/09/29  Circuit City
    Assets:Reimbursements:Company XYZ         $100.00
    Liabilities:MasterCard                   $-100.00
    Company XYZ:Expenses:Computer:Software    $100.00
    Company XYZ:Accounts Payable:Your Name   $-100.00
</pre>

</div>

To “pay back” the reimbursement, just reverse the order of everything, except this time drawing the money from a company asset, paying it to accounts payable, and then drawing it again from the reimbursement account, and paying it to your personal asset account. It’s easier shown than said:

<div class="smallexample">

<pre class="smallexample">2004/10/15  Company XYZ
    Assets:Checking                           $100.00
    Assets:Reimbursements:Company XYZ        $-100.00
    Company XYZ:Accounts Payable:Your Name    $100.00
    Company XYZ:Assets:Checking              $-100.00
</pre>

</div>

And now the reimbursements account is paid off, accounts payable is paid off, and $100.00 has been effectively transferred from the company’s checking account to your personal checking account. The money simply “waited”—in both ‘<samp>Assets:Reimbursements:Company XYZ</samp>’, and ‘<samp>Company XYZ:Accounts Payable:Your Name</samp>’—until such time as it could be paid off.

The value of tracking expenses from both sides like that is that you do not contaminate your personal expense report with expenses made on behalf of others, while at the same time making it possible to generate accurate reports of your company’s expenditures. It is more verbose than just paying for things with your personal assets, but it gives you a very accurate information trail.

The advantage to keep these doubled transactions together is that they always stay in sync. The advantage to keeping them apart is that it clarifies the transfer’s point of view. To keep the postings in separate files, just separate the two transactions that were joined above. For example, for both the expense and the pay-back shown above, the following four transactions would be created. Two in your personal ledger file:

<div class="smallexample">

<pre class="smallexample">2004/09/29  Circuit City
    Assets:Reimbursements:Company XYZ     $100.00
    Liabilities:MasterCard               $-100.00

2004/10/15  Company XYZ
    Assets:Checking                       $100.00
    Assets:Reimbursements:Company XYZ    $-100.00
</pre>

</div>

And two in your company ledger file:

<div class="smallexample">

<pre class="smallexample">apply account Company XYZ

2004/09/29  Circuit City
    Expenses:Computer:Software            $100.00
    Accounts Payable:Your Name           $-100.00

2004/10/15  Company XYZ
    Accounts Payable:Your Name            $100.00
    Assets:Checking                      $-100.00

end apply account
</pre>

</div>

(Note: The `apply account` above means that all accounts mentioned in the file are children of that account. In this case it means that all activity in the file relates to Company XYZ).

After creating these transactions, you will always know that $100.00 was spent using your MasterCard on behalf of Company XYZ, and that Company XYZ spent the money on computer software and paid it back about two weeks later.

<div class="smallexample">

<pre class="smallexample">$ ledger balance --no-total
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">             $100.00  Assets:Checking
                   0  Company XYZ
            $-100.00    Assets:Checking
             $100.00    Expenses:Computer:Software
            $-100.00  Liabilities:MasterCard
</pre>

</div>

* * *

<a name="Commodities-and-Currencies"></a>

<div class="header">

Next: [Accounts and Inventories](#Accounts-and-Inventories), Previous: [Assets and Liabilities](#Assets-and-Liabilities), Up: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Commodities-and-Currencies-1"></a>

### 3.4 Commodities and Currencies

Ledger makes no assumptions about the commodities you use; it only requires that you specify a commodity. The commodity may be any non-numeric string that does not contain a period, comma, forward slash or at-sign. It may appear before or after the amount, although it is assumed that symbols appearing before the amount refer to currencies, while non-joined symbols appearing after the amount refer to commodities. Here are some valid currency and commodity specifiers:

<div class="smallexample">

<pre class="smallexample">$20.00         ; currency: twenty US dollars
40 AAPL        ; commodity: 40 shares of Apple stock
60 DM          ; currency: 60 Deutsch Mark
£50            ; currency: 50 British pounds
50 EUR         ; currency: 50 Euros (or use appropriate symbol)
</pre>

</div>

Ledger will examine the first use of any commodity to determine how that commodity should be printed on reports. It pays attention to whether the name of commodity was separated from the amount, whether it came before or after, the precision used in specifying the amount, whether thousand marks were used, etc. This is done so that printing the commodity looks the same as the way you use it.

An account may contain multiple commodities, in which case it will have separate totals for each. For example, if your brokerage account contains both cash, gold, and several stock quantities, the balance might look like:

<div class="smallexample">

<pre class="smallexample">  $200.00
100.00 AU
  AAPL 40
 BORL 100
 FEQTX 50  Assets:Brokerage
</pre>

</div>

This balance report shows how much of each commodity is in your brokerage account.

Sometimes, you will want to know the current street value of your balance, and not the commodity totals. For this to happen, you must specify what the current price is for each commodity. The price can be any commodity, in which case the balance will be computed in terms of that commodity. The usual way to specify prices is with a price history file, which might look like this:

<div class="smallexample">

<pre class="smallexample">P 2004/06/21 02:18:01 FEQTX $22.49
P 2004/06/21 02:18:01 BORL $6.20
P 2004/06/21 02:18:02 AAPL $32.91
P 2004/06/21 02:18:02 AU $400.00
</pre>

</div>

<a name="index-_002d_002dprice_002ddb-FILE"></a><a name="index-_002d_002dmarket"></a>

Specify the price history to use with the <samp>--price-db <var>FILE</var></samp> option, with the <samp>--market (-V)</samp> option to report in terms of current market value:

<div class="smallexample">

<pre class="smallexample">$ ledger --price-db prices.db -V balance brokerage
</pre>

</div>

The balance for your brokerage account will be reported in US dollars, since the prices database uses that currency.

<div class="smallexample">

<pre class="smallexample">$40880.00  Assets:Brokerage
</pre>

</div>

You can convert from any commodity to any other commodity. Let’s say you had $5000 in your checking account, and for whatever reason you wanted to know many ounces of gold that would buy, in terms of the current price of gold:

<div class="smallexample">

<pre class="smallexample">$ ledger -T "{1 AU}*(O/P{1 AU})" balance checking
</pre>

</div>

Although the total expression appears complex, it is simply saying that the reported total should be in multiples of AU units, where the quantity is the account total divided by the price of one AU. Without the initial multiplication, the reported total would still use the dollars commodity, since multiplying or dividing amounts always keeps the left value’s commodity. The result of this command might be:

<div class="smallexample">

<pre class="smallexample">14.01 AU  Assets:Checking
</pre>

</div>

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Commodity price histories](#Commodity-price-histories):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Commodity equivalences](#Commodity-equivalences):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Commodity-price-histories"></a>

<div class="header">

Next: [Commodity equivalences](#Commodity-equivalences), Previous: [Commodities and Currencies](#Commodities-and-Currencies), Up: [Commodities and Currencies](#Commodities-and-Currencies)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Commodity-price-histories-1"></a>

#### 3.4.1 Commodity price histories

Whenever a commodity is purchased using a different commodity (such as a share of common stock using dollars), it establishes a price for that commodity on that day. It is also possible, by recording price details in a ledger file, to specify other prices for commodities at any given time. Such price transactions might look like those below:

<div class="smallexample">

<pre class="smallexample">P 2004/06/21 02:17:58 TWCUX $27.76
P 2004/06/21 02:17:59 AGTHX $25.41
P 2004/06/21 02:18:00 OPTFX $39.31
P 2004/06/21 02:18:01 FEQTX $22.49
P 2004/06/21 02:18:02 AAPL $32.91
</pre>

</div>

By default, ledger will not consider commodity prices when generating its various reports. It will always report balances in terms of the commodity total, rather than the current value of those commodities. To enable pricing reports, use one of the commodity reporting options.

* * *

<a name="Commodity-equivalences"></a>

<div class="header">

Previous: [Commodity price histories](#Commodity-price-histories), Up: [Commodities and Currencies](#Commodities-and-Currencies)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Commodity-equivalences-1"></a>

#### 3.4.2 Commodity equivalences

Sometimes a commodity has several forms which are all equivalent. An example of this is time. Whether tracked in terms of minutes, hours or days, it should be possible to convert between the various forms. Doing this requires the use of commodity equivalences.

For example, you might have the following two postings, one which transfers an hour of time into a ‘<samp>Billable</samp>’ account, and another which decreases the same account by ten minutes. The resulting report will indicate that fifty minutes remain:

<div class="smallexample">

<pre class="smallexample">2005/10/01 Work done for company
    Billable:Client                 1h
    Project:XYZ

2005/10/02 Return ten minutes to the project
    Project:XYZ                    10m
    Billable:Client
</pre>

</div>

Reporting the balance for this ledger file produces:

<div class="smallexample">

<pre class="smallexample">$ ledger --no-total balance Billable Project
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">               50.0m  Billable:Client
              -50.0m  Project:XYZ
</pre>

</div>

<a name="index-C"></a>

This example works because ledger already knows how to handle seconds, minutes and hours, as part of its time tracking support. Defining other equivalences is simple. The following is an example that creates data equivalences, helpful for tracking bytes, kilobytes, megabytes, and more:

<div class="smallexample">

<pre class="smallexample">C 1.00 Kb = 1024 b
C 1.00 Mb = 1024 Kb
C 1.00 Gb = 1024 Mb
C 1.00 Tb = 1024 Gb
</pre>

</div>

Each of these definitions correlates a commodity (such as ‘<samp>Kb</samp>’) and a default precision, with a certain quantity of another commodity. In the above example, kilobytes are reported with two decimal places of precision and each kilobyte is equal to 1024 bytes.

Equivalence chains can be as long as desired. Whenever a commodity would report as a decimal amount (less than ‘<samp>1.00</samp>’), the next smallest commodity is used. If a commodity could be reported in terms of a higher commodity without resulting to a partial fraction, then the larger commodity is used.

* * *

<a name="Accounts-and-Inventories"></a>

<div class="header">

Next: [Understanding Equity](#Understanding-Equity), Previous: [Commodities and Currencies](#Commodities-and-Currencies), Up: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Accounts-and-Inventories-1"></a>

### 3.5 Accounts and Inventories

Since Ledger’s accounts and commodity system is so flexible, you can have accounts that don’t really exist, and use commodities that no one else recognizes. For example, let’s say you are buying and selling various items in EverQuest, and want to keep track of them using a ledger. Just add items of whatever quantity you wish into your EverQuest account:

<div class="smallexample">

<pre class="smallexample">9/29  Get some stuff at the Inn
    Places:Black's Tavern                   -3 Apples
    Places:Black's Tavern                   -5 Steaks
    EverQuest:Inventory
</pre>

</div>

Now your EverQuest:Inventory has 3 apples and 5 steaks in it. The amounts are negative, because you are taking _from_ Black’s Tavern in order to add to your Inventory account. Note that you don’t have to use ‘<samp>Places:Black's Tavern</samp>’ as the source account. You could use ‘<samp>EverQuest:System</samp>’ to represent the fact that you acquired them online. The only purpose for choosing one kind of source account over another is to generate more informative reports later on. The more you know, the better the analysis you can perform.

If you later sell some of these items to another player, the transaction would look like:

<div class="smallexample">

<pre class="smallexample">10/2  Sturm Brightblade
    EverQuest:Inventory                     -2 Steaks
    EverQuest:Inventory                     15 Gold
</pre>

</div>

Now you’ve turned 2 steaks into 15 gold, courtesy of your customer, Sturm Brightblade.

<div class="smallexample">

<pre class="smallexample">$ ledger balance EverQuest
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">            3 Apples
             15 Gold
            3 Steaks  EverQuest:Inventory
</pre>

</div>

* * *

<a name="Understanding-Equity"></a>

<div class="header">

Next: [Dealing with Petty Cash](#Dealing-with-Petty-Cash), Previous: [Accounts and Inventories](#Accounts-and-Inventories), Up: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Understanding-Equity-1"></a>

### 3.6 Understanding Equity

The most confusing transaction in any ledger will be your equity account—because starting balances can’t come out of nowhere.

When you first start your ledger, you will likely already have money in some of your accounts. Let’s say there’s $100 in your checking account; then add a transaction to your ledger to reflect this amount. Where will the money come from? The answer: your equity.

<div class="smallexample">

<pre class="smallexample">10/2  Opening Balance
    Assets:Checking                         $100.00
    Equity:Opening Balances
</pre>

</div>

But what is equity? You may have heard of equity when people talked about house mortgages, as “the part of the house that you own”. Basically, equity is like the value of something. If you own a car worth $5000, then you have $5000 in equity in that car. In order to turn that car (a commodity) into a cash flow, or a credit to your bank account, you will have to debit the equity by selling it.

When you start a ledger, you are probably already worth something. Your net worth is your current equity. By transferring the money in the ledger from your equity to your bank accounts, you are crediting the ledger account based on your prior equity. That is why, when you look at the balance report, you will see a large negative number for Equity that never changes: Because that is what you were worth (what you debited from yourself in order to start the ledger) before the money started moving around. If the total positive value of your assets is greater than the absolute value of your starting equity, it means you are making money.

Clear as mud? Keep thinking about it. Until you figure it out, put `not Equity` at the end of your balance command, to remove the confusing figure from the total.

* * *

<a name="Dealing-with-Petty-Cash"></a>

<div class="header">

Next: [Working with multiple funds and accounts](#Working-with-multiple-funds-and-accounts), Previous: [Understanding Equity](#Understanding-Equity), Up: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Dealing-with-Petty-Cash-1"></a>

### 3.7 Dealing with Petty Cash

Something that stops many people from keeping a ledger at all is the insanity of tracking small cash expenses. They rarely generate a receipt, and there are often a lot of small postings, rather than a few large ones, as with checks.

One solution is: don’t bother. Move your spending to a debit card, but in general ignore cash. Once you withdraw it from the ATM, mark it as already spent to an ‘<samp>Expenses:Cash</samp>’ category:

<div class="smallexample">

<pre class="smallexample">2004/03/15 ATM
    Expenses:Cash                      $100.00
    Assets:Checking
</pre>

</div>

If at some point you make a large cash expense that you want to track, just _move_ the amount of the expense from ‘<samp>Expenses:Cash</samp>’ into the target account:

<div class="smallexample">

<pre class="smallexample">2004/03/20 Somebody
    Expenses:Food                       $65.00
    Expenses:Cash
</pre>

</div>

This way, you can still track large cash expenses, while ignoring all of the smaller ones.

* * *

<a name="Working-with-multiple-funds-and-accounts"></a>

<div class="header">

Previous: [Dealing with Petty Cash](#Dealing-with-Petty-Cash), Up: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Working-with-multiple-funds-and-accounts-1"></a>

### 3.8 Working with multiple funds and accounts

There are situations when the accounts you’re tracking are different between your clients and the financial institutions where money is kept. An example of this is working as the treasurer for a religious institution. From the secular point of view, you might be working with three different accounts:

*   Checking
*   Savings
*   Credit Card

From a religious point of view, the community expects to divide its resources into multiple “funds”, from which it makes purchases or reserves resources for later:

*   School fund
*   Building fund
*   Community fund

The problem with this kind of setup is that, when you spend money, it comes from two or more places at once: the account and the fund. And yet, the correlation of amounts between funds and accounts is rarely one-to-one. What if the school fund has ‘<samp>$500.00</samp>’, but ‘<samp>$400.00</samp>’ of that comes from Checking, and ‘<samp>$100.00</samp>’ from Savings?

Traditional finance packages require that the money reside in only one place. But there are really two “views” of the data: from the account point of view and from the fund point of view—yet both sets should reflect the same overall expenses and cash flow. It’s simply where the money resides that differs.

This situation can be handled one of two ways. The first is using virtual postings to represent the fact that money is moving to and from two kind of accounts at the same time:

<div class="smallexample">

<pre class="smallexample">2004/03/20 Contributions
    Assets:Checking                    $500.00
    Income:Donations

2004/03/25 Distribution of donations
    [Funds:School]                     $300.00
    [Funds:Building]                   $200.00
    [Assets:Checking]                 $-500.00
</pre>

</div>

The use of square brackets in the second transaction ensures that the virtual postings balance to zero. Now money can be spent directly from a fund at the same time as money is drawn from a physical account:

<div class="smallexample">

<pre class="smallexample">2004/03/25 Payment for books (paid from Checking)
    Expenses:Books                    $100.00
    Assets:Checking                  $-100.00
    (Funds:School)                   $-100.00
</pre>

</div>

When reports are generated, by default they’ll appear in terms of the funds. In this case, you will likely want to mask out your ‘<samp>Assets</samp>’ account, because otherwise the balance won’t make much sense:

<div class="smallexample">

<pre class="smallexample">$ ledger --no-total bal not ^Assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">             $100.00  Expenses:Books
             $400.00  Funds
             $200.00    Building
             $200.00    School
            $-500.00  Income:Donations
</pre>

</div>

<a name="index-_002d_002dreal"></a>

If the <samp>--real</samp> option is used, the report will be in terms of the real accounts:

<div class="smallexample">

<pre class="smallexample">$ ledger --real --no-total bal
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">             $400.00  Assets:Checking
             $100.00  Expenses:Books
            $-500.00  Income:Donations
</pre>

</div>

If more asset accounts are needed as the source of a posting, just list them as you would normally, for example:

<div class="smallexample">

<pre class="smallexample">2004/03/25 Payment for books (paid from Checking)
    Expenses:Books                    $100.00
    Assets:Checking                   $-50.00
    Liabilities:Credit Card           $-50.00
    (Funds:School)                   $-100.00
</pre>

</div>

The second way of tracking funds is to use transaction codes. In this respect the codes become like virtual accounts that embrace the entire set of postings. Basically, we are associating a transaction with a fund by setting its code. Here are two transactions that deposit money into, and spend money from, the ‘<samp>Funds:School</samp>’ fund:

<div class="smallexample">

<pre class="smallexample">2004/03/25 (Funds:School) Donations
    Assets:Checking                   $100.00
    Income:Donations

2004/03/25 (Funds:Building) Donations
    Assets:Checking                   $20.00
    Income:Donations

2004/04/25 (Funds:School) Payment for books
    Expenses:Books                     $50.00
    Assets:Checking
</pre>

</div>

Note how the accounts now relate only to the real accounts, and any balance or register reports will reflect this. That the transactions relate to a particular fund is kept only in the code.

<a name="index-_002d_002dpayee_003dcode"></a><a name="index-_002d_002dby_002dpayee"></a>

How does this become a fund report? By using the <samp>--payee=code</samp> option, you can generate a register report where the payee for each posting shows the code. Alone, this is not terribly interesting; but when combined with the <samp>--by-payee (-P)</samp> option, you will now see account subtotals for any postings related to a specific fund. So, to see the current monetary balances of all funds, the command would be:

<div class="smallexample">

<pre class="smallexample">$ ledger --payee=code -P reg ^Assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">04-Mar-25 Funds:Building        Assets:Checking              $20.00       $20.00
04-Mar-25 Funds:School          Assets:Checking              $50.00       $70.00
</pre>

</div>

Or to see a particular fund’s expenses, the ‘<samp>School</samp>’ fund in this case:

<div class="smallexample">

<pre class="smallexample">$ ledger --payee=code -P reg ^Expenses and code School
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">04-Apr-25 Funds:School          Expenses:Books               $50.00       $50.00
</pre>

</div>

Both approaches yield different kinds of flexibility, depending on how you prefer to think of your funds: as virtual accounts, or as tags associated with particular transactions. Your own tastes will decide which is best for your situation.

* * *

<a name="Keeping-a-Journal"></a>

<div class="header">

Next: [Transactions](#Transactions), Previous: [Principles of Accounting with Ledger](#Principles-of-Accounting-with-Ledger), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Keeping-a-Journal-1"></a>

## 4 Keeping a Journal

The most important part of accounting is keeping a good journal. If you have a good journal, tools can be written to work whatever mathematical tricks you need to better understand your spending patterns. Without a good journal, no tool, however smart, can help you.

The Ledger program aims at making journal transactions as simple as possible. Since it is a command-line tool, it does not provide a user interface for keeping a journal. If you require an user interface to maintain journal transactions GnuCash is a good alternative.

If you are not using GnuCash, but a text editor to maintain your journal, read on. Ledger has been designed to make data transactions as simple as possible, by keeping the journal format easy, and also by automagically determining as much information as possible based on the nature of your transactions.

For example, you do not need to tell Ledger about the accounts you use. Any time Ledger sees a posting involving an account it knows nothing about, it will create it[<sup>2</sup>](#FOOT2). If you use a commodity that is new to Ledger, it will create that commodity, and determine its display characteristics (placement of the symbol before or after the amount, display precision, etc.) based on how you used the commodity in the posting.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [The Most Basic Entry](#The-Most-Basic-Entry):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Starting up](#Starting-up):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Structuring your Accounts](#Structuring-your-Accounts):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Commenting on your Journal](#Commenting-on-your-Journal):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Currency and Commodities](#Currency-and-Commodities):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Keeping it Consistent](#Keeping-it-Consistent):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Journal Format](#Journal-Format):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Converting from other formats](#Converting-from-other-formats):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Archiving Previous Years](#Archiving-Previous-Years):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="The-Most-Basic-Entry"></a>

<div class="header">

Next: [Starting up](#Starting-up), Previous: [Keeping a Journal](#Keeping-a-Journal), Up: [Keeping a Journal](#Keeping-a-Journal)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-Most-Basic-Entry-1"></a>

### 4.1 The Most Basic Entry

Here is the Pacific Bell example from above, given as a Ledger posting, with the addition of a check number:

<div class="smallexample">

<pre class="smallexample">9/29 (1023) Pacific Bell
    Expenses:Utilities:Phone                   $23.00
    Assets:Checking                           $-23.00
</pre>

</div>

As you can see, it is very similar to what would be written on paper, minus the computed balance totals, and adding in account names that work better with Ledger’s scheme of things. In fact, since Ledger is smart about many things, you don’t need to specify the balanced amount, if it is the same as the first line:

<div class="smallexample">

<pre class="smallexample">9/29 (1023) Pacific Bell
    Expenses:Utilities:Phone                   $23.00
    Assets:Checking
</pre>

</div>

For this transaction, Ledger will figure out that $-23.00 must come from ‘<samp>Assets:Checking</samp>’ in order to balance the transaction.

Also note the structure of the account entries. There is an implied hierarchy established by separating with colons (see [Structuring your Accounts](#Structuring-your-Accounts)).

<a name="index-spaces-in-postings"></a><a name="index-posting-format-details"></a>

**The format is very flexible and it isn’t necessary that you indent and space out things exactly as shown. The only requirements are that the start of the transaction (the date typically) is at the beginning of the first line of the transaction, and the accounts are indented by at least one space. If you omit the leading spaces in the account lines Ledger will generate an error. There must be at least two spaces, or a tab, between the amount and the account. If you do not have adequate separation between the amount and the account Ledger will give an error and stop calculating.**

* * *

<a name="Starting-up"></a>

<div class="header">

Next: [Structuring your Accounts](#Structuring-your-Accounts), Previous: [The Most Basic Entry](#The-Most-Basic-Entry), Up: [Keeping a Journal](#Keeping-a-Journal)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Starting-up-1"></a>

### 4.2 Starting up

<a name="index-initial-equity"></a><a name="index-beginning-ledger"></a><a name="index-opening-balance"></a>

Unless you have recently arrived from another planet, you already have a financial state. You need to capture that financial state so that Ledger has a starting point.

At some convenient point in time you knew the balances and outstanding obligation of every financial account you have. Those amounts form the basis of the opening entry for ledger. For example if you chose the beginning of 2011 as the date to start tracking finances with ledger, your opening balance entry could look like this:

<div class="smallexample">

<pre class="smallexample">2011/01/01 * Opening Balance
    Assets:Joint Checking                   $800.14
    Assets:Other Checking                    $63.44
    Assets:Savings                         $2805.54
    Assets:Investments:401K:Deferred         100.0000 VIFSX @ $80.5227
    Assets:Investments:401K:Matching          50.0000 VIFSX @ $83.7015
    Assets:Investments:IRA                   250.0000 VTHRX @ $20.5324
    Liabilities:Mortgage                $-175634.88
    Liabilities:Car Loan                  $-3494.26
    Liabilities:Visa                      -$1762.44
    Equity:Opening Balances
</pre>

</div>

There is nothing special about the name “Opening Balances” as the payee of the account name, anything convenient that you understand will work.

* * *

<a name="Structuring-your-Accounts"></a>

<div class="header">

Next: [Commenting on your Journal](#Commenting-on-your-Journal), Previous: [Starting up](#Starting-up), Up: [Keeping a Journal](#Keeping-a-Journal)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Structuring-your-Accounts-1"></a>

### 4.3 Structuring your Accounts

<a name="index-accounts_002c-naming"></a><a name="index-naming-accounts"></a>

There really are no requirements for how you do this, but to preserve your sanity we suggest some very basic structure to your accounting system.

At the highest level you have five sorts of accounts:

1.  Expenses: where money goes,
2.  Assets: where money sits,
3.  Income: where money comes from,
4.  Liabilities: money you owe,
5.  Equity: the real value of your property.

Starting the structure off this way will make it simpler for you to get answers to the questions you really need to ask about your finances.

Beneath these top level accounts you can have any level of detail you desire. For example, if you want to keep specific track of how much you spend on burgers and fries, you could have the following:

<div class="smallexample">

<pre class="smallexample">Expenses:Food:Hamburgers and Fries
</pre>

</div>

* * *

<a name="Commenting-on-your-Journal"></a>

<div class="header">

Next: [Currency and Commodities](#Currency-and-Commodities), Previous: [Structuring your Accounts](#Structuring-your-Accounts), Up: [Keeping a Journal](#Keeping-a-Journal)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Commenting-on-your-Journal-1"></a>

### 4.4 Commenting on your Journal

<a name="index-comments_002c-characters"></a><a name="index-block-comments"></a><a name="index-comments_002c-block"></a>

Comments are generally started using a ‘<samp>;</samp>’. However, in order to increase compatibility with other text manipulation programs and methods, four additional comment characters are valid if used at the beginning of a line: ‘<samp>#</samp>’, ‘<samp>|</samp>’, and ‘<samp>*</samp>’ and ‘<samp>%</samp>’.

Block comments can be made by use `comment` ... `end comment`.

<div class="smallexample">

<pre class="smallexample">; This is a single line comment,
#  and this,
%   and this,
|    and this,
*     and this.

comment
    This is a block comment with
    multiple lines
end comment
</pre>

</div>

There are several forms of comments within a transaction, for example:

<div class="smallexample">

<pre class="smallexample">; this is a global comment that is not applied to a specific transaction
; it can start with any of the five characters but is not included in the
; output from 'print' or 'output'

2011/12/11  Something Sweet
    ; German Chocolate Cake
    ; :Broke Diet:
    Expenses:Food                  $10.00 ; Friends: The gang
    Assets:Credit Union:Checking
</pre>

</div>

The first comment is global and Ledger will not attach it to any specific transactions. The comments within the transaction must all start with ‘<samp>;</samp>’ and are preserved as part of the transaction. The ‘<samp>:</samp>’ indicates meta-data and tags (see [Metadata](#Metadata)).

* * *

<a name="Currency-and-Commodities"></a>

<div class="header">

Next: [Keeping it Consistent](#Keeping-it-Consistent), Previous: [Commenting on your Journal](#Commenting-on-your-Journal), Up: [Keeping a Journal](#Keeping-a-Journal)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Currency-and-Commodities-1"></a>

### 4.5 Currency and Commodities

<a name="index-currency"></a><a name="index-commodity"></a>

Ledger is agnostic when it comes to how you value your accounts. Dollars, Euros, Pounds, Francs, Shares etc. are all just “commodities”. Holdings in stocks, bonds, mutual funds and other financial instruments can be labeled using whatever is convenient for you (stock ticker symbols are suggested for publicly traded assets).[<sup>3</sup>](#FOOT3)

For the rest of this manual, we will only use the word “commodities” when referring to the units on a transaction value.

This is fundamentally different than many common accounting packages, which assume the same currency throughout all of your accounts. This means if you typically operate in Euros, but travel to the US and have some expenses, you would have to do the currency conversion _before_ you made the entry into your financial system. With ledger this is not required. In the same journal you can have entries in any or all commodities you actually hold. You can use the reporting capabilities to convert all commodities to a single commodity for reporting purposes without ever changing the underlying entry.

For example, the following entries reflect transactions made for a business trip to Europe from the US:

<div class="smallexample">

<pre class="smallexample">2011/09/23 Cash in Munich
    Assets:Cash                               €50.00
    Assets:Checking                          $-66.00

2011/09/24 Dinner in Munich
    Expenses:Business:Travel                  €35.00
    Assets:Cash
</pre>

</div>

This says that $66.00 came out of checking and turned into 50 Euros. The implied exchange rate was $1.32\. Then 35.00 Euros were spent on Dinner in Munich.

Running a ledger balance report shows:

<div class="smallexample">

<pre class="smallexample">$ ledger -f example.dat bal
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">             $-66.00
              €15.00  Assets
              €15.00    Cash
             $-66.00    Checking
              €35.00  Expenses:Business:Travel
--------------------
             $-66.00
              €50.00
</pre>

</div>

The top two lines show my current assets as $-66.00 in checking (in this very short example I didn’t establish opening an opening balance for the checking account) and €15.00\. After spending on dinner I have €15.00 in my wallet. The bottom line balances to zero, but is shown in two lines since we haven’t told ledger to convert commodities.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Naming Commodities](#Naming-Commodities):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Buying and Selling Stock](#Buying-and-Selling-Stock):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Fixing Lot Prices](#Fixing-Lot-Prices):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Complete control over commodity pricing](#Complete-control-over-commodity-pricing):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Naming-Commodities"></a>

<div class="header">

Next: [Buying and Selling Stock](#Buying-and-Selling-Stock), Previous: [Currency and Commodities](#Currency-and-Commodities), Up: [Currency and Commodities](#Currency-and-Commodities)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Naming-Commodities-1"></a>

#### 4.5.1 Naming Commodities

Commodity names can have any character, including white-space. However, if you include white-space or numeric characters, the commodity name must be enclosed in double quotes ‘<samp>"</samp>’:

<div class="smallexample">

<pre class="smallexample">1999/06/09 ! Achat
    Actif:SG PEE STK         49.957 "Arcancia Équilibre 454"
    Actif:SG PEE STK      $-234.90

2000/12/08 ! Achat
    Actif:SG PEE STK        215.796 "Arcancia Équilibre 455"
    Actif:SG PEE STK    $-10742.54
</pre>

</div>

* * *

<a name="Buying-and-Selling-Stock"></a>

<div class="header">

Next: [Fixing Lot Prices](#Fixing-Lot-Prices), Previous: [Naming Commodities](#Naming-Commodities), Up: [Currency and Commodities](#Currency-and-Commodities)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Buying-and-Selling-Stock-1"></a>

#### 4.5.2 Buying and Selling Stock

<a name="index-buying-stock"></a>

Buying stock is a typical example that many will use that involves multiple commodities in the same transaction. The type of the share (AAPL for Apple Inc.) and the share purchase price in the currency unit you made the purchase in ($ for AAPL). Yes, the typical convention is as follows:

<div class="smallexample">

<pre class="smallexample">2004/05/01 Stock purchase
    Assets:Broker                     50 AAPL @ $30.00
    Expenses:Broker:Commissions        $19.95
    Assets:Broker                  $-1,519.95
</pre>

</div>

This assumes you have a brokerage account that is capable of managing both liquid and commodity assets. Now, on the day of the sale:

<div class="smallexample">

<pre class="smallexample">2005/08/01 Stock sale
    Assets:Broker                    -50 AAPL {$30.00} @ $50.00
    Expenses:Broker:Commissions        $19.95
    Income:Capital Gains           $-1,000.00
    Assets:Broker                   $2,480.05
</pre>

</div>

You can, of course, elide the amount of the last posting. It is there for clarity’s sake.

The ‘<samp>{$30.00}</samp>’ is a lot price. You can also use a lot date, ‘<samp>[2004/05/01]</samp>’, or both, in case you have several lots of the same price/date and your taxation model is based on longest-held-first.

* * *

<a name="Fixing-Lot-Prices"></a>

<div class="header">

Next: [Complete control over commodity pricing](#Complete-control-over-commodity-pricing), Previous: [Buying and Selling Stock](#Buying-and-Selling-Stock), Up: [Currency and Commodities](#Currency-and-Commodities)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Fixing-Lot-Prices-1"></a>

#### 4.5.3 Fixing Lot Prices

<a name="index-fixing-lot-prices"></a><a name="index-consumable-commodity-pricing"></a>

Commodities that you keep in order to sell at a later time have a variable value that fluctuates with the market prices. Commodities that you consume should not fluctuate in value, but stay at the lot price they were purchased at. As an extension of “lot pricing”, you can fix the per-unit price of a commodity.

For example, say you buy 10 gallons of gas at $1.20\. In future “value” reports, you don’t want these gallons reported in terms of today’s price, but rather the price when you bought it. At the same time, you also want other kinds of commodities—like stocks— reported in terms of today’s price.

This is supported as follows:

<div class="smallexample">

<pre class="smallexample">2009/01/01 Shell
    Expenses:Gasoline             11 GAL {=$2.299}
    Assets:Checking
</pre>

</div>

This transaction actually introduces a new commodity, ‘<samp>GAL {=$2.29}</samp>’, whose market value disregards any future changes in the price of gasoline.

If you do not want price fixing, you can specify this same transaction in one of two ways, both equivalent (note the lack of the equal sign compared to the transaction above):

<div class="smallexample">

<pre class="smallexample">2009/01/01 Shell
    Expenses:Gasoline             11 GAL {$2.299}
    Assets:Checking

2009/01/01 Shell
    Expenses:Gasoline             11 GAL @ $2.299
    Assets:Checking
</pre>

</div>

There is no difference in meaning between these two forms. Why do both exist, you ask? To support things like this:

<div class="smallexample">

<pre class="smallexample">2009/01/01 Shell
    Expenses:Gasoline             11 GAL {=$2.299} @ $2.30
    Assets:Checking
</pre>

</div>

This transaction says that you bought 11 gallons priced at $2.299 per gallon at a _cost to you_ of $2.30 per gallon. Ledger auto-generates a balance posting in this case to Equity:Capital Losses to reflect the 1.1 cent difference, which is then balanced by Assets:Checking because its amount is null.

* * *

<a name="Complete-control-over-commodity-pricing"></a>

<div class="header">

Previous: [Fixing Lot Prices](#Fixing-Lot-Prices), Up: [Currency and Commodities](#Currency-and-Commodities)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Complete-control-over-commodity-pricing-1"></a>

#### 4.5.4 Complete control over commodity pricing

<a name="index-_002d_002dmarket-1"></a><a name="index-_002d_002dexchange-COMMODITY"></a>

Ledger allows you to have very detailed control over how your commodities are valued. You can fine tune the results given using the <samp>--market</samp> or <samp>--exchange <var>COMMODITY</var></samp> options. There are now several points of interception; you can specify the valuation method:

1.  on a commodity itself,
2.  on a posting, via metadata (effect is largely the same as #1),
3.  on an xact, which then applies to all postings in that xact,
4.  on any posting via an automated transaction,
5.  on a per-account basis,
6.  on a per-commodity basis,
7.  by changing the journal default of `market`.

Fixated pricing (such as ‘<samp>{=$20}</samp>’) still plays a role in this scheme. As far as valuation goes, it’s shorthand for writing ‘<samp>((s,d,t -> market($20,d,t)))</samp>’.

A valuation function receives three arguments:

<dl compact="compact">

<dt>`source`</dt>

<dd>

A string identifying the commodity whose price is being asked for (example: ‘<samp>EUR</samp>’).

</dd>

<dt>`date`</dt>

<dd>

The reference date the price should be relative.

</dd>

<dt>`target`</dt>

<dd>

A string identifying the “target” commodity, or the commodity the returned price should be in. This argument is null if <samp>--market</samp> was used instead of <samp>--exchange <var>COMMODITY</var></samp>.

</dd>

</dl>

The valuation function should return an amount. If you’ve written your function in Python, you can return something like ‘<samp>Amount("$100")</samp>’. If the function returns an explicit value, that value is always used, regardless of the commodity, the date, or the desired target commodity. For example,

<div class="smallexample">

<pre class="smallexample">define myfunc_seven(s, d, t) = 7 EUR
</pre>

</div>

In order to specify a fixed price, but still valuate that price into the target commodity, use something like this:

<div class="smallexample">

<pre class="smallexample">define myfunc_five(s, d, t) = market(5 EUR, d, t)
</pre>

</div>

The `value` directive sets the valuation used for all commodities used in the rest of the data stream. This is the fallback, if nothing more specific is found.

<div class="smallexample">

<pre class="smallexample">value myfunc_seven
</pre>

</div>

You can set a specific valuation function on a per-commodity basis. Instead of defining a function, you can also pass a lambda.

<div class="smallexample">

<pre class="smallexample">commodity $
    value s, d, t -> 6 EUR
</pre>

</div>

Each account can also provide a default valuation function for any commodities transferred to that account.

<div class="smallexample">

<pre class="smallexample">account Expenses:Food5
    value myfunc_five
</pre>

</div>

The metadata field ‘<samp>Value</samp>’, if found, overrides the valuation function on a transaction-wide or per-posting basis.

<div class="smallexample">

<pre class="smallexample">= @XACT and Food
    ; Value:: 8 EUR
    (Equity)                     $1

= @POST and Dining
    (Expenses:Food9)             $1
        ; Value:: 9 EUR
</pre>

</div>

Lastly, you can specify the valuation function/value for any specific amount using the ‘<samp>(( ))</samp>’ commodity annotation.

<div class="smallexample">

<pre class="smallexample">2012-03-02 KFC
    Expenses:Food2               $1 ((2 EUR))
    Assets:Cash2

2012-03-03 KFC
    Expenses:Food3               $1
        ; Value:: 3 EUR
    Assets:Cash3

2012-03-04 KFC
    ; Value:: 4 EUR
    Expenses:Food4               $1
    Assets:Cash4

2012-03-05 KFC
    Expenses:Food5               $1
    Assets:Cash5

2012-03-06 KFC
    Expenses:Food6               $1
    Assets:Cash6

2012-03-07 KFC
    Expenses:Food7                1 CAD
    Assets:Cas7

2012-03-08 XACT
    Expenses:Food8               $1
    Assets:Cash8

2012-03-09 POST
    Expenses:Dining9             $1
    Assets:Cash9
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">$ ledger reg -V food
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">12-Mar-02 KFC                   Expenses:Food2                2 EUR        2 EUR
12-Mar-03 KFC                   Expenses:Food3                3 EUR        5 EUR
12-Mar-04 KFC                   Expenses:Food4                4 EUR        9 EUR
12-Mar-05 KFC                   Expenses:Food5                   $1           $1
                                                                           9 EUR
12-Mar-06 KFC                   Expenses:Food6                   $1           $2
                                                                           9 EUR
12-Mar-07 KFC                   Expenses:Food7                1 CAD           $2
                                                                           1 CAD
                                                                           9 EUR
12-Mar-08 XACT                  Expenses:Food8                   $1           $3
                                                                           1 CAD
                                                                           9 EUR
</pre>

</div>

* * *

<a name="Keeping-it-Consistent"></a>

<div class="header">

Next: [Journal Format](#Journal-Format), Previous: [Currency and Commodities](#Currency-and-Commodities), Up: [Keeping a Journal](#Keeping-a-Journal)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Keeping-it-Consistent-1"></a>

### 4.6 Keeping it Consistent

<a name="index-_002d_002dstrict"></a><a name="index-accounts"></a>

Sometimes Ledger’s flexibility can lead to difficulties. Using a freeform text editor to enter transactions makes it easy to keep the data, but also easy to enter accounts or payees inconsistently or with spelling errors.

In order to combat inconsistency you can define allowable accounts and payees. For simplicity, create a separate text file and define accounts and payees like

<div class="smallexample">

<pre class="smallexample">account Expenses
account Expenses:Utilities
</pre>

</div>

Using the <samp>--strict</samp> option will cause Ledger to complain if any accounts are not previously defined:

If you have a large Ledger register already created use the `accounts` command to get started:

    $ ledger accounts >> Accounts.dat

* * *

<a name="Journal-Format"></a>

<a name="Journal-Format-1"></a>

### 4.7 Journal Format

The ledger file format is quite simple, but also very flexible. It supports many options, though typically the user can ignore most of them. They are summarized below.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Transactions and Comments](#Transactions-and-Comments):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Command Directives](#Command-Directives):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Transactions-and-Comments"></a>

<div class="header">

Next: [Command Directives](#Command-Directives), Previous: [Journal Format](#Journal-Format), Up: [Journal Format](#Journal-Format)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Transactions-and-Comments-1"></a>

#### 4.7.1 Transactions and Comments

The initial character of each line determines what the line means, and how it should be interpreted. Allowable initial characters are:

<dl compact="compact">

<dt>`NUMBER`</dt>

<dd>

A line beginning with a number denotes a transaction. It may be followed by any number of lines, each beginning with white-space, to denote the transaction’s account postings. The format of the first line is:

<div class="smallexample">

<pre class="smallexample">DATE[=EDATE] [*|!] [(CODE)] DESC
</pre>

</div>

If ‘<samp>*</samp>’ appears after the date (with optional effective date), it indicates the transaction is “cleared”, which can mean whatever the user wants it to mean. If ‘<samp>!</samp>’ appears after the date, it indicates the transaction is “pending”; i.e., tentatively cleared from the user’s point of view, but not yet actually cleared. If a `CODE` appears in parentheses, it may be used to indicate a check number, or the type of the posting. Following these is the payee, or a description of the posting.

The format of each following posting is:

<div class="smallexample">

<pre class="smallexample">  ACCOUNT  AMOUNT  [; NOTE]
</pre>

</div>

The `ACCOUNT` may be surrounded by parentheses if it is a virtual posting, or square brackets if it is a virtual posting that must balance. The `AMOUNT` can be followed by a per-unit posting cost, by specifying `@ AMOUNT`, or a complete posting cost with `@@ AMOUNT`. Lastly, the `NOTE` may specify an actual and/or effective date for the posting by using the syntax `[ACTUAL_DATE]` or `[=EFFECTIVE_DATE]` or `[ACTUAL_DATE=EFFECTIVE_DATE]` (see [Virtual postings](#Virtual-postings)).

</dd>

<dt>`P`</dt>

<dd><a name="index-_002d_002ddownload"></a><a name="index-P"></a><a name="index-historical-prices"></a>

Specifies a historical price for a commodity. These are usually found in a pricing history file (see the <samp>--download (-Q)</samp> option). The syntax is:

<div class="smallexample">

<pre class="smallexample">P DATE SYMBOL PRICE
</pre>

</div>

</dd>

<dt>`=`</dt>

<dd><a name="index-_003d"></a><a name="index-automated-transaction"></a><a name="index-transaction_002c-automated"></a>

An automated transaction. A value expression must appear after the equal sign.

After this initial line there should be a set of one or more postings, just as if it were a normal transaction. If the amounts of the postings have no commodity, they will be applied as multipliers to whichever real posting is matched by the value expression (see [Automated Transactions](#Automated-Transactions)).

</dd>

<dt>`~`</dt>

<dd><a name="index-_007e"></a><a name="index-periodic-transaction"></a><a name="index-transaction_002c-periodic"></a>

A periodic transaction. A period expression must appear after the tilde.

After this initial line there should be a set of one or more postings, just as if it were a normal transaction.

</dd>

<dt>`; # % | *`</dt>

<dd><a name="index-comment"></a><a name="index-comments"></a>

A line beginning with a semicolon, pound, percent, bar or asterisk indicates a comment, and is ignored. Comments will not be returned in a “print” response.

</dd>

<dt>`indented ;`</dt>

<dd><a name="index-tags"></a>

If the semicolon is indented and occurs inside a transaction, it is parsed as a persistent note for its preceding category. These notes or tags can be used to augment the reporting and filtering capabilities of Ledger.

</dd>

</dl>

* * *

<a name="Command-Directives"></a>

<div class="header">

Previous: [Transactions and Comments](#Transactions-and-Comments), Up: [Journal Format](#Journal-Format)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Command-Directives-1"></a>

#### 4.7.2 Command Directives

<a name="index-_002d_002dstrict-1"></a><a name="index-_002d_002dpedantic"></a>

<dl compact="compact">

<dt>`beginning of line`</dt>

<dd>

Command directives must occur at the beginning of a line. Use of ‘<samp>!</samp>’ and ‘<samp>@</samp>’ is deprecated.

</dd>

<dt>`account`</dt>

<dd><a name="index-account"></a><a name="index-pre_002ddeclare-account"></a>

Pre-declare valid account names. This only has an effect if <samp>--strict</samp> or <samp>--pedantic</samp> is used (see below). The `account` directive supports several optional sub-directives, if they immediately follow the account directive and if they begin with whitespace:

<div class="smallexample">

<pre class="smallexample">account Expenses:Food
    note This account is all about the chicken!
    alias food
    payee ^(KFC|Popeyes)$
    check commodity == "$"
    assert commodity == "$"
    eval print("Hello!")
    default
</pre>

</div>

The `note` sub-directive associates a textual note with the account. This can be accessed later using the `note` value expression function in any account context.

The `alias` sub-directive, which can occur multiple times, allows the alias to be used in place of the full account name anywhere that account names are allowed.

The `payee` sub-directive, which can occur multiple times, provides regexes that identify the account if that payee is encountered and an account within its transaction ends in the name "Unknown". Example:

<div class="smallexample">

<pre class="smallexample">2012-02-27 KFC
    Expenses:Unknown      $10.00  ; Read now as "Expenses:Food"
    Assets:Cash
</pre>

</div>

The `check` and `assert` directives warn or raise an error (respectively) if the given value expression evaluates to false within the context of any posting.

The `eval` directive evaluates the value expression in the context of the account at the time of definition. At the moment this has little value.

The `default` directive specifies that this account should be used as the “balancing account” for any future transactions that contain only a single posting.

</dd>

<dt>`apply account`</dt>

<dd><a name="index-apply-account"></a>

Sets the root for all accounts following this directive. Ledger supports a hierarchical tree of accounts. It may be convenient to keep two “root accounts”. For example you may be tracking your personal finances and your business finances. In order to keep them separate you could preface all personal accounts with ‘<samp>personal:</samp>’ and all business accounts with ‘<samp>business:</samp>’. You can easily split out large groups of transactions without manually editing them using the account directive. For example:

<div class="smallexample">

<pre class="smallexample">apply account Personal
2011/11/15  Supermarket
    Expenses:Groceries      $ 50.00
    Assets:Checking
</pre>

</div>

Would result in all postings going into ‘<samp>Personal:Expenses:Groceries</samp>’ and ‘<samp>Personal:Assets:Checking</samp>’ until an ‘<samp>end apply account</samp>’ directive was found.

</dd>

<dt>`alias`</dt>

<dd><a name="index-alias"></a><a name="index-account_002c-alias"></a>

Define an alias for an account name. If you have a deeply nested tree of accounts, it may be convenient to define an alias, for example:

<div class="smallexample">

<pre class="smallexample">alias Dining=Expenses:Entertainment:Dining
alias Checking=Assets:Credit Union:Joint Checking Account

2011/11/28 YummyPalace
    Dining        $10.00
    Checking
</pre>

</div>

The aliases are only in effect for transactions read in after the alias is defined and are affected by `account` directives that precede them.

<div class="smallexample">

<pre class="smallexample">$ ledger bal --no-total ^Exp
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">              $10.00  Expenses:Entertainment:Dining
</pre>

</div>

With the option <samp>--recursive-aliases</samp>, aliases can refer to other aliases, the following example produces exactly the same transactions and account names as the preceding one:

<div class="smallexample">

<pre class="smallexample">alias Entertainment=Expenses:Entertainment
alias Dining=Entertainment:Dining
alias Checking=Assets:Credit Union:Joint Checking Account

2011/11/30 ChopChop
  Dining          $10.00
  Checking
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">$ ledger balance --no-total --recursive-aliases ^Exp
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">              $10.00  Expenses:Entertainment:Dining
</pre>

</div>

The option <samp>--no-aliases</samp> completely disables alias expansion. All accounts are read verbatim as they are in the ledger file.

</dd>

<dt>`assert`</dt>

<dd><a name="index-assert"></a><a name="index-assertions"></a>

An assertion can throw an error if a condition is not met during Ledger’s run.

<div class="smallexample">

<pre class="smallexample">assert <VALUE EXPRESSION BOOLEAN RESULT>
</pre>

</div>

</dd>

<dt>`bucket`</dt>

<dd><a name="bucket"></a><a name="index-bucket-1"></a><a name="index-bucket"></a>

Defines the default account to use for balancing transactions. Normally, each transaction has at least two postings, which must balance to zero. Ledger allows you to leave one posting with no amount and automatically balance the transaction in the posting. The `bucket` allows you to fill in all postings and automatically generate an additional posting to the bucket account balancing the transaction. If any transaction is unbalanced, it will automatically be balanced against the `bucket` account. The following example sets ‘<samp>Assets:Checking</samp>’ as the bucket:

<div class="smallexample">

<pre class="smallexample">bucket Assets:Checking
2011/01/25 Tom's Used Cars
    Expenses:Auto                    $ 5,500.00

2011/01/27 Book Store
    Expenses:Books                       $20.00

2011/12/01 Sale
    Assets:Checking:Business            $ 30.00
</pre>

</div>

</dd>

<dt>`capture`</dt>

<dd><a name="index-capture"></a><a name="index-print"></a><a name="index-register-1"></a>

Directs Ledger to replace any account matching a regex with the given account. For example:

<div class="smallexample">

<pre class="smallexample">capture  Expenses:Deductible:Medical  Medical
</pre>

</div>

Would cause any posting with ‘<samp>Medical</samp>’ in its name to be replaced with ‘<samp>Expenses:Deductible:Medical</samp>’.

Ledger will display the mapped payees in `print` and `register` reports.

</dd>

<dt>`check`</dt>

<dd><a name="index-check"></a><a name="index-assertions-1"></a>

A check issues a warning if a condition is not met during Ledger’s run.

<div class="smallexample">

<pre class="smallexample">check <VALUE EXPRESSION BOOLEAN RESULT>
</pre>

</div>

</dd>

<dt>`comment`</dt>

<dd><a name="index-comment-1"></a><a name="index-comments-1"></a>

Start a block comment, closed by `end comment`.

</dd>

<dt>`commodity`</dt>

<dd><a name="index-commodity-1"></a><a name="index-pre_002ddeclare-commodity"></a>

Pre-declare commodity names. This only has an effect if <samp>--strict</samp> or <samp>--pedantic</samp> is used (see below).

<div class="smallexample">

<pre class="smallexample">commodity $
commodity CAD
</pre>

</div>

The `commodity` directive supports several optional sub-directives, if they immediately follow the commodity directive and—if they are on successive lines—begin with whitespace:

<div class="smallexample">

<pre class="smallexample">commodity $
   note American Dollars
   format $1,000.00
   nomarket
   default
</pre>

</div>

The `note` sub-directive associates a textual note with the commodity. At present this has no value other than documentation.

The `format` sub-directive gives you a way to tell Ledger how to format this commodity. In the future, using this directive will disable Ledger’s observation of other ways that commodity is used, and will provide the “canonical” representation.

The `nomarket` sub-directive states that the commodity’s price should never be auto-downloaded.

The `default` sub-directive marks this as the “default” commodity.

</dd>

<dt>`define`</dt>

<dd><a name="index-define"></a>

Allows you to define value expressions for future use. For example:

<div class="smallexample">

<pre class="smallexample">define var_name=$100

2011/12/01 Test
    Expenses  (var_name*4)
    Assets
</pre>

</div>

The posting will have a cost of $400.

</dd>

<dt>`end`</dt>

<dd><a name="index-end"></a>

Closes block commands like `tag` or `comment`.

</dd>

<dt>`expr`</dt>

<dd><a name="index-expr"></a></dd>

<dt>`fixed`</dt>

<dd><a name="index-fixed"></a><a name="index-fixated-prices"></a>

A fixed block is used to set fixated prices (see [Fixated prices and costs](#Fixated-prices-and-costs)) for a series of transactions. It’s purely a typing saver, for use when entering many transactions with fixated prices.

Thus, the following:

<div class="smallexample">

<pre class="smallexample">fixed CAD $0.90
2012-04-10 Lunch in Canada
    Assets:Wallet            -15.50 CAD
    Expenses:Food            15.50 CAD

2012-04-11 Second day Dinner in Canada
    Assets:Wallet            -25.75 CAD
    Expenses:Food            25.75 CAD
endfixed CAD
</pre>

</div>

is equivalent to this:

<div class="smallexample">

<pre class="smallexample">2012-04-10 Lunch in Canada
    Assets:Wallet            -15.50 CAD {=$0.90}
    Expenses:Food            15.50 CAD  {=$0.90}

2012-04-11 Second day Dinner in Canada
    Assets:Wallet            -25.75 CAD  {=$0.90}
    Expenses:Food            25.75 CAD   {=$0.90}
</pre>

</div>

Note that ending a `fixed` is done differently than other directives, as `fixed` is closed with an `endfixed` (i.e., there is _no space_ between `end` and `fixed`).

For the moment, users may wish to study [Bug Report 789](http://bugs.ledger-cli.org/show_bug.cgi?id=789) before using the `fixed` directive in production.

</dd>

<dt>`include`</dt>

<dd><a name="index-include"></a>

Include the stated file as if it were part of the current file.

</dd>

<dt>`payee`</dt>

<dd><a name="index-payee"></a><a name="index-print-1"></a><a name="index-register-2"></a>

The `payee` directive supports two optional sub-directives, if they immediately follow the payee directive and—if it is on a successive line—begins with whitespace:

<div class="smallexample">

<pre class="smallexample">payee KFC
    alias KENTUCKY FRIED CHICKEN
    uuid 2a2e21d434356f886c84371eebac6e44f1337fda
</pre>

</div>

The `alias` sub-directive provides a regex which, if it matches a parsed payee, the declared payee name is substituted:

<div class="smallexample">

<pre class="smallexample">2012-02-27 KENTUCKY FRIED CHICKEN  ; will be read as being 'KFC'
</pre>

</div>

The `uuid` sub-directive specifies that a transaction with exactly the uuid given should have the declared payee name substituted:

<div class="smallexample">

<pre class="smallexample">2014-05-13 UNHELPFUL PAYEE  ; will be read as being 'KFC'
    ; UUID: 2a2e21d434356f886c84371eebac6e44f1337fda
</pre>

</div>

Ledger will display the mapped payees in `print` and `register` reports.

</dd>

<dt>`apply tag`</dt>

<dd><a name="index-apply-tag"></a>

Allows you to designate a block of transactions and assign the same tag to all. Tags can have values and may be nested.

<div class="smallexample">

<pre class="smallexample">apply tag hastag
apply tag nestedtag: true

2011/01/25 Tom's Used Cars
    Expenses:Auto                    $ 5,500.00
    ; :nobudget:
    Assets:Checking

2011/01/27 Book Store
    Expenses:Books                       $20.00
    Liabilities:MasterCard

end apply tag

2011/12/01 Sale
    Assets:Checking:Business            $ 30.00
    Income:Sales

end apply tag
</pre>

</div>

is the equivalent of:

<div class="smallexample">

<pre class="smallexample">2011/01/25 Tom's Used Cars
    ; :hastag:
    ; nestedtag: true
    Expenses:Auto                    $ 5,500.00
    ; :nobudget:
    Assets:Checking

2011/01/27 Book Store
    ; :hastag:
    ; nestedtag: true
    Expenses:Books                       $20.00
    Liabilities:MasterCard

2011/12/01 Sale
    ; :hastag:
    Assets:Checking:Business            $ 30.00
    Income:Sales
</pre>

</div>

</dd>

<dt>`tag`</dt>

<dd><a name="index-tag"></a><a name="index-pre_002ddeclare-tag"></a>

Pre-declares tag names. This only has an effect if <samp>--strict</samp> or <samp>--pedantic</samp> is used (see below).

<div class="smallexample">

<pre class="smallexample">tag Receipt
tag CSV
</pre>

</div>

The `tag` directive supports two optional sub-directives, if they immediately follow the tag directive and—if on a successive line—begin with whitespace:

<div class="smallexample">

<pre class="smallexample">tag Receipt
  check value =~ /pattern/
  assert value != "foobar"
</pre>

</div>

The `check` and `assert` sub-directives warn or error (respectively) if the given value expression evaluates to false within the context of any use of the related tag. In such a context, “value” is bound to the value of the tag (which may be something else but a string if typed metadata is used!). Such checks or assertions are not called if no value is given.

</dd>

<dt>`test`</dt>

<dd><a name="index-test"></a><a name="index-comments-2"></a>

This is a synonym for `comment` and must be closed by an `end` tag.

</dd>

<dt>`year`</dt>

<dd><a name="index-year"></a><a name="year"></a>

Denotes the year used for all subsequent transactions that give a date without a year. The year should appear immediately after the directive, for example: `year 2004`. This is useful at the beginning of a file, to specify the year for that file. If all transactions specify a year, however, this command has no effect.

</dd>

</dl>

The following single letter commands may be at the beginning of a line alone, for backwards compatibility with older Ledger versions.

<dl compact="compact">

<dt>`A`</dt>

<dd><a name="index-A"></a><a name="index-bucket-2"></a>

See [bucket](#bucket).

</dd>

<dt>`Y`</dt>

<dd><a name="index-Y"></a><a name="index-year-1"></a>

See [year](#year).

</dd>

<dt>`N SYMBOL`</dt>

<dd><a name="index-N"></a>

Indicates that pricing information is to be ignored for a given symbol, nor will quotes ever be downloaded for that symbol. Useful with a home currency, such as the dollar ‘<samp>$</samp>’. It is recommended that these pricing options be set in the price database file, which defaults to <samp>~/.pricedb</samp>. The syntax for this command is:

<div class="smallexample">

<pre class="smallexample">N SYMBOL
</pre>

</div>

</dd>

<dt>`D AMOUNT`</dt>

<dd><a name="index-xact"></a><a name="index-D"></a>

Specifies the default commodity to use, by specifying an amount in the expected format. The `xact` command will use this commodity as the default when none other can be determined. This command may be used multiple times, to set the default flags for different commodities; whichever is seen last is used as the default commodity. For example, to set US dollars as the default commodity, while also setting the thousands flag and decimal flag for that commodity, use:

<div class="smallexample">

<pre class="smallexample">D $1,000.00
</pre>

</div>

</dd>

<dt>`C AMOUNT1 = AMOUNT2`</dt>

<dd><a name="index-C-1"></a>

Specifies a commodity conversion, where the first amount is given to be equivalent to the second amount. The first amount should use the decimal precision desired during reporting:

<div class="smallexample">

<pre class="smallexample">C 1.00 Kb = 1024 bytes
</pre>

</div>

</dd>

<dt>`I, i, O, o, b, h`</dt>

<dd><a name="index-I"></a><a name="index-i"></a><a name="index-O"></a><a name="index-o"></a><a name="index-b"></a><a name="index-h"></a>

These four relate to timeclock support, which permits Ledger to read timelog files. See timeclock’s documentation for more info on the syntax of its timelog files.

</dd>

</dl>

* * *

<a name="Converting-from-other-formats"></a>

<div class="header">

Next: [Archiving Previous Years](#Archiving-Previous-Years), Previous: [Journal Format](#Journal-Format), Up: [Keeping a Journal](#Keeping-a-Journal)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Converting-from-other-formats-1"></a>

### 4.8 Converting from other formats

<a name="index-csv-importing"></a>

There are numerous tools to help convert various formats to a Ledger file. Most banks will generate a comma separated values file that can easily be parsed into Ledger format using one of those tools. Some of the most popular tools are:

*   `ledger convert download.csv`
*   `hledger -f checking.csv print`
*   [`icsv2ledger`](https://github.com/quentinsf/icsv2ledger)
*   [`csvToLedger`](https://github.com/tazzben/csvToLedger)
*   [`CSV2Ledger`](https://launchpad.net/csv2ledger)

Directly pulling information from banks is outside the scope of Ledger’s function.

* * *

<a name="Archiving-Previous-Years"></a>

<div class="header">

Previous: [Converting from other formats](#Converting-from-other-formats), Up: [Keeping a Journal](#Keeping-a-Journal)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Archiving-Previous-Years-1"></a>

### 4.9 Archiving Previous Years

<a name="index-equity"></a><a name="index-print-2"></a>

After a while, your journal can get to be pretty large. While this will not slow down Ledger—it’s designed to process journals very quickly—things can start to feel “messy”; and it’s a universal complaint that when finances feel messy, people avoid them.

Thus, archiving the data from previous years into their own files can offer a sense of completion, and freedom from the past. But how to best accomplish this with the ledger program? There are two commands that make it very simple: `print`, and `equity`.

Let’s take an example file, with data ranging from year 2000 until 2004\. We want to archive years 2000 and 2001 to their own file, leaving 2002–2004 in the current file. So, use `print` to output all the earlier transactions to a file called <samp>ledger-old.dat</samp>:

<div class="smallexample">

<pre class="smallexample">$ ledger -f ledger.dat -b 2000 -e 2002 print > ledger-old.dat
</pre>

</div>

Note that <samp>-e</samp> limits output to transactions _before_ the date specified.

To delete older data from the current ledger file, use `print` again, this time specifying year 2002 as the starting date:

<div class="smallexample">

<pre class="smallexample">$ ledger -f ledger.dat -b 2002 print > x
$ mv x ledger.dat
</pre>

</div>

However, now the current file contains _only_ postings from 2002 onward, which will not yield accurate present-day balances, because the net income from previous years is no longer being tallied. To compensate for this, we must append an equity report for the old ledger at the beginning of the new one:

<div class="smallexample">

<pre class="smallexample">$ ledger -f ledger-old.dat equity > equity.dat
$ cat equity.dat ledger.dat > x
$ mv x ledger.dat
$ rm equity.dat
</pre>

</div>

Now the balances reported from <samp>ledger.dat</samp> are identical to what they were before the data was split.

* * *

<a name="Transactions"></a>

<div class="header">

Next: [Building Reports](#Building-Reports), Previous: [Keeping a Journal](#Keeping-a-Journal), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Transactions-1"></a>

## 5 Transactions

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Basic format](#Basic-format):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Eliding amounts](#Eliding-amounts):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Auxiliary dates](#Auxiliary-dates):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Codes](#Codes):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Transaction state](#Transaction-state):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Transaction notes](#Transaction-notes):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Metadata](#Metadata):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Virtual postings](#Virtual-postings):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Expression amounts](#Expression-amounts):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Balance verification](#Balance-verification):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Posting cost](#Posting-cost):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Explicit posting costs](#Explicit-posting-costs):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Posting cost expressions](#Posting-cost-expressions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Total posting costs](#Total-posting-costs):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Virtual posting costs](#Virtual-posting-costs):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Commodity prices](#Commodity-prices):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Prices versus costs](#Prices-versus-costs):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Fixated prices and costs](#Fixated-prices-and-costs):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Lot dates](#Lot-dates):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Lot notes](#Lot-notes):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Lot value expressions](#Lot-value-expressions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Automated Transactions](#Automated-Transactions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Basic-format"></a>

<div class="header">

Next: [Eliding amounts](#Eliding-amounts), Previous: [Transactions](#Transactions), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Basic-format-1"></a>

### 5.1 Basic format

The most basic form of transaction is:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash                 $-20.00
</pre>

</div>

This transaction has a date, a payee or description, a target account (the first posting), and a source account (the second posting). Each posting specifies what action is taken related to that account.

A transaction can have any number of postings:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash                 $-10.00
    Liabilities:Credit          $-10.00
</pre>

</div>

* * *

<a name="Eliding-amounts"></a>

<div class="header">

Next: [Auxiliary dates](#Auxiliary-dates), Previous: [Basic format](#Basic-format), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Eliding-amounts-1"></a>

### 5.2 Eliding amounts

The first thing you can do to make things easier is elide amounts. That is, if exactly one posting has no amount specified, Ledger will infer the inverse of the other postings’ amounts:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash                 $-10.00
    Liabilities:Credit                   ; same as specifying $-10
</pre>

</div>

If the other postings use multiple commodities, Ledger will copy the empty posting N times and fill in the negated values of the various commodities:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Expenses:Tips                 $2.00
    Assets:Cash              EUR -10.00
    Assets:Cash              GBP -10.00
    Liabilities:Credit
</pre>

</div>

This transaction is identical to writing:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Expenses:Tips                 $2.00
    Assets:Cash              EUR -10.00
    Assets:Cash              GBP -10.00
    Liabilities:Credit          $-22.00
    Liabilities:Credit        EUR 10.00
    Liabilities:Credit        GBP 10.00
</pre>

</div>

* * *

<a name="Auxiliary-dates"></a>

<div class="header">

Next: [Codes](#Codes), Previous: [Eliding amounts](#Eliding-amounts), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Auxiliary-dates-1"></a>

### 5.3 Auxiliary dates

<a name="index-_002d_002daux_002ddate"></a>

You can associate a second date with a transaction by following the primary date with an equals sign:

<div class="smallexample">

<pre class="smallexample">2012-03-10=2012-03-08 KFC
    Expenses:Food                $20.00
    Assets:Cash                 $-20.00
</pre>

</div>

What this auxiliary date means is entirely up to you. The only use Ledger has for it is that if you specify <samp>--aux-date</samp>, then all reports and calculations (including pricing) will use the auxiliary date as if it were the primary date.

* * *

<a name="Codes"></a>

<div class="header">

Next: [Transaction state](#Transaction-state), Previous: [Auxiliary dates](#Auxiliary-dates), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Codes-1"></a>

### 5.4 Codes

A transaction can have a textual “code”. This has no meaning and is only displayed by the print command. Checking accounts often use codes like DEP, XFER, etc., as well as check numbers. This is to give you a place to put those codes:

<div class="smallexample">

<pre class="smallexample">2012-03-10 (#100) KFC
    Expenses:Food                $20.00
    Assets:Checking
</pre>

</div>

* * *

<a name="Transaction-state"></a>

<div class="header">

Next: [Transaction notes](#Transaction-notes), Previous: [Codes](#Codes), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Transaction-state-1"></a>

### 5.5 Transaction state

<a name="index-_002d_002dcleared"></a><a name="index-_002d_002duncleared"></a><a name="index-_002d_002dpending"></a>

A transaction can have a “state”: cleared, pending, or uncleared. The default is uncleared. To mark a transaction cleared, put an asterisk ‘<samp>*</samp>’ before the payee, after the date or code:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

To mark it pending, use a ‘<samp>!</samp>’:

<div class="smallexample">

<pre class="smallexample">2012-03-10 ! KFC
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

What these mean is entirely up to you. The <samp>--cleared</samp> option limits reports to only cleared items, while <samp>--uncleared</samp> shows both uncleared and pending items, and <samp>--pending</samp> shows only pending items.

I use cleared to mean that I’ve reconciled the transaction with my bank statement, and pending to mean that I’m in the middle of a reconciliation.

When you clear a transaction, that’s really just shorthand for clearing all of its postings. That is:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

Is the same as writing:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    * Expenses:Food                $20.00
    * Assets:Cash
</pre>

</div>

You can mark individual postings as cleared or pending, in case one “side” of the transaction has cleared, but the other hasn’t yet:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Liabilities:Credit            $100.00
    * Assets:Checking
</pre>

</div>

* * *

<a name="Transaction-notes"></a>

<div class="header">

Next: [Metadata](#Metadata), Previous: [Transaction state](#Transaction-state), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Transaction-notes-1"></a>

### 5.6 Transaction notes

After the payee, and after at least one tab or two spaces (or a space and a tab), which Ledger calls a “hard separator”, you may introduce a note about the transaction using the ‘<samp>;</samp>’ character:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC                ; yum, chicken...
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

Notes can also appear on the next line, so long as that line begins with whitespace:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC                ; yum, chicken...
    ; and more notes...
    Expenses:Food                $20.00
    Assets:Cash

2012-03-10 * KFC
    ; just these notes...
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

A transaction’s note is shared by all its postings. This becomes significant when querying for metadata (see below). To specify that a note belongs only to one posting, place it after a hard separator after the amount, or on its own line preceded by whitespace:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00  ; posting #1 note
    Assets:Cash
      ; posting #2 note, extra indentation is optional
</pre>

</div>

* * *

<a name="Metadata"></a>

<div class="header">

Next: [Virtual postings](#Virtual-postings), Previous: [Transaction notes](#Transaction-notes), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Metadata-1"></a>

### 5.7 Metadata

One of Ledger’s more powerful features is the ability to associate typed metadata with postings and transactions (by which I mean all of a transaction’s postings). This metadata can be queried, displayed, and used in calculations.

The are two forms of metadata: plain tags, and tag/value pairs.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Metadata tags](#Metadata-tags):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Metadata values](#Metadata-values):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Typed metadata](#Typed-metadata):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Metadata-tags"></a>

<div class="header">

Next: [Metadata values](#Metadata-values), Previous: [Metadata](#Metadata), Up: [Metadata](#Metadata)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Metadata-tags-1"></a>

#### 5.7.1 Metadata tags

To tag an item, put any word not containing whitespace between two colons inside a comment:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00
    Assets:Cash
      ; :TAG:
</pre>

</div>

You can gang up multiple tags by sharing colons:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00
    Assets:Cash
      ; :TAG1:TAG2:TAG3:
</pre>

</div>

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Payee metadata tag](#Payee-metadata-tag):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Payee-metadata-tag"></a>

<div class="header">

Previous: [Metadata tags](#Metadata-tags), Up: [Metadata tags](#Metadata-tags)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Payee-metadata-tag-1"></a>

#### 5.7.1.1 Payee metadata tag

<a name="index-Payee-metadata-tag"></a><a name="index-register-3"></a><a name="index-payees"></a><a name="index-_002d_002dby_002dpayee-1"></a>

“Payee” is a special metadata field. If set on a posting, it will be used as the payee name for that posting. This affects the `register` report, the `payees` report, and the <samp>--by-payee</samp> option.

This is useful when for example you deposit 4 checks at a time to the bank. On the bank statement, there is just one amount ‘<samp>$400</samp>’, but you can specify from whom each check came from, as shown by example below:

<div class="smallexample">

<pre class="smallexample">2010-06-17 Sample
    Assets:Bank        $400.00
    Income:Check1     $-100.00  ; Payee: Person One
    Income:Check2     $-100.00  ; Payee: Person Two
    Income:Check3     $-100.00  ; Payee: Person Three
    Income:Check4     $-100.00  ; Payee: Person Four
</pre>

</div>

When reporting with

<div class="smallexample">

<pre class="smallexample">$ ledger reg
</pre>

</div>

it appears as:

<div class="smallexample">

<pre class="smallexample">10-Jun-17 Sample                Assets:Bank                 $400.00      $400.00
          Person One            Income:Check1              $-100.00      $300.00
          Person Two            Income:Check2              $-100.00      $200.00
          Person Three          Income:Check3              $-100.00      $100.00
          Person Four           Income:Check4              $-100.00            0
</pre>

</div>

This shows that they are all in the same transaction (which is why the date is not repeated), but they have different payees now.

* * *

<a name="Metadata-values"></a>

<div class="header">

Next: [Typed metadata](#Typed-metadata), Previous: [Metadata tags](#Metadata-tags), Up: [Metadata](#Metadata)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Metadata-values-1"></a>

#### 5.7.2 Metadata values

To associate a value with a tag, use the syntax “Key: Value”, where the value can be any string of characters. Whitespace is needed after the colon, and cannot appear in the Key:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00
    Assets:Cash
      ; MyTag: This is just a bogus value for MyTag
</pre>

</div>

* * *

<a name="Typed-metadata"></a>

<div class="header">

Previous: [Metadata values](#Metadata-values), Up: [Metadata](#Metadata)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Typed-metadata-1"></a>

#### 5.7.3 Typed metadata

If a metadata tag ends in ::, its value will be parsed as a value expression and stored internally as a value rather than as a string. For example, although I can specify a date textually like so:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00
    Assets:Cash
      ; AuxDate: 2012/02/30
</pre>

</div>

This date is just a string, and won’t be parsed as a date unless its value is used in a date-context (at which time the string is parsed into a date automatically every time it is needed as a date). If on the other hand I write this:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00
    Assets:Cash
      ; AuxDate:: [2012/02/30]
</pre>

</div>

Then it is parsed as a date only once, and during parsing of the journal file, which would let me know right away that it is an invalid date.

* * *

<a name="Virtual-postings"></a>

<div class="header">

Next: [Expression amounts](#Expression-amounts), Previous: [Metadata](#Metadata), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Virtual-postings-1"></a>

### 5.8 Virtual postings

<a name="index-_002d_002dreal-1"></a>

Ordinarily, the amounts of all postings in a transaction must balance to zero. This is non-negotiable. It’s what double-entry accounting is all about! But there are some tricks up Ledger’s sleeve...

You can use virtual accounts to transfer amounts to an account on the sly, bypassing the balancing requirement. The trick is that these postings are not considered “real”, and can be removed from all reports using <samp>--real</samp>.

To specify a virtual account, surround the account name with parentheses:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00
    Assets:Cash
    (Budget:Food)               $-20.00
</pre>

</div>

If you want, you can state that virtual postings _should_ balance against one or more other virtual postings by using brackets (which look “harder”) rather than parentheses:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food                $20.00
    Assets:Cash
    [Budget:Food]               $-20.00
    [Equity:Budgets]             $20.00
</pre>

</div>

* * *

<a name="Expression-amounts"></a>

<div class="header">

Next: [Balance verification](#Balance-verification), Previous: [Virtual postings](#Virtual-postings), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Expression-amounts-1"></a>

### 5.9 Expression amounts

An amount is usually a numerical figure with an (optional) commodity, but it can also be any value expression. To indicate this, surround the amount expression with parentheses:

<div class="smallexample">

<pre class="smallexample">2012-03-10 * KFC
    Expenses:Food      ($10.00 + $20.00)  ; Ledger adds it up for you
    Assets:Cash
</pre>

</div>

* * *

<a name="Balance-verification"></a>

<div class="header">

Next: [Posting cost](#Posting-cost), Previous: [Expression amounts](#Expression-amounts), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Balance-verification-1"></a>

### 5.10 Balance verification

<a name="index-_002d_002dpermissive"></a>

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Balance assertions](#Balance-assertions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Balance assignments](#Balance-assignments):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Resetting a balance](#Resetting-a-balance):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Balancing transactions](#Balancing-transactions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

If at the end of a posting’s amount (and after the cost too, if there is one) there is an equals sign, then Ledger will verify that the total value for that account as of that posting matches the amount specified. See <samp>--permissive</samp> option to relax the balance assertions checks.

There are two forms of this features: balance assertions, and balance assignments.

* * *

<a name="Balance-assertions"></a>

<div class="header">

Next: [Balance assignments](#Balance-assignments), Previous: [Balance verification](#Balance-verification), Up: [Balance verification](#Balance-verification)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Balance-assertions-1"></a>

#### 5.10.1 Balance assertions

A balance assertion has this general form:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash                 $-20.00 = $500.00
</pre>

</div>

This simply asserts that after subtracting $20.00 from Assets:Cash, that the resulting total matches $500.00\. If not, it is an error.

* * *

<a name="Balance-assignments"></a>

<div class="header">

Next: [Resetting a balance](#Resetting-a-balance), Previous: [Balance assertions](#Balance-assertions), Up: [Balance verification](#Balance-verification)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Balance-assignments-1"></a>

#### 5.10.2 Balance assignments

A balance assignment has this form:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash                         = $500.00
</pre>

</div>

This sets the amount of the second posting to whatever it would need to be for the total in ‘<samp>Assets:Cash</samp>’ to be $500.00 after the posting. If the resulting amount is not $-20.00 in this case, it is an error.

* * *

<a name="Resetting-a-balance"></a>

<div class="header">

Next: [Balancing transactions](#Balancing-transactions), Previous: [Balance assignments](#Balance-assignments), Up: [Balance verification](#Balance-verification)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Resetting-a-balance-1"></a>

#### 5.10.3 Resetting a balance

Say your book-keeping has gotten a bit out of date, and your Ledger balance no longer matches your bank balance. You can create an adjustment transaction using balance assignments:

<div class="smallexample">

<pre class="smallexample">2012-03-10 Adjustment
    Assets:Cash                         = $500.00
    Equity:Adjustments
</pre>

</div>

Since the second posting is also null, it’s value will become the inverse of whatever amount is generated for the first posting.

This is the only time in ledger when more than one posting’s amount may be empty—and then only because it’s not truly empty, it is indirectly provided by the balance assignment’s value.

* * *

<a name="Balancing-transactions"></a>

<div class="header">

Previous: [Resetting a balance](#Resetting-a-balance), Up: [Balance verification](#Balance-verification)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Balancing-transactions-1"></a>

#### 5.10.4 Balancing transactions

<a name="index-_002d_002dempty"></a>

As a consequence of all the above, consider the following transaction:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Broker
    [Assets:Brokerage]            = 10 AAPL
</pre>

</div>

What this says is: set the amount of the posting to whatever value is needed so that ‘<samp>Assets:Brokerage</samp>’ contains 10 AAPL. Then, because this posting must balance, ensure that its value is zero. This can only be true if Assets:Brokerage does indeed contain 10 AAPL at that point in the input file.

A balanced virtual transaction is used simply to indicate to Ledger that this is not a “real” transaction. It won’t appear in any reports anyway (unless you use a register report with <samp>--empty</samp>).

* * *

<a name="Posting-cost"></a>

<div class="header">

Next: [Explicit posting costs](#Explicit-posting-costs), Previous: [Balance verification](#Balance-verification), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Posting-cost-1"></a>

### 5.11 Posting cost

When you transfer a commodity from one account to another, sometimes it gets transformed during the transaction. This happens when you spend money on gas, for example, which transforms dollars into gallons of gasoline, or dollars into stocks in a company.

In those cases, Ledger will remember the “cost” of that transaction for you, and can use it during reporting in various ways. Here’s an example of a stock purchase:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Broker
    Assets:Brokerage             10 AAPL
    Assets:Brokerage:Cash       $-500.00
</pre>

</div>

This is different from transferring 10 AAPL shares from one account to another, in this case you are _exchanging_ one commodity for another. The resulting posting’s cost is $50.00 per share.

* * *

<a name="Explicit-posting-costs"></a>

<div class="header">

Next: [Posting cost expressions](#Posting-cost-expressions), Previous: [Posting cost](#Posting-cost), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Explicit-posting-costs-1"></a>

### 5.12 Explicit posting costs

You can make any posting’s cost explicit using the ‘<samp>@</samp>’ symbol after the amount or amount expression:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Broker
    Assets:Brokerage             10 AAPL @ $50.00
    Assets:Brokerage:Cash       $-500.00
</pre>

</div>

When you do this, since Ledger can now figure out the balancing amount from the first posting’s cost, you can elide the other amount:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Broker
    Assets:Brokerage             10 AAPL @ $50.00
    Assets:Brokerage:Cash
</pre>

</div>

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Primary and secondary commodities](#Primary-and-secondary-commodities):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Primary-and-secondary-commodities"></a>

<div class="header">

Previous: [Explicit posting costs](#Explicit-posting-costs), Up: [Explicit posting costs](#Explicit-posting-costs)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Primary-and-secondary-commodities-1"></a>

#### 5.12.1 Primary and secondary commodities

<a name="index-_002d_002dmarket-2"></a><a name="index-_002d_002dexchange-COMMODITY-1"></a>

It is a general convention within Ledger that the “top” postings in a transaction contain the target accounts, while the final posting contains the source account. Whenever a commodity is exchanged like this, the commodity moved to the target account is considered “secondary”, while the commodity used for purchasing and tracked in the cost is “primary”.

Said another way, whenever Ledger sees a posting cost of the form "AMOUNT @ AMOUNT", the commodity used in the second amount is marked “primary”.

The only meaning a primary commodity has is that the <samp>--market (-V)</samp> flag will never convert a primary commodity into any other commodity. <samp>--exchange <var>COMMODITY</var> (-X)</samp> still will, however.

* * *

<a name="Posting-cost-expressions"></a>

<div class="header">

Next: [Total posting costs](#Total-posting-costs), Previous: [Explicit posting costs](#Explicit-posting-costs), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Posting-cost-expressions-1"></a>

### 5.13 Posting cost expressions

Just as you can have amount expressions, you can have posting expressions:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Broker
    Assets:Brokerage             10 AAPL @ ($500.00 / 10)
    Assets:Brokerage:Cash
</pre>

</div>

You can even have both:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Broker
    Assets:Brokerage             (5 AAPL * 2) @ ($500.00 / 10)
    Assets:Brokerage:Cash
</pre>

</div>

* * *

<a name="Total-posting-costs"></a>

<div class="header">

Next: [Virtual posting costs](#Virtual-posting-costs), Previous: [Posting cost expressions](#Posting-cost-expressions), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Total-posting-costs-1"></a>

### 5.14 Total posting costs

The cost figure following the ‘<samp>@</samp>’ character specifies the _per-unit_ price for the commodity being transferred. If you’d like to specify the total cost instead, use ‘<samp>@@</samp>’:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Broker
    Assets:Brokerage             10 AAPL @@ $500.00
    Assets:Brokerage:Cash
</pre>

</div>

Ledger reads this as if you had written:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Broker
    Assets:Brokerage             10 AAPL @ ($500.00 / 10)
    Assets:Brokerage:Cash
</pre>

</div>

* * *

<a name="Virtual-posting-costs"></a>

<div class="header">

Next: [Commodity prices](#Commodity-prices), Previous: [Total posting costs](#Total-posting-costs), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Virtual-posting-costs-1"></a>

### 5.15 Virtual posting costs

Normally whenever a commodity exchange like this happens, the price of the exchange (such as $50 per share of AAPL, above) is recorded in Ledger’s internal price history database. To prevent this from happening in the case of an exceptional transaction, surround the ‘<samp>@</samp>’ or ‘<samp>@@</samp>’ with parentheses:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Brother
    Assets:Brokerage            1000 AAPL (@) $1
    Income:Gifts Received
</pre>

</div>

* * *

<a name="Commodity-prices"></a>

<div class="header">

Next: [Prices versus costs](#Prices-versus-costs), Previous: [Virtual posting costs](#Virtual-posting-costs), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Commodity-prices-1"></a>

### 5.16 Commodity prices

<a name="index-_002d_002dlot_002dprices"></a>

When a transaction occurs that exchanges one commodity for another, Ledger records that commodity price not only within its internal price database, but also attached to the commodity itself. Usually this fact remains invisible to the user, unless you turn on <samp>--lot-prices</samp> to show these hidden price figures.

For example, consider the stock sale given above:

<div class="smallexample">

<pre class="smallexample">2012-03-10 My Broker
    Assets:Brokerage             10 AAPL @ $50.00
    Assets:Brokerage:Cash
</pre>

</div>

The commodity transferred into ‘<samp>Assets:Brokerage</samp>’ is not actually 10 AAPL, but rather 10 AAPL {$50.00}. The figure in braces after the amount is called the “lot price”. It’s Ledger’s way of remembering that this commodity was transferred through an exchange, and that $50.00 was the price of that exchange.

This becomes significant if you later sell that commodity again. For example, you might write this:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage:Cash
    Assets:Brokerage            -10 AAPL @ $75.00
</pre>

</div>

And that would be perfectly fine, but how do you track the capital gains on the sale? It could be done with a virtual posting:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage:Cash
    Assets:Brokerage            -10 AAPL @ $75.00
    (Income:Capital Gains)      $-250.00
</pre>

</div>

But this gets messy since capital gains income is very real, and not quite appropriate for a virtual posting.

Instead, if you reference that same hidden price annotation, Ledger will figure out that the price of the shares you’re selling, and the cost you’re selling them at, don’t balance:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage:Cash       $750.00
    Assets:Brokerage            -10 AAPL {$50.00} @ $75.00
</pre>

</div>

This transaction will fail because the $250.00 price difference between the price you bought those shares at, and the cost you’re selling them for, does not match. The lot price also identifies which shares you purchased on that prior date.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Total commodity prices](#Total-commodity-prices):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Total-commodity-prices"></a>

<div class="header">

Previous: [Commodity prices](#Commodity-prices), Up: [Commodity prices](#Commodity-prices)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Total-commodity-prices-1"></a>

#### 5.16.1 Total commodity prices

As a shorthand, you can specify the total price instead of the per-share price in doubled braces. This goes well with total costs, but is not required to be used with them:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage:Cash       $750.00
    Assets:Brokerage            -10 AAPL {{$500.00}} @@ $750.00
    Income:Capital Gains       $-250.00
</pre>

</div>

It should be noted that this is a convenience only for cases where you buy and sell whole lots. The {{$500.00}} is _not_ an attribute of the commodity, whereas {$50.00} is. In fact, when you write {{$500.00}}, Ledger just divides that value by 10 and sees {$50.00}. So if you use the print command to look at this transaction, you’ll see the single braces form in the output. The double braces price form is a shorthand only.

Plus, it comes with dangers. This works fine:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage            10 AAPL @ $50.00
    Assets:Brokerage:Cash      $-500.00

2012-04-10 My Broker
    Assets:Brokerage:Cash       $375.00
    Assets:Brokerage            -5 AAPL {$50.00} @ $375.00
    Income:Capital Gains       $-125.00

2012-04-10 My Broker
    Assets:Brokerage:Cash       $375.00
    Assets:Brokerage            -5 AAPL {$50.00} @ $375.00
    Income:Capital Gains       $-125.00
</pre>

</div>

But this does not do what you might expect:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage            10 AAPL @ $50.00
    Assets:Brokerage:Cash       $750.00

2012-04-10 My Broker
    Assets:Brokerage:Cash       $375.00
    Assets:Brokerage            -5 AAPL {{$500.00}} @ $375.00
    Income:Capital Gains       $-125.00

2012-04-10 My Broker
    Assets:Brokerage:Cash       $375.00
    Assets:Brokerage            -5 AAPL {{$500.00}} @ $375.00
    Income:Capital Gains       $-125.00
</pre>

</div>

And in cases where the amounts do not divide into whole figures and must be rounded, the capital gains figure could be off by a cent. Use with caution.

* * *

<a name="Prices-versus-costs"></a>

<div class="header">

Next: [Fixated prices and costs](#Fixated-prices-and-costs), Previous: [Commodity prices](#Commodity-prices), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Prices-versus-costs-1"></a>

### 5.17 Prices versus costs

Because lot pricing provides enough information to infer the cost, the following two transactions are equivalent:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage            10 AAPL @ $50.00
    Assets:Brokerage:Cash       $750.00

2012-04-10 My Broker
    Assets:Brokerage            10 AAPL {$50.00}
    Assets:Brokerage:Cash       $750.00
</pre>

</div>

However, note that what you see in some reports may differ, for example in the print report. Functionally, however, there is no difference, and neither the register nor the balance report are sensitive to this difference.

* * *

<a name="Fixated-prices-and-costs"></a>

<div class="header">

Next: [Lot dates](#Lot-dates), Previous: [Prices versus costs](#Prices-versus-costs), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Fixated-prices-and-costs-1"></a>

### 5.18 Fixated prices and costs

If you buy a stock last year, and ask for its value today, Ledger will consult its price database to see what the most recent price for that stock is. You can short-circuit this lookup by “fixing” the price at the time of a transaction. This is done using ‘<samp>{=AMOUNT}</samp>’:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage            10 AAPL {=$50.00}
    Assets:Brokerage:Cash       $750.00
</pre>

</div>

These 10 AAPL will now always be reported as being worth $50, no matter what else happens to the stock in the meantime.

Fixated prices are a special case of using lot valuation expressions (see below) to fix the value of a commodity lot.

Since price annotations and costs are largely interchangeable and a matter of preference, there is an equivalent syntax for specified fixated prices by way of the cost:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage            10 AAPL @ =$50.00
    Assets:Brokerage:Cash       $750.00
</pre>

</div>

This is the same as the previous transaction, with the same caveats found in [Prices versus costs](#Prices-versus-costs).

* * *

<a name="Lot-dates"></a>

<div class="header">

Next: [Lot notes](#Lot-notes), Previous: [Fixated prices and costs](#Fixated-prices-and-costs), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Lot-dates-1"></a>

### 5.19 Lot dates

<a name="index-_002d_002dlot_002ddates"></a>

In addition to lot prices, you can specify lot dates and reveal them with <samp>--lot-dates</samp>. Other than that, however, they have no special meaning to Ledger. They are specified after the amount in square brackets (the same way that dates are parsed in value expressions):

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage:Cash       $375.00
    Assets:Brokerage            -5 AAPL {$50.00} [2012-04-10] @ $375.00
    Income:Capital Gains       $-125.00
</pre>

</div>

* * *

<a name="Lot-notes"></a>

<div class="header">

Next: [Lot value expressions](#Lot-value-expressions), Previous: [Lot dates](#Lot-dates), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Lot-notes-1"></a>

### 5.20 Lot notes

<a name="index-_002d_002dlot_002dnotes"></a><a name="index-_002d_002dlots"></a>

You can also associate arbitrary notes for your own record keeping in parentheses, and reveal them with <samp>--lot-notes</samp>. One caveat is that the note cannot begin with an ‘<samp>@</samp>’ character, as that would indicate a virtual cost:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage:Cash       $375.00
    Assets:Brokerage            -5 AAPL {$50.00} [2012-04-10] (Oh my!) @ $375.00
    Income:Capital Gains       $-125.00
</pre>

</div>

You can specify any combination of lot prices, dates or notes, in any order. They are all optional.

To show all lot information in a report, use <samp>--lots</samp>.

* * *

<a name="Lot-value-expressions"></a>

<div class="header">

Next: [Automated Transactions](#Automated-Transactions), Previous: [Lot notes](#Lot-notes), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Lot-value-expressions-1"></a>

### 5.21 Lot value expressions

Normally when you ask Ledger to display the values of commodities held, it uses a value expression called “market” to determine the most recent value from its price database—even downloading prices from the Internet, if <samp>--download (-Q)</samp> was specified and a suitable <samp>getquote</samp> script is found on your system.

However, you can override this valuation logic by providing a commodity valuation expression in doubled parentheses. This expression must result in one of two values: either an amount to always be used as the per-share price for that commodity; or a function taking three arguments, which is called to determine that price.

If you use the functional form, you can either specify a function name, or a lambda expression. Here’s a function that yields the price as $10 in whatever commodity is being requested:

<div class="smallexample">

<pre class="smallexample">define ten_dollars(s, date, t) = market($10, date, t)
</pre>

</div>

I can now use that in a lot value expression as follows:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    Assets:Brokerage:Cash       $375.00
    Assets:Brokerage            -5 AAPL {$50.00} ((ten_dollars)) @@ $375.00
    Income:Capital Gains       $-125.00
</pre>

</div>

Alternatively, I could do the same thing without pre-defining a function by using a lambda expression taking three arguments:

<div class="smallexample">

<pre class="smallexample">2012-04-10 My Broker
    A:B:Cash       $375.00
    A:B     -5 AAPL {$50.00} ((s, d, t -> market($10, date, t))) @@ $375.00
    Income:Capital Gains       $-125.00
</pre>

</div>

The arguments passed to these functions have the following meaning:

*   source The source commodity string, or an amount object. If it is a string, the return value must be an amount representing the price of the commodity identified by that string (example: ‘<samp>$</samp>’). If it is an amount, return the value of that amount as a new amount (usually calculated as commodity price times source amount).
*   date The date to use for determining the value. If null, it means no date was specified, which can mean whatever you want it to mean.
*   target If not null, a string representing the desired target commodity that the commodity price, or repriced amount, should be valued in. Note that this string can be a comma-separated list, and that some or all of the commodities in that list may be suffixed with an exclamation mark, to indicate what is being desired.

In most cases, it is simplest to either use explicit amounts in your valuation expressions, or just pass the arguments down to ‘<samp>market</samp>’ after modifying them to suit your needs.

* * *

<a name="Automated-Transactions"></a>

<div class="header">

Previous: [Lot value expressions](#Lot-value-expressions), Up: [Transactions](#Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Automated-Transactions-1"></a>

### 5.22 Automated Transactions

An automated transaction is a special kind of transaction which adds its postings to other transactions any time one of that other transactions’ postings matches its predicate. The predicate uses the same query syntax as the Ledger command-line.

Consider this posting:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

If I write this automated transaction before it in the file:

<div class="smallexample">

<pre class="smallexample">= expr true
    Foo                          $50.00
    Bar                         $-50.00
</pre>

</div>

Then the first transaction will be modified during parsing as if I’d written this:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Foo                          $50.00
    Bar                         $-50.00
    Assets:Cash                 $-20.00
    Foo                          $50.00
    Bar                         $-50.00
</pre>

</div>

Despite this fancy logic, automated transactions themselves follow most of the same rules as regular transactions: their postings must balance (unless you use a virtual posting), you can have metadata, etc.

One thing you cannot do, however, is elide amounts in an automated transaction.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Amount multipliers](#Amount-multipliers):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Accessing the matching posting's amount](#Accessing-the-matching-posting_0027s-amount):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Referring to the matching posting's account](#Referring-to-the-matching-posting_0027s-account):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Applying metadata to every matched posting](#Applying-metadata-to-every-matched-posting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Applying metadata to the generated posting](#Applying-metadata-to-the-generated-posting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [State flags](#State-flags):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Effective Dates](#Effective-Dates):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Periodic Transactions](#Periodic-Transactions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Concrete Example of Automated Transactions](#Concrete-Example-of-Automated-Transactions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Amount-multipliers"></a>

<div class="header">

Next: [Accessing the matching posting's amount](#Accessing-the-matching-posting_0027s-amount), Previous: [Automated Transactions](#Automated-Transactions), Up: [Automated Transactions](#Automated-Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Amount-multipliers-1"></a>

#### 5.22.1 Amount multipliers

As a special case, if an automated transaction’s posting’s amount (phew) has no commodity, it is taken as a multiplier upon the matching posting’s cost. For example:

<div class="smallexample">

<pre class="smallexample">= expr true
    Foo                           50.00
    Bar                          -50.00

2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

Then the latter transaction turns into this during parsing:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    Foo                        $1000.00
    Bar                       $-1000.00
    Assets:Cash                 $-20.00
    Foo                        $1000.00
    Bar                       $-1000.00
</pre>

</div>

* * *

<a name="Accessing-the-matching-posting_0027s-amount"></a>

<div class="header">

Next: [Referring to the matching posting's account](#Referring-to-the-matching-posting_0027s-account), Previous: [Amount multipliers](#Amount-multipliers), Up: [Automated Transactions](#Automated-Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Accessing-the-matching-posting_0027s-amount-1"></a>

#### 5.22.2 Accessing the matching posting’s amount

If you use an amount expression for an automated transaction’s posting, that expression has access to all the details of the matched posting. For example, you can refer to that posting’s amount using the “amount” value expression variable:

<div class="smallexample">

<pre class="smallexample">= expr true
    (Foo)                  (amount * 2)  ; same as just "2" in this case

2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

This becomes:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    (Foo)                        $40.00
    Assets:Cash                 $-20.00
    (Foo)                       $-40.00
</pre>

</div>

* * *

<a name="Referring-to-the-matching-posting_0027s-account"></a>

<div class="header">

Next: [Applying metadata to every matched posting](#Applying-metadata-to-every-matched-posting), Previous: [Accessing the matching posting's amount](#Accessing-the-matching-posting_0027s-amount), Up: [Automated Transactions](#Automated-Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Referring-to-the-matching-posting_0027s-account-1"></a>

#### 5.22.3 Referring to the matching posting’s account

Sometimes you want to refer to the account that was matched in some way within the automated transaction itself. This is done by using the string ‘<samp>$account</samp>’, anywhere within the account part of the automated posting:

<div class="smallexample">

<pre class="smallexample">= food
    (Budget:$account)                10

2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

Becomes:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    (Budget:Expenses:Food)      $200.00
    Assets:Cash                 $-20.00
</pre>

</div>

* * *

<a name="Applying-metadata-to-every-matched-posting"></a>

<div class="header">

Next: [Applying metadata to the generated posting](#Applying-metadata-to-the-generated-posting), Previous: [Referring to the matching posting's account](#Referring-to-the-matching-posting_0027s-account), Up: [Automated Transactions](#Automated-Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Applying-metadata-to-every-matched-posting-1"></a>

#### 5.22.4 Applying metadata to every matched posting

If the automated transaction has a transaction note, that note is copied (along with any metadata) to every posting that matches the predicate:

<div class="smallexample">

<pre class="smallexample">= food
    ; Foo: Bar
    (Budget:$account)                10

2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

Becomes:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
      ; Foo: Bar
    (Budget:Expenses:Food)      $200.00
    Assets:Cash                 $-20.00
</pre>

</div>

* * *

<a name="Applying-metadata-to-the-generated-posting"></a>

<div class="header">

Next: [State flags](#State-flags), Previous: [Applying metadata to every matched posting](#Applying-metadata-to-every-matched-posting), Up: [Automated Transactions](#Automated-Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Applying-metadata-to-the-generated-posting-1"></a>

#### 5.22.5 Applying metadata to the generated posting

If the automated transaction’s posting has a note, that note is carried to the generated posting within the matched transaction:

<div class="smallexample">

<pre class="smallexample">= food
    (Budget:$account)                10
      ; Foo: Bar

2012-03-10 KFC
    Expenses:Food                $20.00
    Assets:Cash
</pre>

</div>

Becomes:

<div class="smallexample">

<pre class="smallexample">2012-03-10 KFC
    Expenses:Food                $20.00
    (Budget:Expenses:Food)      $200.00
      ; Foo: Bar
    Assets:Cash                 $-20.00
</pre>

</div>

This is slightly different from the rules for regular transaction notes, in that an automated transaction’s note does not apply to every posting within the automated transaction itself, but rather to every posting it matches.

* * *

<a name="State-flags"></a>

<div class="header">

Next: [Effective Dates](#Effective-Dates), Previous: [Applying metadata to the generated posting](#Applying-metadata-to-the-generated-posting), Up: [Automated Transactions](#Automated-Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="State-flags-1"></a>

#### 5.22.6 State flags

Although you cannot mark an automated transaction as a whole as cleared or pending, you can mark its postings with a ‘<samp>*</samp>’ or ‘<samp>!</samp>’ before the account name, and that state flag gets carried to the generated posting.

* * *

<a name="Effective-Dates"></a>

<div class="header">

Next: [Periodic Transactions](#Periodic-Transactions), Previous: [State flags](#State-flags), Up: [Automated Transactions](#Automated-Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Effective-Dates-1"></a>

#### 5.22.7 Effective Dates

<a name="index-effective-dates"></a><a name="index-_002d_002deffective"></a>

In the real world, transactions do not take place instantaneously. Purchases can take several days to post to a bank account. And you may pay ahead for something for which you want to distribute costs. With Ledger you can control every aspect of the timing of a transaction.

Say you’re in business. If you bill a customer, you can enter something like

<a name="index-effective-date-of-invoice"></a>

<div class="smallexample">

<pre class="smallexample">2008/01/01=2008/01/14 Client invoice  ;  estimated date you'll be paid
    Assets:Accounts Receivable            $100.00
    Income: Client name
</pre>

</div>

Then, when you receive the payment, you change it to

<div class="smallexample">

<pre class="smallexample">2008/01/01=2008/01/15 Client invoice ;  actual date money received
    Assets:Accounts Receivable            $100.00
    Income: Client name
</pre>

</div>

and add something like

<div class="smallexample">

<pre class="smallexample">2008/01/15 Client payment
    Assets:Checking                       $100.00
    Assets:Accounts Receivable
</pre>

</div>

Now

<div class="smallexample">

<pre class="smallexample">$ ledger --begin 2008/01/01 --end 2008/01/14 bal Income
</pre>

</div>

gives you your accrued income in the first two weeks of the year, and

<div class="smallexample">

<pre class="smallexample">$ ledger --effective --begin 2008/01/01 --end 2008/01/14 bal Income
</pre>

</div>

gives you your cash basis income in the same two weeks.

Another use is distributing costs out in time. As an example, suppose you just prepaid into a local vegetable co-op that sustains you through the winter. It costs $225 to join the program, so you write a check. You don’t want your October grocery budget to be blown because you bought food ahead, however. What you really want is for the money to be evenly distributed over the next six months so that your monthly budgets gradually take a hit for the vegetables you’ll pick up from the co-op, even though you’ve already paid for them.

<div class="smallexample">

<pre class="smallexample">2008/10/16 * (2090) Bountiful Blessings Farm
    Expenses:Food:Groceries                  $ 37.50  ; [=2008/10/01]
    Expenses:Food:Groceries                  $ 37.50  ; [=2008/11/01]
    Expenses:Food:Groceries                  $ 37.50  ; [=2008/12/01]
    Expenses:Food:Groceries                  $ 37.50  ; [=2009/01/01]
    Expenses:Food:Groceries                  $ 37.50  ; [=2009/02/01]
    Expenses:Food:Groceries                  $ 37.50  ; [=2009/03/01]
    Assets:Checking
</pre>

</div>

This entry accomplishes this. Every month you’ll see an automatic $37.50 deficit like you should, while your checking account really knows that it debited $225 this month.

And using the <samp>--effective</samp> option, the initial date will be overridden by the effective dates.

<div class="smallexample">

<pre class="smallexample">$ ledger --effective register Groceries
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">08-Oct-01 Bountiful Blessings.. Expense:Food:Groceries      $ 37.50      $ 37.50
08-Nov-01 Bountiful Blessings.. Expense:Food:Groceries      $ 37.50      $ 75.00
08-Dec-01 Bountiful Blessings.. Expense:Food:Groceries      $ 37.50     $ 112.50
09-Jan-01 Bountiful Blessings.. Expense:Food:Groceries      $ 37.50     $ 150.00
09-Feb-01 Bountiful Blessings.. Expense:Food:Groceries      $ 37.50     $ 187.50
09-Mar-01 Bountiful Blessings.. Expense:Food:Groceries      $ 37.50     $ 225.00
</pre>

</div>

* * *

<a name="Periodic-Transactions"></a>

<div class="header">

Next: [Concrete Example of Automated Transactions](#Concrete-Example-of-Automated-Transactions), Previous: [Effective Dates](#Effective-Dates), Up: [Automated Transactions](#Automated-Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Periodic-Transactions-1"></a>

#### 5.22.8 Periodic Transactions

<a name="index-_002d_002dbudget"></a>

A periodic transaction starts with a tilde ‘<samp>~</samp>’ followed by a period expression (see [Period Expressions](#Period-Expressions)). Periodic transactions are used for budgeting and forecasting only, they have no effect without the <samp>--budget</samp> option specified. For examples and details, see [Budgeting and Forecasting](#Budgeting-and-Forecasting).

* * *

<a name="Concrete-Example-of-Automated-Transactions"></a>

<div class="header">

Previous: [Periodic Transactions](#Periodic-Transactions), Up: [Automated Transactions](#Automated-Transactions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Concrete-Example-of-Automated-Transactions-1"></a>

#### 5.22.9 Concrete Example of Automated Transactions

As a Bahá’í, I need to compute Huqúqu’lláh whenever I acquire assets. It is similar to tithing for Jews and Christians, or to Zakát for Muslims. The exact details of computing Huqúqu’lláh are somewhat complex, but if you have further interest, please consult the Web.

Ledger makes this otherwise difficult law very easy. Just set up an automated posting at the top of your ledger file:

<div class="smallexample">

<pre class="smallexample">; This automated transaction will compute Huqúqu'lláh based on this
; journal's postings.  Any accounts that match will affect the
; Liabilities:Huququ'llah account by 19% of the value of that posting.

= /^(?:Income:|Expenses:(?:Business|Rent$|Furnishings|Taxes|Insurance))/
  (Liabilities:Huququ'llah)               0.19
</pre>

</div>

This automated posting works by looking at each posting in the ledger file. If any match the given value expression, 19% of the posting’s value is applied to the ‘<samp>Liabilities:Huququ'llah</samp>’ account. So, if $1000 is earned from ‘<samp>Income:Salary</samp>’, $190 is added to ‘<samp>Liabilities:Huqúqu'lláh</samp>’; if $1000 is spent on Rent, $190 is subtracted.

<div class="smallexample">

<pre class="smallexample">2003/01/01 (99) Salary
  Income:Salary  -$1000
  Assets:Checking

2003/01/01 (100) Rent
  Expenses:Rent  $500
  Assets:Checking
</pre>

</div>

The ultimate balance of Huqúqu’lláh reflects how much is owed in order to fulfill one’s obligation to Huqúqu’lláh. When ready to pay, just write a check to cover the amount shown in ‘<samp>Liabilities:Huququ'llah</samp>’. That transaction would look like:

<div class="smallexample">

<pre class="smallexample">2003/01/01 (101) Baha'i Huqúqu'lláh Trust
    Liabilities:Huququ'llah          $1,000.00
    Assets:Checking
</pre>

</div>

That’s it. To see how much Huqúq is currently owed based on your ledger transactions, use:

<div class="smallexample">

<pre class="smallexample">$ ledger balance Liabilities:Huquq
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">                $-95  Liabilities:Huququ'llah
</pre>

</div>

This works fine, but omits one aspect of the law: that Huqúq is only due once the liability exceeds the value of 19 mithqáls of gold (which is roughly 2.22 ounces). So what we want is for the liability to appear in the balance report only when it exceeds the present day value of 2.22 ounces of gold. This can be accomplished using the command:

<div class="smallexample">

<pre class="smallexample">$ ledger -Q -t "/Liab.*Huquq/?(a/P{2.22 AU}<={-1.0}&a):a" bal liab
</pre>

</div>

With this command, the current price for gold is downloaded, and the Huqúqu’lláh is reported only if its value exceeds that of 2.22 ounces of gold. If you wish the liability to be reflected in the parent subtotal either way, use this instead:

<div class="smallexample">

<pre class="smallexample">$ ledger -Q -T "/Liab.*Huquq/?(O/P{2.22 AU}<={-1.0}&O):O" bal liab
</pre>

</div>

In some cases, you may wish to refer to the account of whichever posting matched your automated transaction’s value expression. To do this, use the special account name ‘<samp>$account</samp>’:

<div class="smallexample">

<pre class="smallexample">= /^Some:Long:Account:Name/
    [$account]  -0.10
    [Savings]    0.10
</pre>

</div>

This example causes 10% of the matching account’s total to be deferred to the ‘<samp>Savings</samp>’ account—as a balanced virtual posting, which may be excluded from reports by using <samp>--real</samp>.

* * *

<a name="Building-Reports"></a>

<div class="header">

Next: [Reporting Commands](#Reporting-Commands), Previous: [Transactions](#Transactions), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Building-Reports-1"></a>

## 6 Building Reports

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Introduction](#Introduction):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Balance Reports](#Balance-Reports):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Typical queries](#Typical-queries):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Advanced Reports](#Advanced-Reports):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Introduction"></a>

<div class="header">

Next: [Balance Reports](#Balance-Reports), Previous: [Building Reports](#Building-Reports), Up: [Building Reports](#Building-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Introduction-1"></a>

### 6.1 Introduction

The power of Ledger comes from the incredible flexibility in its reporting commands, combined with formatting commands. Some options control what is included in the calculations, and formatting controls how it is displayed. The combinations are infinite. This chapter will show you the basics of combining various options and commands. In the next chapters you will find details about the specific commands and options.

* * *

<a name="Balance-Reports"></a>

<div class="header">

Next: [Typical queries](#Typical-queries), Previous: [Introduction](#Introduction), Up: [Building Reports](#Building-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Balance-Reports-1"></a>

### 6.2 Balance Reports

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Controlling the Accounts and Payees](#Controlling-the-Accounts-and-Payees):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Controlling Formatting](#Controlling-Formatting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Controlling-the-Accounts-and-Payees"></a>

<div class="header">

Next: [Controlling Formatting](#Controlling-Formatting), Previous: [Balance Reports](#Balance-Reports), Up: [Balance Reports](#Balance-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Controlling-the-Accounts-and-Payees-1"></a>

#### 6.2.1 Controlling the Accounts and Payees

The balance report is the most commonly used report. The simplest invocation is:

<div class="smallexample">

<pre class="smallexample">$ ledger balance -f drewr3.dat
</pre>

</div>

which will print the balances of every account in your journal.

<div class="smallexample">

<pre class="smallexample">         $ -3,804.00  Assets
          $ 1,396.00    Checking
             $ 30.00      Business
         $ -5,200.00    Savings
         $ -1,000.00  Equity:Opening Balances
          $ 6,654.00  Expenses
          $ 5,500.00    Auto
             $ 20.00    Books
            $ 300.00    Escrow
            $ 334.00    Food:Groceries
            $ 500.00    Interest:Mortgage
         $ -2,030.00  Income
         $ -2,000.00    Salary
            $ -30.00    Sales
            $ -63.60  Liabilities
            $ -20.00    MasterCard
            $ 200.00    Mortgage:Principal
           $ -243.60    Tithe
--------------------
           $ -243.60
</pre>

</div>

Most times, this is more than you want. Limiting the results to specific accounts is as easy as entering the names of the accounts after the command:

<div class="smallexample">

<pre class="smallexample">$ ledger balance -f drewr3.dat Auto MasterCard
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">          $ 5,500.00  Expenses:Auto
            $ -20.00  Liabilities:MasterCard
--------------------
          $ 5,480.00
</pre>

</div>

Note the implicit logical or between ‘<samp>Auto</samp>’ and ‘<samp>Mastercard</samp>’.

If you want the entire contents of a branch of your account tree, use the highest common name in the branch:

<div class="smallexample">

<pre class="smallexample">$ ledger balance -f drewr3.dat Income
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">         $ -2,030.00  Income
         $ -2,000.00    Salary
            $ -30.00    Sales
--------------------
         $ -2,030.00
</pre>

</div>

You can use general regular expressions in nearly any place Ledger needs a string:

<div class="smallexample">

<pre class="smallexample">$ ledger balance -f drewr3.dat ^Bo
</pre>

</div>

This first example looks for any account starting with ‘<samp>Bo</samp>’, of which there are none.

<div class="smallexample">

<pre class="smallexample">$ ledger balance -f drewr3.dat Bo
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">             $ 20.00  Expenses:Books
</pre>

</div>

This second example looks for any account containing ‘<samp>Bo</samp>’, which is ‘<samp>Expenses:Books</samp>’.

<a name="index-limit-by-payees"></a><a name="index-_002d_002dlimit-EXPR"></a>

If you want to know exactly how much you have spent in a particular account on a particular payee, the following are equivalent:

<div class="smallexample">

<pre class="smallexample">$ ledger balance Auto:Fuel and Chevron
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">$ ledger balance --limit 'account=~/Fuel/' and 'payee=~/Chev/'
</pre>

</div>

will show you the amount expended on gasoline at Chevron. The second example is the first example of the very powerful expression language available to shape reports. The first example may be easier to remember, but learning to use the second will open up far more possibilities.

If you want to exclude specific accounts from the report, you can exclude multiple accounts with parentheses:

<div class="smallexample">

<pre class="smallexample">$ ledger bal Expenses and not (Expenses:Drinks or Expenses:Candy or Expenses:Gifts)
</pre>

</div>

* * *

<a name="Controlling-Formatting"></a>

<div class="header">

Previous: [Controlling the Accounts and Payees](#Controlling-the-Accounts-and-Payees), Up: [Balance Reports](#Balance-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Controlling-Formatting-1"></a>

#### 6.2.2 Controlling Formatting

These examples all use the default formatting for the balance report. Customizing the formatting can easily allowing to see only what you want, or interface Ledger with other programs.

* * *

<a name="Typical-queries"></a>

<div class="header">

Next: [Advanced Reports](#Advanced-Reports), Previous: [Balance Reports](#Balance-Reports), Up: [Building Reports](#Building-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Typical-queries-1"></a>

### 6.3 Typical queries

A query such as the following shows all expenses since last October, sorted by total:

<div class="smallexample">

<pre class="smallexample">$ ledger -b "last oct" -S T bal ^expenses
</pre>

</div>

From left to right the options mean: Show transactions since last October; sort by the absolute value of the total; and report the balance for all accounts that begin with ‘<samp>expenses</samp>’.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Reporting monthly expenses](#Reporting-monthly-expenses):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Reporting-monthly-expenses"></a>

<div class="header">

Previous: [Typical queries](#Typical-queries), Up: [Typical queries](#Typical-queries)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Reporting-monthly-expenses-1"></a>

#### 6.3.1 Reporting monthly expenses

<a name="index-_002d_002dmonthly"></a><a name="index-_002d_002ddisplay-EXPR"></a><a name="index-_002d_002dperiod_002dsort-VEXPR"></a><a name="index-_002d_002drelated"></a><a name="index-_002d_002dsubtotal"></a>

The following query makes it easy to see monthly expenses, with each month’s expenses sorted by the amount:

<div class="smallexample">

<pre class="smallexample">$ ledger -M --period-sort "(amount)" reg ^expenses
</pre>

</div>

Now, you might wonder where the money came from to pay for these things. To see that report, add <samp>--related (-r)</samp>, which shows the “related account” postings:

<div class="smallexample">

<pre class="smallexample">$ ledger -M --period-sort "(amount)" -r reg ^expenses
</pre>

</div>

But maybe this prints too much information. You might just want to see how much you’re spending with your MasterCard. That kind of query requires the use of a display predicate, since the postings calculated must match ‘<samp>^expenses</samp>’, while the postings displayed must match ‘<samp>mastercard</samp>’. The command would be:

<div class="smallexample">

<pre class="smallexample">$ ledger -M -r --display 'account=~/mastercard/' reg ^expenses
</pre>

</div>

This query says: Report monthly subtotals; report the “related account” postings; display only related postings whose account matches ‘<samp>mastercard</samp>’, and base the calculation on postings matching ‘<samp>^expenses</samp>’.

This works just as well for reporting the overall total, too:

<div class="smallexample">

<pre class="smallexample">$ ledger -s -r --display "account=~/mastercard/" reg ^expenses
</pre>

</div>

The <samp>--subtotal (-s)</samp> option subtotals all postings, just as <samp>--monthly (-M)</samp> subtotaled by the month. The running total in both cases is off, however, since a display expression is being used.

* * *

<a name="Advanced-Reports"></a>

<div class="header">

Previous: [Typical queries](#Typical-queries), Up: [Building Reports](#Building-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Advanced-Reports-1"></a>

### 6.4 Advanced Reports

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Asset Allocation](#Asset-Allocation):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Visualizing with Gnuplot](#Visualizing-with-Gnuplot):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Asset-Allocation"></a>

<div class="header">

Next: [Visualizing with Gnuplot](#Visualizing-with-Gnuplot), Previous: [Advanced Reports](#Advanced-Reports), Up: [Advanced Reports](#Advanced-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Asset-Allocation-1"></a>

#### 6.4.1 Asset Allocation

A very popular method of managing portfolios is to control the percent allocation of assets by certain categories. The mix of categories and the weights applied to them vary by investing philosophy, but most follow a similar pattern. Tracking asset allocation in ledger is not difficult but does require some additional effort to describe how the various assets you own contribute to the asset classes you want to track.

In our simple example we assume you want to apportion your assets into the general categories of domestic and international equities (stocks) and a combined category of bonds and cash. For illustrative purposes, we will use several publicly available mutual funds from Vanguard. The three funds we will track are the Vanguard 500 IDX FD Signal (VIFSX), the Vanguard Target Retirement 2030 (VTHRX), and the Vanguard Short Term Federal Fund (VSGBX). Each of these funds allocates assets to different categories of the investment universe and in different proportions. When you buy a share of VTHRX, that share is partially invested in equities, and partially invested in bonds and cash. Below is the asset allocation for each of the instruments listed above:

<table>

<tbody>

<tr>

<td width="20%"></td>

<td width="20%">Domestic</td>

<td width="30%">Global</td>

<td width="30%"></td>

</tr>

<tr>

<td width="20%">Symbol</td>

<td width="20%">Equity</td>

<td width="30%">Equity</td>

<td width="30%">bonds/cash</td>

</tr>

<tr>

<td width="20%">VIFSX</td>

<td width="20%">100%</td>

<td width="30%"></td>

<td width="30%"></td>

</tr>

<tr>

<td width="20%">VTHRX</td>

<td width="20%">24.0%</td>

<td width="30%">56.3%</td>

<td width="30%">19.7%</td>

</tr>

<tr>

<td width="20%">VSGBX</td>

<td width="20%"></td>

<td width="30%"></td>

<td width="30%">100%</td>

</tr>

</tbody>

</table>

These numbers are available from the prospectus of any publicly available mutual fund. Of course a single stock issue is 100% equity and a single bond issue is 100% bonds.

We track purchases of specific investments using the symbol of that investment as its commodity. How do we tell Ledger that a share of VTHRX is 24% Domestic equity? Enter automatic transactions and virtual accounts.

At the top of our ledger we enter automatic transactions that describe these proportions to Ledger. In the same entries we set up virtual accounts that let us separate these abstract calculations from our actual balances.

For the three instruments listed above, those automatic transactions would look like:

<div class="smallexample">

<pre class="smallexample">= expr ( commodity == 'VIFSX' )
    (Allocation:Equities:Domestic)             1.000

= expr ( commodity == 'VTHRX' )
    (Allocation:Equities:Global)               0.240
    (Allocation:Equities:Domestic)             0.563
    (Allocation:Bonds/Cash)                    0.197

= expr ( commodity == 'VBMFX')
    (Allocation:Bonds/Cash)                    1.000

2015-01-01 Buy VIFSX
    Assets:Broker                                100 VIFSX
    Assets:Cash                              $-10000

2015-01-01 Buy VTHRX
    Assets:Broker                                 10 VTHRX
    Assets:Cash                              $-10000

2015-01-01 Buy VBMFX
    Assets:Broker                                  1 VBMFX
    Assets:Cash                              $-10000
</pre>

</div>

How do these work? First the ‘<samp>=</samp>’ sign at the beginning of the line tells ledger this is an automatic transaction to be applied when the condition following the ‘<samp>=</samp>’ is true. After the ‘<samp>=</samp>’ sign is a value expression (see [Value Expressions](#Value-Expressions)) that returns true any time a posting contains the commodity of interest.

The following line gives the proportions (not percentages) of each unit of commodity that belongs to each asset class. Whenever Ledger sees a buy or sell of a particular commodity it will credit or debit these virtual accounts with that proportion of the number of shares moved.

Now that Ledger understands how to distribute the commodities amongst the various asset classes how do we get a report that tells us our current allocation? Using the balance command and some tricky formatting!

<div class="smallexample">

<pre class="smallexample">ledger bal Allocation --current --format "\
        %-17((depth_spacer)+(partial_account))\
        %10(percent(market(display_total), market(parent.total)))\
        %16(market(display_total))\n%/"
</pre>

</div>

Which yields:

<div class="smallexample">

<pre class="smallexample">        Allocation                  100.00%                  $30000
          Bonds/Cash                 39.90%                  $11970
          Equities                   60.10%                  $18030
            Domestic                 86.69%                  $15630
            Global                   13.31%                   $2400
</pre>

</div>

Let’s look at the Ledger invocation a bit closer. The command above is split into lines for clarity. The first line is very vanilla Ledger asking for the current balances of the account in the “Allocation” tree, using a special formatter.

<a name="index-depth_005fspacer"></a><a name="index-display_005ftotal"></a><a name="index-parent_002etotal"></a>

The magic is in the formatter. The second line simply tells Ledger to print the partial account name indented by its depth in the tree. The third line is where we calculate and display the percentages. The `display_total` command gives the values of the total calculated for the account in this line. The `parent.total` command gives the total for the next level up in the tree. `percent` formats their ratio as a percentage. The fourth line tells ledger to display the current market value of the line. The last two characters ‘<samp>%/</samp>’ tell Ledger what to do for the last line, in this case, nothing.

* * *

<a name="Visualizing-with-Gnuplot"></a>

<div class="header">

Previous: [Asset Allocation](#Asset-Allocation), Up: [Advanced Reports](#Advanced-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Visualizing-with-Gnuplot-1"></a>

#### 6.4.2 Visualizing with Gnuplot

<a name="index-plotting"></a><a name="index-Gnuplot"></a><a name="index-_002d_002damount_002ddata"></a><a name="index-_002d_002dtotal_002ddata"></a><a name="index-_002d_002dlimit-EXPR-1"></a><a name="index-_002d_002ddisplay-EXPR-1"></a>

If you have the “Gnuplot” program installed, you can graph any of the above register reports. The script to do this is included in the ledger distribution, and is named <samp>contrib/report</samp>. Install <samp>report</samp> anywhere along your `PATH`, and then use <samp>report</samp> instead of <samp>ledger</samp> when doing a register report. The only thing to keep in mind is that you must specify <samp>--amount-data (-j)</samp> or <samp>--total-data (-J)</samp> to indicate whether “Gnuplot” should plot the amount, or the running total. For example, this command plots total monthly expenses made on your MasterCard.

<div class="smallexample">

<pre class="smallexample">$ report -j -M -r --display "account =~ /mastercard/" reg ^expenses
</pre>

</div>

The <samp>report</samp> script is a very simple Bourne shell script, that passes a set of scripted commands to “Gnuplot”. Feel free to modify the script to your liking, since you may prefer histograms to line plots, for example.

Here are some useful plots:

<div class="smallexample">

<pre class="smallexample">report -j -M reg ^expenses         # monthly expenses
report -J reg checking             # checking account balance
report -J reg ^income ^expenses    # cash flow report

# net worth report, ignoring non-$ postings

report -J -l "Ua>={\$0.01}" reg ^assets ^liab

# net worth report starting last February. the use of a display
# predicate (-d) is needed, otherwise the balance will start at
# zero, and thus the y-axis will not reflect the true balance

report -J -l "Ua>={\$0.01}" -d "d>=[last feb]" reg ^assets ^liab
</pre>

</div>

The last report uses both a calculation predicate <samp>--limit <var>EXPR</var> (-l)</samp> and a display predicate <samp>--display <var>EXPR</var> (-d)</samp>. The calculation predicate limits the report to postings whose amount is greater than or equal to $1 (which can only happen if the posting amount is in dollars). The display predicate limits the transactions _displayed_ to just those since last February, even though those transactions from before will be computed as part of the balance.

* * *

<a name="Reporting-Commands"></a>

<div class="header">

Next: [Command-Line Syntax](#Command_002dLine-Syntax), Previous: [Building Reports](#Building-Reports), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Reporting-Commands-1"></a>

## 7 Reporting Commands

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Primary Financial Reports](#Primary-Financial-Reports):</td>

<td>  </td>

<td align="left" valign="top">Reports in other formats:: Reports about</td>

</tr>

<tr>

<td align="left" valign="top">• [Reports in other Formats](#Reports-in-other-Formats):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Reports about your Journals](#Reports-about-your-Journals):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Primary-Financial-Reports"></a>

<div class="header">

Next: [Reports in other Formats](#Reports-in-other-Formats), Previous: [Reporting Commands](#Reporting-Commands), Up: [Reporting Commands](#Reporting-Commands)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Primary-Financial-Reports-1"></a>

### 7.1 Primary Financial Reports

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [The `balance` command](#The-balance-command):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [The `equity` command](#The-equity-command):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [The `register` command](#The-register-command):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [The `print` command](#The-print-command):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="The-balance-command"></a>

<div class="header">

Next: [The `equity` command](#The-equity-command), Previous: [Primary Financial Reports](#Primary-Financial-Reports), Up: [Primary Financial Reports](#Primary-Financial-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-balance-command-1"></a>

#### 7.1.1 The `balance` command

<a name="index-balance-1"></a>

The `balance` command reports the current balance of all accounts. It accepts a list of optional regexes, which confine the balance report to the matching accounts. If an account contains multiple types of commodities, each commodity’s total is reported separately.

* * *

<a name="The-equity-command"></a>

<div class="header">

Next: [The `register` command](#The-register-command), Previous: [The `balance` command](#The-balance-command), Up: [Primary Financial Reports](#Primary-Financial-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-equity-command-1"></a>

#### 7.1.2 The `equity` command

<a name="index-equity-1"></a>

The `equity` command prints out account balances as if they were transactions. This makes it easy to establish the starting balances for an account, such as when [Archiving Previous Years](#Archiving-Previous-Years).

* * *

<a name="The-register-command"></a>

<div class="header">

Next: [The `print` command](#The-print-command), Previous: [The `equity` command](#The-equity-command), Up: [Primary Financial Reports](#Primary-Financial-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-register-command-1"></a>

#### 7.1.3 The `register` command

<a name="index-register-4"></a><a name="index-_002d_002damount_002ddata-1"></a><a name="index-_002d_002dtotal_002ddata-1"></a>

The `register` command displays all the postings occurring in a single account, line by line. The account regex must be specified as the only argument to this command. If any regexes occur after the required account name, the register will contain only those postings that match, which makes it very useful for hunting down a particular posting.

The output from `register` is very close to what a typical checkbook, or single-account ledger, would look like. It also shows a running balance. The final running balance of any register should always be the same as the current balance of that account.

If you have “Gnuplot” installed, you may plot the amount or running total of any register by using the script <samp>report</samp>, which is included in the Ledger distribution. The only requirement is that you add either <samp>--amount-data (-j)</samp> or <samp>--total-data (-J)</samp> to your `register` command, in order to plot either the amount or total column, respectively.

* * *

<a name="The-print-command"></a>

<div class="header">

Previous: [The `register` command](#The-register-command), Up: [Primary Financial Reports](#Primary-Financial-Reports)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-print-command-1"></a>

#### 7.1.4 The `print` command

<a name="index-print-3"></a>

The `print` command prints out ledger transactions in a textual format that can be parsed by Ledger. They will be properly formatted, and output in the most economic form possible. The `print` command also takes a list of optional regexes, which will cause only those postings which match in some way to be printed.

The `print` command can be a handy way to clean up a ledger file whose formatting has gotten out of hand.

* * *

<a name="Reports-in-other-Formats"></a>

<div class="header">

Next: [Reports about your Journals](#Reports-about-your-Journals), Previous: [Primary Financial Reports](#Primary-Financial-Reports), Up: [Reporting Commands](#Reporting-Commands)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Reports-in-other-Formats-1"></a>

### 7.2 Reports in other Formats

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Comma Separated Values files](#Comma-Separated-Values-files):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [The `lisp` command](#The-lisp-command):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Emacs `org` Mode](#Emacs-org-Mode):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Org mode with Babel](#Org-mode-with-Babel):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [The `pricemap` command](#The-pricemap-command):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [The `xml` command](#The-xml-command):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [`prices` and `pricedb` commands](#prices-and-pricedb-commands):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Comma-Separated-Values-files"></a>

<div class="header">

Next: [The `lisp` command](#The-lisp-command), Previous: [Reports in other Formats](#Reports-in-other-Formats), Up: [Reports in other Formats](#Reports-in-other-Formats)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Comma-Separated-Values-files-1"></a>

#### 7.2.1 Comma Separated Values files

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [The `csv` command](#The-csv-command):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [The `convert` command](#The-convert-command):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="The-csv-command"></a>

<div class="header">

Next: [The `convert` command](#The-convert-command), Previous: [Comma Separated Values files](#Comma-Separated-Values-files), Up: [Comma Separated Values files](#Comma-Separated-Values-files)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-csv-command-1"></a>

#### 7.2.1.1 The `csv` command

<a name="index-csv"></a>

The `csv` command prints the desired ledger transactions in a csv format suitable for importing into other programs. You can specify the transactions to print using all the normal limiting and searching functions.

* * *

<a name="The-convert-command"></a>

<div class="header">

Previous: [The `csv` command](#The-csv-command), Up: [Comma Separated Values files](#Comma-Separated-Values-files)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-convert-command-1"></a>

#### 7.2.1.2 The `convert` command

<a name="index-csv-importing-1"></a><a name="index-comma-separated-variable-file-reading"></a><a name="index-convert"></a><a name="index-_002d_002dinput_002ddate_002dformat-DATE_005fFORMAT"></a>

The `convert` command parses a comma separated value (csv) file and prints Ledger transactions. Many banks offer csv file downloads. Unfortunately, the file formats, aside from the commas, are all different. The ledger `convert` command tries to help as much as it can.

Your bank’s csv files will have fields in different orders from other banks, so there must be a way to tell Ledger what to expect. Insert a line at the beginning of the csv file that describes the fields to Ledger.

For example, this is a portion of a csv file downloaded from a credit union in the United States:

<div class="smallexample">

<pre class="smallexample">Account Name: VALUFIRST CHECKING
Account Number: 71
Date Range: 11/13/2011 - 12/13/2011

Transaction Number,Date,Description,Memo,Amount Debit,Amount Credit,Balance,Check Number,Fees
767718,12/13/2011,"Withdrawal","ACE HARDWARE 16335 S HOUGHTON RD",-8.80,,00001640.04,,
767406,12/13/2011,"Withdrawal","ACE HARDWARE 16335 S HOUGHTON RD",-1.03,,00001648.84,,
683342,12/13/2011,"Visa Checking","NetFlix Date 12/12/11 000326585896 5968",-21.85,,00001649.87,,
639668,12/13/2011,"Withdrawal","ID: 1741472662 CO: XXAA.COM PAYMNT",-236.65,,00001671.72,,
1113648,12/12/2011,"Withdrawal","Tuscan IT #00037657",-29.73,,00001908.37,,
</pre>

</div>

Unfortunately, as it stands Ledger cannot read it, but you can. Ledger expects the first line to contain a description of the fields on each line of the file. The fields ledger can recognize contain these case-insensitive strings `date`, `posted`, `code`, `payee` or `desc` or `description`, `amount`, `cost`, `total`, and `note`.

Delete the account description lines at the top, and replace the first line in the data above with:

<div class="smallexample">

<pre class="smallexample">,date,payee,note,amount,,,code,
</pre>

</div>

Then execute ledger like this:

<div class="smallexample">

<pre class="smallexample">$ ledger convert download.csv --input-date-format "%m/%d/%Y"
</pre>

</div>

Where the <samp>--input-date-format <var>DATE_FORMAT</var></samp> option tells ledger how to interpret the dates.

Importing csv files is a lot of work, but is very amenable to scripting.

If there are columns in the bank data you would like to keep in your ledger data, besides the primary fields described above, you can name them in the field descriptor list and Ledger will include them in the transaction as meta data if it doesn’t recognize the field name. For example, if you want to capture the bank transaction number and it occurs in the first column of the data use:

<div class="smallexample">

<pre class="smallexample">transid,date,payee,note,amount,,,code,
</pre>

</div>

Ledger will include ‘<samp>; transid: 767718</samp>’ in the first transaction from the file above.

<a name="index-_002d_002dinvert"></a><a name="index-_002d_002dauto_002dmatch"></a><a name="index-_002d_002daccount-STR"></a><a name="index-_002d_002drich_002ddata"></a>

The `convert` command accepts four options. They are <samp>--invert</samp> which inverts the amount field, <samp>--auto-match</samp> which automatically matches an account from the Ledger journal for every CSV line, <samp>--account <var>STR</var></samp> which you can use to specify the account to balance against, and <samp>--rich-data</samp> which stores additional tag/value pairs.

Using the two first lines of the above csv file,

<div class="smallexample">

<pre class="smallexample">,date,payee,note,amount,,,code,
767718,12/13/2011,"Withdrawal","ACE HARDWARE 16335 S HOUGHTON RD",-8.80,,00001640.04,,
767406,12/13/2011,"Withdrawal","ACE HARDWARE 16335 S HOUGHTON RD",-1.03,,00001648.84,,
</pre>

</div>

and launching the below command,

<div class="smallexample">

<pre class="smallexample">$ ledger convert download.csv --input-date-format "%m/%d/%Y" \
  --invert --account Assets:MyBank --rich-data \
  --file sample.dat --now=2012/01/13
</pre>

</div>

you will get the result:

<div class="smallexample">

<pre class="smallexample">2011/12/13 * Withdrawal  ;ACE HARDWARE 16335 S HOUGHTON RD
    ; CSV: 767718,12/13/2011,"Withdrawal","ACE HARDWARE 16335 S HOUGHTON RD",-8.80,,00001640.04,,
    ; Imported: 2012/01/13
    ; UUID: dfdc3c3d5c54c6967dd39d5b4e4fd1ea76e87233
    Expenses:Unknown                             8.8
    Assets:MyBank

2011/12/13 * Withdrawal  ;ACE HARDWARE 16335 S HOUGHTON RD
    ; CSV: 767406,12/13/2011,"Withdrawal","ACE HARDWARE 16335 S HOUGHTON RD",-1.03,,00001648.84,,
    ; Imported: 2012/01/13
    ; UUID: 63086448b1f29f7fd6efb11ea40660185a213f9d
    Expenses:Unknown                            1.03
    Assets:MyBank
</pre>

</div>

The three added metadata are: ‘<samp>CSV</samp>’ as the original line from csv file, ‘<samp>Imported</samp>’ as the date when the csv file was imported into Ledger, and ‘<samp>UUID</samp>’ as a checksum of original csv line.

If an entry with the same ‘<samp>UUID</samp>’ tag is already included in the normal ledger file (specified via <samp>--file <var>FILE</var> (-f)</samp> or via the environment variable `LEDGER_FILE`) this entry will not be printed again.

In the output above, the account is ‘<samp>Expenses:Unknown</samp>’ for CSV lines. You can use the <samp>--auto-match</samp> option to automatically match an account from your Ledger journal.

You can also use `convert` with `payee` and `account` directives. First, you can use the `payee` and `alias` directive to rewrite the `payee` field based on some rules. Then you can use the account and its `payee` directive to specify the account. I use it like this, for example:

<div class="smallexample">

<pre class="smallexample">payee Aldi
    alias ^ALDI SUED SAGT DANKE
account Aufwand:Einkauf:Lebensmittel
    payee ^(Aldi|Alnatura|Kaufland|REWE)$
</pre>

</div>

Note that it may be necessary for the output of ‘<samp>ledger convert</samp>’ to be passed through `ledger print` a second time if you want to match on the new payee field. During the `ledger convert` run, only the original payee name as specified in the csv data seems to be used.

* * *

<a name="The-lisp-command"></a>

<div class="header">

Next: [Emacs `org` Mode](#Emacs-org-Mode), Previous: [Comma Separated Values files](#Comma-Separated-Values-files), Up: [Reports in other Formats](#Reports-in-other-Formats)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-lisp-command-1"></a>

#### 7.2.2 The `lisp` command

<a name="index-lisp"></a><a name="index-emacs"></a>

The `lisp` command prints results in a form that can be read directly by Emacs Lisp. The format of the `sexp` is:

<div class="smallexample">

<pre class="smallexample">((BEG-POS CLEARED DATE CODE PAYEE
  (ACCOUNT AMOUNT)...)  ; list of postings
 ...)                   ; list of transactions
</pre>

</div>

`emacs` can also be used as a synonym for `lisp`.

* * *

<a name="Emacs-org-Mode"></a>

<div class="header">

Next: [Org mode with Babel](#Org-mode-with-Babel), Previous: [The `lisp` command](#The-lisp-command), Up: [Reports in other Formats](#Reports-in-other-Formats)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Emacs-org-Mode-1"></a>

#### 7.2.3 Emacs `org` Mode

<a name="index-org"></a>

The `org` command produces a journal file suitable for use in the Emacs Org mode. More details on using Org mode can be found at [http://www.orgmode.org](http://www.orgmode.org).

Org mode has a sub-system known as Babel which allows for literate programming. This allows you to mix text and code within the same document and automatically execute code which may generate results which will then appear in the text.

One of the languages supported by Babel is Ledger, so that you can have ledger commands embedded in a text file and have the output of ledger commands also appear in the text file. The output can be updated whenever any new ledger entries are added.

For instance, the following Org mode text document snippet illustrates a very naive but still useful application of the Babel system:

<div class="smallexample">

<pre class="smallexample">* A simple test of ledger in an org file
The following are some entries and I have requested that ledger be run
to generate a balance on the accounts.  I could have asked for
a register or, in fact, anything at all the ledger can do through
command-line options.

#+begin_src ledger :cmdline bal :results value
2010/01/01 * Starting balance
  assets:bank:savings       £1300.00
  income:starting balances
2010/07/22 * Got paid
  assets:bank:chequing      £1000.00
  income:salary
2010/07/23 Rent
  expenses:rent              £500.00
  assets:bank:chequing
#+end_src

#+results:
:            £1800.00  assets:bank
:             £500.00    chequing
:            £1300.00    savings
:             £500.00  expenses:rent
:           £-2300.00  income
:           £-1000.00    salary
:           £-1300.00    starting balances
</pre>

</div>

Typing <kbd>C-c C-c</kbd> anywhere in the “ledger source code block” will invoke ledger on the contents of that block and generate a “results” block. The results block can appear anywhere in the file but, by default, will appear immediately below the source code block.

You can combine multiple source code blocks before executing ledger and do all kinds of other wonderful things with Babel (and Org mode).

* * *

<a name="Org-mode-with-Babel"></a>

<div class="header">

Next: [The `pricemap` command](#The-pricemap-command), Previous: [Emacs `org` Mode](#Emacs-org-Mode), Up: [Reports in other Formats](#Reports-in-other-Formats)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Org-mode-with-Babel-1"></a>

#### 7.2.4 Org mode with Babel

Using Babel, it is possible to record financial transactions conveniently in an org file and subsequently generate the financial reports required.

As of Org mode 7.01, Ledger support is provided. Check the Babel documentation on Worg for instructions on how to achieve this but I currently do this directly as follows:

<div class="smallexample">

<pre class="smallexample">(org-babel-do-load-languages
 'org-babel-load-languages
 '((ledger . t)         ;this is the important one for this tutorial
  ))
</pre>

</div>

Once Ledger support in Babel has been enabled, we can proceed to include Ledger entries within an org file. There are three ways (at least) in which these can be included:

1.  place all Ledger entries within one single source block and execute this block with different arguments to generate the appropriate reports,
2.  place Ledger entries in more than one source block and use the `noweb` literary programming approach, supported by Babel, to combine these into one block elsewhere in the file for processing by Ledger,
3.  place Ledger entries in different source blocks and use `tangle` to generate a Ledger file which you can subsequently process using Ledger directly.

The first two are described in more detail in this short tutorial.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Embedded Ledger example with single source block](#Embedded-Ledger-example-with-single-source-block):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Multiple Ledger source blocks with `noweb`](#Multiple-Ledger-source-blocks-with-noweb):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Income Entries](#Income-Entries):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Expenses](#Expenses):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Financial Summaries](#Financial-Summaries):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [An overall balance summary](#An-overall-balance-summary):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Generating a monthly register](#Generating-a-monthly-register):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Summary](#Summary):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Embedded-Ledger-example-with-single-source-block"></a>

<div class="header">

Next: [Multiple Ledger source blocks with `noweb`](#Multiple-Ledger-source-blocks-with-noweb), Previous: [Org mode with Babel](#Org-mode-with-Babel), Up: [Org mode with Babel](#Org-mode-with-Babel)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Embedded-Ledger-example-with-single-source-block-1"></a>

#### 7.2.4.1 Embedded Ledger example with single source block

The easiest, albeit possibly least useful, way in which to use Ledger within an org file is to use a single source block to record all Ledger entries. The following is an example source block:

<div class="smallexample">

<pre class="smallexample">#+name: allinone
#+begin_src ledger
2010/01/01 * Starting balance
  assets:bank:savings       £1300.00
  income:starting balances
2010/07/22 * Got paid
  assets:bank:chequing      £1000.00
  income:salary
2010/07/23 Rent
  expenses:rent              £500.00
  assets:bank:chequing
2010/07/24 Food
  expenses:food              £150.00
  assets:bank:chequing
2010/07/31 * Interest on bank savings
  assets:bank:savings          £3.53
  income:interest
2010/07/31 * Transfer savings
  assets:bank:savings        £250.00
  assets:bank:chequing
2010/08/01 got paid again
  assets:bank:chequing      £1000.00
  income:salary
#+end_src
</pre>

</div>

In this example, we have combined both expenses and income into one set of Ledger entries. We can now generate register and balance reports (as well as many other types of reports) using Babel to invoke Ledger with specific arguments. The arguments are passed to Ledger using the `:cmdline` header argument. In the code block above, there is no such argument so the system takes the default. For Ledger code blocks, the default `:cmdline` argument is `bal` and the result of evaluating this code block (<kbd>C-c C-c</kbd>) would be:

<div class="smallexample">

<pre class="smallexample">#+results: allinone()
:            £2653.53  assets:bank
:            £1100.00    chequing
:            £1553.53    savings
:             £650.00  expenses
:             £150.00    food
:             £500.00    rent
:           £-3303.53  income
:              £-3.53    interest
:           £-2000.00    salary
:           £-1300.00    starting balances
</pre>

</div>

If, instead, you wished to generate a register of all the transactions, you would change the `#+begin_src` line for the code block to include the required command-line option:

<div class="smallexample">

<pre class="smallexample">#+begin_src ledger :cmdline reg
</pre>

</div>

Evaluating the code block again would generate a different report.

Having to change the actual directive on the code block and re-evaluate makes it difficult to have more than one view of your transactions and financial state. Eventually, Babel will support passing arguments to `#+call` evaluations of code blocks but this support is missing currently. Instead, we can use the concepts of literary programming, as implemented by the `noweb` features of Babel, to help us.

* * *

<a name="Multiple-Ledger-source-blocks-with-noweb"></a>

<div class="header">

Next: [Income Entries](#Income-Entries), Previous: [Embedded Ledger example with single source block](#Embedded-Ledger-example-with-single-source-block), Up: [Org mode with Babel](#Org-mode-with-Babel)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Multiple-Ledger-source-blocks-with-noweb-1"></a>

#### 7.2.4.2 Multiple Ledger source blocks with `noweb`

The `noweb` feature of Babel allows us to expand references to other code blocks within a code block. For Ledger, this can be used to group transactions according to type, say, and then bring various sets of transactions together to generate reports.

Using the same transactions used above, we could consider splitting these into expenses and income, as follows:

* * *

<a name="Income-Entries"></a>

<div class="header">

Next: [Expenses](#Expenses), Previous: [Multiple Ledger source blocks with `noweb`](#Multiple-Ledger-source-blocks-with-noweb), Up: [Org mode with Babel](#Org-mode-with-Babel)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Income-Entries-1"></a>

#### 7.2.4.3 Income Entries

The first set of entries relates to income, either monthly pay or interest, all typically going into one of my bank accounts. Here, I have placed several entries, but we could have had each entry in a separate `src` block. Note that all code blocks you wish to refer to later must have the `:noweb yes` header argument specified.

<div class="smallexample">

<pre class="smallexample">#+name: income
#+begin_src ledger :noweb yes
2010/01/01 * Starting balance
  assets:bank:savings       £1300.00
  income:starting balances
2010/07/22 * Got paid
  assets:bank:chequing      £1000.00
  income:salary
2010/07/31 * Interest on bank savings
  assets:bank:savings          £3.53
  income:interest
2010/07/31 * Transfer savings
  assets:bank:savings        £250.00
  assets:bank:chequing
2010/08/01 got paid again
  assets:bank:chequing      £1000.00
  income:salary
#+end_src
</pre>

</div>

* * *

<a name="Expenses"></a>

<div class="header">

Next: [Financial Summaries](#Financial-Summaries), Previous: [Income Entries](#Income-Entries), Up: [Org mode with Babel](#Org-mode-with-Babel)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Expenses-1"></a>

#### 7.2.4.4 Expenses

The following entries relate to personal expenses, such as rent and food. Again, these have all been placed in a single `src` block but could have been done individually.

<div class="smallexample">

<pre class="smallexample">#+name: expenses
#+begin_src ledger :noweb yes
2010/07/23 Rent
  expenses:rent              £500.00
  assets:bank:chequing
2010/07/24 Food
  expenses:food              £150.00
  assets:bank:chequing
#+end_src
</pre>

</div>

* * *

<a name="Financial-Summaries"></a>

<div class="header">

Next: [An overall balance summary](#An-overall-balance-summary), Previous: [Expenses](#Expenses), Up: [Org mode with Babel](#Org-mode-with-Babel)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Financial-Summaries-1"></a>

#### 7.2.4.5 Financial Summaries

Given the ledger entries defined above in the income and expenses code blocks, we can now refer to these using the noweb expansion directives, `<<name>>`. We can now define different code blocks to generate specific reports for those transactions. Below are two examples, one to generate a balance report and one to generate a register report of all transactions.

* * *

<a name="An-overall-balance-summary"></a>

<div class="header">

Next: [Generating a monthly register](#Generating-a-monthly-register), Previous: [Financial Summaries](#Financial-Summaries), Up: [Org mode with Babel](#Org-mode-with-Babel)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="An-overall-balance-summary-1"></a>

#### 7.2.4.6 An overall balance summary

<a name="index-_002d_002dsubtotal-1"></a>

The overall balance of your account and expenditure with a breakdown according to category is specified by passing the `:cmdline bal` argument to Ledger. This code block can now be evaluated (<kbd>C-c C-c</kbd>) and the results generated by incorporating the transactions referred to by the `<<income>>` and `<<expenses>>` lines.

<div class="smallexample">

<pre class="smallexample">#+name: balance
#+begin_src ledger :cmdline bal :noweb yes
<<income>>
<<expenses>>
#+end_src

#+results: balance
:            £2653.53  assets:bank
:            £1100.00    chequing
:            £1553.53    savings
:             £650.00  expenses
:             £150.00    food
:             £500.00    rent
:           £-3303.53  income
:              £-3.53    interest
:           £-2000.00    salary
:           £-1300.00    starting balances
</pre>

</div>

If you want a less detailed breakdown of where your money is, you can specify the <samp>--collapse (-n)</samp> flag (i.e. ‘<samp>:cmdline -n bal</samp>’) to tell Ledger to exclude sub-accounts in the report.

<div class="smallexample">

<pre class="smallexample">#+begin_src ledger :cmdline -n bal :noweb yes
<<income>>
<<expenses>>
#+end_src

#+results:
:            £2653.53  assets
:             £650.00  expenses
:           £-3303.53  income
</pre>

</div>

* * *

<a name="Generating-a-monthly-register"></a>

<div class="header">

Next: [Summary](#Summary), Previous: [An overall balance summary](#An-overall-balance-summary), Up: [Org mode with Babel](#Org-mode-with-Babel)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Generating-a-monthly-register-1"></a>

#### 7.2.4.7 Generating a monthly register

<a name="index-register-5"></a><a name="index-_002d_002dmonthly-1"></a>

You can also generate a monthly register (the `reg` command) by executing the following `src` block. This presents a summary of transactions for each monthly period (the <samp>--monthly (-M)</samp> argument) with a running total in the final column (which should be 0 at the end if all the entries are correct).

<div class="smallexample">

<pre class="smallexample">#+name: monthlyregister
#+begin_src ledger :cmdline -M reg :noweb yes
<<income>>
<<expenses>>
#+end_src

#+results: monthlyregister
:2010/01/01 - 2010/01/31         assets:bank:savings       £1300.00    £1300.00
:                                in:starting balances     £-1300.00           0
:2010/07/01 - 2010/07/31         assets:bank:chequing       £100.00     £100.00
:                                assets:bank:savings        £253.53     £353.53
:                                expenses:food              £150.00     £503.53
:                                expenses:rent              £500.00    £1003.53
:                                income:interest             £-3.53    £1000.00
:                                income:salary            £-1000.00           0
:2010/08/01 - 2010/08/01         assets:bank:chequing      £1000.00    £1000.00
:                                income:salary            £-1000.00           0
</pre>

</div>

We could also generate a monthly report on our assets showing how these are increasing (or decreasing!). In this case, the final column will be the running total of the assets in our ledger.

<div class="smallexample">

<pre class="smallexample">#+name: monthlyassetsregister
#+begin_src ledger :cmdline -M reg assets :noweb yes
<<income>>
<<expenses>>
#+end_src

#+results: monthlyassetsregister
: 2010/01/01 - 2010/01/31         assets:bank:savings       £1300.00    £1300.00
: 2010/07/01 - 2010/07/31         assets:bank:chequing       £100.00    £1400.00
:                                 assets:bank:savings        £253.53    £1653.53
: 2010/08/01 - 2010/08/01         assets:bank:chequing      £1000.00    £2653.53
</pre>

</div>

* * *

<a name="Summary"></a>

<div class="header">

Previous: [Generating a monthly register](#Generating-a-monthly-register), Up: [Org mode with Babel](#Org-mode-with-Babel)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Summary-1"></a>

#### 7.2.4.8 Summary

This short tutorial shows how Ledger entries can be embedded in an org file and manipulated using Babel. However, only simple Ledger features have been illustrated; please refer to the Ledger documentation for examples of more complex operations on a ledger.

* * *

<a name="The-pricemap-command"></a>

<div class="header">

Next: [The `xml` command](#The-xml-command), Previous: [Org mode with Babel](#Org-mode-with-Babel), Up: [Reports in other Formats](#Reports-in-other-Formats)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-pricemap-command-1"></a>

#### 7.2.5 The `pricemap` command

<a name="index-pricemap"></a>

If you have the <samp>graphviz</samp> graph visualization package installed, ledger can generate a graph of the relationship between your various commodities. The output file is in the “dot” format.

This is probably not very interesting, unless you have many different commodities valued in terms of each other. For example, multiple currencies and multiple investments valued in those currencies.

* * *

<a name="The-xml-command"></a>

<div class="header">

Next: [`prices` and `pricedb` commands](#prices-and-pricedb-commands), Previous: [The `pricemap` command](#The-pricemap-command), Up: [Reports in other Formats](#Reports-in-other-Formats)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="The-xml-command-1"></a>

#### 7.2.6 The `xml` command

<a name="index-xml"></a>

By default, Ledger uses a human-readable data format, and displays its reports in a manner meant to be read on screen. For the purpose of writing tools which use Ledger, however, it is possible to read and display data using XML. This section documents that format.

The general format used for Ledger data is:

<div class="smallexample">

<pre class="smallexample"><?xml version="1.0"?>
<ledger>
  <xact>...</xact>
  <xact>...</xact>
  <xact>...</xact>...
</ledger>
</pre>

</div>

The data stream is enclosed in a `ledger` tag, which contains a series of one or more transactions. Each `xact` describes one transaction and contains a series of one or more postings:

<div class="smallexample">

<pre class="smallexample"><xact>
  <en:date>2004/03/01</en:date>
  <en:cleared/>
  <en:code>100</en:code>
  <en:payee>John Wiegley</en:payee>
  <en:postings>
    <posting>...</posting>
    <posting>...</posting>
    <posting>...</posting>...
  </en:postings>
</xact>
</pre>

</div>

The date format for `en:date` is always `YYYY/MM/DD`. The `en:cleared` tag is optional, and indicates whether the posting has been cleared or not. There is also an `en:pending` tag, for marking pending postings. The `en:code` and `en:payee` tags both contain whatever text the user wishes.

After the initial transaction data, there must follow a set of postings marked with `en:postings`. Typically these postings will all balance each other, but if not they will be automatically balanced into an account named ‘<samp>Unknown</samp>’.

Within the `en:postings` tag is a series of one or more `posting`’s, which have the following form:

<div class="smallexample">

<pre class="smallexample"><posting>
  <tr:account>Expenses:Computer:Hardware</tr:account>
  <tr:amount>
    <value type="amount">
      <amount>
        <commodity flags="PT">$</commodity>
        <quantity>90.00</quantity>
      </amount>
    </value>
  </tr:amount>
</posting>
</pre>

</div>

This is a basic posting. It may also begin with `tr:virtual` and/or `tr:generated` tags, to indicate virtual and auto-generated postings. Then follows the `tr:account` tag, which contains the full name of the account the posting is related to. Colons separate parent from child in an account name.

Lastly follows the amount of the posting, indicated by `tr:amount`. Within this tag is a `value` tag, of which there are four different kinds, each with its own format:

1.  Boolean,
2.  integer,
3.  amount,
4.  balance.

The format of a Boolean value is `true` or `false` surrounded by a `boolean` tag, for example:

<div class="smallexample">

<pre class="smallexample"><boolean>true</boolean>
</pre>

</div>

The format of an integer value is the numerical value surrounded by an `integer` tag, for example:

<div class="smallexample">

<pre class="smallexample"><integer>12036</integer>
</pre>

</div>

The format of an amount contains two members, the commodity and the quantity. The commodity can have a set of flags that indicate how to display it. The meaning of the flags (all of which are optional) are:

<dl compact="compact">

<dt>`P`</dt>

<dd>

The commodity is prefixed to the value.

</dd>

<dt>`S`</dt>

<dd>

The commodity is separated from the value by a space.

</dd>

<dt>`T`</dt>

<dd>

Thousands markers are used to display the amount.

</dd>

<dt>`E`</dt>

<dd>

The format of the amount is European, with period used as a thousands marker, and comma used as the decimal point.

</dd>

</dl>

The actual quantity for an amount is an integer of arbitrary size. Ledger uses the GNU multiple precision arithmetic library to handle such values. The XML format assumes the reader to be equally capable. Here is an example amount:

<div class="smallexample">

<pre class="smallexample"><value type="amount">
  <amount>
    <commodity flags="PT">$</commodity>
    <quantity>90.00</quantity>
  </amount>
</value>
</pre>

</div>

Lastly, a balance value contains a series of amounts, each with a different commodity. Unlike the name, such a value does need to balance. It is called a balance because it sums several amounts. For example:

<div class="smallexample">

<pre class="smallexample"><value type="balance">
  <balance>
    <amount>
      <commodity flags="PT">$</commodity>
      <quantity>90.00</quantity>
    </amount>
    <amount>
      <commodity flags="TE">DM</commodity>
      <quantity>200.00</quantity>
    </amount>
  </balance>
</value>
</pre>

</div>

That is the extent of the XML data format used by Ledger. It will output such data if the `xml` command is used, and can read the same data.

* * *

<a name="prices-and-pricedb-commands"></a>

<div class="header">

Previous: [The `xml` command](#The-xml-command), Up: [Reports in other Formats](#Reports-in-other-Formats)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="prices-and-pricedb-commands-1"></a>

#### 7.2.7 `prices` and `pricedb` commands

<a name="index-prices"></a><a name="index-pricedb"></a><a name="index-_002d_002daverage"></a>

The `prices` command displays the price history for matching commodities. The <samp>--average (-A)</samp> option is useful with this report, to display the running average price, or <samp>--deviation (-D)</samp> to show each price’s deviation from that average.

There is also a `pricedb` command which outputs the same information as `prices`, but does so in a format that can be parsed by Ledger. This is useful for generating and tidying up pricedb database files.

* * *

<a name="Reports-about-your-Journals"></a>

<div class="header">

Previous: [Reports in other Formats](#Reports-in-other-Formats), Up: [Reporting Commands](#Reporting-Commands)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Reports-about-your-Journals-1"></a>

### 7.3 Reports about your Journals

<a name="index-_002d_002dcount"></a>

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [`accounts`](#accounts):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [`payees`](#payees):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [`commodities`](#commodities):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [`tags`](#tags):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [`xact`](#xact):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [`stats`](#stats):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [`select`](#select):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="accounts"></a>

<div class="header">

Next: [`payees`](#payees), Previous: [Reports about your Journals](#Reports-about-your-Journals), Up: [Reports about your Journals](#Reports-about-your-Journals)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="accounts-1"></a>

#### 7.3.1 `accounts`

<a name="index-accounts-1"></a>

The `accounts` command reports all of the accounts in the journal. Following the command with a regular expression will limit the output to accounts matching the regex. The output is sorted by name. Using the <samp>--count</samp> option will tell you how many entries use each account.

* * *

<a name="payees"></a>

<div class="header">

Next: [`commodities`](#commodities), Previous: [`accounts`](#accounts), Up: [Reports about your Journals](#Reports-about-your-Journals)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="payees-1"></a>

#### 7.3.2 `payees`

<a name="index-payees-1"></a>

The `payees` command reports all of the unique payees in the journal. Using the <samp>--count</samp> option will tell you how many entries use each payee. To filter the payees displayed you must use the prefix @:

<div class="smallexample">

<pre class="smallexample">$ ledger payees @Nic
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">Nicolas
Nicolas BOILABUS
Oudtshoorn Municipality
Vaca Veronica
</pre>

</div>

* * *

<a name="commodities"></a>

<div class="header">

Next: [`tags`](#tags), Previous: [`payees`](#payees), Up: [Reports about your Journals](#Reports-about-your-Journals)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="commodities-1"></a>

#### 7.3.3 `commodities`

<a name="index-commodities"></a>

Report all commodities present in the journals under consideration. The output is sorted by name. Using the <samp>--count</samp> option will tell you how many entries use each commodity.

* * *

<a name="tags"></a>

<div class="header">

Next: [`xact`](#xact), Previous: [`commodities`](#commodities), Up: [Reports about your Journals](#Reports-about-your-Journals)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="tags-1"></a>

#### 7.3.4 `tags`

<a name="index-tags-1"></a><a name="index-_002d_002dvalues"></a>

The `tags` command reports all of the tags in the journal. The output is sorted by name. Using the <samp>--count</samp> option will tell you how many entries use each tag. Using the <samp>--values</samp> option will report the values used by each tag.

* * *

<a name="xact"></a>

<div class="header">

Next: [`stats`](#stats), Previous: [`tags`](#tags), Up: [Reports about your Journals](#Reports-about-your-Journals)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="xact-1"></a>

#### 7.3.5 `xact`

<a name="index-draft"></a><a name="index-entry"></a><a name="index-xact-1"></a>

The `xact` command simplifies the creation of new transactions. It works on the principle that 80% of all postings are variants of earlier postings. Here’s how it works:

Say you currently have this posting in your ledger file:

<div class="smallexample">

<pre class="smallexample">2004/03/15 * Viva Italiano
    Expenses:Food                       $12.45
    Expenses:Tips                        $2.55
    Liabilities:MasterCard             $-15.00
</pre>

</div>

Now it’s ‘<samp>2004/4/9</samp>’, and you’ve just eaten at ‘<samp>Viva Italiano</samp>’ again. The exact amounts are different, but the overall form is the same. With the `xact` command you can type:

<div class="smallexample">

<pre class="smallexample">$ ledger xact 2004/4/9 viva food 11 tips 2.50
</pre>

</div>

This produces the following output:

<div class="smallexample">

<pre class="smallexample">2004/04/09 Viva Italiano
    Expenses:Food                             $11.00
    Expenses:Tips                              $2.50
    Liabilities:MasterCard
</pre>

</div>

It works by finding a past posting matching the regular expression ‘<samp>viva</samp>’, and assuming that any accounts or amounts specified will be similar to that earlier posting. If Ledger does not succeed in generating a new transaction, an error is printed and the exit code is set to ‘<samp>1</samp>’.

Here are a few more examples of the `xact` command, assuming the above journal transaction:

<div class="smallexample">

<pre class="smallexample">$ ledger xact 4/9 viva 11.50
$ ledger xact 4/9 viva 11.50 checking # (from `checking')
$ ledger xact 4/9 viva food 11.50 tips 8
$ ledger xact 4/9 viva food 11.50 tips 8 cash
$ ledger xact 4/9 viva food $11.50 tips $8 cash
$ ledger xact 4/9 viva dining "DM 11.50"
</pre>

</div>

`draft` and `entry` are both synonyms of `xact`. `entry` is provided for backwards compatibility with Ledger 2.X.

* * *

<a name="stats"></a>

<div class="header">

Next: [`select`](#select), Previous: [`xact`](#xact), Up: [Reports about your Journals](#Reports-about-your-Journals)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="stats-1"></a>

#### 7.3.6 `stats`

<a name="index-stats"></a><a name="index-stat"></a>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

* * *

<a name="select"></a>

<div class="header">

Previous: [`stats`](#stats), Up: [Reports about your Journals](#Reports-about-your-Journals)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="select-1"></a>

#### 7.3.7 `select`

<a name="index-select"></a>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

* * *

<a name="Command_002dLine-Syntax"></a>

<div class="header">

Next: [Budgeting and Forecasting](#Budgeting-and-Forecasting), Previous: [Reporting Commands](#Reporting-Commands), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Command_002dLine-Syntax-1"></a>

## 8 Command-Line Syntax

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Basic Usage](#Basic-Usage):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Command-Line Quick Reference](#Command_002dLine-Quick-Reference):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Detailed Option Description](#Detailed-Option-Description):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Period Expressions](#Period-Expressions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Basic-Usage"></a>

<div class="header">

Next: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference), Previous: [Command-Line Syntax](#Command_002dLine-Syntax), Up: [Command-Line Syntax](#Command_002dLine-Syntax)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Basic-Usage-1"></a>

### 8.1 Basic Usage

This chapter describes Ledger’s features and options. You may wish to survey this to get an overview before diving into the [Ledger Tutorial](#Ledger-Tutorial) and more detailed examples that follow.

Ledger has a very simple command-line interface, named—enticingly enough—<samp>ledger</samp>. It supports a few reporting commands, and a large number of options for refining the output from those commands. The basic syntax of any ledger command is:

<div class="smallexample">

<pre class="smallexample">$ ledger [OPTIONS...] COMMAND [ARGS...]
</pre>

</div>

After the command word there may appear any number of arguments. For most commands, these arguments are regular expressions that cause the output to relate only to postings matching those regular expressions. For the `xact` command, the arguments have a special meaning, described below.

The regular expressions arguments always match the account name that a posting refers to. To match on the payee of the transaction instead, precede the regular expression with ‘<samp>payee</samp>’ or ‘<samp>@</samp>’. For example, the following balance command reports account totals for rent, food and movies, but only those whose payee matches Freddie:

<div class="smallexample">

<pre class="smallexample">$ ledger bal rent food movies payee freddie
</pre>

</div>

or

<div class="smallexample">

<pre class="smallexample">$ ledger bal rent food movies @freddie
</pre>

</div>

There are many, many command options available with the <samp>ledger</samp> program, and it takes a while to master them. However, none of them are required to use the basic reporting commands.

* * *

<a name="Command_002dLine-Quick-Reference"></a>

<div class="header">

Next: [Detailed Option Description](#Detailed-Option-Description), Previous: [Basic Usage](#Basic-Usage), Up: [Command-Line Syntax](#Command_002dLine-Syntax)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Command_002dLine-Quick-Reference-1"></a>

### 8.2 Command-Line Quick Reference

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Basic Reporting Commands](#Basic-Reporting-Commands):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Basic Options](#Basic-Options):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Report Filtering](#Report-Filtering):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Error Checking and Calculation Options](#Error-Checking-and-Calculation-Options):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Output Customization](#Output-Customization):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Grouping Options](#Grouping-Options):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Commodity Reporting](#Commodity-Reporting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Basic-Reporting-Commands"></a>

<div class="header">

Next: [Basic Options](#Basic-Options), Previous: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference), Up: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Basic-Reporting-Commands-1"></a>

#### 8.2.1 Basic Reporting Commands

<dl compact="compact">

<dt>`balance`<a name="index-balance-2"></a></dt>

<dt>`bal`<a name="index-bal"></a></dt>

<dd>

Show account balances.

</dd>

<dt>`register`<a name="index-register-6"></a></dt>

<dt>`reg`<a name="index-reg"></a></dt>

<dd>

Show all transactions with running total.

</dd>

<dt>`csv`<a name="index-csv-1"></a></dt>

<dd><a name="index-csv-exporting"></a>

Show transactions in csv format, for exporting to other programs.

</dd>

<dt>`print`<a name="index-print-4"></a></dt>

<dd>

Print transactions in a format readable by ledger.

</dd>

<dt>`xml`<a name="index-xml-1"></a></dt>

<dd>

Produce XML output of the register command.

</dd>

<dt>`lisp`<a name="index-lisp-1"></a></dt>

<dt>`emacs`<a name="index-emacs-1"></a></dt>

<dd>

Produce s-expression output, suitable for Emacs.

</dd>

<dt>`equity`<a name="index-equity-2"></a></dt>

<dd>

Print account balances as transactions.

</dd>

<dt>`prices`<a name="index-prices-1"></a></dt>

<dd>

Print price history for matching commodities.

</dd>

<dt>`pricedb`<a name="index-pricedb-1"></a></dt>

<dd>

Print price history for matching commodities in a format readable by ledger.

</dd>

<dt>`xact`<a name="index-xact-2"></a></dt>

<dd>

Generate transactions based on previous postings.

</dd>

</dl>

* * *

<a name="Basic-Options"></a>

<div class="header">

Next: [Report Filtering](#Report-Filtering), Previous: [Basic Reporting Commands](#Basic-Reporting-Commands), Up: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Basic-Options-1"></a>

#### 8.2.2 Basic Options

<dl compact="compact">

<dt><samp>--help</samp><a name="index-_002d_002dhelp"></a></dt>

<dt><samp>-h</samp><a name="index-_002dh"></a></dt>

<dd>

Display the man page for <samp>ledger</samp>.

</dd>

<dt><samp>--version</samp><a name="index-_002d_002dversion"></a></dt>

<dd>

Print version information and exit.

</dd>

<dt><samp>--file <var>FILE</var></samp><a name="index-_002d_002dfile-FILE"></a></dt>

<dt><samp>-f <var>FILE</var></samp><a name="index-_002df-FILE"></a></dt>

<dd>

Read <samp>FILE</samp> as a ledger file.

</dd>

<dt><samp>--output <var>FILE</var></samp><a name="index-_002d_002doutput-FILE"></a></dt>

<dt><samp>-o <var>FILE</var></samp><a name="index-_002do-FILE"></a></dt>

<dd>

Redirect output to <samp>FILE</samp>.

</dd>

<dt><samp>--init-file <var>FILE</var></samp><a name="index-_002d_002dinit_002dfile-FILE"></a></dt>

<dt><samp>-i <var>FILE</var></samp><a name="index-_002di-FILE"></a></dt>

<dd>

Specify an options file.

</dd>

<dt><samp>--import <var>FILE</var></samp><a name="index-_002d_002dimport-FILE"></a></dt>

<dd>

Import <var>FILE</var> as Python module.

</dd>

<dt><samp>--account <var>STR</var></samp><a name="index-_002d_002daccount-STR-1"></a></dt>

<dt><samp>-a <var>STR</var></samp><a name="index-_002da-STR"></a></dt>

<dd>

Specify default account <var>STR</var> for QIF file postings.

</dd>

</dl>

* * *

<a name="Report-Filtering"></a>

<div class="header">

Next: [Error Checking and Calculation Options](#Error-Checking-and-Calculation-Options), Previous: [Basic Options](#Basic-Options), Up: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Report-Filtering-1"></a>

#### 8.2.3 Report Filtering

<dl compact="compact">

<dt><samp>--current</samp><a name="index-_002d_002dcurrent"></a></dt>

<dt><samp>-c</samp><a name="index-_002dc"></a></dt>

<dd>

Display only transactions on or before the current date.

</dd>

<dt><samp>--begin <var>DATE</var></samp><a name="index-_002d_002dbegin-DATE"></a></dt>

<dt><samp>-b <var>DATE</var></samp><a name="index-_002db-DATE"></a></dt>

<dd>

Limit the processing to transactions on or after <var>DATE</var>.

</dd>

<dt><samp>--end <var>DATE</var></samp><a name="index-_002d_002dend-DATE"></a></dt>

<dt><samp>-e <var>DATE</var></samp><a name="index-_002de-DATE"></a></dt>

<dd>

Limit the processing to transactions before <var>DATE</var>.

</dd>

<dt><samp>--period <var>PERIOD_EXPRESSION</var></samp><a name="index-_002d_002dperiod-PERIOD_005fEXPRESSION"></a></dt>

<dt><samp>-p <var>PERIOD_EXPRESSION</var></samp><a name="index-_002dp-PERIOD_005fEXPRESSION"></a></dt>

<dd>

Limit the processing to transactions in <var>PERIOD_EXPRESSION</var>.

</dd>

<dt><samp>--period-sort <var>VEXPR</var></samp><a name="index-_002d_002dperiod_002dsort-VEXPR-1"></a></dt>

<dd>

Sort postings within each period according to <var>VEXPR</var>.

</dd>

<dt><samp>--cleared</samp><a name="index-_002d_002dcleared-1"></a></dt>

<dt><samp>-C</samp><a name="index-_002dC"></a></dt>

<dd>

Display only cleared postings.

</dd>

<dt><samp>--dc</samp><a name="index-_002d_002ddc"></a></dt>

<dd>

Display register or balance in debit/credit format.

</dd>

<dt><samp>--uncleared</samp><a name="index-_002d_002duncleared-1"></a></dt>

<dt><samp>-U</samp><a name="index-_002dU"></a></dt>

<dd>

Display only uncleared postings.

</dd>

<dt><samp>--real</samp><a name="index-_002d_002dreal-2"></a></dt>

<dt><samp>-R</samp><a name="index-_002dR"></a></dt>

<dd>

Display only real postings.

</dd>

<dt><samp>--actual</samp><a name="index-_002d_002dactual"></a></dt>

<dt><samp>-L</samp><a name="index-_002dL"></a></dt>

<dd>

Display only actual postings, not automated ones.

</dd>

<dt><samp>--related</samp><a name="index-_002d_002drelated-1"></a></dt>

<dt><samp>-r</samp><a name="index-_002dr"></a></dt>

<dd>

Display related postings.

</dd>

<dt><samp>--budget</samp><a name="index-_002d_002dbudget-1"></a></dt>

<dd>

Display how close your postings meet your budget.

</dd>

<dt><samp>--add-budget</samp><a name="index-_002d_002dadd_002dbudget"></a></dt>

<dd>

Show unbudgeted postings.

</dd>

<dt><samp>--unbudgeted</samp><a name="index-_002d_002dunbudgeted"></a></dt>

<dd>

Show only unbudgeted postings.

</dd>

<dt><samp>--forecast-while <var>VEXPR</var></samp><a name="index-_002d_002dforecast_002dwhile-VEXPR"></a></dt>

<dt><samp>--forecast <var>VEXPR</var></samp><a name="index-_002d_002dforecast-VEXPR"></a></dt>

<dd>

Project balances into the future.

</dd>

<dt><samp>--limit <var>EXPR</var></samp><a name="index-_002d_002dlimit-EXPR-2"></a></dt>

<dt><samp>-l <var>EXPR</var></samp><a name="index-_002dl-EXPR"></a></dt>

<dd>

Limit which postings are used in calculations by <var>EXPR</var>.

</dd>

<dt><samp>--amount <var>EXPR</var></samp><a name="index-_002d_002damount-EXPR"></a></dt>

<dt><samp>-t <var>EXPR</var></samp><a name="index-_002dt-EXPR"></a></dt>

<dd>

Change value expression reported in `register` report.

</dd>

<dt><samp>--total <var>VEXPR</var></samp><a name="index-_002d_002dtotal-VEXPR"></a></dt>

<dt><samp>-T <var>VEXPR</var></samp><a name="index-_002dT-VEXPR"></a></dt>

<dd>

Change the value expression used for “totals” column in `register` and `balance` reports.

</dd>

</dl>

* * *

<a name="Error-Checking-and-Calculation-Options"></a>

<div class="header">

Next: [Output Customization](#Output-Customization), Previous: [Report Filtering](#Report-Filtering), Up: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Error-Checking-and-Calculation-Options-1"></a>

#### 8.2.4 Error Checking and Calculation Options

<dl compact="compact">

<dt><samp>--strict</samp><a name="index-_002d_002dstrict-2"></a></dt>

<dd>

Accounts, tags or commodities not previously declared will cause warnings.

</dd>

<dt><samp>--pedantic</samp><a name="index-_002d_002dpedantic-1"></a></dt>

<dd>

Accounts, tags or commodities not previously declared will cause errors.

</dd>

<dt><samp>--check-payees</samp><a name="index-_002d_002dcheck_002dpayees"></a></dt>

<dd>

Enable strict and pedantic checking for payees as well as accounts, commodities and tags. This only works in conjunction with <samp>--strict</samp> or <samp>--pedantic</samp>.

</dd>

<dt><samp>--immediate</samp><a name="index-_002d_002dimmediate"></a></dt>

<dd>

Instruct ledger to evaluate calculations immediately rather than lazily.

</dd>

</dl>

* * *

<a name="Output-Customization"></a>

<div class="header">

Next: [Grouping Options](#Grouping-Options), Previous: [Error Checking and Calculation Options](#Error-Checking-and-Calculation-Options), Up: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Output-Customization-1"></a>

#### 8.2.5 Output Customization

<dl compact="compact">

<dt><samp>--collapse</samp><a name="index-_002d_002dcollapse"></a></dt>

<dt><samp>-n</samp><a name="index-_002dn"></a></dt>

<dd>

Collapse transactions with multiple postings.

</dd>

<dt><samp>--subtotal</samp><a name="index-_002d_002dsubtotal-2"></a></dt>

<dt><samp>-s</samp><a name="index-_002ds"></a></dt>

<dd>

Report register as a single subtotal.

</dd>

<dt><samp>--by-payee</samp><a name="index-_002d_002dby_002dpayee-2"></a></dt>

<dt><samp>-P</samp><a name="index-_002dP"></a></dt>

<dd>

Report subtotals by payee.

</dd>

<dt><samp>--empty</samp><a name="index-_002d_002dempty-1"></a></dt>

<dt><samp>-E</samp><a name="index-_002dE"></a></dt>

<dd>

Include empty accounts in the report.

</dd>

<dt><samp>--weekly</samp><a name="index-_002d_002dweekly"></a></dt>

<dt><samp>-W</samp><a name="index-_002dW"></a></dt>

<dd>

Report posting totals by week.

</dd>

<dt><samp>--quarterly</samp><a name="index-_002d_002dquarterly"></a></dt>

<dd>

Report posting totals by quarter.

</dd>

<dt><samp>--yearly</samp><a name="index-_002d_002dyearly"></a></dt>

<dt><samp>-Y</samp><a name="index-_002dY"></a></dt>

<dd>

Report posting totals by year.

</dd>

<dt><samp>--dow</samp><a name="index-_002d_002ddow"></a></dt>

<dd>

Report posting totals by day of week.

</dd>

<dt><samp>--sort <var>VEXPR</var></samp><a name="index-_002d_002dsort-VEXPR"></a></dt>

<dt><samp>-S <var>VEXPR</var></samp><a name="index-_002dS-VEXPR"></a></dt>

<dd>

Sort a report using <var>VEXPR</var>.

</dd>

<dt><samp>--wide</samp><a name="index-_002d_002dwide"></a></dt>

<dt><samp>-w</samp><a name="index-_002dw"></a></dt>

<dd>

Assume 132 columns instead of 80.

</dd>

<dt><samp>--head <var>INT</var></samp><a name="index-_002d_002dhead-INT"></a></dt>

<dd>

Report the first <var>INT</var> postings.

</dd>

<dt><samp>--tail <var>INT</var></samp><a name="index-_002d_002dtail-INT"></a></dt>

<dd>

Report the last <var>INT</var> postings.

</dd>

<dt><samp>--pager <var>FILE</var></samp><a name="index-_002d_002dpager-FILE"></a></dt>

<dd>

Direct output to <var>FILE</var> pager program.

</dd>

<dt><samp>--no-pager</samp><a name="index-_002d_002dno_002dpager"></a></dt>

<dd>

Direct output to stdout, avoiding pager program.

</dd>

<dt><samp>--average</samp><a name="index-_002d_002daverage-1"></a></dt>

<dt><samp>-A</samp><a name="index-_002dA"></a></dt>

<dd>

Report the average posting value.

</dd>

<dt><samp>--deviation</samp><a name="index-_002d_002ddeviation"></a></dt>

<dt><samp>-D</samp><a name="index-_002dD"></a></dt>

<dd>

Report each posting’s deviation from the average.

</dd>

<dt><samp>--percent</samp><a name="index-_002d_002dpercent"></a></dt>

<dt><samp>-%</samp><a name="index-_002d_0025"></a></dt>

<dd>

Show subtotals in the balance report as percentages.

</dd>

<dt><samp>--pivot <var>TAG</var></samp><a name="index-_002d_002dpivot-TAG"></a></dt>

<dd>

Produce a pivot table of the <var>TAG</var> type specified.

</dd>

<dt><samp>--amount-data</samp><a name="index-_002d_002damount_002ddata-2"></a></dt>

<dt><samp>-j</samp><a name="index-_002dj"></a></dt>

<dd>

Show only the date and value columns to format the output for plots.

</dd>

<dt><samp>--plot-amount-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dplot_002damount_002dformat-FORMAT_005fSTRING"></a></dt>

<dd>

Specify the format for the plot output.

</dd>

<dt><samp>--total-data</samp><a name="index-_002d_002dtotal_002ddata-2"></a></dt>

<dt><samp>-J</samp><a name="index-_002dJ"></a></dt>

<dd>

Show only the date and total columns to format the output for plots.

</dd>

<dt><samp>--plot-total-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dplot_002dtotal_002dformat-FORMAT_005fSTRING"></a></dt>

<dd>

Specify the format for the plot output.

</dd>

<dt><samp>--display <var>EXPR</var></samp><a name="index-_002d_002ddisplay-EXPR-2"></a></dt>

<dt><samp>-d <var>EXPR</var></samp><a name="index-_002dd-EXPR"></a></dt>

<dd>

Display only postings that meet the criteria in the <var>EXPR</var>.

</dd>

<dt><samp>--date-format <var>DATE_FORMAT</var></samp><a name="index-_002d_002ddate_002dformat-DATE_005fFORMAT"></a></dt>

<dt><samp>-y <var>DATE_FORMAT</var></samp><a name="index-_002dy-DATE_005fFORMAT"></a></dt>

<dd>

Change the basic date format used in reports.

</dd>

<dt><samp>--format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dformat-FORMAT_005fSTRING"></a></dt>

<dt><samp>--balance-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dbalance_002dformat-FORMAT_005fSTRING"></a></dt>

<dt><samp>--register-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dregister_002dformat-FORMAT_005fSTRING"></a></dt>

<dt><samp>--prices-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dprices_002dformat-FORMAT_005fSTRING"></a></dt>

<dt><samp>-F <var>FORMAT_STRING</var></samp><a name="index-_002dF-FORMAT_005fSTRING"></a></dt>

<dd>

Set the reporting format for various reports.

</dd>

<dt><samp>--anon</samp><a name="index-_002d_002danon"></a></dt>

<dd>

Print the ledger register with anonymized accounts and payees, useful for filing bug reports.

</dd>

</dl>

* * *

<a name="Grouping-Options"></a>

<div class="header">

Next: [Commodity Reporting](#Commodity-Reporting), Previous: [Output Customization](#Output-Customization), Up: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Grouping-Options-1"></a>

#### 8.2.6 Grouping Options

<dl compact="compact">

<dt><samp>--by-payee</samp><a name="index-_002d_002dby_002dpayee-3"></a></dt>

<dt><samp>-P</samp><a name="index-_002dP-1"></a></dt>

<dd>

Group postings by common payee names.

</dd>

<dt><samp>--daily</samp><a name="index-_002d_002ddaily"></a></dt>

<dt><samp>-D</samp><a name="index-_002dD-1"></a></dt>

<dd>

Group postings by day.

</dd>

<dt><samp>--weekly</samp><a name="index-_002d_002dweekly-1"></a></dt>

<dt><samp>-W</samp><a name="index-_002dW-1"></a></dt>

<dd>

Group postings by week.

</dd>

<dt><samp>--monthly</samp><a name="index-_002d_002dmonthly-2"></a></dt>

<dt><samp>-M</samp><a name="index-_002dM"></a></dt>

<dd>

Group postings by month.

</dd>

<dt><samp>--quarterly</samp><a name="index-_002d_002dquarterly-1"></a></dt>

<dd>

Group postings by quarter.

</dd>

<dt><samp>--yearly</samp><a name="index-_002d_002dyearly-1"></a></dt>

<dt><samp>-Y</samp><a name="index-_002dY-1"></a></dt>

<dd>

Group postings by year.

</dd>

<dt><samp>--dow</samp><a name="index-_002d_002ddow-1"></a></dt>

<dd>

Group by day of weeks.

</dd>

<dt><samp>--subtotal</samp><a name="index-_002d_002dsubtotal-3"></a></dt>

<dt><samp>-s</samp><a name="index-_002ds-1"></a></dt>

<dd>

Group postings together, similar to the balance report.

</dd>

</dl>

* * *

<a name="Commodity-Reporting"></a>

<div class="header">

Previous: [Grouping Options](#Grouping-Options), Up: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Commodity-Reporting-1"></a>

#### 8.2.7 Commodity Reporting

<dl compact="compact">

<dt><samp>--price-db <var>FILE</var></samp><a name="index-_002d_002dprice_002ddb-FILE-1"></a></dt>

<dd>

Use <samp>FILE</samp> for retrieving stored commodity prices.

</dd>

<dt><samp>--price-exp <var>INT</var></samp><a name="index-_002d_002dprice_002dexp-INT"></a></dt>

<dt><samp>--leeway <var>INT</var></samp><a name="index-_002d_002dleeway-INT"></a></dt>

<dt><samp>-Z <var>INT</var></samp><a name="index-_002dZ-INT"></a></dt>

<dd>

Set expected freshness of prices in <var>INT</var> minutes.

</dd>

<dt><samp>--download</samp><a name="index-_002d_002ddownload-1"></a></dt>

<dt><samp>-Q</samp><a name="index-_002dQ"></a></dt>

<dd>

Download quotes using the script named <samp>getquote</samp>.

</dd>

<dt><samp>--quantity</samp><a name="index-_002d_002dquantity"></a></dt>

<dt><samp>-O</samp><a name="index-_002dO"></a></dt>

<dd>

Report commodity totals without conversion.

</dd>

<dt><samp>--basis</samp><a name="index-_002d_002dbasis"></a></dt>

<dt><samp>-B</samp><a name="index-_002dB"></a></dt>

<dd>

Report cost basis.

</dd>

<dt><samp>--market</samp><a name="index-_002d_002dmarket-3"></a></dt>

<dt><samp>-V</samp><a name="index-_002dV"></a></dt>

<dd>

Report last known market value.

</dd>

<dt><samp>--gain</samp><a name="index-_002d_002dgain"></a></dt>

<dt><samp>-G</samp><a name="index-_002dG"></a></dt>

<dd>

Report net gain or loss for commodities that have a price history.

</dd>

</dl>

* * *

<a name="Detailed-Option-Description"></a>

<div class="header">

Next: [Period Expressions](#Period-Expressions), Previous: [Command-Line Quick Reference](#Command_002dLine-Quick-Reference), Up: [Command-Line Syntax](#Command_002dLine-Syntax)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Detailed-Option-Description-1"></a>

### 8.3 Detailed Option Description

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Global Options](#Global-Options):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Session Options](#Session-Options):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Report Options](#Report-Options):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Basic options](#Basic-options):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Report filtering](#Report-filtering):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Output customization](#Output-customization):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Commodity reporting](#Commodity-reporting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Environment variables](#Environment-variables):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Global-Options"></a>

<div class="header">

Next: [Session Options](#Session-Options), Previous: [Detailed Option Description](#Detailed-Option-Description), Up: [Detailed Option Description](#Detailed-Option-Description)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Global-Options-1"></a>

#### 8.3.1 Global Options

Options for Ledger reports affect three separate scopes of operation: Global, Session, and Report. In practice there is very little difference between these scopes. Ledger 3.0 contains provisions for GUIs, which would make use of the different scopes by keeping an instance of Ledger running in the background and running multiple sessions with multiple reports per session.

<dl compact="compact">

<dt><samp>--args-only</samp><a name="index-_002d_002dargs_002donly"></a></dt>

<dd>

Ignore all environment and init-file settings and use only command-line arguments to control Ledger. Useful for debugging or testing small journal files not associated with your main financial database.

</dd>

<dt><samp>--debug <var>CODE</var></samp><a name="index-_002d_002ddebug-CODE"></a></dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature. If ledger has been built with debug options this will provide extra data during the run.

</dd>

<dt><samp>--help</samp><a name="index-_002d_002dhelp-1"></a></dt>

<dt><samp>-h</samp><a name="index-_002dh-1"></a></dt>

<dd>

Display the man page for <samp>ledger</samp>.

</dd>

<dt><samp>--init-file <var>FILE</var></samp><a name="index-_002d_002dinit_002dfile-FILE-1"></a></dt>

<dd>

Specify the location of the init file. The default is home directory <samp>~/.ledgerrc</samp>, or current directory <samp>./.ledgerrc</samp> if not found in home directory.

</dd>

<dt><samp>--options</samp><a name="index-_002d_002doptions"></a></dt>

<dd>

Display the options in effect for this Ledger invocation, along with their values and the source of those values, for example:

<div class="smallexample">

<pre class="smallexample">$ ledger --options bal --cleared
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">===============================================================================
[Global scope options]
             --args-only                                             --args-only

[Session scope options]
                  --file = A9349E4.dat                               --file

[Report scope options]
               --cleared                                             --cleared
               --columns = 80                                        --columns
                 --limit = cleared                                   --cleared
===============================================================================
              $15.00  Expenses
              $12.45    Food
               $2.55    Tips
             $-15.00  Liabilities:MasterCard
--------------------
                   0
</pre>

</div>

For the source column, a value starting with a ‘<samp>-</samp>’ or ‘<samp>--</samp>’ indicated the source was a command-line argument. If the entry starts with a ‘<samp>$</samp>’, the source was an environment variable. If the source is `?normalize` the value was set internally by ledger, in a function called `normalize_options`.

</dd>

<dt><samp>--script <var>FILE</var></samp><a name="index-_002d_002dscript-FILE"></a></dt>

<dd>

Execute a ledger script.

</dd>

<dt><samp>--trace <var>INT</var></samp><a name="index-_002d_002dtrace-INT"></a></dt>

<dd>

Enable tracing. The <var>INT</var> specifies the level of trace desired.

</dd>

<dt><samp>--verbose</samp><a name="index-_002d_002dverbose"></a></dt>

<dt><samp>-v</samp><a name="index-_002dv"></a></dt>

<dd>

Print detailed information on the execution of Ledger.

</dd>

<dt><samp>--verify</samp><a name="index-_002d_002dverify"></a></dt>

<dd>

Enable additional assertions during run-time. This causes a significant slowdown. When combined with <samp>--debug <var>CODE</var></samp> ledger will produce memory trace information.

</dd>

<dt><samp>--verify-memory</samp><a name="index-_002d_002dverify_002dmemory"></a></dt>

<dd>

Verify that every constructed object is properly destructed. This is for debugging purposes only.

</dd>

<dt><samp>--version</samp><a name="index-_002d_002dversion-1"></a></dt>

<dd>

Print version information and exit.

</dd>

</dl>

* * *

<a name="Session-Options"></a>

<div class="header">

Next: [Report Options](#Report-Options), Previous: [Global Options](#Global-Options), Up: [Detailed Option Description](#Detailed-Option-Description)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Session-Options-1"></a>

#### 8.3.2 Session Options

Options for Ledger reports affect three separate scopes of operation: Global, Session, and Report. In practice there is very little difference between these scopes. Ledger 3.0 contains provisions for GUIs, which would make use of the different scopes by keeping an instance of Ledger running in the background and running multiple sessions with multiple reports per session.

<dl compact="compact">

<dt><samp>--check-payees</samp><a name="index-_002d_002dcheck_002dpayees-1"></a></dt>

<dd>

Enable strict and pedantic checking for payees as well as accounts, commodities and tags. This only works in conjunction with <samp>--strict</samp> or <samp>--pedantic</samp>.

</dd>

<dt><samp>--day-break</samp><a name="index-_002d_002dday_002dbreak"></a></dt>

<dd>

Break up `register` report of [timelog](#timelog) entries that span multiple days by day.

</dd>

<dt><samp>--decimal-comma</samp><a name="index-_002d_002ddecimal_002dcomma"></a></dt>

<dd>

Direct Ledger to parse journals using the European standard comma as a decimal separator, not the usual period.

</dd>

<dt><samp>--download</samp><a name="index-_002d_002ddownload-2"></a></dt>

<dt><samp>-Q</samp><a name="index-_002dQ-1"></a></dt>

<dd>

Direct Ledger to download prices.

</dd>

<dt><samp>--explicit</samp><a name="index-_002d_002dexplicit"></a></dt>

<dd>

Direct Ledger to require pre-declarations for entities (such as accounts, commodities and tags) rather than taking entities from cleared transactions as defined. This option is useful in combination with <samp>--strict</samp> or <samp>--pedantic</samp>.

</dd>

<dt><samp>--file <var>FILE</var></samp><a name="index-_002d_002dfile-FILE-1"></a></dt>

<dt><samp>-f <var>FILE</var></samp><a name="index-_002df-FILE-1"></a></dt>

<dd>

Specify the input <samp>FILE</samp> for this invocation.

</dd>

<dt><samp>--input-date-format <var>DATE_FORMAT</var></samp><a name="index-_002d_002dinput_002ddate_002dformat-DATE_005fFORMAT-1"></a></dt>

<dd>

Specify the input date format for journal entries. For example,

<div class="smallexample">

<pre class="smallexample">$ ledger convert Export.csv --input-date-format "%m/%d/%Y"
</pre>

</div>

Would convert the <samp>Export.csv</samp> file to ledger format, assuming the dates in the CSV file are like 12/23/2009 (see [Date and Time Format Codes](#Date-and-Time-Format-Codes)).

</dd>

<dt><samp>--master-account <var>STR</var></samp><a name="index-_002d_002dmaster_002daccount-STR"></a></dt>

<dd>

Prepend all account names with the argument.

<div class="smallexample">

<pre class="smallexample">$ ledger -f drewr3.dat bal --no-total --master-account HUMBUG
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">                   0  HUMBUG
         $ -3,804.00    Assets
          $ 1,396.00      Checking
             $ 30.00        Business
         $ -5,200.00      Savings
         $ -1,000.00    Equity:Opening Balances
          $ 6,654.00    Expenses
          $ 5,500.00      Auto
             $ 20.00      Books
            $ 300.00      Escrow
            $ 334.00      Food:Groceries
            $ 500.00      Interest:Mortgage
         $ -2,030.00    Income
         $ -2,000.00      Salary
            $ -30.00      Sales
            $ 180.00    Liabilities
            $ -20.00      MasterCard
            $ 200.00      Mortgage:Principal
</pre>

</div>

</dd>

<dt><samp>--no-aliases</samp><a name="index-_002d_002dno_002daliases"></a></dt>

<dd>

Ledger does not expand any aliases if this option is specified.

</dd>

<dt><samp>--pedantic</samp><a name="index-_002d_002dpedantic-2"></a></dt>

<dd>

Accounts, tags or commodities not previously declared will cause errors.

</dd>

<dt><samp>--permissive</samp><a name="index-_002d_002dpermissive-1"></a></dt>

<dd>

Quiet balance assertions.

</dd>

<dt><samp>--price-db <var>FILE</var></samp><a name="index-_002d_002dprice_002ddb-FILE-2"></a></dt>

<dd>

Specify the location of the price entry data file.

</dd>

<dt><samp>--price-exp <var>INT</var></samp><a name="index-_002d_002dprice_002dexp-INT-1"></a></dt>

<dt><samp>--leeway <var>INT</var></samp><a name="index-_002d_002dleeway-INT-1"></a></dt>

<dt><samp>-Z <var>INT</var></samp><a name="index-_002dZ-INT-1"></a></dt>

<dd>

Set the expected freshness of price quotes, in <var>INT</var> minutes. That is, if the last known quote for any commodity is older than this value, and if <samp>--download</samp> is being used, then the Internet will be consulted again for a newer price. Otherwise, the old price is still considered to be fresh enough.

</dd>

<dt><samp>--strict</samp><a name="index-_002d_002dstrict-3"></a></dt>

<dd>

Ledger normally silently accepts any account or commodity in a posting, even if you have misspelled a commonly used one. The option <samp>--strict</samp> changes that behavior. While running with <samp>--strict</samp>, Ledger interprets all cleared transactions as correct, and if it encounters a new account or commodity (same as a misspelled commodity or account) it will issue a warning giving you the file and line number of the problem.

</dd>

<dt><samp>--recursive-aliases</samp><a name="index-_002d_002drecursive_002daliases"></a></dt>

<dd>

Normally, ledger only expands aliases once. With this option, ledger tries to expand the result of alias expansion recursively, until no more expansions apply.

</dd>

<dt><samp>--time-colon</samp><a name="index-_002d_002dtime_002dcolon"></a></dt>

<dd>

The <samp>--time-colon</samp> option will display the value for a seconds based commodity as real hours and minutes.

For example 8100 seconds by default will be displayed as 2.25 whereas with the <samp>--time-colon</samp> option they will be displayed as 2:15.

</dd>

<dt><samp>--value-expr <var>VEXPR</var></samp><a name="index-_002d_002dvalue_002dexpr-VEXPR"></a></dt>

<dd>

Set a global value expression annotation.

</dd>

</dl>

* * *

<a name="Report-Options"></a>

<div class="header">

Next: [Basic options](#Basic-options), Previous: [Session Options](#Session-Options), Up: [Detailed Option Description](#Detailed-Option-Description)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Report-Options-1"></a>

#### 8.3.3 Report Options

Options for Ledger reports affect three separate scopes of operation: Global, Session, and Report. In practice there is very little difference between these scopes. Ledger 3.0 contains provisions for GUIs, which would make use of the different scopes by keeping an instance of Ledger running in the background and running multiple sessions with multiple reports per session.

<dl compact="compact">

<dt><samp>--abbrev-len <var>INT</var></samp><a name="index-_002d_002dabbrev_002dlen-INT"></a></dt>

<dd>

Set the minimum length an account can be abbreviated to if it doesn’t fit inside the `account-width`. If <var>INT</var> is zero, then the account name will be truncated on the right. If <var>INT</var> is greater than `account-width` then the account will be truncated on the left, with no shortening of the account names in order to fit into the desired width.

</dd>

<dt><samp>--account <var>STR</var></samp><a name="index-_002d_002daccount-STR-2"></a></dt>

<dd>

Prepend <var>STR</var> to all accounts reported. That is, the option ‘<samp>--account Personal</samp>’ would tack ‘<samp>Personal:</samp>’ to the beginning of every account reported in a balance report or register report.

</dd>

<dt><samp>--account-width <var>INT</var></samp><a name="index-_002d_002daccount_002dwidth-INT"></a></dt>

<dd>

Set the width of the account column in the `register` report to <var>INT</var> characters.

</dd>

<dt><samp>--actual</samp><a name="index-_002d_002dactual-1"></a></dt>

<dt><samp>-L</samp><a name="index-_002dL-1"></a></dt>

<dd>

Report only real transactions, ignoring all automated or virtual transactions.

</dd>

<dt><samp>--add-budget</samp><a name="index-_002d_002dadd_002dbudget-1"></a></dt>

<dd>

Show only unbudgeted postings.

</dd>

<dt><samp>--amount <var>EXPR</var></samp><a name="index-_002d_002damount-EXPR-1"></a></dt>

<dt><samp>-t <var>EXPR</var></samp><a name="index-_002dt-EXPR-1"></a></dt>

<dd>

Apply the given value expression to the posting amount (see [Value Expressions](#Value-Expressions)). Using <samp>--amount <var>EXPR</var></samp> you can apply an arbitrary transformation to the postings.

</dd>

<dt><samp>--amount-data</samp><a name="index-_002d_002damount_002ddata-3"></a></dt>

<dt><samp>-j</samp><a name="index-_002dj-1"></a></dt>

<dd>

On a register report print only the date and amount of postings. Useful for graphing and spreadsheet applications.

</dd>

<dt><samp>--amount-width <var>INT</var></samp><a name="index-_002d_002damount_002dwidth-INT"></a></dt>

<dd>

Set the width in characters of the amount column in the `register` report.

</dd>

<dt><samp>--anon</samp><a name="index-_002d_002danon-1"></a></dt>

<dd>

Anonymize registry output, mostly for sending in bug reports.

</dd>

<dt><samp>--auto-match</samp><a name="index-_002d_002dauto_002dmatch-1"></a></dt>

<dd>

When generating a ledger transaction from a CSV file using the `convert` command, automatically match an account from the Ledger journal.

</dd>

<dt><samp>--aux-date</samp><a name="index-_002d_002daux_002ddate-1"></a></dt>

<dt><samp>--effective</samp><a name="index-_002d_002deffective-1"></a></dt>

<dd>

Show auxiliary dates for all calculations (see [Effective Dates](#Effective-Dates)).

</dd>

<dt><samp>--average</samp><a name="index-_002d_002daverage-2"></a></dt>

<dt><samp>-A</samp><a name="index-_002dA-1"></a></dt>

<dd>

Print average values over the number of transactions instead of running totals.

</dd>

<dt><samp>--balance-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dbalance_002dformat-FORMAT_005fSTRING-1"></a></dt>

<dd>

Specify the format to use for the `balance` report (see [Format Strings](#Format-Strings)). The default is:

<div class="smallexample">

<pre class="smallexample">"%(justify(scrub(display_total), 20, -1, true, color))"
"  %(!options.flat ? depth_spacer : \"\")"
"%-(ansify_if(partial_account(options.flat), blue if color))\n%/"
"%$1\n%/"
"--------------------\n"
</pre>

</div>

</dd>

<dt><samp>--base</samp><a name="index-_002d_002dbase"></a></dt>

<dd>

Reduce convertible commodities down the bottom of the conversion, e.g. display time in seconds. This also applies to custom commodity conversions (see [Commodity equivalences](#Commodity-equivalences)).

</dd>

<dt><samp>--basis</samp><a name="index-_002d_002dbasis-1"></a></dt>

<dt><samp>-B</samp><a name="index-_002dB-1"></a></dt>

<dt><samp>--cost</samp><a name="index-_002d_002dcost"></a></dt>

<dd>

Report the cost basis on all posting.

</dd>

<dt><samp>--begin <var>DATE</var></samp><a name="index-_002d_002dbegin-DATE-1"></a></dt>

<dd>

Specify the start <var>DATE</var> of all calculations. Transactions before that date will be ignored.

</dd>

<dt><samp>--bold-if <var>VEXPR</var></samp><a name="index-_002d_002dbold_002dif-VEXPR"></a></dt>

<dd>

Print the entire line in bold if the given value expression is true (see [Value Expressions](#Value-Expressions)).

<div class="smallexample">

<pre class="smallexample">$ ledger reg Expenses --begin Dec --bold-if "amount>100"
</pre>

</div>

list all transactions since the beginning of December and print in bold any posting greater than $100.

</dd>

<dt><samp>--budget</samp><a name="index-_002d_002dbudget-2"></a></dt>

<dd>

Only display budgeted items. In a register report this displays transactions in the budget, in a balance report this displays accounts in the budget (see [Budgeting and Forecasting](#Budgeting-and-Forecasting)).

</dd>

<dt><samp>--budget-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dbudget_002dformat-FORMAT_005fSTRING"></a></dt>

<dd>

Specify the format to use for the `budget` report (see [Format Strings](#Format-Strings)). The default is:

<div class="smallexample">

<pre class="smallexample">"%(justify(scrub(get_at(display_total, 0)), 12, -1, true, color))"
" %(justify(-scrub(get_at(display_total, 1)), 12, "
"           12 + 1 + 12, true, color))"
" %(justify(scrub(get_at(display_total, 1) + "
"                 get_at(display_total, 0)), 12, "
"           12 + 1 + 12 + 1 + 12, true, color))"
" %(ansify_if("
"   justify((get_at(display_total, 1) ? "
"            (100% * quantity(scrub(get_at(display_total, 0)))) / "
"             -quantity(scrub(get_at(display_total, 1))) : 0), "
"           5, -1, true, false),"
"   magenta if (color and get_at(display_total, 1) and "
"               (abs(quantity(scrub(get_at(display_total, 0))) / "
"                    quantity(scrub(get_at(display_total, 1)))) >= 1))))"
"  %(!options.flat ? depth_spacer : \"\")"
"%-(ansify_if(partial_account(options.flat), blue if color))\n"
"%/%$1 %$2 %$3 %$4\n%/"
"%(prepend_width ? \" \" * int(prepend_width) : \"\")"
"------------ ------------ ------------ -----\n"
</pre>

</div>

</dd>

<dt><samp>--by-payee</samp><a name="index-_002d_002dby_002dpayee-4"></a></dt>

<dt><samp>-P</samp><a name="index-_002dP-2"></a></dt>

<dd>

Group the register report by payee.

</dd>

<dt><samp>--cleared</samp><a name="index-_002d_002dcleared-2"></a></dt>

<dt><samp>-C</samp><a name="index-_002dC-1"></a></dt>

<dd>

Consider only transactions that have been cleared for display and calculation.

</dd>

<dt><samp>--cleared-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dcleared_002dformat-FORMAT_005fSTRING"></a></dt>

<dd>

Specify the format to use for the `cleared` report (see [Format Strings](#Format-Strings)). The default is:

<div class="smallexample">

<pre class="smallexample">"%(justify(scrub(get_at(total_expr, 0)), 16, 16 + prepend_width, "
" true, color))  %(justify(scrub(get_at(total_expr, 1)), 18, "
" 36 + prepend_width, true, color))"
"    %(latest_cleared ? format_date(latest_cleared) : \"         \")"
"    %(!options.flat ? depth_spacer : \"\")"
"%-(ansify_if(partial_account(options.flat), blue if color))\n%/"
"%$1  %$2    %$3\n%/"
"%(prepend_width ? \" \" * prepend_width : \"\")"
"----------------    ----------------    ---------\n"
</pre>

</div>

</dd>

<dt><samp>--collapse</samp><a name="index-_002d_002dcollapse-1"></a></dt>

<dt><samp>-n</samp><a name="index-_002dn-1"></a></dt>

<dd>

By default ledger prints all accounts in an account tree. With <samp>--collapse</samp> it prints only the top level account specified.

</dd>

<dt><samp>--collapse-if-zero</samp><a name="index-_002d_002dcollapse_002dif_002dzero"></a></dt>

<dd>

Collapse the account display only if it has a zero balance.

</dd>

<dt><samp>--color</samp><a name="index-_002d_002dcolor"></a></dt>

<dt><samp>--ansi</samp><a name="index-_002d_002dansi"></a></dt>

<dd>

Use color if the terminal supports it.

</dd>

<dt><samp>--columns <var>INT</var></samp><a name="index-_002d_002dcolumns-INT"></a></dt>

<dd>

Specify the width of the `register` report in characters.

</dd>

<dt><samp>--count</samp><a name="index-_002d_002dcount-1"></a></dt>

<dd>

Direct ledger to report the number of items when appended to the `commodities`, `accounts` or `payees` command.

</dd>

<dt><samp>--csv-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dcsv_002dformat-FORMAT_005fSTRING"></a></dt>

<dd>

Specify the format to use for the `csv` report (see [Format Strings](#Format-Strings)). The default is:

<div class="smallexample">

<pre class="smallexample">"%(quoted(date)),"
"%(quoted(code)),"
"%(quoted(payee)),"
"%(quoted(display_account)),"
"%(quoted(commodity(scrub(display_amount)))),"
"%(quoted(quantity(scrub(display_amount)))),"
"%(quoted(cleared ? \"*\" : (pending ? \"!\" : \"\"))),"
"%(quoted(join(note | xact.note)))\n"
</pre>

</div>

</dd>

<dt><samp>--current</samp><a name="index-_002d_002dcurrent-1"></a></dt>

<dd>

Shorthand for ‘<samp>--limit "date <= today"</samp>’.

</dd>

<dt><samp>--daily</samp><a name="index-_002d_002ddaily-1"></a></dt>

<dt><samp>-D</samp><a name="index-_002dD-2"></a></dt>

<dd>

Shorthand for ‘<samp>--period "daily"</samp>’.

</dd>

<dt><samp>--date <var>EXPR</var></samp><a name="index-_002d_002ddate-EXPR"></a></dt>

<dd>

Transform the date of the transaction using <var>EXPR</var>.

</dd>

<dt><samp>--date-format <var>DATE_FORMAT</var></samp><a name="index-_002d_002ddate_002dformat-DATE_005fFORMAT-1"></a></dt>

<dt><samp>-y <var>DATE_FORMAT</var></samp><a name="index-_002dy-DATE_005fFORMAT-1"></a></dt>

<dd>

Specify the format ledger should use to read and print dates (see [Date and Time Format Codes](#Date-and-Time-Format-Codes)).

</dd>

<dt><samp>--date-width <var>INT</var></samp><a name="index-_002d_002ddate_002dwidth-INT"></a></dt>

<dd>

Specify the width, in characters, of the date column in the `register` report.

</dd>

<dt><samp>--datetime-format <var>DATETIME_FORMAT</var></samp><a name="index-_002d_002ddatetime_002dformat-DATETIME_005fFORMAT"></a></dt>

<dd>

Specify the format ledger should use to print datetimes.

</dd>

<dt><samp>--dc</samp><a name="index-_002d_002ddc-1"></a></dt>

<dd>

Display register or balance in debit/credit format If you use <samp>--dc</samp> with either the `register` (reg) or `balance` (bal) commands, you will now get extra columns. The register goes from this:

<div class="smallexample">

<pre class="smallexample">12-Mar-10 Employer           Assets:Cash                $100        $100
                             Income:Employer           $-100           0
12-Mar-10 KFC                Expenses:Food               $20         $20
                             Assets:Cash                $-20           0
12-Mar-10 KFC - Rebate       Assets:Cash                  $5          $5
                             Expenses:Food               $-5           0
12-Mar-10 KFC - Food & Reb.. Expenses:Food               $20         $20
                             Expenses:Food               $-5         $15
                             Assets:Cash                $-15           0
</pre>

</div>

To this:

<div class="smallexample">

<pre class="smallexample">12-Mar-10 Employer       Assets:Cash        $100           0        $100
                         In:Employer           0        $100           0
12-Mar-10 KFC            Expens:Food         $20           0         $20
                         Assets:Cash           0         $20           0
12-Mar-10 KFC - Rebate   Assets:Cash          $5           0          $5
                         Expens:Food           0          $5           0
12-Mar-10 KFC - Food &.. Expens:Food         $20           0         $20
                         Expens:Food           0          $5         $15
                         Assets:Cash           0         $15           0
</pre>

</div>

Where the first column is debits, the second is credits, and the third is the running total. Only the running total may contain negative values.

For the balance report without <samp>--dc</samp>:

<div class="smallexample">

<pre class="smallexample">                 $70  Assets:Cash
                 $30  Expenses:Food
               $-100  Income:Employer
--------------------
                   0
</pre>

</div>

And with <samp>--dc</samp> it becomes this:

<div class="smallexample">

<pre class="smallexample">          $105            $35            $70  Assets:Cash
           $40            $10            $30  Expenses:Food
             0           $100          $-100  Income:Employer
--------------------------------------------
          $145           $145              0
</pre>

</div>

</dd>

<dt><samp>--depth <var>INT</var></samp><a name="index-_002d_002ddepth-INT"></a></dt>

<dd>

Limit the depth of the account tree. In a balance report, for example, a ‘<samp>--depth 2</samp>’ statement will print balances only for accounts with two levels, i.e. ‘<samp>Expenses:Entertainment</samp>’ but not ‘<samp>Expenses:Entertainment:Dining</samp>’. This is a display predicate, which means it only affects display, not the total calculations.

</dd>

<dt><samp>--deviation</samp><a name="index-_002d_002ddeviation-1"></a></dt>

<dd>

Report each posting’s deviation from the average. It is only meaningful in the register and prices reports.

</dd>

<dt><samp>--display <var>EXPR</var></samp><a name="index-_002d_002ddisplay-EXPR-3"></a></dt>

<dd>

Display only lines that satisfy the expression <var>EXPR</var>.

</dd>

<dt><samp>--display-amount <var>EXPR</var></samp><a name="index-_002d_002ddisplay_002damount-EXPR"></a></dt>

<dd>

Apply a transformation to the _displayed_ amount. This happens after calculations occur.

</dd>

<dt><samp>--display-total <var>EXPR</var></samp><a name="index-_002d_002ddisplay_002dtotal-EXPR"></a></dt>

<dd>

Apply a transformation to the _displayed_ total. This happens after calculations occur.

</dd>

<dt><samp>--dow</samp><a name="index-_002d_002ddow-2"></a></dt>

<dt><samp>--days-of-week</samp><a name="index-_002d_002ddays_002dof_002dweek"></a></dt>

<dd>

Group transactions by the day of the week.

<div class="smallexample">

<pre class="smallexample">$ ledger reg Expenses --dow --collapse
</pre>

</div>

Will print all Expenses totaled for each day of the week.

</dd>

<dt><samp>--empty</samp><a name="index-_002d_002dempty-2"></a></dt>

<dt><samp>-E</samp><a name="index-_002dE-1"></a></dt>

<dd>

Include empty accounts in the report and in average calculations.

</dd>

<dt><samp>--end <var>DATE</var></samp><a name="index-_002d_002dend-DATE-1"></a></dt>

<dd>

Specify the end <var>DATE</var> for a transaction to be considered in the report. All transactions on or after this date are ignored.

</dd>

<dt><samp>--equity</samp><a name="index-_002d_002dequity"></a></dt>

<dd>

Related to the `equity` command (see [The `equity` command](#The-equity-command)). Gives current account balances in the form of a register report.

</dd>

<dt><samp>--exact</samp><a name="index-_002d_002dexact"></a></dt>

<dd>

Report beginning and ending of periods by the date of the first and last posting occurring in that period.

</dd>

<dt><samp>--exchange <var>COMMODITY</var></samp><a name="index-_002d_002dexchange-COMMODITY-2"></a></dt>

<dt><samp>-X <var>COMMODITY</var></samp><a name="index-_002dX-COMMODITY"></a></dt>

<dd>

Display values in terms of the given <var>COMMODITY</var>. The latest available price is used. The syntax <samp>-X <var>COMMODITY1</var>:<var>COMMODITY2</var></samp> displays values in <var>COMMODITY1</var> in terms of <var>COMMODITY2</var> using the latest available price, but will not automatically covert any other commodities to <var>COMMODITY2</var>. Multiple <samp>-X</samp> arguments may be used on a single command-line (as in <samp>-X COMMODITY1:COMMODITY2 -X COMMODITY3:COMMODITY2</samp>), which is particularly useful for situations where many prices are available for reporting in terms of <var>COMMODITY2</var>, but only a few should be displayed that way.

</dd>

<dt><samp>--flat</samp><a name="index-_002d_002dflat"></a></dt>

<dd>

Force the full names of accounts to be used in the balance report. The balance report will not use an indented tree.

</dd>

<dt><samp>--force-color</samp><a name="index-_002d_002dforce_002dcolor"></a></dt>

<dd>

Output TTY color codes even if the TTY doesn’t support them. Useful for TTYs that don’t advertise their capabilities correctly.

</dd>

<dt><samp>--force-pager</samp><a name="index-_002d_002dforce_002dpager"></a></dt>

<dd>

Force Ledger to paginate its output.

</dd>

<dt><samp>--forecast-while <var>VEXPR</var></samp><a name="index-_002d_002dforecast_002dwhile-VEXPR-1"></a></dt>

<dt><samp>--forecast <var>VEXPR</var></samp><a name="index-_002d_002dforecast-VEXPR-1"></a></dt>

<dd>

Continue forecasting while <var>VEXPR</var> is true.

</dd>

<dt><samp>--forecast-years <var>INT</var></samp><a name="index-_002d_002dforecast_002dyears-INT"></a></dt>

<dd>

Forecast at most <var>INT</var> years into the future.

</dd>

<dt><samp>--format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dformat-FORMAT_005fSTRING-1"></a></dt>

<dt><samp>-F <var>FORMAT_STRING</var></samp><a name="index-_002dF-FORMAT_005fSTRING-1"></a></dt>

<dd>

Use the given format string to print output.

</dd>

<dt><samp>--gain</samp><a name="index-_002d_002dgain-1"></a></dt>

<dt><samp>-G</samp><a name="index-_002dG-1"></a></dt>

<dt><samp>--change</samp><a name="index-_002d_002dchange"></a></dt>

<dd>

Report on gains using the latest available prices.

</dd>

<dt><samp>--generated</samp><a name="index-_002d_002dgenerated"></a></dt>

<dd>

Include auto-generated postings (such as those from automated transactions) in the report, in cases where you normally wouldn’t want them.

</dd>

<dt><samp>--group-by <var>EXPR</var></samp><a name="index-_002d_002dgroup_002dby-EXPR"></a></dt>

<dd>

Group transactions together in the `register` report. <var>EXPR</var> can be anything, although most common would be `payee` or `commodity`. The `tags()` function is also useful here.

</dd>

<dt><samp>--group-title-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dgroup_002dtitle_002dformat-FORMAT_005fSTRING"></a></dt>

<dd>

Set the format for the headers that separates the report sections of a grouped report. Only has an effect with a <samp>--group-by <var>EXPR</var></samp> register report.

<div class="smallexample">

<pre class="smallexample">$ ledger reg Expenses --group-by "payee" --group-title-format "------------------------ %-20(value) ---------------------\n"
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">------------------------ 7-Eleven             ---------------------
2011/08/13 7-Eleven              Expenses:Auto:Misc          $ 5.80       $ 5.80

------------------------ AAA Dues             ---------------------
2011/06/02 AAA Dues              Expenses:Auto:Misc        $ 215.00     $ 215.00

------------------------ ABC Towing and Wrecking ---------------------
2011/03/17 ABC Towing and Wrec..  Expenses:Auto:Hobbies      $ 48.20      $ 48.20
...
</pre>

</div>

</dd>

<dt><samp>--head <var>INT</var></samp><a name="index-_002d_002dhead-INT-1"></a></dt>

<dt><samp>--first <var>INT</var></samp><a name="index-_002d_002dfirst-INT"></a></dt>

<dd>

Print the first <var>INT</var> entries. Opposite of <samp>--tail <var>INT</var></samp>.

</dd>

<dt><samp>--historical</samp><a name="index-_002d_002dhistorical"></a></dt>

<dt><samp>-H</samp><a name="index-_002dH"></a></dt>

<dd>

Value commodities at the time of their acquisition.

</dd>

<dt><samp>--immediate</samp><a name="index-_002d_002dimmediate-1"></a></dt>

<dd>

Evaluate calculations immediately rather than lazily.

</dd>

<dt><samp>--inject</samp><a name="index-_002d_002dinject"></a></dt>

<dd>

Use `Expected` amounts in calculations. In case you know what amount a transaction should be, but the actual transaction has the wrong value you can use metadata to specify the expected amount:

<div class="smallexample">

<pre class="smallexample">2012-03-12  Paycheck
    Income  $-990;  Expected:: $-1000.00
    Checking
</pre>

</div>

Then using the command `ledger reg --inject=Expected Income` would treat the transaction as if the “Expected Value” was actual.

</dd>

<dt><samp>--invert</samp><a name="index-_002d_002dinvert-1"></a></dt>

<dd>

Change the sign of all reported values.

</dd>

<dt><samp>--limit <var>EXPR</var></samp><a name="index-_002d_002dlimit-EXPR-3"></a></dt>

<dt><samp>-l <var>EXPR</var></samp><a name="index-_002dl-EXPR-1"></a></dt>

<dd>

Only transactions that satisfy <var>EXPR</var> are considered in calculations and for display.

</dd>

<dt><samp>--lot-dates</samp><a name="index-_002d_002dlot_002ddates-1"></a></dt>

<dd>

Report the date on which each commodity in a balance report was purchased.

</dd>

<dt><samp>--lot-notes</samp><a name="index-_002d_002dlot_002dnotes-1"></a></dt>

<dt><samp>--lot-tags</samp><a name="index-_002d_002dlot_002dtags"></a></dt>

<dd>

Report the tag attached to each commodity in a balance report.

</dd>

<dt><samp>--lot-prices</samp><a name="index-_002d_002dlot_002dprices-1"></a></dt>

<dd>

Report the price at which each commodity in a balance report was purchased.

</dd>

<dt><samp>--lots</samp><a name="index-_002d_002dlots-1"></a></dt>

<dd>

Report the date and price at which each commodity was purchased in a balance report.

</dd>

<dt><samp>--lots-actual</samp><a name="index-_002d_002dlots_002dactual"></a></dt>

<dd>

Preserve the uniqueness of commodities so they aren’t merged during reporting without printing the lot annotations.

</dd>

<dt><samp>--market</samp><a name="index-_002d_002dmarket-4"></a></dt>

<dt><samp>-V</samp><a name="index-_002dV-1"></a></dt>

<dd>

Use the latest market value for all commodities.

</dd>

<dt><samp>--meta <var>TAG</var></samp><a name="index-_002d_002dmeta-TAG"></a></dt>

<dd>

In the register report, prepend the transaction with the value of the given <var>TAG</var>.

</dd>

<dt><samp>--meta-width <var>INT</var></samp><a name="index-_002d_002dmeta_002dwidth-INT"></a></dt>

<dd>

Specify the width of the Meta column used for the <samp>--meta <var>TAG</var></samp> options.

</dd>

<dt><samp>--monthly</samp><a name="index-_002d_002dmonthly-3"></a></dt>

<dt><samp>-M</samp><a name="index-_002dM-1"></a></dt>

<dd>

Synonym for ‘<samp>--period "monthly"</samp>’.

</dd>

<dt><samp>--no-aliases</samp><a name="index-_002d_002dno_002daliases-1"></a></dt>

<dd>

Aliases are completely ignored.

</dd>

<dt><samp>--no-color</samp><a name="index-_002d_002dno_002dcolor"></a></dt>

<dd>

Suppress any color TTY output.

</dd>

<dt><samp>--no-pager</samp><a name="index-_002d_002dno_002dpager-1"></a></dt>

<dd>

Direct output to stdout, avoiding pager program.

</dd>

<dt><samp>--no-revalued</samp><a name="index-_002d_002dno_002drevalued"></a></dt>

<dd>

Stop Ledger from showing `<Revalued>` postings. This option is useful in combination with the <samp>--exchange</samp> or <samp>--market</samp> option.

</dd>

<dt><samp>--no-rounding</samp><a name="index-_002d_002dno_002drounding"></a></dt>

<dd>

Don’t output ‘<samp><Adjustment></samp>’ postings. Note that this will cause the running total to often not add up! Its main use is for <samp>--amount-data (-j)</samp> and <samp>--total-data (-J)</samp> reports.

</dd>

<dt><samp>--no-titles</samp><a name="index-_002d_002dno_002dtitles"></a></dt>

<dd>

Suppress the output of group titles.

</dd>

<dt><samp>--no-total</samp><a name="index-_002d_002dno_002dtotal"></a></dt>

<dd>

Suppress printing the final total line in a balance report.

</dd>

<dt><samp>--now <var>DATE</var></samp><a name="index-_002d_002dnow-DATE"></a></dt>

<dd>

Define the current date in case you want to calculate in the past or future using <samp>--current</samp>.

</dd>

<dt><samp>--only <var>FIXME</var></samp><a name="index-_002d_002donly-FIXME"></a></dt>

<dd>

This is a postings predicate that applies after certain transforms have been executed, such as periodic gathering.

</dd>

<dt><samp>--output <var>FILE</var></samp><a name="index-_002d_002doutput-FILE-1"></a></dt>

<dd>

Redirect the output of ledger to the file defined in <samp>FILE</samp>.

</dd>

<dt><samp>--pager <var>FILE</var></samp><a name="index-_002d_002dpager-FILE-1"></a></dt>

<dd>

Direct output to <var>FILE</var> pager program.

</dd>

<dt><samp>--payee <var>VEXPR</var></samp><a name="index-_002d_002dpayee-VEXPR"></a></dt>

<dd>

Sets a value expression for formatting the payee. In the `register` report this prevents the second entry from having a date and payee for each transaction.

</dd>

<dt><samp>--payee-width <var>INT</var></samp><a name="index-_002d_002dpayee_002dwidth-INT"></a></dt>

<dd>

Set the number of columns dedicated to the payee in the register report to <var>INT</var>.

</dd>

<dt><samp>--pending</samp><a name="index-_002d_002dpending-1"></a></dt>

<dd>

Use only postings that are marked pending.

</dd>

<dt><samp>--percent</samp><a name="index-_002d_002dpercent-1"></a></dt>

<dt><samp>-%</samp><a name="index-_002d_0025-1"></a></dt>

<dd>

Calculate the percentage value of each account in balance reports. Only works for accounts that have a single commodity.

</dd>

<dt><samp>--period <var>PERIOD_EXPRESSION</var></samp><a name="index-_002d_002dperiod-PERIOD_005fEXPRESSION-1"></a></dt>

<dd>

Define a period expression that sets the time period during which transactions are to be accounted. For a `register` report only the transactions that satisfy the period expression with be displayed. For a `balance` report only those transactions will be accounted in the final balances.

</dd>

<dt><samp>--pivot <var>TAG</var></samp><a name="index-_002d_002dpivot-TAG-1"></a></dt>

<dd>

Produce a balance pivot report _around_ the given <var>TAG</var>. For example, if you have multiple cars and track each fuel purchase in ‘<samp>Expenses:Auto:Fuel</samp>’ and tag each fuel purchase with a tag identifying which car the purchase was for ‘<samp>; Car: Prius</samp>’, then the command:

<div class="smallexample">

<pre class="smallexample">$ ledger bal Fuel --pivot "Car" --period "this year"
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">           $ 3491.26  Car
           $ 1084.22    M3:Expenses:Auto:Fuel
            $ 149.65    MG V11:Expenses:Auto:Fuel
            $ 621.89    Prius:Expenses:Auto:Fuel
           $ 1635.50    Sienna:Expenses:Auto:Fuel
             $ 42.69  Expenses:Auto:Fuel
--------------------
           $ 3533.95
</pre>

</div>

See [Metadata values](#Metadata-values).

</dd>

<dt><samp>--plot-amount-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dplot_002damount_002dformat-FORMAT_005fSTRING-1"></a></dt>

<dd>

Define the output format for an amount data plot. See [Visualizing with Gnuplot](#Visualizing-with-Gnuplot).

</dd>

<dt><samp>--plot-total-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dplot_002dtotal_002dformat-FORMAT_005fSTRING-1"></a></dt>

<dd>

Define the output format for a total data plot. See [Visualizing with Gnuplot](#Visualizing-with-Gnuplot).

</dd>

<dt><samp>--prepend-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dprepend_002dformat-FORMAT_005fSTRING"></a></dt>

<dd>

Prepend <var>STR</var> to every line of the output.

</dd>

<dt><samp>--prepend-width <var>INT</var></samp><a name="index-_002d_002dprepend_002dwidth-INT"></a></dt>

<dd>

Reserve <var>INT</var> spaces at the beginning of each line of the output.

</dd>

<dt><samp>--price</samp><a name="index-_002d_002dprice"></a></dt>

<dt><samp>-I</samp><a name="index-_002dI"></a></dt>

<dd>

Use the price of the commodity purchase for performing calculations.

</dd>

<dt><samp>--pricedb-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dpricedb_002dformat-FORMAT_005fSTRING"></a></dt>

<dd>

Set the format expected for the historical price file.

</dd>

<dt><samp>--prices-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dprices_002dformat-FORMAT_005fSTRING-1"></a></dt>

<dd>

Set the format for the `prices` report.

</dd>

<dt><samp>--primary-date</samp><a name="index-_002d_002dprimary_002ddate"></a></dt>

<dt><samp>--actual-dates</samp><a name="index-_002d_002dactual_002ddates"></a></dt>

<dd>

Show primary dates for all calculations (see [Effective Dates](#Effective-Dates)).

</dd>

<dt><samp>--quantity</samp><a name="index-_002d_002dquantity-1"></a></dt>

<dt><samp>-O</samp><a name="index-_002dO-1"></a></dt>

<dd>

Report commodity totals (this is the default).

</dd>

<dt><samp>--quarterly</samp><a name="index-_002d_002dquarterly-2"></a></dt>

<dd>

Synonym for ‘<samp>--period "quarterly"</samp>’.

</dd>

<dt><samp>--raw</samp><a name="index-_002d_002draw"></a></dt>

<dd>

In the `print` report, show transactions using the exact same syntax as specified by the user in their data file. Don’t do any massaging or interpreting. This can be useful for minor cleanups, like just aligning amounts.

</dd>

<dt><samp>--real</samp><a name="index-_002d_002dreal-3"></a></dt>

<dt><samp>-R</samp><a name="index-_002dR-1"></a></dt>

<dd>

Account using only real transactions ignoring virtual and automatic transactions.

</dd>

<dt><samp>--register-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dregister_002dformat-FORMAT_005fSTRING-1"></a></dt>

<dd>

Define the output format for the `register` report.

</dd>

<dt><samp>--related</samp><a name="index-_002d_002drelated-2"></a></dt>

<dd>

In a `register` report show the related account. This is the other _side_ of the transaction.

</dd>

<dt><samp>--related-all</samp><a name="index-_002d_002drelated_002dall"></a></dt>

<dd>

Show all postings in a transaction, similar to <samp>--related</samp> but show both _sides_ of each transaction.

</dd>

<dt><samp>--revalued</samp><a name="index-_002d_002drevalued"></a></dt>

<dd>

Report discrepancy in values for manual reports by inserting `<Revalued>` postings. This is implied when using the <samp>--exchange</samp> or <samp>--market</samp> option.

</dd>

<dt><samp>--revalued-only</samp><a name="index-_002d_002drevalued_002donly"></a></dt>

<dd>

Show only `<Revalued>` postings.

</dd>

<dt><samp>--revalued-total <var>FIXME</var></samp><a name="index-_002d_002drevalued_002dtotal-FIXME"></a></dt>

<dd>

Display the sum of the revalued postings as the running total, which serves to show unrealized capital in a gain/losses report.

</dd>

<dt><samp>--rich-data</samp><a name="index-_002d_002drich_002ddata-1"></a></dt>

<dt><samp>--detail</samp><a name="index-_002d_002ddetail"></a></dt>

<dd>

When generating a ledger transaction from a CSV file using the `convert` command, add CSV, Imported, and UUID metadata.

</dd>

<dt><samp>--seed <var>INT</var></samp><a name="index-_002d_002dseed-INT"></a></dt>

<dd>

Set the random seed to <var>INT</var> for the `generate` command. Used as part of development testing.

</dd>

<dt><samp>--sort <var>VEXPR</var></samp><a name="index-_002d_002dsort-VEXPR-1"></a></dt>

<dt><samp>-S <var>VEXPR</var></samp><a name="index-_002dS-VEXPR-1"></a></dt>

<dd>

Sort the `register` report based on the value expression given to sort.

</dd>

<dt><samp>--sort-all <var>FIXME</var></samp><a name="index-_002d_002dsort_002dall-FIXME"></a></dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

<dt><samp>--sort-xacts <var>VEXPR</var></samp><a name="index-_002d_002dsort_002dxacts-VEXPR"></a></dt>

<dt><samp>--period-sort <var>VEXPR</var></samp><a name="index-_002d_002dperiod_002dsort-VEXPR-2"></a></dt>

<dd>

Sort the postings within transactions using the given value expression.

</dd>

<dt><samp>--start-of-week <var>INT</var></samp><a name="index-_002d_002dstart_002dof_002dweek-INT"></a></dt>

<dd>

Tell ledger to use a particular day of the week to start its “weekly” summary. ‘<samp>--start-of-week=1</samp>’ specifies Monday as the start of the week.

</dd>

<dt><samp>--subtotal</samp><a name="index-_002d_002dsubtotal-4"></a></dt>

<dt><samp>-s</samp><a name="index-_002ds-2"></a></dt>

<dd>

Cause all transactions in a `register` report to be collapsed into a single, subtotaled transaction.

</dd>

<dt><samp>--tail <var>INT</var></samp><a name="index-_002d_002dtail-INT-1"></a></dt>

<dt><samp>--last <var>INT</var></samp><a name="index-_002d_002dlast-INT"></a></dt>

<dd>

Report only the last <var>INT</var> entries. Only useful in a `register` report.

</dd>

<dt><samp>--time-report</samp><a name="index-_002d_002dtime_002dreport"></a></dt>

<dd>

Add two columns to the balance report to show the earliest checkin and checkout times for timelog entries.

</dd>

<dt><samp>--total <var>VEXPR</var></samp><a name="index-_002d_002dtotal-VEXPR-1"></a></dt>

<dt><samp>-T <var>VEXPR</var></samp><a name="index-_002dT-VEXPR-1"></a></dt>

<dd>

Define a value expression used to calculate the total in reports.

</dd>

<dt><samp>--total-data</samp><a name="index-_002d_002dtotal_002ddata-3"></a></dt>

<dt><samp>-J</samp><a name="index-_002dJ-1"></a></dt>

<dd>

Show only dates and totals to format the output for plots.

</dd>

<dt><samp>--total-width <var>INT</var></samp><a name="index-_002d_002dtotal_002dwidth-INT"></a></dt>

<dd>

Set the width of the total field in the register report.

</dd>

<dt><samp>--truncate <var>CODE</var></samp><a name="index-_002d_002dtruncate-CODE"></a></dt>

<dd>

Indicates how truncation should happen when the contents of columns exceed their width. Valid arguments are ‘<samp>leading</samp>’, ‘<samp>middle</samp>’, and ‘<samp>trailing</samp>’. The default is smarter than any of these three, as it considers sub-names within the account name (that style is called “abbreviate”).

</dd>

<dt><samp>--unbudgeted</samp><a name="index-_002d_002dunbudgeted-1"></a></dt>

<dd>

Show only unbudgeted postings.

</dd>

<dt><samp>--uncleared</samp><a name="index-_002d_002duncleared-2"></a></dt>

<dt><samp>-U</samp><a name="index-_002dU-1"></a></dt>

<dd>

Use only uncleared transactions in calculations and reports.

</dd>

<dt><samp>--unrealized</samp><a name="index-_002d_002dunrealized"></a></dt>

<dd>

Show generated unrealized gain and loss accounts in the balance report.

</dd>

<dt><samp>--unrealized-gains <var>STR</var></samp><a name="index-_002d_002dunrealized_002dgains-STR"></a></dt>

<dd>

Allow the user to specify what account name should be used for unrealized gains. Defaults to ‘<samp>"Equity:Unrealized Gains"</samp>’. Often set in one’s <samp>~/.ledgerrc</samp> file to change the default.

</dd>

<dt><samp>--unrealized-losses <var>STR</var></samp><a name="index-_002d_002dunrealized_002dlosses-STR"></a></dt>

<dd>

Allow the user to specify what account name should be used for unrealized losses. Defaults to ‘<samp>"Equity:Unrealized Losses"</samp>’. Often set in one’s <samp>~/.ledgerrc</samp> file to change the default.

</dd>

<dt><samp>--unround</samp><a name="index-_002d_002dunround"></a></dt>

<dd>

Perform all calculations without rounding and display results to full precision.

</dd>

<dt><samp>--values</samp><a name="index-_002d_002dvalues-1"></a></dt>

<dd>

Shows the values used by each tag when used in combination with the `tags` command.

</dd>

<dt><samp>--weekly</samp><a name="index-_002d_002dweekly-2"></a></dt>

<dt><samp>-W</samp><a name="index-_002dW-2"></a></dt>

<dd>

Synonym for ‘<samp>--period "weekly"</samp>’.

</dd>

<dt><samp>--wide</samp><a name="index-_002d_002dwide-1"></a></dt>

<dd>

Let the register report use 132 columns instead of 80 (the default). Identical to ‘<samp>--columns "132"</samp>’.

</dd>

<dt><samp>--yearly</samp><a name="index-_002d_002dyearly-2"></a></dt>

<dt><samp>-Y</samp><a name="index-_002dY-2"></a></dt>

<dd>

Synonym for ‘<samp>--period "yearly"</samp>’.

</dd>

</dl>

* * *

<a name="Basic-options"></a>

<div class="header">

Next: [Report filtering](#Report-filtering), Previous: [Report Options](#Report-Options), Up: [Detailed Option Description](#Detailed-Option-Description)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Basic-options-1"></a>

#### 8.3.4 Basic options

These are the most basic command options. Most likely, the user will want to set them using environment variables (see [Environment variables](#Environment-variables)), instead of using actual command-line options:

<dl compact="compact">

<dt><samp>--help</samp><a name="index-_002d_002dhelp-2"></a></dt>

<dt><samp>-h</samp><a name="index-_002dh-2"></a></dt>

<dd>

Display the man page for <samp>ledger</samp>.

</dd>

<dt><samp>--version</samp><a name="index-_002d_002dversion-2"></a></dt>

<dd>

Print the current version of ledger and exits. This is useful for sending bug reports, to let the author know which version of ledger you are using.

</dd>

<dt><samp>--file <var>FILE</var></samp><a name="index-_002d_002dfile-FILE-2"></a></dt>

<dt><samp>-f <var>FILE</var></samp><a name="index-_002df-FILE-2"></a></dt>

<dd>

Read <samp>FILE</samp> as a ledger file. <var>FILE</var> can be ‘<samp>-</samp>’ which is a synonym for ‘<samp>/dev/stdin</samp>’. This command may be used multiple times. Typically, the environment variable `LEDGER_FILE` is set, rather than using this command-line option.

</dd>

<dt><samp>--output <var>FILE</var></samp><a name="index-_002d_002doutput-FILE-2"></a></dt>

<dt><samp>-o <var>FILE</var></samp><a name="index-_002do-FILE-1"></a></dt>

<dd>

Redirect output from any command to <samp>FILE</samp>. By default, all output goes to standard output.

</dd>

<dt><samp>--init-file <var>FILE</var></samp><a name="index-_002d_002dinit_002dfile-FILE-2"></a></dt>

<dt><samp>-i <var>FILE</var></samp><a name="index-_002di-FILE-1"></a></dt>

<dd>

Causes <samp>FILE</samp> to be read by ledger before any other ledger file. This file may not contain any postings, but it may contain option settings. To specify options in the init file, use the same syntax as on the command-line, but put each option on its own line. Here is an example init file:

<div class="smallexample">

<pre class="smallexample">--price-db ~/finance/.pricedb
--wide
; ~/.ledgerrc ends here
</pre>

</div>

Option settings on the command-line or in the environment always take precedence over settings in the init file.

</dd>

<dt><samp>--account <var>STR</var></samp><a name="index-_002d_002daccount-STR-3"></a></dt>

<dt><samp>-a <var>STR</var></samp><a name="index-_002da-STR-1"></a></dt>

<dd>

Specify the default account which QIF file postings are assumed to relate to.

</dd>

</dl>

* * *

<a name="Report-filtering"></a>

<div class="header">

Next: [Output customization](#Output-customization), Previous: [Basic options](#Basic-options), Up: [Detailed Option Description](#Detailed-Option-Description)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Report-filtering-1"></a>

#### 8.3.5 Report filtering

These options change which postings affect the outcome of a report, in ways other than just using regular expressions:

<dl compact="compact">

<dt><samp>--current</samp><a name="index-_002d_002dcurrent-2"></a></dt>

<dt><samp>-c</samp><a name="index-_002dc-1"></a></dt>

<dd>

Display only transactions occurring on or before the current date.

</dd>

<dt><samp>--begin <var>DATE</var></samp><a name="index-_002d_002dbegin-DATE-2"></a></dt>

<dt><samp>-b <var>DATE</var></samp><a name="index-_002db-DATE-1"></a></dt>

<dd>

Constrain the report to transactions on or after <var>DATE</var>. Only transactions after that date will be calculated, which means that the running total in the balance report will always start at zero with the first matching transaction. (Note: This is different from using <samp>--display <var>EXPR</var></samp> to constrain what is displayed).

</dd>

<dt><samp>--end <var>DATE</var></samp><a name="index-_002d_002dend-DATE-2"></a></dt>

<dt><samp>-e <var>DATE</var></samp><a name="index-_002de-DATE-1"></a></dt>

<dd>

Constrain the report so that transactions on or after <var>DATE</var> are not considered.

</dd>

<dt><samp>--period <var>PERIOD_EXPRESSION</var></samp><a name="index-_002d_002dperiod-PERIOD_005fEXPRESSION-2"></a></dt>

<dt><samp>-p <var>PERIOD_EXPRESSION</var></samp><a name="index-_002dp-PERIOD_005fEXPRESSION-1"></a></dt>

<dd>

Set the reporting period to <var>STR</var>. This will subtotal all matching transactions within each period separately, making it easy to see weekly, monthly, quarterly, etc., posting totals. A period string can even specify the beginning and end of the report range, using simple terms like ‘<samp>last June</samp>’ or ‘<samp>next month</samp>’. For more details on period expressions, see [Period Expressions](#Period-Expressions).

</dd>

<dt><samp>--period-sort <var>VEXPR</var></samp><a name="index-_002d_002dperiod_002dsort-VEXPR-3"></a></dt>

<dd>

Sort the postings within each reporting period using the value expression <var>EXPR</var>. This is most often useful when reporting monthly expenses, in order to view the highest expense categories at the top of each month:

<div class="smallexample">

<pre class="smallexample">$ ledger -M --period-sort total reg ^Expenses
</pre>

</div>

</dd>

<dt><samp>--cleared</samp><a name="index-_002d_002dcleared-3"></a></dt>

<dt><samp>-C</samp><a name="index-_002dC-2"></a></dt>

<dd>

Display only postings whose transaction has been marked “cleared” (by placing an asterisk to the right of the date).

</dd>

<dt><samp>--uncleared</samp><a name="index-_002d_002duncleared-3"></a></dt>

<dt><samp>-U</samp><a name="index-_002dU-2"></a></dt>

<dd>

Display only postings whose transaction has not been marked “cleared” (i.e., if there is no asterisk to the right of the date).

</dd>

<dt><samp>--real</samp><a name="index-_002d_002dreal-4"></a></dt>

<dt><samp>-R</samp><a name="index-_002dR-2"></a></dt>

<dd>

Display only real postings, not virtual. (A virtual posting is indicated by surrounding the account name with parentheses or brackets; see [Virtual postings](#Virtual-postings) for more information).

</dd>

<dt><samp>--actual</samp><a name="index-_002d_002dactual-2"></a></dt>

<dt><samp>-L</samp><a name="index-_002dL-2"></a></dt>

<dd>

Display only actual postings, and not those created by automated transactions.

</dd>

<dt><samp>--related</samp><a name="index-_002d_002drelated-3"></a></dt>

<dt><samp>-r</samp><a name="index-_002dr-1"></a></dt>

<dd>

Display postings that are related to whichever postings would otherwise have matched the filtering criteria. In the register report, this shows where money went to, or the account it came from. In the balance report, it shows all the accounts affected by transactions having a related posting. For example, if a file had this transaction:

<div class="smallexample">

<pre class="smallexample">2004/03/20 Safeway
    Expenses:Food                       $65.00
    Expenses:Cash                       $20.00
    Assets:Checking                    $-85.00
</pre>

</div>

And the register command was:

<div class="smallexample">

<pre class="smallexample">$ ledger -f example.dat -r register food
</pre>

</div>

The following would be printed, showing the postings related to the posting that matched:

<div class="smallexample">

<pre class="smallexample">04-Mar-20 Safeway               Expenses:Cash                $20.00       $20.00
                                Assets:Checking             $-85.00      $-65.00
</pre>

</div>

</dd>

<dt><samp>--budget</samp><a name="index-_002d_002dbudget-3"></a></dt>

<dd>

Useful for displaying how close your postings meet your budget. <samp>--add-budget</samp> also shows unbudgeted postings, while <samp>--unbudgeted</samp> shows only those. <samp>--forecast <var>VEXPR</var></samp> is a related option that projects your budget into the future, showing how it will affect future balances. See [Budgeting and Forecasting](#Budgeting-and-Forecasting).

</dd>

<dt><samp>--limit <var>EXPR</var></samp><a name="index-_002d_002dlimit-EXPR-4"></a></dt>

<dt><samp>-l <var>EXPR</var></samp><a name="index-_002dl-EXPR-2"></a></dt>

<dd>

Limit which postings take part in the calculations of a report.

</dd>

<dt><samp>--amount <var>EXPR</var></samp><a name="index-_002d_002damount-EXPR-2"></a></dt>

<dt><samp>-t <var>EXPR</var></samp><a name="index-_002dt-EXPR-2"></a></dt>

<dd>

Change the value expression used to calculate the “value” column in the `register` report, the amount used to calculate account totals in the `balance` report, and the values printed in the `equity` report. See [Value Expressions](#Value-Expressions).

</dd>

<dt><samp>--total <var>VEXPR</var></samp><a name="index-_002d_002dtotal-VEXPR-2"></a></dt>

<dt><samp>-T <var>VEXPR</var></samp><a name="index-_002dT-VEXPR-2"></a></dt>

<dd>

Set the value expression used for the “totals” column in the `register` and `balance` reports.

</dd>

</dl>

* * *

<a name="Output-customization"></a>

<div class="header">

Next: [Commodity reporting](#Commodity-reporting), Previous: [Report filtering](#Report-filtering), Up: [Detailed Option Description](#Detailed-Option-Description)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Output-customization-1"></a>

#### 8.3.6 Output customization

These options affect only the output, but not which postings are used to create it:

<dl compact="compact">

<dt><samp>--collapse</samp><a name="index-_002d_002dcollapse-2"></a></dt>

<dt><samp>-n</samp><a name="index-_002dn-2"></a></dt>

<dd>

Cause transactions in a `register` report with multiple postings to be collapsed into a single, subtotaled transaction.

</dd>

<dt><samp>--subtotal</samp><a name="index-_002d_002dsubtotal-5"></a></dt>

<dt><samp>-s</samp><a name="index-_002ds-3"></a></dt>

<dd>

Cause all transactions in a `register` report to be collapsed into a single, subtotaled transaction.

</dd>

<dt><samp>--by-payee</samp><a name="index-_002d_002dby_002dpayee-5"></a></dt>

<dt><samp>-P</samp><a name="index-_002dP-3"></a></dt>

<dd>

Report subtotals by payee.

</dd>

<dt><samp>--empty</samp><a name="index-_002d_002dempty-3"></a></dt>

<dt><samp>-E</samp><a name="index-_002dE-2"></a></dt>

<dd>

Include even empty accounts in the `balance` report.

</dd>

<dt><samp>--weekly</samp><a name="index-_002d_002dweekly-3"></a></dt>

<dt><samp>-W</samp><a name="index-_002dW-3"></a></dt>

<dd>

Report posting totals by the week. The week begins on whichever day of the week begins the month containing that posting. To set a specific begin date, use a period string, such as ‘<samp>weekly from DATE</samp>’.

</dd>

<dt><samp>--monthly</samp><a name="index-_002d_002dmonthly-4"></a></dt>

<dt><samp>-M</samp><a name="index-_002dM-2"></a></dt>

<dd>

Report posting totals by month.

</dd>

<dt><samp>--yearly</samp><a name="index-_002d_002dyearly-3"></a></dt>

<dt><samp>-Y</samp><a name="index-_002dY-3"></a></dt>

<dd>

Report posting totals by year. For more complex periods, use <samp>--period</samp>.

</dd>

<dt><samp>--period <var>PERIOD_EXPRESSION</var></samp><a name="index-_002d_002dperiod-PERIOD_005fEXPRESSION-3"></a></dt>

<dd>

Option described above.

</dd>

<dt><samp>--dow</samp><a name="index-_002d_002ddow-3"></a></dt>

<dd>

Report posting totals for each day of the week. This is an easy way to see if weekend spending is more than on weekdays.

</dd>

<dt><samp>--sort <var>VEXPR</var></samp><a name="index-_002d_002dsort-VEXPR-2"></a></dt>

<dt><samp>-S <var>VEXPR</var></samp><a name="index-_002dS-VEXPR-2"></a></dt>

<dd>

Sort a report by comparing the values determined using the value expression <var>VEXPR</var>. For example, using ‘<samp>-S "-abs(total)"</samp>’ in the `balance` report will sort account balances from greatest to least, using the absolute value of the total. For more on how to use value expressions, see [Value Expressions](#Value-Expressions).

</dd>

<dt><samp>--pivot <var>TAG</var></samp><a name="index-_002d_002dpivot-TAG-2"></a></dt>

<dd>

Produce a pivot table around the <var>TAG</var> provided. This requires meta data using valued tags.

</dd>

<dt><samp>--wide</samp><a name="index-_002d_002dwide-2"></a></dt>

<dt><samp>-w</samp><a name="index-_002dw-1"></a></dt>

<dd>

Cause the default `register` report to assume 132 columns instead of 80.

</dd>

<dt><samp>--head <var>INT</var></samp><a name="index-_002d_002dhead-INT-2"></a></dt>

<dd>

Cause only the first <var>INT</var> transactions to be printed. This is different from using the command-line utility <samp>head</samp>, which would limit to the first <var>INT</var> postings. <samp>--tail <var>INT</var></samp> outputs only the last <var>INT</var> transactions. Both options may be used simultaneously. If a negative amount is given, it will invert the meaning of the flag (instead of the first five transactions being printed, for example, it would print all but the first five).

</dd>

<dt><samp>--pager <var>FILE</var></samp><a name="index-_002d_002dpager-FILE-2"></a></dt>

<dd>

Tell Ledger to pass its output to the given <var>FILE</var> pager program; very useful when the output is especially long. This behavior can be made the default by setting the `LEDGER_PAGER` environment variable.

</dd>

<dt><samp>--no-pager</samp><a name="index-_002d_002dno_002dpager-2"></a></dt>

<dd>

Tell Ledger to _not_ pass its output to a pager program; useful when a pager is set by default.

</dd>

<dt><samp>--average</samp><a name="index-_002d_002daverage-3"></a></dt>

<dt><samp>-A</samp><a name="index-_002dA-2"></a></dt>

<dd>

Report the average posting value.

</dd>

<dt><samp>--deviation</samp><a name="index-_002d_002ddeviation-2"></a></dt>

<dt><samp>-D</samp><a name="index-_002dD-3"></a></dt>

<dd>

Report each posting’s deviation from the average. It is only meaningful in the `register` and `prices` reports.

</dd>

<dt><samp>--percent</samp><a name="index-_002d_002dpercent-2"></a></dt>

<dt><samp>-%</samp><a name="index-_002d_0025-2"></a></dt>

<dd>

Show account subtotals in the `balance` report as percentages of the parent account.

</dd>

<dt><samp>--amount-data</samp><a name="index-_002d_002damount_002ddata-4"></a></dt>

<dt><samp>-j</samp><a name="index-_002dj-2"></a></dt>

<dd>

Change the `register` report so that it prints nothing but the date and the value column, and the latter without commodities. This is only meaningful if the report uses a single commodity. This data can then be fed to other programs, which could plot the date, analyze it, etc.

</dd>

<dt><samp>--total-data</samp><a name="index-_002d_002dtotal_002ddata-4"></a></dt>

<dt><samp>-J</samp><a name="index-_002dJ-2"></a></dt>

<dd>

Change the `register` report so that it prints nothing but the date and total columns, without commodities.

</dd>

<dt><samp>--display <var>EXPR</var></samp><a name="index-_002d_002ddisplay-EXPR-4"></a></dt>

<dt><samp>-d <var>EXPR</var></samp><a name="index-_002dd-EXPR-1"></a></dt>

<dd>

Limit which postings or accounts are actually displayed in a report. They might still be calculated, and be part of the running total of a register report, for example, but they will not be displayed. This is useful for seeing last month’s checking postings, against a running balance which includes all posting values:

<div class="smallexample">

<pre class="smallexample">$ ledger -d "d>=[last month]" reg checking
</pre>

</div>

The output from this command is very different from the following, whose running total includes only postings from the last month onward:

<div class="smallexample">

<pre class="smallexample">$ ledger -p "last month" reg checking
</pre>

</div>

Which is more useful depends on what you’re looking to know: the total amount for the reporting range (using <samp>--period <var>PERIOD_EXPRESSION</var> (-p)</samp>), or simply a display restricted to the reporting range (using <samp>--display <var>EXPR</var> (-d)</samp>).

</dd>

<dt><samp>--date-format <var>DATE_FORMAT</var></samp><a name="index-_002d_002ddate_002dformat-DATE_005fFORMAT-2"></a></dt>

<dt><samp>-y <var>DATE_FORMAT</var></samp><a name="index-_002dy-DATE_005fFORMAT-2"></a></dt>

<dd>

Change the basic date format used by reports. The default uses a date like ‘<samp>2004/08/01</samp>’, which represents the default date format of `%Y/%m/%d`. To change the way dates are printed in general, the easiest way is to put <samp>--date-format <var>DATE_FORMAT</var></samp> in the Ledger initialization file <samp>~/.ledgerrc</samp> (or the file referred to by `LEDGER_INIT`).

</dd>

<dt><samp>--format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dformat-FORMAT_005fSTRING-2"></a></dt>

<dt><samp>-F <var>FORMAT_STRING</var></samp><a name="index-_002dF-FORMAT_005fSTRING-2"></a></dt>

<dd>

Set the reporting format for whatever report ledger is about to make. See [Format Strings](#Format-Strings). There are also specific format commands for each report type:

</dd>

<dt><samp>--balance-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dbalance_002dformat-FORMAT_005fSTRING-2"></a></dt>

<dd>

Define the output format for the `balance` report. The default (defined in <samp>report.h</samp> is:

<div class="smallexample">

<pre class="smallexample">"%(ansify_if(
        justify(scrub(display_total), 20,
                20 + int(prepend_width), true, color),
                  bold if should_bold))
        %(!options.flat ? depth_spacer : \"\")
      %-(ansify_if(
         ansify_if(partial_account(options.flat), blue if color),
                   bold if should_bold))\n%/
      %$1\n%/
      %(prepend_width ? \" \" * int(prepend_width) : \"\")
      --------------------\n"
</pre>

</div>

</dd>

<dt><samp>--cleared-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dcleared_002dformat-FORMAT_005fSTRING-1"></a></dt>

<dd>

Define the format for the cleared report. The default is:

<div class="smallexample">

<pre class="smallexample">"%(justify(scrub(get_at(display_total, 0)), 16, 16 + int(prepend_width),
       true, color))  %(justify(scrub(get_at(display_total, 1)), 18,
       36 + int(prepend_width), true, color))
          %(latest_cleared ? format_date(latest_cleared) : \"         \")
          %(!options.flat ? depth_spacer : \"\")
      %-(ansify_if(partial_account(options.flat), blue if color))\n%/
      %$1  %$2    %$3\n%/
      %(prepend_width ? \" \" * int(prepend_width) : \"\")
      ----------------    ----------------    ---------\n"
</pre>

</div>

</dd>

<dt><samp>--register-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dregister_002dformat-FORMAT_005fSTRING-2"></a></dt>

<dd>

Define the output format for the `register` report. The default (defined in <samp>report.h</samp> is:

<div class="smallexample">

<pre class="smallexample">"%(ansify_if(
        ansify_if(justify(format_date(date), int(date_width)),
                  green if color and date > today),
                  bold if should_bold))
       %(ansify_if(
         ansify_if(justify(truncated(payee, int(payee_width)), int(payee_width)),
                   bold if color and !cleared and actual),
                   bold if should_bold))
       %(ansify_if(
         ansify_if(justify(truncated(display_account, int(account_width),
                                     int(abbrev_len)), int(account_width)),
                   blue if color),
                   bold if should_bold))
       %(ansify_if(
         justify(scrub(display_amount), int(amount_width),
                 3 + int(meta_width) + int(date_width) + int(payee_width)
                   + int(account_width) + int(amount_width) + int(prepend_width),
                 true, color),
                 bold if should_bold))
       %(ansify_if(
         justify(scrub(display_total), int(total_width),
                 4 + int(meta_width) + int(date_width) + int(payee_width)
                   + int(account_width) + int(amount_width) + int(total_width)
                   + int(prepend_width), true, color),
                 bold if should_bold))\n%/
      %(justify(\" \", int(date_width)))
       %(ansify_if(
         justify(truncated(has_tag(\"Payee\") ? payee : \" \",
                           int(payee_width)), int(payee_width)),
                   bold if should_bold))
       %$3 %$4 %$5\n"
</pre>

</div>

</dd>

<dt><samp>--csv-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dcsv_002dformat-FORMAT_005fSTRING-1"></a></dt>

<dd>

Set the format for `csv` reports. The default is:

<div class="smallexample">

<pre class="smallexample">"%(quoted(date)),
 %(quoted(code)),
 %(quoted(payee)),
 %(quoted(display_account)),
 %(quoted(commodity(scrub(display_amount)))),
 %(quoted(quantity(scrub(display_amount)))),
 %(quoted(cleared ? \"*\" : (pending ? \"!\" : \"\"))),
 %(quoted(join(note | xact.note)))\n"
</pre>

</div>

</dd>

<dt><samp>--plot-amount-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dplot_002damount_002dformat-FORMAT_005fSTRING-2"></a></dt>

<dd>

Set the format for amount plots, using the <samp>--amount-data (-j)</samp> option. The default is:

<div class="smallexample">

<pre class="smallexample">"%(format_date(date, \"%Y-%m-%d\")) %(quantity(scrub(display_amount)))\n"
</pre>

</div>

</dd>

<dt><samp>--plot-total-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dplot_002dtotal_002dformat-FORMAT_005fSTRING-2"></a></dt>

<dd>

Set the format for total plots, using the <samp>--total-data (-J)</samp> option. The default is:

<div class="smallexample">

<pre class="smallexample">"%(format_date(date, \"%Y-%m-%d\")) %(quantity(scrub(display_total)))\n"
</pre>

</div>

</dd>

<dt><samp>--pricedb-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dpricedb_002dformat-FORMAT_005fSTRING-1"></a></dt>

<dd>

Set the format expected for the historical price file. The default is:

<div class="smallexample">

<pre class="smallexample">"P %(datetime) %(display_account) %(scrub(display_amount))\n"
</pre>

</div>

</dd>

<dt><samp>--prices-format <var>FORMAT_STRING</var></samp><a name="index-_002d_002dprices_002dformat-FORMAT_005fSTRING-2"></a></dt>

<dd>

Set the format for the `prices` report. The default is:

<div class="smallexample">

<pre class="smallexample">"%(date) %-8(display_account) %(justify(scrub(display_amount), 12,
           2 + 9 + 8 + 12, true, color))\n"
</pre>

</div>

</dd>

</dl>

* * *

<a name="Commodity-reporting"></a>

<div class="header">

Next: [Environment variables](#Environment-variables), Previous: [Output customization](#Output-customization), Up: [Detailed Option Description](#Detailed-Option-Description)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Commodity-reporting-1"></a>

#### 8.3.7 Commodity reporting

These options affect how commodity values are displayed:

<dl compact="compact">

<dt><samp>--price-db <var>FILE</var></samp><a name="index-_002d_002dprice_002ddb-FILE-3"></a></dt>

<dd>

Set the file that is used for recording downloaded commodity prices. It is always read on startup, to determine historical prices. Other settings can be placed in this file manually, to prevent downloading quotes for a specific commodity, for example. This is done by adding a line like the following:

<div class="smallexample">

<pre class="smallexample">; Don't download quotes for the dollar, or timelog values
N $
N h
</pre>

</div>

Note: Ledger NEVER writes output to files. You are responsible for updating the price-db file. The best way is to have your price download script maintain this file.

The format of the file can be changed by telling ledger to use the <samp>--pricedb-format <var>FORMAT_STRING</var></samp> you define.

</dd>

<dt><samp>--price-exp <var>INT</var></samp><a name="index-_002d_002dprice_002dexp-INT-2"></a></dt>

<dt><samp>--leeway <var>INT</var></samp><a name="index-_002d_002dleeway-INT-2"></a></dt>

<dt><samp>-Z <var>INT</var></samp><a name="index-_002dZ-INT-2"></a></dt>

<dd>

Set the expected freshness of price quotes, in <var>INT</var> minutes. That is, if the last known quote for any commodity is older than this value, and if <samp>--download</samp> is being used, then the Internet will be consulted again for a newer price. Otherwise, the old price is still considered to be fresh enough.

</dd>

<dt><samp>--download</samp><a name="index-_002d_002ddownload-3"></a></dt>

<dt><samp>-Q</samp><a name="index-_002dQ-2"></a></dt>

<dd>

Cause quotes to be automagically downloaded, as needed, by running a script named <samp>getquote</samp> and expecting that script to return a value understood by ledger. A sample implementation of a <samp>getquote</samp> script, implemented in Perl, is provided in the distribution. Downloaded quote price are then appended to the price database, usually specified using the environment variable `LEDGER_PRICE_DB`.

</dd>

</dl>

There are several different ways that ledger can report the totals it displays. The most flexible way to adjust them is by using value expressions, and the <samp>--amount <var>EXPR</var> (-t)</samp> and <samp>--total <var>VEXPR</var> (-T)</samp> options. However, there are also several “default” reports, which will satisfy most users’ basic reporting needs:

<dl compact="compact">

<dt><samp>--quantity</samp><a name="index-_002d_002dquantity-2"></a></dt>

<dt><samp>-O</samp><a name="index-_002dO-2"></a></dt>

<dd>

Report commodity totals (this is the default).

</dd>

<dt><samp>--basis</samp><a name="index-_002d_002dbasis-2"></a></dt>

<dt><samp>-B</samp><a name="index-_002dB-2"></a></dt>

<dd>

Report the cost basis for all postings.

</dd>

<dt><samp>--market</samp><a name="index-_002d_002dmarket-5"></a></dt>

<dt><samp>-V</samp><a name="index-_002dV-2"></a></dt>

<dd>

Use the last known value for commodities to calculate final values.

</dd>

<dt><samp>--gain</samp><a name="index-_002d_002dgain-2"></a></dt>

<dt><samp>-G</samp><a name="index-_002dG-2"></a></dt>

<dd>

Report the net gain/loss for all commodities in the report that have a price history.

</dd>

</dl>

Often you will be more interested in the value of your entire holdings, in your preferred currency. It might be nice to know you hold 10,000 shares of PENNY, but you are more interested in whether or not that is worth $1000.00 or $10,000.00\. However, the current day value of a commodity can mean different things to different people, depending on the accounts involved, the commodities, the nature of the transactions, etc.

<a name="index-_002d_002dnow-DATE-1"></a><a name="index-_002d_002dmarket-6"></a><a name="index-_002d_002dexchange-COMMODITY-3"></a>

When you specify <samp>--market (-V)</samp>, or <samp>--exchange <var>COMMODITY</var> (-X)</samp>, you are requesting that some or all of the commodities be valuated as of today (or whatever <samp>--now <var>DATE</var></samp> is set to). But what does such a valuation mean? This meaning is governed by the presence of a <var>VALUE</var> meta-data property, whose content is an expression used to compute that value.

If no <var>VALUE</var> property is specified, each posting is assumed to have a default, as if you’d specified a global, automated transaction as follows:

<div class="smallexample">

<pre class="smallexample">= expr true
    ; VALUE:: market(amount, date, exchange)
</pre>

</div>

This definition emulates the present day behavior of <samp>--market (-V)</samp> and <samp>--exchange <var>COMMODITY</var> (-X)</samp> (in the case of ‘<samp>-X</samp>’, the requested commodity is passed via the string ‘<samp>exchange</samp>’ above).

<a name="index-Euro-conversion"></a>

One thing many people have wanted to do is to fixate the valuation of old European currencies in terms of the Euro after a certain date:

<div class="smallexample">

<pre class="smallexample">= expr commodity == "DM"
    ; VALUE:: date < [Jun 2008] ? market(amount, date, exchange) : 1.44 EUR
</pre>

</div>

This says: If <samp>--now <var>DATE</var></samp> is some old date, use market prices as they were at that time; but if <samp>--now <var>DATE</var></samp> is past June 2008, use a fixed price for converting Deutsch Mark to Euro.

Or how about never re-valuating commodities used in Expenses, since they cannot have a different future value:

<div class="smallexample">

<pre class="smallexample">= /^Expenses:/
    ; VALUE:: market(amount, post.date, exchange)
</pre>

</div>

This says the future valuation is the same as the valuation at the time of posting. `post.date` equals the posting’s date, while just ’date’ is the value of <samp>--now <var>DATE</var></samp> (defaults to today).

Or how about valuating miles based on a reimbursement rate during a specific time period:

<div class="smallexample">

<pre class="smallexample">= expr commodity == "miles" and date >= [2007] and date < [2008]
    ; VALUE:: market($1.05, date, exchange)
</pre>

</div>

In this case, miles driven in 2007 will always be valuated at $1.05 each. If you use ‘<samp>-X EUR</samp>’ to expressly request all amounts in Euro, Ledger shall convert $1.05 to Euro by whatever means are appropriate for dollars.

Note that you can have a valuation expression specific to a particular posting or transaction, by overriding these general defaults using specific meta-data:

<div class="smallexample">

<pre class="smallexample">2010-12-26 Example
    Expenses:Food                $20
    ; Just to be silly, always valuate *these* $20 as 30 DM, no matter what
    ; the user asks for with -V or -X
    ; VALUE:: 30 DM
    Assets:Cash
</pre>

</div>

This example demonstrates that your value expression should be as symbolic as possible, using terms like ’amount’ and ’date’, rather than specific amounts and dates. Also, you should pass the amount along to the function ’market’ so it can be further revalued if the user has asked for a specific currency.

Or, if it better suits your accounting, you can be less symbolic, which allows you to report most everything in EUR if you use ‘<samp>-X EUR</samp>’, except for certain accounts or postings which should always be valuated in another currency. For example:

<div class="smallexample">

<pre class="smallexample">= /^Assets:Brokerage:CAD$/
    ; Always report the value of commodities in this account in
    ; terms of present day dollars, despite what was asked for
    ; on the command-line VALUE:: market(amount, date, ‘<samp>$</samp>’)
</pre>

</div>

<a name="index-FIFO_002fLIFO"></a><a name="index-LIFO_002fFIFO"></a><a name="index-_002d_002dlots-2"></a><a name="index-_002d_002dlot_002dprices-2"></a><a name="index-_002d_002dexchange-COMMODITY-4"></a><a name="index-_002d_002dhistorical-1"></a><a name="index-_002d_002dbasis-3"></a><a name="index-_002d_002dprice-1"></a>

Ledger presently has no way of handling such things as FIFO and LIFO.

If you specify an unadorned commodity name, like AAPL, it will balance against itself. If <samp>--lots</samp> are not being displayed, then it will appear to balance against any lot of AAPL.

<a name="index-adorned-commodity"></a><a name="index-_002d_002dlot_002dprices-3"></a>

If you specify an adorned commodity, like AAPL {$10.00}, it will also balance against itself, and against any AAPL if <samp>--lots</samp> is not specified. But if you do specify <samp>--lot-prices</samp>, for example, then it will balance against that specific price for AAPL.

Normally when you use <samp>--exchange <var>COMMODITY</var> (-X)</samp> to request that amounts be reported in a specific commodity, Ledger uses these values:

*   Register Report For the `register` report, use the value of that commodity on the date of the posting being reported, with a ‘<samp><Revalued></samp>’ posting added at the end if today’s value is different from the value of the last posting.
*   Balance Report For the `balance` report, use the value of that commodity as of today.

You can now specify <samp>--historical (-H)</samp> to ask that all valuations for any amount be done relative to the date that amount was encountered.

You can also now use <samp>--exchange <var>COMMODITY</var> (-X)</samp> (and <samp>--historical (-H)</samp>) in conjunction with <samp>--basis (-B)</samp> and <samp>--price (-I)</samp>, to see valuation reports of just your basis costs or lot prices.

Finally, sometimes, you may seek to only report one (or some subset) of the commodities in terms of another commodity. In this situation, you can use the syntax <samp>--exchange <var>COMMODITY1</var>:<var>COMMODITY2</var></samp> to request that ledger always display <var>COMMODITY1</var> in terms of <var>COMMODITY2</var>, but you want no other commodities to be automatically displayed in terms of <var>COMMODITY2</var> without additional <samp>--exchange</samp> options. For example, if you wanted to report EUR and BTC in terms of USD, but report all other commodities without conversion to USD, you could use: <samp>--exchange EUR:USD --exchange BTC:USD</samp>.

* * *

<a name="Environment-variables"></a>

<div class="header">

Previous: [Commodity reporting](#Commodity-reporting), Up: [Detailed Option Description](#Detailed-Option-Description)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Environment-variables-1"></a>

#### 8.3.8 Environment variables

Every option to ledger may be set using an environment variable if the option has a long name. For example setting the environment variable ‘<samp>`LEDGER_DATE_FORMAT`="%d.%m.%Y"</samp>’ will have the same effect as specifying ‘<samp><samp>--date-format</samp> '%d.%m.%Y'</samp>’ on the command-line. Options on the command-line always take precedence over environment variable settings, however.

Note that you may also permanently specify option values by placing option settings in the file <samp>~/.ledgerrc</samp> one option per line, for example:

<div class="smallexample">

<pre class="smallexample">--pager /bin/cat
</pre>

</div>

* * *

<a name="Period-Expressions"></a>

<div class="header">

Previous: [Detailed Option Description](#Detailed-Option-Description), Up: [Command-Line Syntax](#Command_002dLine-Syntax)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Period-Expressions-1"></a>

### 8.4 Period Expressions

A period expression indicates a span of time, or a reporting interval, or both. Ledger’s end dates are always exclusive, imagine the date is followed by 00:00:00 time. They are instants in time not entire days. The full syntax is:

<div class="smallexample">

<pre class="smallexample">[INTERVAL] [BEGIN] [END]
</pre>

</div>

The optional <var>INTERVAL</var> part may be any one of:

<div class="smallexample">

<pre class="smallexample">every day
every week
every month
every quarter
every year
every N days     # N is any integer
every N weeks
every N months
every N quarters
every N years
daily
weekly
biweekly
monthly
bimonthly
quarterly
yearly
</pre>

</div>

After the interval, a begin time, end time, both or neither may be specified. As for the begin time, it can be either of:

<div class="smallexample">

<pre class="smallexample">from <SPEC>
since <SPEC>
</pre>

</div>

The end time can be either of:

<div class="smallexample">

<pre class="smallexample">to <SPEC>
until <SPEC>
</pre>

</div>

Where <var>SPEC</var> can be any of:

<div class="smallexample">

<pre class="smallexample">2004
2004/10
2004/10/1
10/1
october
oct
this week  # or day, month, quarter, year
next week
last week
</pre>

</div>

The beginning and ending can be given at the same time, if it spans a single period. In that case, just use <var>SPEC</var> by itself. In that case, the period ‘<samp>oct</samp>’, for example, will cover all the days in October. The possible forms are:

<div class="smallexample">

<pre class="smallexample"><SPEC>
in <SPEC>
</pre>

</div>

Here are a few examples of period expressions:

<div class="smallexample">

<pre class="smallexample">monthly
monthly in 2004
weekly from oct
weekly from last month
from sep to oct
from 10/1 to 10/5
monthly until 2005
from apr
until nov
last oct
weekly last august
</pre>

</div>

* * *

<a name="Budgeting-and-Forecasting"></a>

<div class="header">

Next: [Time Keeping](#Time-Keeping), Previous: [Command-Line Syntax](#Command_002dLine-Syntax), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Budgeting-and-Forecasting-1"></a>

## 9 Budgeting and Forecasting

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Budgeting](#Budgeting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Forecasting](#Forecasting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Budgeting"></a>

<div class="header">

Next: [Forecasting](#Forecasting), Previous: [Budgeting and Forecasting](#Budgeting-and-Forecasting), Up: [Budgeting and Forecasting](#Budgeting-and-Forecasting)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Budgeting-1"></a>

### 9.1 Budgeting

<a name="index-_002d_002dbudget-4"></a><a name="index-_002d_002dadd_002dbudget-2"></a><a name="index-_002d_002dunbudgeted-2"></a><a name="index-_002d_002dmonthly-5"></a>

Keeping a budget allows you to pay closer attention to your income and expenses, by reporting how far your actual financial activity is from your expectations.

To start keeping a budget, put some periodic transactions (see [Periodic Transactions](#Periodic-Transactions)) at the top of your ledger file. A periodic transaction is almost identical to a regular transaction, except that it begins with a tilde and has a period expression in place of a payee. For example:

<div class="smallexample">

<pre class="smallexample">~ Monthly
    Expenses:Rent               $500.00
    Expenses:Food               $450.00
    Expenses:Auto:Gas           $120.00
    Expenses:Insurance          $150.00
    Expenses:Phone              $125.00
    Expenses:Utilities          $100.00
    Expenses:Movies              $50.00
    Expenses                    $200.00  ; all other expenses
    Assets

~ Yearly
    Expenses:Auto:Repair        $500.00
    Assets
</pre>

</div>

These two periodic transactions give the usual monthly expenses, as well as one typical yearly expense. For help on finding out what your average monthly expenses are for any category, use a command like:

<div class="smallexample">

<pre class="smallexample">$ ledger -p "this year" --monthly --average balance ^expenses
</pre>

</div>

The reported totals are the current year’s average for each account.

Once these periodic transactions are defined, creating a budget report is as easy as adding <samp>--budget</samp> to the command-line. For example, a typical monthly expense report would be:

<div class="smallexample">

<pre class="smallexample">$ ledger --monthly register ^expenses
</pre>

</div>

To see the same report balanced against your budget, use:

<div class="smallexample">

<pre class="smallexample">$ ledger --budget --monthly register ^expenses
</pre>

</div>

A budget report includes only those accounts that appear in the budget. To see all expenses balanced against the budget, use <samp>--add-budget</samp>. You can even see only the unbudgeted expenses using <samp>--unbudgeted</samp>:

<div class="smallexample">

<pre class="smallexample">$ ledger --unbudgeted --monthly register ^expenses
</pre>

</div>

You can also use these flags with the `balance` command.

* * *

<a name="Forecasting"></a>

<div class="header">

Previous: [Budgeting](#Budgeting), Up: [Budgeting and Forecasting](#Budgeting-and-Forecasting)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Forecasting-1"></a>

### 9.2 Forecasting

<a name="index-_002d_002dforecast-VEXPR-2"></a>

Sometimes it’s useful to know what your finances will look like in the future, such as determining when an account will reach zero. Ledger makes this easy to do, using the same periodic transactions as are used for budgeting. An example forecast report can be generated with:

<div class="smallexample">

<pre class="smallexample">$ ledger --file drewr3.dat --forecast "T>{\$-500.00}" register ^assets ^liabilities
</pre>

</div>

This report continues outputting postings until the running total is greater than $-500.00\. A final posting is always shown, to inform you what the total afterwards would be.

Forecasting can also be used with the `balance` report, but by date only, and not against the running total:

<div class="smallexample">

<pre class="smallexample">$ ledger --forecast "d<[2010]" bal ^assets ^liabilities
</pre>

</div>

* * *

<a name="Time-Keeping"></a>

<div class="header">

Next: [Value Expressions](#Value-Expressions), Previous: [Budgeting and Forecasting](#Budgeting-and-Forecasting), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Time-Keeping-1"></a>

## 10 Time Keeping

<a name="index-_002d_002dday_002dbreak-1"></a><a name="timelog"></a>

Ledger directly supports “timelog” entries, which have this form:

<div class="smallexample">

<pre class="smallexample">i 2013/03/28 22:13:00 ACCOUNT[  PAYEE]
o 2013/03/29 03:39:00
</pre>

</div>

This records a check-in to the given ACCOUNT, and a check-out. You can be checked-in to multiple accounts at a time, if you wish, and they can span multiple days (use <samp>--day-break</samp> to break them up in the report). The number of seconds between check-in and check-out is accumulated as time to that ACCOUNT. If the checkout uses a capital ‘<samp>O</samp>’, the transaction is marked “cleared”. You can use an optional PAYEE for whatever meaning you like.

Now, there are a few ways to generate this information. You can use the <samp>timeclock.el</samp> package, which is part of Emacs. Or you can write a simple script in whichever language you prefer to emit similar information. Or you can use Org mode’s time-clocking abilities and the <samp>org2tc</samp> script developed by John Wiegley.

These timelog entries can appear in a separate file, or directly in your main ledger file. The initial ‘<samp>i</samp>’ and ‘<samp>o</samp>’ characters count as Ledger “directives”, and are accepted anywhere that ordinary transactions are valid.

* * *

<a name="Value-Expressions"></a>

<div class="header">

Next: [Format Strings](#Format-Strings), Previous: [Time Keeping](#Time-Keeping), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Value-Expressions-1"></a>

## 11 Value Expressions

<a name="index-_002d_002dlimit-EXPR-5"></a><a name="index-_002d_002ddisplay-EXPR-5"></a>

Ledger uses value expressions to make calculations for many different purposes:

1.  The values displayed in reports.
2.  For predicates (where truth is anything non-zero), to determine which postings are calculated (option <samp>--limit <var>EXPR</var> (-l)</samp>) or displayed (option <samp>--display <var>EXPR</var> (-d)</samp>).
3.  For sorting criteria, to yield the sort key.
4.  In the matching criteria used by automated postings.

Value expressions support most simple math and logic operators, in addition to a set of functions and variables.

Display predicates are also very handy with register reports, to constrain which transactions are printed. For example, the following command shows only transactions from the beginning of the current month, while still calculating the running balance based on all transactions:

<div class="smallexample">

<pre class="smallexample">$ ledger -d "d>[this month]" register checking
</pre>

</div>

The advantage of this command’s complexity is that it prints the running total in terms of all transactions in the register. The following, simpler command is similar, but totals only the displayed postings:

<div class="smallexample">

<pre class="smallexample">$ ledger -b "this month" register checking
</pre>

</div>

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Variables](#Variables):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Functions](#Functions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Operators](#Operators):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Complex expressions](#Complex-expressions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Variables"></a>

<div class="header">

Next: [Functions](#Functions), Previous: [Value Expressions](#Value-Expressions), Up: [Value Expressions](#Value-Expressions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Variables-1"></a>

### 11.1 Variables

<a name="index-_002d_002damount-EXPR-3"></a><a name="index-_002d_002dtotal-VEXPR-3"></a>

Below are the one letter variables available in any value expression. For the `register` and `print` commands, these variables relate to individual postings, and sometimes the account affected by a posting. For the `balance` command, these variables relate to accounts, often with a subtle difference in meaning. The use of each variable for both is specified.

<dl compact="compact">

<dt>`t`</dt>

<dd>

This maps to whatever the user specified with <samp>--amount <var>EXPR</var> (-t)</samp>. In a `register` report, <samp>--amount <var>EXPR</var> (-t)</samp> changes the value column; in a `balance` report, it has no meaning by default. If <samp>--amount <var>EXPR</var> (-t)</samp> was not specified, the current report style’s value expression is used.

</dd>

<dt>`T`</dt>

<dd>

This maps to whatever the user specified with <samp>--total <var>VEXPR</var> (-T)</samp>. In a register report, <samp>--total <var>VEXPR</var> (-T)</samp> changes the totals column; in a balance report, this is the value given for each account. If <samp>--total <var>VEXPR</var> (-T)</samp> was not specified, the current report style’rsquo;s value expression is used.

</dd>

<dt>`m`</dt>

<dd>

This is always the present moment/date.

</dd>

</dl>

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Posting/account details](#Posting_002faccount-details):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Calculated totals](#Calculated-totals):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Posting_002faccount-details"></a>

<div class="header">

Next: [Calculated totals](#Calculated-totals), Previous: [Variables](#Variables), Up: [Variables](#Variables)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Posting_002faccount-details-1"></a>

#### 11.1.1 Posting/account details

<dl compact="compact">

<dt>`d`</dt>

<dd>

A posting’s date, as the number of seconds past the epoch. This is always “today” for an account.

</dd>

<dt>`a`</dt>

<dd>

The posting’s amount; the balance of an account, without considering children.

</dd>

<dt>`b`</dt>

<dd>

The cost of a posting; the cost of an account, without its children.

</dd>

<dt>`v`</dt>

<dd>

The market value of a posting or an account, without its children.

</dd>

<dt>`g`</dt>

<dd>

The net gain (market value minus cost basis), for a posting or an account, without its children. It is the same as ‘<samp>v-b</samp>’.

</dd>

<dt>`l`</dt>

<dd>

The depth (“level”) of an account. If an account has one parent, its depth is one.

</dd>

<dt>`n`</dt>

<dd>

The index of a posting, or the count of postings affecting an account.

</dd>

<dt>`X`</dt>

<dd>

‘<samp>1</samp>’ if a posting’s transaction has been cleared, ‘<samp>0</samp>’ otherwise.

</dd>

<dt>`R`</dt>

<dd>

‘<samp>1</samp>’ if a posting is not virtual, ‘<samp>0</samp>’ otherwise.

</dd>

<dt>`Z`</dt>

<dd>

‘<samp>1</samp>’ if a posting is not automated, ‘<samp>0</samp>’ otherwise.

</dd>

</dl>

* * *

<a name="Calculated-totals"></a>

<div class="header">

Previous: [Posting/account details](#Posting_002faccount-details), Up: [Variables](#Variables)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Calculated-totals-1"></a>

#### 11.1.2 Calculated totals

<dl compact="compact">

<dt>`O`</dt>

<dd>

The total of all postings seen so far, or the total of an account and all its children.

</dd>

<dt>`N`</dt>

<dd>

The total count of postings affecting an account and all its children.

</dd>

</dl>

* * *

<a name="Functions"></a>

<div class="header">

Next: [Operators](#Operators), Previous: [Variables](#Variables), Up: [Value Expressions](#Value-Expressions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Functions-1"></a>

### 11.2 Functions

The available one letter functions are:

<dl compact="compact">

<dt>`-`</dt>

<dd>

Negates the argument.

</dd>

<dt>`U`</dt>

<dd>

The absolute (unsigned) value of the argument.

</dd>

<dt>`S`</dt>

<dd>

Strips the commodity from the argument.

</dd>

<dt>`P`</dt>

<dd>

The present market value of the argument. The syntax ‘<samp>P(x,d)</samp>’ is supported, which yields the market value at time ‘<samp>d</samp>’. If no date is given, then the current moment is used.

</dd>

</dl>

* * *

<a name="Operators"></a>

<div class="header">

Next: [Complex expressions](#Complex-expressions), Previous: [Functions](#Functions), Up: [Value Expressions](#Value-Expressions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Operators-1"></a>

### 11.3 Operators

The binary and ternary operators, in order of precedence, are:

1.  `* /`
2.  `+ -`
3.  `! < > =`
4.  `& | ?:`

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Unary Operators](#Unary-Operators):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Binary Operators](#Binary-Operators):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Unary-Operators"></a>

<div class="header">

Next: [Binary Operators](#Binary-Operators), Previous: [Operators](#Operators), Up: [Operators](#Operators)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Unary-Operators-1"></a>

#### 11.3.1 Unary Operators

`not` `neg`

* * *

<a name="Binary-Operators"></a>

<div class="header">

Previous: [Unary Operators](#Unary-Operators), Up: [Operators](#Operators)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Binary-Operators-1"></a>

#### 11.3.2 Binary Operators

`==` `<` `<=` `>` `>=` `and` `or` `+` `-` `*` `/` `QUERY` `COLON` `CONS` `SEQ` `DEFINE` `LOOKUP` `LAMBDA` `CALL` `MATCH`

* * *

<a name="Complex-expressions"></a>

<div class="header">

Previous: [Operators](#Operators), Up: [Value Expressions](#Value-Expressions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Complex-expressions-1"></a>

### 11.4 Complex expressions

More complicated expressions are possible using:

<dl compact="compact">

<dt>`"amount == COMMODITY AMOUNT"`</dt>

<dd>

The amount can be any kind of amount supported by ledger, with or without a commodity. Use this for decimal values.

</dd>

<dt>`/REGEX/`</dt>

<dt>`account =~ /REGEX/`</dt>

<dd>

A regular expression that matches against an account’s full name. If a posting, this will match against the account affected by the posting.

</dd>

<dt>`@/REGEX/`</dt>

<dt>`expr payee =~ /REGEX/`</dt>

<dd>

A regular expression that matches against a transaction’s payee name.

</dd>

<dt>`%/REGEX/`</dt>

<dt>`tag(REGEX)`</dt>

<dd>

A regular expression that matches against a transaction’s tags.

</dd>

<dt>`expr date =~ /REGEX/`</dt>

<dd>

Useful for specifying a date in plain terms. For example, you could say ‘<samp>expr date =~ /2014/</samp>’.

</dd>

<dt>`expr comment =~ /REGEX/`</dt>

<dd>

A regular expression that matches against a posting’s comment field. This searches only a posting’s field, not the transaction’s note or comment field. For example, `ledger reg "expr" "comment =~ /landline/"` will match:

<div class="smallexample">

<pre class="smallexample">2014/1/29  Phone bill
    Assets:Checking                           $50.00
    Expenses:Phone                           $-50.00  ; landline bill
</pre>

</div>

but will not match:

<div class="smallexample">

<pre class="smallexample">2014/1/29  Phone bill  ; landline bill
    ; landline bill
    Assets:Checking                           $50.00
    Expenses:Phone                           $-50.00
</pre>

</div>

To match the latter, use ‘<samp>ledger reg "expr" "note =~ /landline/"</samp>’ instead.

</dd>

<dt>`expr note =~ /REGEX/`</dt>

<dd>

A regular expression that matches against a transaction’s note field. This searches all comments in the transaction, including comments on individual postings. Thus, ‘<samp>ledger reg "expr" "note =~ /landline/"</samp>’ will match both all the three examples below:

<div class="smallexample">

<pre class="smallexample">2014/1/29  Phone bill
    Assets:Checking                           $50.00
    Expenses:Phone                           $-50.00  ; landline bill
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">2014/1/29  Phone bill  ; landline bill
    Assets:Checking                           $50.00
    Expenses:Phone                           $-50.00
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">2014/1/29  Phone bill
    ; landline bill
    Assets:Checking                           $50.00
    Expenses:Phone                           $-50.00
</pre>

</div>

</dd>

<dt>`(EXPR)`</dt>

<dd>

A sub-expression is nested in parenthesis. This can be useful passing more complicated arguments to functions, or for overriding the natural precedence order of operators.

</dd>

<dt>`expr base =~ /REGEX/`</dt>

<dd>

A regular expression that matches against an account’s base name. If a posting, this will match against the account affected by the posting.

</dd>

<dt>`expr code =~ /REGEX/`</dt>

<dd>

A regular expression that matches against the transaction code (the text that occurs between parentheses before the payee).

</dd>

</dl>

The `query` command can be used to see how Ledger interprets your query. This can be useful if you are not getting the results you expect (see [Pre-Commands](#Pre_002dCommands)).

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Miscellaneous](#Miscellaneous):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Miscellaneous"></a>

<div class="header">

Previous: [Complex expressions](#Complex-expressions), Up: [Complex expressions](#Complex-expressions)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Miscellaneous-1"></a>

#### 11.4.1 Miscellaneous

The following Ledger journal data (saved as <samp>expr.dat</samp>) is used to explain the behaviour of the functions and variables below:<a name="expr_002edat"></a>

<div class="smallexample">

<pre class="smallexample">2015/01/16 * (C0D3) Payee
  Assets:Cash                 ¤ -123,45
    ; Payee: PiggyBank
  Expenses:Office Supplies
</pre>

</div>

<dl>

<dt><a name="index-abs"></a>Function: **abs** _value_</dt>

<dt><a name="index-U"></a>Function: **U** _value_</dt>

<dd>

Return the absolute value of the given <var>value</var>, e.g. <var>amount</var>.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(account) %(abs(amount))\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">Assets:Cash ¤ 123,45
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-amount_005fexpr"></a>Function: **amount_expr**</dt>

<dd>

Return the calculated amount of the posting according to the <samp>--amount</samp> option.

</dd>

</dl>

<dl>

<dt><a name="index-ansify_005fif"></a>Function: **ansify_if** _value color bool_</dt>

<dd>

Render the given <var>expression</var> as a string, applying the proper ANSI escape codes to display it in the given <var>color</var> if <var>bool</var> is true. It typically checks the value of the option <samp>--color</samp>. Since ANSI escape codes include non-printable character sequences, such as escape <kbd>^[</kbd> the following example may not appear as the final result on the command-line.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(ansify_if(account, blue, options.color))\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">[34mAssets:Cash[0m
[34mExpenses:Office Supplies[0m
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-ceiling"></a>Function: **ceiling** _value_</dt>

<dd>

Return the next integer of <var>value</var> toward _+_infinity.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(account) %(ceiling(amount))\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">Assets:Cash ¤ -123,00
Expenses:Office Supplies ¤ 124,00
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-code"></a>Variable: **code**</dt>

<dd>

Return the transaction code, the string between the parenthesis after the date.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(account) %(code)\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">Assets:Cash C0D3
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-commodity-2"></a>Variable: **commodity**</dt>

<dd>

Return the commodity of the posting amount.

</dd>

</dl>

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(account) %(commodity)\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">Assets:Cash ¤
Expenses:Office Supplies ¤
</pre>

</div>

<dl>

<dt><a name="index-date"></a>Variable: **date**</dt>

<dd>

Return the date of the posting.

</dd>

</dl>

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(date) %(account)\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">2015/01/16 Assets:Cash
</pre>

</div>

<dl>

<dt><a name="index-display_005famount"></a>Variable: **display_amount**</dt>

<dt><a name="index-t"></a>Variable: **t**</dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

</dl>

<dl>

<dt><a name="index-display_005ftotal-1"></a>Variable: **display_total**</dt>

<dt><a name="index-T"></a>Variable: **T**</dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

</dl>

<dl>

<dt><a name="index-floor"></a>Function: **floor** _value_</dt>

<dd>

Return the next integer of <var>value</var> toward _-_infinity.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(account) %(floor(amount))\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">Assets:Cash ¤ -124,00
Expenses:Office Supplies ¤ 123,00
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-format"></a>Function: **format** _string_</dt>

<dd>

Evaluate <var>string</var> as format just like the <samp>--format</samp> option.

</dd>

</dl>

<dl>

<dt><a name="index-format_005fdate"></a>Function: **format_date** _date format_</dt>

<dd>

Return the <var>date</var> as a string using <var>format</var>. See `strftime (3)` for format string details.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(format_date(date, '%A, %B %d. %Y'))\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">Friday, January 16\. 2015
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-format_005fdatetime"></a>Function: **format_datetime** _datetime format_</dt>

<dd>

Return the <var>datetime</var> as a string using <var>format</var>. Refer to `strftime (3)` for format string details.

</dd>

</dl>

<dl>

<dt><a name="index-get_005fat"></a>Function: **get_at** _sequence index_</dt>

<dd>

Return the value in <var>sequence</var> at <var>index</var>. The first element is <var>index</var> 0. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-is_005fseq"></a>Function: **is_seq** _value_</dt>

<dd>

Return true if <var>value</var> is a sequence. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-join"></a>Function: **join** _value_</dt>

<dd>

Replace all newlines in <var>value</var> with `\n`.

</dd>

</dl>

<dl>

<dt><a name="index-justify"></a>Function: **justify** _value first_width latter_width right_justify colorize_</dt>

<dd>

Right or left justify the string representing <var>value</var>. The width of the field in the first line is given by <var>first_width</var>. For subsequent lines the width is given by <var>latter_width</var>. If <var>latter_width=-1</var>, then <var>first_width</var> is used for all lines. If <var>right_justify=true</var> then the field is right justified within the width of the field. If it is <var>false</var>, then the field is left justified and padded to the full width of the field. If <var>colorize</var> is true, then ledger will honor color settings.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "»%(justify(account, 30, 30, true))«\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">»                   Assets:Cash«
»      Expenses:Office Supplies«
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-market"></a>Function: **market** _value datetime_</dt>

<dt><a name="index-P-1"></a>Function: **P**</dt>

<dd>

Return the price of <var>value</var> at <var>datetime</var>. Note that <var>datetime</var> must be surrounded by brackets in order to be parsed correctly, e.g. `[2012/03/23]`.

</dd>

</dl>

<dl>

<dt><a name="index-nail_005fdown"></a>Function: **nail_down**</dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

</dl>

<dl>

<dt><a name="index-now"></a>Variable: **now**</dt>

<dt><a name="index-d"></a>Variable: **d**</dt>

<dt><a name="index-m"></a>Variable: **m**</dt>

<dd>

Return the current datetime.

</dd>

</dl>

<dl>

<dt><a name="index-options"></a>Variable: **options**</dt>

<dd>

A variable that allows access to the values of the given command-line options using the long option names, e.g. to see whether <samp>--daily</samp> or <samp>-D</samp> was given use `option.daily`.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat -X $ -D --format "%(options.daily) %(options.exchange)\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">true $
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-percent"></a>Function: **percent** _value_a value_b_</dt>

<dd>

Return the percentage of <var>value_a</var> in relation to <var>value_b</var> (used as 100%)

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(percent(amount, 200))\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">-61.73%
61.73%
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-print-5"></a>Function: **print** _value_</dt>

<dd>

Print <var>value</var> to stdout. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-quantity"></a>Function: **quantity** _value_</dt>

<dd>

Return the quantity of <var>value</var> for values that have a per-unit cost.

</dd>

</dl>

<dl>

<dt><a name="index-quoted"></a>Function: **quoted** _expression_</dt>

<dd>

Surround <var>expression</var> with double-quotes.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(quoted(account)) %(quoted(amount))\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">"Assets:Cash" "¤ -123,45"
"Expenses:Office Supplies" "¤ 123,45"
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-round"></a>Function: **round**</dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

</dl>

<dl>

<dt><a name="index-rounded"></a>Function: **rounded**</dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

</dl>

<dl>

<dt><a name="index-roundto"></a>Function: **roundto** _value n_</dt>

<dd>

Return <var>value</var> rounded to <var>n</var> digits. Does not affect formatting.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(account) %(roundto(amount, 1))\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">Assets:Cash ¤ -123,40
Expenses:Office Supplies ¤ 123,50
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-scrub"></a>Function: **scrub** _value_</dt>

<dd>

Clean <var>value</var> using various transformations such as `round`, stripping value annotations, and more.

</dd>

</dl>

<dl>

<dt><a name="index-should_005fbold"></a>Function: **should_bold**</dt>

<dd>

Return true if expression given to <samp>--bold-if</samp> evaluates to true. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-strip"></a>Function: **strip** _value_</dt>

<dt><a name="index-S"></a>Function: **S**</dt>

<dd>

Strip value annotation from <var>value</var>.

</dd>

</dl>

<dl>

<dt><a name="index-to_005famount"></a>Function: **to_amount** _value_</dt>

<dd>

Convert <var>value</var> to an amount. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-to_005fbalance"></a>Function: **to_balance** _value_</dt>

<dd>

Convert <var>value</var> to a balance. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-to_005fboolean"></a>Function: **to_boolean** _value_</dt>

<dd>

Convert <var>value</var> to a boolean. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-to_005fdate"></a>Function: **to_date** _value_</dt>

<dd>

Convert <var>value</var> to a date. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-to_005fdatetime"></a>Function: **to_datetime** _value_</dt>

<dd>

Convert <var>value</var> to a datetime. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-to_005fint"></a>Function: **to_int** _value_</dt>

<dt><a name="index-int"></a>Function: **int** _value_</dt>

<dd>

Return the integer value for <var>value</var>.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%(1 + to_int('1'))\n%(2,5 + int(2,5))\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">2
4.5
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-to_005fmask"></a>Function: **to_mask** _value_</dt>

<dd>

Convert <var>value</var> to a mask. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-to_005fsequence"></a>Function: **to_sequence** _value_</dt>

<dd>

Convert <var>value</var> to a sequence. For internal use only.

</dd>

</dl>

<dl>

<dt><a name="index-to_005fstring"></a>Function: **to_string** _value_</dt>

<dt><a name="index-str"></a>Function: **str** _value_</dt>

<dd>

Convert <var>value</var> to a character string.

</dd>

</dl>

<dl>

<dt><a name="index-today"></a>Variable: **today**</dt>

<dd>

Return today’s date.

</dd>

</dl>

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --now 2015/01/01 --format "%(today)\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">2015/01/01
</pre>

</div>

<dl>

<dt><a name="index-top_005famount"></a>Function: **top_amount**</dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

</dl>

<dl>

<dt><a name="index-total_005fexpr"></a>Function: **total_expr**</dt>

<dd>

Return the calculated total of the posting according to the <samp>--total</samp> option.

</dd>

</dl>

<dl>

<dt><a name="index-trim"></a>Function: **trim** _value_</dt>

<dd>

Trim leading and trailing whitespace from <var>value</var>.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "»%(trim(' 	Trimmed	 '))«\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">»Trimmed«
</pre>

</div>

</dd>

</dl>

<dl>

<dt><a name="index-truncatedstring"></a>Function: **truncatedstring** _total_len account_len_</dt>

<dd>

Truncate <var>string</var> to <var>total_len</var> ensuring that each account is at least <var>account_len</var> long.

</dd>

</dl>

<dl>

<dt><a name="index-unround"></a>Function: **unround**</dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

</dl>

<dl>

<dt><a name="index-unrounded"></a>Function: **unrounded**</dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

</dl>

<dl>

<dt><a name="index-value_005fdate"></a>Function: **value_date**</dt>

<dd>

<small>UNDOCUMENTED</small>! Please help by contributing documentation for this feature.

</dd>

</dl>

* * *

<a name="Format-Strings"></a>

<div class="header">

Next: [Extending with Python](#Extending-with-Python), Previous: [Value Expressions](#Value-Expressions), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Format-Strings-1"></a>

## 12 Format Strings

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Format String Basics](#Format-String-Basics):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Format String Structure](#Format-String-Structure):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Format Expressions](#Format-Expressions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Balance format](#Balance-format):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Formatting Functions and Codes](#Formatting-Functions-and-Codes):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Format-String-Basics"></a>

<div class="header">

Next: [Format String Structure](#Format-String-Structure), Previous: [Format Strings](#Format-Strings), Up: [Format Strings](#Format-Strings)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Format-String-Basics-1"></a>

### 12.1 Format String Basics

<a name="index-_002d_002dformat-FORMAT_005fSTRING-3"></a><a name="index-_002d_002dbalance_002dformat-FORMAT_005fSTRING-3"></a><a name="index-_002d_002dbudget_002dformat-FORMAT_005fSTRING-1"></a><a name="index-_002d_002dcleared_002dformat-FORMAT_005fSTRING-2"></a><a name="index-_002d_002dcsv_002dformat-FORMAT_005fSTRING-2"></a><a name="index-_002d_002dplot_002damount_002dformat-FORMAT_005fSTRING-3"></a><a name="index-_002d_002dplot_002dtotal_002dformat-FORMAT_005fSTRING-3"></a><a name="index-_002d_002dpricedb_002dformat-FORMAT_005fSTRING-2"></a><a name="index-_002d_002dprices_002dformat-FORMAT_005fSTRING-3"></a><a name="index-_002d_002dregister_002dformat-FORMAT_005fSTRING-3"></a>

Format strings may be used to change the output format of reports. They are specified by passing a formatting string to the <samp>--format <var>FORMAT_STRING</var> (-F)</samp> option. Within that string, constructs are allowed which make it possible to display the various parts of an account or posting in custom ways.

There are several additional flags that allow you to define formats for specific reports. These are useful to define in your configuration file and will allow you to run ledger reports from the command-line without having to enter a new format for each command.

*   <samp>--balance-format <var>FORMAT_STRING</var></samp>
*   <samp>--budget-format <var>FORMAT_STRING</var></samp>
*   <samp>--cleared-format <var>FORMAT_STRING</var></samp>
*   <samp>--csv-format <var>FORMAT_STRING</var></samp>
*   <samp>--plot-amount-format <var>FORMAT_STRING</var></samp>
*   <samp>--plot-total-format <var>FORMAT_STRING</var></samp>
*   <samp>--pricedb-format <var>FORMAT_STRING</var></samp>
*   <samp>--prices-format <var>FORMAT_STRING</var></samp>
*   <samp>--register-format <var>FORMAT_STRING</var></samp>

* * *

<a name="Format-String-Structure"></a>

<div class="header">

Next: [Format Expressions](#Format-Expressions), Previous: [Format String Basics](#Format-String-Basics), Up: [Format Strings](#Format-Strings)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Format-String-Structure-1"></a>

### 12.2 Format String Structure

Within a format string, a substitution is specified using a percent ‘<samp>%</samp>’ character. The basic format of all substitutions is:

<div class="smallexample">

<pre class="smallexample">%[-][MIN WIDTH][.MAX WIDTH](VALEXPR)
</pre>

</div>

If the optional minus sign ‘<samp>-</samp>’ follows the percent character ‘<samp>%</samp>’, whatever is substituted will be left justified. The default is right justified. If a minimum width is given next, the substituted text will be at least that wide, perhaps wider. If a period and a maximum width is given, the substituted text will never be wider than this, and will be truncated to fit. Here are some examples:

<dl compact="compact">

<dt>`%-20P`</dt>

<dd>

A transaction’s payee, left justified and padded to 20 characters wide.

</dd>

<dt>`%20P`</dt>

<dd>

The same, right justified, at least 20 chars wide.

</dd>

<dt>`%.20P`</dt>

<dd>

The same, no more than 20 chars wide.

</dd>

</dl>

The expression following the format constraints can be a single letter, or an expression enclosed in parentheses or brackets.

* * *

<a name="Format-Expressions"></a>

<div class="header">

Next: [Balance format](#Balance-format), Previous: [Format String Structure](#Format-String-Structure), Up: [Format Strings](#Format-Strings)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Format-Expressions-1"></a>

### 12.3 Format Expressions

<a name="index-_002d_002damount-EXPR-4"></a><a name="index-_002d_002dtotal-VEXPR-4"></a>

For demonstration purposes the journal data from [expr.dat](#expr_002edat) is used. The allowable expressions are:

<dl compact="compact">

<dt>`%`</dt>

<dd>

Inserts a percent sign.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%%\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">%
</pre>

</div>

</dd>

<dt>`t`</dt>

<dd>

Inserts the results of the value expression specified by <samp>--amount <var>EXPR</var> (-t)</samp>. If <samp>--amount <var>EXPR</var> (-t)</samp> was not specified, the current report style’s value expression is used.

</dd>

<dt>`T`</dt>

<dd>

Inserts the results of the value expression specified by <samp>--total <var>VEXPR</var> (-T)</samp>. If <samp>--total <var>VEXPR</var> (-T)</samp> was not specified, the current report style’s value expression is used.

</dd>

<dt>`(EXPR)`</dt>

<dd>

Inserts the amount resulting from the value expression given in parentheses. To insert five times the total value of an account, for example, one could say ‘<samp>%12(5*O)</samp>’. Note: It’s important to put the five first in that expression, so that the commodity doesn’t get stripped from the total.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%12(5*O)\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">   ¤ -617,25
</pre>

</div>

</dd>

<dt>`[DATEFMT]`</dt>

<dd>

Inserts the result of formatting a posting’s date with a date format string, exactly like those supported by `strftime (3)`. For example: ‘<samp>%[%Y/%m/%d %H:%M:%S]</samp>’.

</dd>

<dt>`S`</dt>

<dd>

Insert the path name of the file from which the transaction’s data was read. Only sensible in a `register` report.

<div class="smallexample">

<pre class="smallexample">$ ledger -f ~/journal.dat --format "%S\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">/home/jwiegley/journal.dat
</pre>

</div>

</dd>

<dt>`B`</dt>

<dd>

Inserts the beginning character position of that transaction within the file.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%B\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">26
</pre>

</div>

</dd>

<dt>`b`</dt>

<dd>

Inserts the beginning line of that transaction within the file.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%b\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">2
</pre>

</div>

</dd>

<dt>`E`</dt>

<dd>

Inserts the ending character position of that transaction within the file.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%E\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">90
</pre>

</div>

</dd>

<dt>`e`</dt>

<dd>

Inserts the ending line of that transaction within the file.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%e\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">3
</pre>

</div>

</dd>

<dt>`D`</dt>

<dd>

Returns the date according to the default format.

</dd>

<dt>`d`</dt>

<dd>

Returns the date according to the default format. If the transaction has an effective date, it prints `ACTUAL_DATE=EFFECTIVE_DATE`.

</dd>

<dt>`X`</dt>

<dd>

If a posting has been cleared, this returns a 1, otherwise returns 0.

</dd>

<dt>`Y`</dt>

<dd>

This is the same as ‘<samp>%X</samp>’, except that it only displays a state character if all of the member postings have the same state.

</dd>

<dt>`C`</dt>

<dd>

Inserts the transaction code. This is the value specified between parentheses on the first line of the transaction.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%C\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">(C0D3) 
</pre>

</div>

</dd>

<dt>`P`</dt>

<dd>

Inserts the payee related to a posting.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%P\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">PiggyBank
</pre>

</div>

</dd>

<dt>`A`</dt>

<dd>

Inserts the full name of an account.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%A\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">Assets:Cash
Expenses:Office Supplies
</pre>

</div>

</dd>

<dt>`N`</dt>

<dd>

Inserts the note associated with a posting, if one exists.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%N\n" reg assets
</pre>

</div>

<div class="smallexample">

<pre class="smallexample"> Payee: PiggyBank
</pre>

</div>

</dd>

<dt>`/`</dt>

<dd>

The ‘<samp>%/</samp>’ construct is special. It separates a format string between what is printed for the first posting of a transaction, and what is printed for all subsequent postings. If not used, the same format string is used for all postings.

<div class="smallexample">

<pre class="smallexample">$ ledger -f expr.dat --format "%P\n%/%A\n" reg
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">PiggyBank
Expenses:Office Supplies
</pre>

</div>

</dd>

</dl>

* * *

<a name="Balance-format"></a>

<div class="header">

Next: [Formatting Functions and Codes](#Formatting-Functions-and-Codes), Previous: [Format Expressions](#Format-Expressions), Up: [Format Strings](#Format-Strings)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Balance-format-1"></a>

### 12.4 Balance format

<a name="index-_002d_002dbalance_002dformat-FORMAT_005fSTRING-4"></a><a name="index-_002d_002dformat-FORMAT_005fSTRING-4"></a>

As an example of how flexible the <samp>--format <var>FORMAT_STRING</var></samp> strings can be, the default balance format looks like this (the various functions are described later):

<div class="smallexample">

<pre class="smallexample">"%(justify(scrub(display_total), 20, -1, true, color))"
"  %(!options.flat ? depth_spacer : \"\")"
"%-(ansify_if(partial_account(options.flat), blue if color))\n%/"
"%$1\n%/"
"--------------------\n"
</pre>

</div>

* * *

<a name="Formatting-Functions-and-Codes"></a>

<div class="header">

Previous: [Balance format](#Balance-format), Up: [Format Strings](#Format-Strings)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Formatting-Functions-and-Codes-1"></a>

### 12.5 Formatting Functions and Codes

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Field Widths](#Field-Widths):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Colors](#Colors):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Quantities and Calculations](#Quantities-and-Calculations):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Date Functions](#Date-Functions):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Date and Time Format Codes](#Date-and-Time-Format-Codes):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Text Formatting](#Text-Formatting):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Data File Parsing Information](#Data-File-Parsing-Information):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Field-Widths"></a>

<div class="header">

Next: [Colors](#Colors), Previous: [Formatting Functions and Codes](#Formatting-Functions-and-Codes), Up: [Formatting Functions and Codes](#Formatting-Functions-and-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Field-Widths-1"></a>

#### 12.5.1 Field Widths

The following codes return the width allocated for the specific fields. The defaults can be changed using the corresponding command-line options:

*   `date_width`
*   `payee_width`
*   `account_width`
*   `amount_width`
*   `total_width`

* * *

<a name="Colors"></a>

<div class="header">

Next: [Quantities and Calculations](#Quantities-and-Calculations), Previous: [Field Widths](#Field-Widths), Up: [Formatting Functions and Codes](#Formatting-Functions-and-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Colors-1"></a>

#### 12.5.2 Colors

The character-based formatting ledger can do is limited to the ANSI terminal character colors and font highlights in a normal TTY session.

<table>

<tbody>

<tr>

<td width="30%">`red`</td>

<td width="30%">`magenta`</td>

<td width="30%">`bold`</td>

</tr>

<tr>

<td width="30%">`green`</td>

<td width="30%">`cyan`</td>

<td width="30%">`underline`</td>

</tr>

<tr>

<td width="30%">`yellow`</td>

<td width="30%">`white`</td>

<td width="30%">`blink`</td>

</tr>

<tr>

<td width="30%">`blue`</td>

<td width="30%">`black`</td>

</tr>

</tbody>

</table>

* * *

<a name="Quantities-and-Calculations"></a>

<div class="header">

Next: [Date Functions](#Date-Functions), Previous: [Colors](#Colors), Up: [Formatting Functions and Codes](#Formatting-Functions-and-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Quantities-and-Calculations-1"></a>

#### 12.5.3 Quantities and Calculations

<dl compact="compact">

<dt>`amount_expr`</dt>

<dt>`abs`</dt>

<dt>`commodity`</dt>

<dt>`display_amount`</dt>

<dt>`display_total`</dt>

<dt>`floor`</dt>

<dt>`get_at`</dt>

<dt>`is_seq`</dt>

<dt>`market`</dt>

<dt>`percent`</dt>

<dt>`price`</dt>

<dt>`quantity`</dt>

<dt>`rounded`</dt>

<dt>`truncated`</dt>

<dt>`total_expr`</dt>

<dt>`top_amount`</dt>

<dt>`to_boolean`</dt>

<dt>`to_int`</dt>

<dt>`to_amount`</dt>

<dt>`to_balance`</dt>

<dt>`unrounded`</dt>

</dl>

* * *

<a name="Date-Functions"></a>

<div class="header">

Next: [Date and Time Format Codes](#Date-and-Time-Format-Codes), Previous: [Quantities and Calculations](#Quantities-and-Calculations), Up: [Formatting Functions and Codes](#Formatting-Functions-and-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Date-Functions-1"></a>

#### 12.5.4 Date Functions

<a name="index-_002d_002dnow-DATE-2"></a>

The following functions allow you to manipulate and format dates.

<dl compact="compact">

<dt>`date`</dt>

<dd>

Return the date of the current transaction.

</dd>

<dt>`format_date(date, "FORMAT_STRING")`</dt>

<dd>

Format the date using the given format string.

</dd>

<dt>`now`</dt>

<dd>

Return the current date and time. If the <samp>--now <var>DATE</var></samp> option is defined it will return that value.

</dd>

<dt>`today`</dt>

<dd>

Return the current date. If the <samp>--now <var>DATE</var></samp> option is defined it will return that value.

</dd>

<dt>`to_datetime`</dt>

<dd>

Convert a string to a date-time value.

</dd>

<dt>`to_date`</dt>

<dd>

Convert a string to date value.

</dd>

<dt>`value_date`</dt>

</dl>

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Date and Time Format Codes](#Date-and-Time-Format-Codes):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Date-and-Time-Format-Codes"></a>

<div class="header">

Next: [Text Formatting](#Text-Formatting), Previous: [Date Functions](#Date-Functions), Up: [Formatting Functions and Codes](#Formatting-Functions-and-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Date-and-Time-Format-Codes-1"></a>

#### 12.5.5 Date and Time Format Codes

Date and time format are specified as strings of single letter codes preceded by percent signs. Any separator, or no separator can be specified.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Days](#Days):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Weekdays](#Weekdays):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Month](#Month):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Miscellaneous Date Codes](#Miscellaneous-Date-Codes):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Days"></a>

<div class="header">

Next: [Weekdays](#Weekdays), Previous: [Date and Time Format Codes](#Date-and-Time-Format-Codes), Up: [Date and Time Format Codes](#Date-and-Time-Format-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Days-1"></a>

#### 12.5.5.1 Days

Dates are formed from a combination of day, month and year codes, in whatever order you prefer:

<dl compact="compact">

<dt>`%Y`</dt>

<dd>

Four digit year.

</dd>

<dt>`%y`</dt>

<dd>

Two digit year.

</dd>

<dt>`%m`</dt>

<dd>

Two digit month.

</dd>

<dt>`%d`</dt>

<dd>

Two digit date.

</dd>

</dl>

So `"%Y%m%d"` yields ‘<samp>20111214</samp>’ which provides a date that is simple to sort on.

* * *

<a name="Weekdays"></a>

<div class="header">

Next: [Month](#Month), Previous: [Days](#Days), Up: [Date and Time Format Codes](#Date-and-Time-Format-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Weekdays-1"></a>

#### 12.5.5.2 Weekdays

You can have additional weekday information in your date with ‘<samp>%A</samp>’ as

<dl compact="compact">

<dt>`%m-%d-%Y %A`</dt>

<dd>

yields ‘<samp>02-10-2010 Wednesday</samp>’.

</dd>

<dt>`%A %m-%d-%Y`</dt>

<dd>

yields ‘<samp>Wednesday 02-10-2010</samp>’.

</dd>

</dl>

These are options you can select for weekday

<dl compact="compact">

<dt>`%a`</dt>

<dd>

weekday, abbreviated Wed.

</dd>

<dt>`%A`</dt>

<dd>

weekday, full Wednesday.

</dd>

<dt>`%d`</dt>

<dd>

day of the month (dd), zero padded up to 10.

</dd>

<dt>`%e`</dt>

<dd>

day of the month (dd), no leading zero up to 10.

</dd>

<dt>`%j`</dt>

<dd>

day of year, zero padded 000–366.

</dd>

<dt>`%u`</dt>

<dd>

day of week starting with Monday (1), i.e. `mtwtfss` 3.

</dd>

<dt>`%w`</dt>

<dd>

day of week starting with Sunday (0), i.e. `smtwtfs` 3.

</dd>

</dl>

* * *

<a name="Month"></a>

<div class="header">

Next: [Miscellaneous Date Codes](#Miscellaneous-Date-Codes), Previous: [Weekdays](#Weekdays), Up: [Date and Time Format Codes](#Date-and-Time-Format-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Month-1"></a>

#### 12.5.5.3 Month

You can have additional month information in your date with ‘<samp>%B</samp>’ as

<dl compact="compact">

<dt>`%m-%d-%Y %B`</dt>

<dd>

yields ‘<samp>02-10-2010 February</samp>’.

</dd>

<dt>`%B %m-%d-%Y`</dt>

<dd>

yields ‘<samp>February 02-10-2010</samp>’.

</dd>

</dl>

These are options you can select for month

<dl compact="compact">

<dt>`%m`</dt>

<dd>

‘<samp>mm</samp>’ month as two digits.

</dd>

<dt>`%b`</dt>

<dd>

Locale’s abbreviated month, for example ‘<samp>02</samp>’ might be abbreviated as ‘<samp>Feb</samp>’.

</dd>

<dt>`%B`</dt>

<dd>

Locale’s full month, variable length, e.g. February.

</dd>

</dl>

* * *

<a name="Miscellaneous-Date-Codes"></a>

<div class="header">

Previous: [Month](#Month), Up: [Date and Time Format Codes](#Date-and-Time-Format-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Miscellaneous-Date-Codes-1"></a>

#### 12.5.5.4 Miscellaneous Date Codes

Additional date format parameters which can be used:

<dl compact="compact">

<dt>`%U`</dt>

<dd>

week number Sunday as first day of week, ranging 01–53.

</dd>

<dt>`%W`</dt>

<dd>

week number Monday as first day of week, ranging 01–53.

</dd>

<dt>`%V`</dt>

<dd>

week of the year, ranging 01–53.

</dd>

<dt>`%C`</dt>

<dd>

century, ranging 00–99.

</dd>

<dt>`%D`</dt>

<dd>

yields `%m/%d/%y` as in ‘<samp>02/10/10</samp>’.

</dd>

<dt>`%x`</dt>

<dd>

locale’s date representation, as ‘<samp>02/10/2010</samp>’ for the U.S.

</dd>

<dt>`%F`</dt>

<dd>

yields `%Y-%m-%d` as in ‘<samp>2010-02-10</samp>’.

</dd>

</dl>

* * *

<a name="Text-Formatting"></a>

<div class="header">

Next: [Data File Parsing Information](#Data-File-Parsing-Information), Previous: [Date and Time Format Codes](#Date-and-Time-Format-Codes), Up: [Formatting Functions and Codes](#Formatting-Functions-and-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Text-Formatting-1"></a>

#### 12.5.6 Text Formatting

The following format functions allow you limited formatting of text:

<dl compact="compact">

<dt>`ansify_if(value, color)`</dt>

<dd>

Surrounds the string representing value with ANSI codes to give it `color` on an TTY display. Has no effect if directed to a file.

</dd>

<dt>`justify(value, first_width, latter_width, right_justify, colorize)`</dt>

<dd>

Right or left justify the string representing `value`. The width of the field in the first line is given by `first_width`. For subsequent lines the width is given by `latter_width`. If `latter_width=-1`, then `first_width` is use for all lines. If `right_justify=true` then the field is right justify within the width of the field. If it is `false`, then the field is left justified and padded to the full width of the field. If `colorize` is true, then ledger will honor color settings.

</dd>

<dt>`join(STR)`</dt>

<dd>

Replaces line feeds in `STR` with ‘<samp>\n</samp>’.

</dd>

<dt>`quoted(STR)`</dt>

<dd>

Return `STR` surrounded by double quotes, ‘<samp>"STR"</samp>’.

</dd>

<dt>`strip(value)`</dt>

<dd>

Values can have numerous annotations, such as effective dates and lot prices. `strip` removes these annotations.

</dd>

</dl>

* * *

<a name="Data-File-Parsing-Information"></a>

<div class="header">

Previous: [Text Formatting](#Text-Formatting), Up: [Formatting Functions and Codes](#Formatting-Functions-and-Codes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Data-File-Parsing-Information-1"></a>

#### 12.5.7 Data File Parsing Information

The following format strings provide locational metadata regarding the coordinates of entries in the source data file(s) that generated the posting.

<dl compact="compact">

<dt>`filename`</dt>

<dd>

the name of the ledger data file from whence the posting came, abbreviated ‘<samp>S</samp>’.

</dd>

<dt>`beg_pos`</dt>

<dd>

character position in `filename` where entry for posting begins, abbreviated ‘<samp>B</samp>’.

</dd>

<dt>`end_pos`</dt>

<dd>

character position in `filename` where entry for posting ends, abbreviated ‘<samp>E</samp>’.

</dd>

<dt>`beg_line`</dt>

<dd>

line number in `filename` where entry for posting begins, abbreviated ‘<samp>b</samp>’.

</dd>

<dt>`end_line`</dt>

<dd>

line number in `filename` where entry for posting ends, abbreviated ‘<samp>e</samp>’.

</dd>

</dl>

* * *


If a _quoted commodity_ is found, it is displayed in quotes as well, to avoid any confusion as to which part is the amount, and which part is the commodity.

Another feature of commoditized amounts is that they are reported back in the same form as parsed. If you specify dollar amounts using ‘<samp>$100</samp>’, they will print the same; likewise with ‘<samp>100 $</samp>’ or ‘<samp>$100.000</samp>’. You may even use decimal commas, such as ‘<samp>$100,00</samp>’, or thousand-marks, as in ‘<samp>$10,000.00</samp>’.

These display characteristics become associated with the commodity, with the result being that all amounts of the same commodity are reported consistently. Where this is most noticeable is the _display precision_, which is determined by the most precise value seen for a given commodity—in most cases.

Ledger makes a distinction between _observed amounts_ and unobserved amounts. An observed amount is critiqued by Ledger to determine how amounts using that commodity should be displayed; unobserved amounts are significant in their value only—no matter how they are specified, it does not change how other amounts in that commodity will be displayed.

An example of this is found in cost expressions, covered next.

* * *

<a name="Posting-costs"></a>

<div class="header">

Next: [Primary commodities](#Primary-commodities), Previous: [Specifying Amounts](#Specifying-Amounts), Up: [Journal File Format for Developers](#Journal-File-Format-for-Developers)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Posting-costs-1"></a>

#### 14.2.3 Posting costs

You have seen how to specify either a commoditized or an integer amount for a posting. But what if the amount you paid for something was in one commodity, and the amount received was another? There are two main ways to express this:

<div class="smallexample">

<pre class="smallexample">2010/05/31 Farmer's Market
    Assets:My Larder           100 apples
    Assets:Checking                -$20.00
</pre>

</div>

In this example, you have paid twenty dollars for one hundred apples. The cost to you is twenty cents per apple, and Ledger calculates this implied cost for you. You can also make the cost explicit using a _cost amount_:

<div class="smallexample">

<pre class="smallexample">2010/05/31 Farmer's Market
    Assets:My Larder           100 apples @ $0.200000
    Assets:Checking
</pre>

</div>

Here the _per-unit cost_ is given explicitly in the form of a cost amount; and since cost amounts are _unobserved_, the use of six decimal places has no effect on how dollar amounts are displayed in the final report. You can also specify the _total cost_:

<div class="smallexample">

<pre class="smallexample">2010/05/31 Farmer's Market
    Assets:My Larder           100 apples @@ $20
    Assets:Checking
</pre>

</div>

These three forms have identical meaning. In most cases the first is preferred, but the second two are necessary when more than two postings are involved:

<div class="smallexample">

<pre class="smallexample">2010/05/31 Farmer's Market
    Assets:My Larder           100 apples        @ $0.200000
    Assets:My Larder           100 pineapples    @ $0.33
    Assets:My Larder           100 "crab apples" @ $0.04
    Assets:Checking
</pre>

</div>

Here the implied cost is ‘<samp>$57.00</samp>’, which is entered into the null posting automatically so that the transaction balances.

* * *

<a name="Primary-commodities"></a>

<div class="header">

Previous: [Posting costs](#Posting-costs), Up: [Journal File Format for Developers](#Journal-File-Format-for-Developers)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Primary-commodities-1"></a>

#### 14.2.4 Primary commodities

<a name="index-_002d_002dmarket-7"></a><a name="index-_002d_002dbasis-4"></a>

In every transaction involving more than one commodity, there is always one which is the _primary commodity_. This commodity should be thought of as the exchange commodity, or the commodity used to buy and sell units of the other commodity. In the fruit examples above, dollars are the primary commodity. This is decided by Ledger based on the placement of the commodity in the transaction:

<div class="smallexample">

<pre class="smallexample">2010/05/31 Sample Transaction
    Expenses               100 secondary
    Assets                  -50 primary

2010/05/31 Sample Transaction
    Expenses               100 secondary @ 0.5 primary
    Assets

2010/05/31 Sample Transaction
    Expenses               100 secondary @@ 50 primary
    Assets
</pre>

</div>

The only case where knowledge of primary versus secondary comes into play is in reports that use the <samp>--market (-V)</samp> or <samp>--basis (-B)</samp> options. With these, only primary commodities are shown.

If a transaction uses only one commodity, this commodity is also considered a primary. In fact, when Ledger goes about ensuring that all transactions balance to zero, it only ever asks this of primary commodities.

* * *

* * *

<a name="Example-Journal-File"></a>

<div class="header">

Next: [Miscellaneous Notes](#Miscellaneous-Notes), Previous: [Major Changes from version 2.6](#Major-Changes-from-version-2_002e6), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Example-Journal-File-1"></a>

## Appendix A Example Journal File

The following journal file is included with the source distribution of ledger. It is called <samp>drewr3.dat</samp> and exhibits many ledger features, include automatic and virtual transactions,

<div class="smallexample">

<pre class="smallexample">; -*- ledger -*-

= /^Income/
  (Liabilities:Tithe)                    0.12

;~ Monthly
;  Assets:Checking                     $500.00
;  Income:Salary

;~ Monthly
;   Expenses:Food  $100
;   Assets

2010/12/01 * Checking balance
  Assets:Checking                   $1,000.00
  Equity:Opening Balances

2010/12/20 * Organic Co-op
  Expenses:Food:Groceries             $ 37.50  ; [=2011/01/01]
  Expenses:Food:Groceries             $ 37.50  ; [=2011/02/01]
  Expenses:Food:Groceries             $ 37.50  ; [=2011/03/01]
  Expenses:Food:Groceries             $ 37.50  ; [=2011/04/01]
  Expenses:Food:Groceries             $ 37.50  ; [=2011/05/01]
  Expenses:Food:Groceries             $ 37.50  ; [=2011/06/01]
  Assets:Checking                   $ -225.00

2010/12/28=2011/01/01 Acme Mortgage
  Liabilities:Mortgage:Principal    $  200.00
  Expenses:Interest:Mortgage        $  500.00
  Expenses:Escrow                   $  300.00
  Assets:Checking                  $ -1000.00

2011/01/02 Grocery Store
  Expenses:Food:Groceries             $ 65.00
  Assets:Checking

2011/01/05 Employer
  Assets:Checking                   $ 2000.00
  Income:Salary

2011/01/14 Bank
  ; Regular monthly savings transfer
  Assets:Savings                     $ 300.00
  Assets:Checking

2011/01/19 Grocery Store
  Expenses:Food:Groceries             $ 44.00 ; hastag: not block
  Assets:Checking

2011/01/25 Bank
  ; Transfer to cover car purchase
  Assets:Checking                  $ 5,500.00
  Assets:Savings
  ; :nobudget:

apply tag hastag: true
apply tag nestedtag: true
2011/01/25 Tom's Used Cars
  Expenses:Auto                    $ 5,500.00
  ; :nobudget:
  Assets:Checking

2011/01/27 Book Store
  Expenses:Books                       $20.00
  Liabilities:MasterCard
end tag
2011/12/01 Sale
  Assets:Checking:Business            $ 30.00
  Income:Sales
end tag
</pre>

</div>

* * *

<a name="Miscellaneous-Notes"></a>

<div class="header">

Next: [Concepts Index](#Concepts-Index), Previous: [Example Journal File](#Example-Journal-File), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Miscellaneous-Notes-1"></a>

## Appendix B Miscellaneous Notes

Various notes from the discussion list that I haven’t incorporated in to the main body of the documentation.

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Cookbook](#Cookbook):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Cookbook"></a>

<div class="header">

Previous: [Miscellaneous Notes](#Miscellaneous-Notes), Up: [Miscellaneous Notes](#Miscellaneous-Notes)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Cookbook-1"></a>

### B.1 Cookbook

<table class="menu" border="0" cellspacing="0">

<tbody>

<tr>

<td align="left" valign="top">• [Invoking Ledger](#Invoking-Ledger):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

<tr>

<td align="left" valign="top">• [Ledger Files](#Ledger-Files):</td>

<td>  </td>

<td align="left" valign="top"></td>

</tr>

</tbody>

</table>

* * *

<a name="Invoking-Ledger"></a>

<div class="header">

Next: [Ledger Files](#Ledger-Files), Previous: [Cookbook](#Cookbook), Up: [Cookbook](#Cookbook)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Invoking-Ledger-1"></a>

#### B.1.1 Invoking Ledger

<div class="smallexample">

<pre class="smallexample">$ ledger --group-by "tag('trip')" bal
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">$ ledger cleared VWCU NFCU Tithe Misentry
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">$ ledger register Joint --uncleared
</pre>

</div>

<div class="smallexample">

<pre class="smallexample">$ ledger register Checking --sort d -d 'd>[2011/04/01]' until 2011/05/25
</pre>

</div>

* * *

<a name="Ledger-Files"></a>

<div class="header">

Previous: [Invoking Ledger](#Invoking-Ledger), Up: [Cookbook](#Cookbook)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Ledger-Files-1"></a>

#### B.1.2 Ledger Files

<div class="smallexample">

<pre class="smallexample">= /^Income:Taxable/
  (Liabilities:Tithe Owed)    -0.1
= /Noah/
  (Liabilities:Tithe Owed)    -0.1
= /Jonah/
  (Liabilities:Tithe Owed)    -0.1
= /Tithe/
  (Liabilities:Tithe Owed)    -1.0
</pre>

</div>

* * *

<a name="Concepts-Index"></a>

<div class="header">

Next: [Commands & Options Index](#Commands-_0026-Options-Index), Previous: [Miscellaneous Notes](#Miscellaneous-Notes), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Concepts-Index-1"></a>

## Concepts Index

<table>

<tbody>

<tr>

<th valign="top">Jump to:  </th>

<td>[**A**](#Concepts-Index_cp_letter-A)   [**B**](#Concepts-Index_cp_letter-B)   [**C**](#Concepts-Index_cp_letter-C)   [**D**](#Concepts-Index_cp_letter-D)   [**E**](#Concepts-Index_cp_letter-E)   [**F**](#Concepts-Index_cp_letter-F)   [**G**](#Concepts-Index_cp_letter-G)   [**H**](#Concepts-Index_cp_letter-H)   [**I**](#Concepts-Index_cp_letter-I)   [**J**](#Concepts-Index_cp_letter-J)   [**L**](#Concepts-Index_cp_letter-L)   [**M**](#Concepts-Index_cp_letter-M)   [**N**](#Concepts-Index_cp_letter-N)   [**O**](#Concepts-Index_cp_letter-O)   [**P**](#Concepts-Index_cp_letter-P)   [**R**](#Concepts-Index_cp_letter-R)   [**S**](#Concepts-Index_cp_letter-S)   [**T**](#Concepts-Index_cp_letter-T)   [**U**](#Concepts-Index_cp_letter-U)   [**W**](#Concepts-Index_cp_letter-W)  </td>

</tr>

</tbody>

</table>

<table class="index-cp" border="0">

<tbody>

<tr>

<td></td>

<th align="left">Index Entry</th>

<td> </td>

<th align="left">Section</th>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-A">A</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[account, alias](#index-account_002c-alias):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[account, meaning of](#index-account_002c-meaning-of):</td>

<td> </td>

<td valign="top">[Fat-free Accounting](#Fat_002dfree-Accounting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[accounts, limiting by](#index-accounts_002c-limiting-by):</td>

<td> </td>

<td valign="top">[Register Report](#Register-Report)</td>

</tr>

<tr>

<td></td>

<td valign="top">[accounts, naming](#index-accounts_002c-naming):</td>

<td> </td>

<td valign="top">[Structuring your Accounts](#Structuring-your-Accounts)</td>

</tr>

<tr>

<td></td>

<td valign="top">[adorned commodity](#index-adorned-commodity):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[amounts](#index-amounts):</td>

<td> </td>

<td valign="top">[Specifying Amounts](#Specifying-Amounts)</td>

</tr>

<tr>

<td></td>

<td valign="top">[assertions](#index-assertions):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[assertions](#index-assertions-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[assets and liabilities](#index-assets-and-liabilities):</td>

<td> </td>

<td valign="top">[Assets and Liabilities](#Assets-and-Liabilities)</td>

</tr>

<tr>

<td></td>

<td valign="top">[automated transaction](#index-automated-transaction):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-B">B</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[balance report](#index-balance-report):</td>

<td> </td>

<td valign="top">[Balance Report](#Balance-Report)</td>

</tr>

<tr>

<td></td>

<td valign="top">[beginning ledger](#index-beginning-ledger):</td>

<td> </td>

<td valign="top">[Starting up](#Starting-up)</td>

</tr>

<tr>

<td></td>

<td valign="top">[block comments](#index-block-comments):</td>

<td> </td>

<td valign="top">[Commenting on your Journal](#Commenting-on-your-Journal)</td>

</tr>

<tr>

<td></td>

<td valign="top">[bucket](#index-bucket):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[buying stock](#index-buying-stock):</td>

<td> </td>

<td valign="top">[Buying and Selling Stock](#Buying-and-Selling-Stock)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-C">C</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[cleared report](#index-cleared-report):</td>

<td> </td>

<td valign="top">[Cleared Report](#Cleared-Report)</td>

</tr>

<tr>

<td></td>

<td valign="top">[comma separated variable file reading](#index-comma-separated-variable-file-reading):</td>

<td> </td>

<td valign="top">[The `convert` command](#The-convert-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[comments](#index-comments):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td></td>

<td valign="top">[comments](#index-comments-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[comments](#index-comments-2):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[comments, block](#index-comments_002c-block):</td>

<td> </td>

<td valign="top">[Commenting on your Journal](#Commenting-on-your-Journal)</td>

</tr>

<tr>

<td></td>

<td valign="top">[comments, characters](#index-comments_002c-characters):</td>

<td> </td>

<td valign="top">[Commenting on your Journal](#Commenting-on-your-Journal)</td>

</tr>

<tr>

<td></td>

<td valign="top">[commodity](#index-commodity):</td>

<td> </td>

<td valign="top">[Currency and Commodities](#Currency-and-Commodities)</td>

</tr>

<tr>

<td></td>

<td valign="top">[consumable commodity pricing](#index-consumable-commodity-pricing):</td>

<td> </td>

<td valign="top">[Fixing Lot Prices](#Fixing-Lot-Prices)</td>

</tr>

<tr>

<td></td>

<td valign="top">[credits and debits](#index-credits-and-debits):</td>

<td> </td>

<td valign="top">[Stating where money goes](#Stating-where-money-goes)</td>

</tr>

<tr>

<td></td>

<td valign="top">[csv exporting](#index-csv-exporting):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[csv importing](#index-csv-importing):</td>

<td> </td>

<td valign="top">[Converting from other formats](#Converting-from-other-formats)</td>

</tr>

<tr>

<td></td>

<td valign="top">[csv importing](#index-csv-importing-1):</td>

<td> </td>

<td valign="top">[The `convert` command](#The-convert-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[currency](#index-currency):</td>

<td> </td>

<td valign="top">[Currency and Commodities](#Currency-and-Commodities)</td>

</tr>

<tr>

<td></td>

<td valign="top">[currency symbol display on windows](#index-currency-symbol-display-on-windows):</td>

<td> </td>

<td valign="top">[Using the Windows Command-Line](#Using-the-Windows-Command_002dLine)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-D">D</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[debts are liabilities](#index-debts-are-liabilities):</td>

<td> </td>

<td valign="top">[Assets and Liabilities](#Assets-and-Liabilities)</td>

</tr>

<tr>

<td></td>

<td valign="top">[depth_spacer](#index-depth_005fspacer):</td>

<td> </td>

<td valign="top">[Asset Allocation](#Asset-Allocation)</td>

</tr>

<tr>

<td></td>

<td valign="top">[display_total](#index-display_005ftotal):</td>

<td> </td>

<td valign="top">[Asset Allocation](#Asset-Allocation)</td>

</tr>

<tr>

<td></td>

<td valign="top">[double-entry accounting](#index-double_002dentry-accounting):</td>

<td> </td>

<td valign="top">[Accounting with Ledger](#Accounting-with-Ledger)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-E">E</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[effective date of invoice](#index-effective-date-of-invoice):</td>

<td> </td>

<td valign="top">[Effective Dates](#Effective-Dates)</td>

</tr>

<tr>

<td></td>

<td valign="top">[effective dates](#index-effective-dates):</td>

<td> </td>

<td valign="top">[Effective Dates](#Effective-Dates)</td>

</tr>

<tr>

<td></td>

<td valign="top">[Euro conversion](#index-Euro-conversion):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-F">F</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[FIFO/LIFO](#index-FIFO_002fLIFO):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[fixated prices](#index-fixated-prices):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[fixing lot prices](#index-fixing-lot-prices):</td>

<td> </td>

<td valign="top">[Fixing Lot Prices](#Fixing-Lot-Prices)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-G">G</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[Gnuplot](#index-Gnuplot):</td>

<td> </td>

<td valign="top">[Visualizing with Gnuplot](#Visualizing-with-Gnuplot)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-H">H</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[historical prices](#index-historical-prices):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-I">I</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[income is negative](#index-income-is-negative):</td>

<td> </td>

<td valign="top">[Stating where money goes](#Stating-where-money-goes)</td>

</tr>

<tr>

<td></td>

<td valign="top">[initial equity](#index-initial-equity):</td>

<td> </td>

<td valign="top">[Starting up](#Starting-up)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-J">J</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[journals](#index-journals):</td>

<td> </td>

<td valign="top">[Start a Journal File](#Start-a-Journal-File)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-L">L</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[LIFO/FIFO](#index-LIFO_002fFIFO):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[limit by payees](#index-limit-by-payees):</td>

<td> </td>

<td valign="top">[Controlling the Accounts and Payees](#Controlling-the-Accounts-and-Payees)</td>

</tr>

<tr>

<td></td>

<td valign="top">[limiting by accounts](#index-limiting-by-accounts):</td>

<td> </td>

<td valign="top">[Register Report](#Register-Report)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-M">M</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[meaning of account](#index-meaning-of-account):</td>

<td> </td>

<td valign="top">[Fat-free Accounting](#Fat_002dfree-Accounting)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-N">N</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[naming accounts](#index-naming-accounts):</td>

<td> </td>

<td valign="top">[Structuring your Accounts](#Structuring-your-Accounts)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-O">O</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[opening balance](#index-opening-balance):</td>

<td> </td>

<td valign="top">[Starting up](#Starting-up)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-P">P</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[parent.total](#index-parent_002etotal):</td>

<td> </td>

<td valign="top">[Asset Allocation](#Asset-Allocation)</td>

</tr>

<tr>

<td></td>

<td valign="top">[Payee metadata tag](#index-Payee-metadata-tag):</td>

<td> </td>

<td valign="top">[Payee metadata tag](#Payee-metadata-tag)</td>

</tr>

<tr>

<td></td>

<td valign="top">[periodic transaction](#index-periodic-transaction):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td></td>

<td valign="top">[plotting](#index-plotting):</td>

<td> </td>

<td valign="top">[Visualizing with Gnuplot](#Visualizing-with-Gnuplot)</td>

</tr>

<tr>

<td></td>

<td valign="top">[posting format details](#index-posting-format-details):</td>

<td> </td>

<td valign="top">[The Most Basic Entry](#The-Most-Basic-Entry)</td>

</tr>

<tr>

<td></td>

<td valign="top">[postings](#index-postings):</td>

<td> </td>

<td valign="top">[Fat-free Accounting](#Fat_002dfree-Accounting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[pre-commands](#index-pre_002dcommands):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[pre-declare account](#index-pre_002ddeclare-account):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[pre-declare commodity](#index-pre_002ddeclare-commodity):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[pre-declare tag](#index-pre_002ddeclare-tag):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-R">R</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[register report](#index-register-report):</td>

<td> </td>

<td valign="top">[Register Report](#Register-Report)</td>

</tr>

<tr>

<td></td>

<td valign="top">[reimbursable expense tracking](#index-reimbursable-expense-tracking):</td>

<td> </td>

<td valign="top">[Tracking reimbursable expenses](#Tracking-reimbursable-expenses)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-S">S</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[spaces in postings](#index-spaces-in-postings):</td>

<td> </td>

<td valign="top">[The Most Basic Entry](#The-Most-Basic-Entry)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-T">T</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[tags](#index-tags):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td></td>

<td valign="top">[transaction, automated](#index-transaction_002c-automated):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td></td>

<td valign="top">[transaction, periodic](#index-transaction_002c-periodic):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td></td>

<td valign="top">[tutorial](#index-tutorial):</td>

<td> </td>

<td valign="top">[Ledger Tutorial](#Ledger-Tutorial)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-U">U</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[uncommoditized amounts](#index-uncommoditized-amounts):</td>

<td> </td>

<td valign="top">[Integer Amounts](#Integer-Amounts)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Concepts-Index_cp_letter-W">W</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[why is income negative](#index-why-is-income-negative):</td>

<td> </td>

<td valign="top">[Stating where money goes](#Stating-where-money-goes)</td>

</tr>

<tr>

<td></td>

<td valign="top">[windows cmd.exe](#index-windows-cmd_002eexe):</td>

<td> </td>

<td valign="top">[Using the Windows Command-Line](#Using-the-Windows-Command_002dLine)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

</tbody>

</table>

<table>

<tbody>

<tr>

<th valign="top">Jump to:  </th>

<td>[**A**](#Concepts-Index_cp_letter-A)   [**B**](#Concepts-Index_cp_letter-B)   [**C**](#Concepts-Index_cp_letter-C)   [**D**](#Concepts-Index_cp_letter-D)   [**E**](#Concepts-Index_cp_letter-E)   [**F**](#Concepts-Index_cp_letter-F)   [**G**](#Concepts-Index_cp_letter-G)   [**H**](#Concepts-Index_cp_letter-H)   [**I**](#Concepts-Index_cp_letter-I)   [**J**](#Concepts-Index_cp_letter-J)   [**L**](#Concepts-Index_cp_letter-L)   [**M**](#Concepts-Index_cp_letter-M)   [**N**](#Concepts-Index_cp_letter-N)   [**O**](#Concepts-Index_cp_letter-O)   [**P**](#Concepts-Index_cp_letter-P)   [**R**](#Concepts-Index_cp_letter-R)   [**S**](#Concepts-Index_cp_letter-S)   [**T**](#Concepts-Index_cp_letter-T)   [**U**](#Concepts-Index_cp_letter-U)   [**W**](#Concepts-Index_cp_letter-W)  </td>

</tr>

</tbody>

</table>

* * *

<a name="Commands-_0026-Options-Index"></a>

<div class="header">

Previous: [Concepts Index](#Concepts-Index), Up: [Top](#Top)   [[Contents](#SEC_Contents "Table of contents")][[Index](#Concepts-Index "Index")]

</div>

<a name="Commands-_0026-Options-Index-1"></a>

## Commands & Options Index

<table>

<tbody>

<tr>

<th valign="top">Jump to:  </th>

<td>[**-**](#Commands-_0026-Options-Index_fn_symbol-1)   [**=**](#Commands-_0026-Options-Index_fn_symbol-2)   [**~**](#Commands-_0026-Options-Index_fn_symbol-3)    
[**A**](#Commands-_0026-Options-Index_fn_letter-A)   [**B**](#Commands-_0026-Options-Index_fn_letter-B)   [**C**](#Commands-_0026-Options-Index_fn_letter-C)   [**D**](#Commands-_0026-Options-Index_fn_letter-D)   [**E**](#Commands-_0026-Options-Index_fn_letter-E)   [**F**](#Commands-_0026-Options-Index_fn_letter-F)   [**G**](#Commands-_0026-Options-Index_fn_letter-G)   [**H**](#Commands-_0026-Options-Index_fn_letter-H)   [**I**](#Commands-_0026-Options-Index_fn_letter-I)   [**J**](#Commands-_0026-Options-Index_fn_letter-J)   [**L**](#Commands-_0026-Options-Index_fn_letter-L)   [**M**](#Commands-_0026-Options-Index_fn_letter-M)   [**N**](#Commands-_0026-Options-Index_fn_letter-N)   [**O**](#Commands-_0026-Options-Index_fn_letter-O)   [**P**](#Commands-_0026-Options-Index_fn_letter-P)   [**Q**](#Commands-_0026-Options-Index_fn_letter-Q)   [**R**](#Commands-_0026-Options-Index_fn_letter-R)   [**S**](#Commands-_0026-Options-Index_fn_letter-S)   [**T**](#Commands-_0026-Options-Index_fn_letter-T)   [**U**](#Commands-_0026-Options-Index_fn_letter-U)   [**V**](#Commands-_0026-Options-Index_fn_letter-V)   [**X**](#Commands-_0026-Options-Index_fn_letter-X)   [**Y**](#Commands-_0026-Options-Index_fn_letter-Y)  </td>

</tr>

</tbody>

</table>

<table class="index-fn" border="0">

<tbody>

<tr>

<td></td>

<th align="left">Index Entry</th>

<td> </td>

<th align="left">Section</th>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_symbol-1">-</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`-%`](#index-_002d_0025):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-%`](#index-_002d_0025-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-%`](#index-_002d_0025-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--abbrev-len <var>INT</var>`](#index-_002d_002dabbrev_002dlen-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--account <var>STR</var>`](#index-_002d_002daccount-STR):</td>

<td> </td>

<td valign="top">[The `convert` command](#The-convert-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--account <var>STR</var>`](#index-_002d_002daccount-STR-1):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--account <var>STR</var>`](#index-_002d_002daccount-STR-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--account <var>STR</var>`](#index-_002d_002daccount-STR-3):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--account-width <var>INT</var>`](#index-_002d_002daccount_002dwidth-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--actual`](#index-_002d_002dactual):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--actual`](#index-_002d_002dactual-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--actual`](#index-_002d_002dactual-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--actual-dates`](#index-_002d_002dactual_002ddates):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--add-budget`](#index-_002d_002dadd_002dbudget):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--add-budget`](#index-_002d_002dadd_002dbudget-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--add-budget`](#index-_002d_002dadd_002dbudget-2):</td>

<td> </td>

<td valign="top">[Budgeting](#Budgeting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount <var>EXPR</var>`](#index-_002d_002damount-EXPR):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount <var>EXPR</var>`](#index-_002d_002damount-EXPR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount <var>EXPR</var>`](#index-_002d_002damount-EXPR-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount <var>EXPR</var>`](#index-_002d_002damount-EXPR-3):</td>

<td> </td>

<td valign="top">[Variables](#Variables)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount <var>EXPR</var>`](#index-_002d_002damount-EXPR-4):</td>

<td> </td>

<td valign="top">[Format Expressions](#Format-Expressions)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount-data`](#index-_002d_002damount_002ddata):</td>

<td> </td>

<td valign="top">[Visualizing with Gnuplot](#Visualizing-with-Gnuplot)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount-data`](#index-_002d_002damount_002ddata-1):</td>

<td> </td>

<td valign="top">[The `register` command](#The-register-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount-data`](#index-_002d_002damount_002ddata-2):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount-data`](#index-_002d_002damount_002ddata-3):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount-data`](#index-_002d_002damount_002ddata-4):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--amount-width <var>INT</var>`](#index-_002d_002damount_002dwidth-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--anon`](#index-_002d_002danon):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--anon`](#index-_002d_002danon-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--ansi`](#index-_002d_002dansi):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--args-only`](#index-_002d_002dargs_002donly):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--args-only`](#index-_002d_002dargs_002donly-1):</td>

<td> </td>

<td valign="top">[Debug Options](#Debug-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--auto-match`](#index-_002d_002dauto_002dmatch):</td>

<td> </td>

<td valign="top">[The `convert` command](#The-convert-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--auto-match`](#index-_002d_002dauto_002dmatch-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--aux-date`](#index-_002d_002daux_002ddate):</td>

<td> </td>

<td valign="top">[Auxiliary dates](#Auxiliary-dates)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--aux-date`](#index-_002d_002daux_002ddate-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--average`](#index-_002d_002daverage):</td>

<td> </td>

<td valign="top">[`prices` and `pricedb` commands](#prices-and-pricedb-commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--average`](#index-_002d_002daverage-1):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--average`](#index-_002d_002daverage-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--average`](#index-_002d_002daverage-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--balance-format <var>FORMAT_STRING</var>`](#index-_002d_002dbalance_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--balance-format <var>FORMAT_STRING</var>`](#index-_002d_002dbalance_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--balance-format <var>FORMAT_STRING</var>`](#index-_002d_002dbalance_002dformat-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--balance-format <var>FORMAT_STRING</var>`](#index-_002d_002dbalance_002dformat-FORMAT_005fSTRING-3):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--balance-format <var>FORMAT_STRING</var>`](#index-_002d_002dbalance_002dformat-FORMAT_005fSTRING-4):</td>

<td> </td>

<td valign="top">[Balance format](#Balance-format)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--base`](#index-_002d_002dbase):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--basis`](#index-_002d_002dbasis):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--basis`](#index-_002d_002dbasis-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--basis`](#index-_002d_002dbasis-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--basis`](#index-_002d_002dbasis-3):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--basis`](#index-_002d_002dbasis-4):</td>

<td> </td>

<td valign="top">[Primary commodities](#Primary-commodities)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--begin <var>DATE</var>`](#index-_002d_002dbegin-DATE):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--begin <var>DATE</var>`](#index-_002d_002dbegin-DATE-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--begin <var>DATE</var>`](#index-_002d_002dbegin-DATE-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--bold-if <var>VEXPR</var>`](#index-_002d_002dbold_002dif-VEXPR):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--budget`](#index-_002d_002dbudget):</td>

<td> </td>

<td valign="top">[Periodic Transactions](#Periodic-Transactions)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--budget`](#index-_002d_002dbudget-1):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--budget`](#index-_002d_002dbudget-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--budget`](#index-_002d_002dbudget-3):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--budget`](#index-_002d_002dbudget-4):</td>

<td> </td>

<td valign="top">[Budgeting](#Budgeting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--budget-format <var>FORMAT_STRING</var>`](#index-_002d_002dbudget_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--budget-format <var>FORMAT_STRING</var>`](#index-_002d_002dbudget_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--by-payee`](#index-_002d_002dby_002dpayee):</td>

<td> </td>

<td valign="top">[Working with multiple funds and accounts](#Working-with-multiple-funds-and-accounts)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--by-payee`](#index-_002d_002dby_002dpayee-1):</td>

<td> </td>

<td valign="top">[Payee metadata tag](#Payee-metadata-tag)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--by-payee`](#index-_002d_002dby_002dpayee-2):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--by-payee`](#index-_002d_002dby_002dpayee-3):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--by-payee`](#index-_002d_002dby_002dpayee-4):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--by-payee`](#index-_002d_002dby_002dpayee-5):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--change`](#index-_002d_002dchange):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--check-payees`](#index-_002d_002dcheck_002dpayees):</td>

<td> </td>

<td valign="top">[Error Checking and Calculation Options](#Error-Checking-and-Calculation-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--check-payees`](#index-_002d_002dcheck_002dpayees-1):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--cleared`](#index-_002d_002dcleared):</td>

<td> </td>

<td valign="top">[Transaction state](#Transaction-state)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--cleared`](#index-_002d_002dcleared-1):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--cleared`](#index-_002d_002dcleared-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--cleared`](#index-_002d_002dcleared-3):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--cleared-format <var>FORMAT_STRING</var>`](#index-_002d_002dcleared_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--cleared-format <var>FORMAT_STRING</var>`](#index-_002d_002dcleared_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--cleared-format <var>FORMAT_STRING</var>`](#index-_002d_002dcleared_002dformat-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--collapse`](#index-_002d_002dcollapse):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--collapse`](#index-_002d_002dcollapse-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--collapse`](#index-_002d_002dcollapse-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--collapse-if-zero`](#index-_002d_002dcollapse_002dif_002dzero):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--color`](#index-_002d_002dcolor):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--columns <var>INT</var>`](#index-_002d_002dcolumns-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--cost`](#index-_002d_002dcost):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--count`](#index-_002d_002dcount):</td>

<td> </td>

<td valign="top">[Reports about your Journals](#Reports-about-your-Journals)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--count`](#index-_002d_002dcount-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--csv-format <var>FORMAT_STRING</var>`](#index-_002d_002dcsv_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--csv-format <var>FORMAT_STRING</var>`](#index-_002d_002dcsv_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--csv-format <var>FORMAT_STRING</var>`](#index-_002d_002dcsv_002dformat-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--current`](#index-_002d_002dcurrent):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--current`](#index-_002d_002dcurrent-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--current`](#index-_002d_002dcurrent-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--daily`](#index-_002d_002ddaily):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--daily`](#index-_002d_002ddaily-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--date <var>EXPR</var>`](#index-_002d_002ddate-EXPR):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--date-format <var>DATE_FORMAT</var>`](#index-_002d_002ddate_002dformat-DATE_005fFORMAT):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--date-format <var>DATE_FORMAT</var>`](#index-_002d_002ddate_002dformat-DATE_005fFORMAT-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--date-format <var>DATE_FORMAT</var>`](#index-_002d_002ddate_002dformat-DATE_005fFORMAT-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--date-width <var>INT</var>`](#index-_002d_002ddate_002dwidth-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--datetime-format <var>DATETIME_FORMAT</var>`](#index-_002d_002ddatetime_002dformat-DATETIME_005fFORMAT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--day-break`](#index-_002d_002dday_002dbreak):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--day-break`](#index-_002d_002dday_002dbreak-1):</td>

<td> </td>

<td valign="top">[Time Keeping](#Time-Keeping)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--days-of-week`](#index-_002d_002ddays_002dof_002dweek):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--dc`](#index-_002d_002ddc):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--dc`](#index-_002d_002ddc-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--debug <var>CODE</var>`](#index-_002d_002ddebug-CODE):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--debug <var>CODE</var>`](#index-_002d_002ddebug-CODE-1):</td>

<td> </td>

<td valign="top">[Debug Options](#Debug-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--decimal-comma`](#index-_002d_002ddecimal_002dcomma):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--depth <var>INT</var>`](#index-_002d_002ddepth-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--detail`](#index-_002d_002ddetail):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--deviation`](#index-_002d_002ddeviation):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--deviation`](#index-_002d_002ddeviation-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--deviation`](#index-_002d_002ddeviation-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--display <var>EXPR</var>`](#index-_002d_002ddisplay-EXPR):</td>

<td> </td>

<td valign="top">[Reporting monthly expenses](#Reporting-monthly-expenses)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--display <var>EXPR</var>`](#index-_002d_002ddisplay-EXPR-1):</td>

<td> </td>

<td valign="top">[Visualizing with Gnuplot](#Visualizing-with-Gnuplot)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--display <var>EXPR</var>`](#index-_002d_002ddisplay-EXPR-2):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--display <var>EXPR</var>`](#index-_002d_002ddisplay-EXPR-3):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--display <var>EXPR</var>`](#index-_002d_002ddisplay-EXPR-4):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--display <var>EXPR</var>`](#index-_002d_002ddisplay-EXPR-5):</td>

<td> </td>

<td valign="top">[Value Expressions](#Value-Expressions)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--display-amount <var>EXPR</var>`](#index-_002d_002ddisplay_002damount-EXPR):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--display-total <var>EXPR</var>`](#index-_002d_002ddisplay_002dtotal-EXPR):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--dow`](#index-_002d_002ddow):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--dow`](#index-_002d_002ddow-1):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--dow`](#index-_002d_002ddow-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--dow`](#index-_002d_002ddow-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--download`](#index-_002d_002ddownload):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--download`](#index-_002d_002ddownload-1):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--download`](#index-_002d_002ddownload-2):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--download`](#index-_002d_002ddownload-3):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--effective`](#index-_002d_002deffective):</td>

<td> </td>

<td valign="top">[Effective Dates](#Effective-Dates)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--effective`](#index-_002d_002deffective-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--empty`](#index-_002d_002dempty):</td>

<td> </td>

<td valign="top">[Balancing transactions](#Balancing-transactions)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--empty`](#index-_002d_002dempty-1):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--empty`](#index-_002d_002dempty-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--empty`](#index-_002d_002dempty-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--end <var>DATE</var>`](#index-_002d_002dend-DATE):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--end <var>DATE</var>`](#index-_002d_002dend-DATE-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--end <var>DATE</var>`](#index-_002d_002dend-DATE-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--equity`](#index-_002d_002dequity):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--exact`](#index-_002d_002dexact):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--exchange <var>COMMODITY</var>`](#index-_002d_002dexchange-COMMODITY):</td>

<td> </td>

<td valign="top">[Complete control over commodity pricing](#Complete-control-over-commodity-pricing)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--exchange <var>COMMODITY</var>`](#index-_002d_002dexchange-COMMODITY-1):</td>

<td> </td>

<td valign="top">[Primary and secondary commodities](#Primary-and-secondary-commodities)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--exchange <var>COMMODITY</var>`](#index-_002d_002dexchange-COMMODITY-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--exchange <var>COMMODITY</var>`](#index-_002d_002dexchange-COMMODITY-3):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--exchange <var>COMMODITY</var>`](#index-_002d_002dexchange-COMMODITY-4):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--explicit`](#index-_002d_002dexplicit):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--file <var>FILE</var>`](#index-_002d_002dfile-FILE):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--file <var>FILE</var>`](#index-_002d_002dfile-FILE-1):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--file <var>FILE</var>`](#index-_002d_002dfile-FILE-2):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--first <var>INT</var>`](#index-_002d_002dfirst-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--flat`](#index-_002d_002dflat):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--force-color`](#index-_002d_002dforce_002dcolor):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--force-pager`](#index-_002d_002dforce_002dpager):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--forecast <var>VEXPR</var>`](#index-_002d_002dforecast-VEXPR):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--forecast <var>VEXPR</var>`](#index-_002d_002dforecast-VEXPR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--forecast <var>VEXPR</var>`](#index-_002d_002dforecast-VEXPR-2):</td>

<td> </td>

<td valign="top">[Forecasting](#Forecasting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--forecast-while <var>VEXPR</var>`](#index-_002d_002dforecast_002dwhile-VEXPR):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--forecast-while <var>VEXPR</var>`](#index-_002d_002dforecast_002dwhile-VEXPR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--forecast-years <var>INT</var>`](#index-_002d_002dforecast_002dyears-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--format <var>FORMAT_STRING</var>`](#index-_002d_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--format <var>FORMAT_STRING</var>`](#index-_002d_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--format <var>FORMAT_STRING</var>`](#index-_002d_002dformat-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--format <var>FORMAT_STRING</var>`](#index-_002d_002dformat-FORMAT_005fSTRING-3):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--format <var>FORMAT_STRING</var>`](#index-_002d_002dformat-FORMAT_005fSTRING-4):</td>

<td> </td>

<td valign="top">[Balance format](#Balance-format)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--gain`](#index-_002d_002dgain):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--gain`](#index-_002d_002dgain-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--gain`](#index-_002d_002dgain-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--generated`](#index-_002d_002dgenerated):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--group-by <var>EXPR</var>`](#index-_002d_002dgroup_002dby-EXPR):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--group-title-format <var>FORMAT_STRING</var>`](#index-_002d_002dgroup_002dtitle_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--head <var>INT</var>`](#index-_002d_002dhead-INT):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--head <var>INT</var>`](#index-_002d_002dhead-INT-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--head <var>INT</var>`](#index-_002d_002dhead-INT-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--help`](#index-_002d_002dhelp):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--help`](#index-_002d_002dhelp-1):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--help`](#index-_002d_002dhelp-2):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--historical`](#index-_002d_002dhistorical):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--historical`](#index-_002d_002dhistorical-1):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--immediate`](#index-_002d_002dimmediate):</td>

<td> </td>

<td valign="top">[Error Checking and Calculation Options](#Error-Checking-and-Calculation-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--immediate`](#index-_002d_002dimmediate-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--import <var>FILE</var>`](#index-_002d_002dimport-FILE):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--init-file <var>FILE</var>`](#index-_002d_002dinit_002dfile-FILE):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--init-file <var>FILE</var>`](#index-_002d_002dinit_002dfile-FILE-1):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--init-file <var>FILE</var>`](#index-_002d_002dinit_002dfile-FILE-2):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--inject`](#index-_002d_002dinject):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--input-date-format <var>DATE_FORMAT</var>`](#index-_002d_002dinput_002ddate_002dformat-DATE_005fFORMAT):</td>

<td> </td>

<td valign="top">[The `convert` command](#The-convert-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--input-date-format <var>DATE_FORMAT</var>`](#index-_002d_002dinput_002ddate_002dformat-DATE_005fFORMAT-1):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--invert`](#index-_002d_002dinvert):</td>

<td> </td>

<td valign="top">[The `convert` command](#The-convert-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--invert`](#index-_002d_002dinvert-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--last <var>INT</var>`](#index-_002d_002dlast-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--leeway <var>INT</var>`](#index-_002d_002dleeway-INT):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--leeway <var>INT</var>`](#index-_002d_002dleeway-INT-1):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--leeway <var>INT</var>`](#index-_002d_002dleeway-INT-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--limit <var>EXPR</var>`](#index-_002d_002dlimit-EXPR):</td>

<td> </td>

<td valign="top">[Controlling the Accounts and Payees](#Controlling-the-Accounts-and-Payees)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--limit <var>EXPR</var>`](#index-_002d_002dlimit-EXPR-1):</td>

<td> </td>

<td valign="top">[Visualizing with Gnuplot](#Visualizing-with-Gnuplot)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--limit <var>EXPR</var>`](#index-_002d_002dlimit-EXPR-2):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--limit <var>EXPR</var>`](#index-_002d_002dlimit-EXPR-3):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--limit <var>EXPR</var>`](#index-_002d_002dlimit-EXPR-4):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--limit <var>EXPR</var>`](#index-_002d_002dlimit-EXPR-5):</td>

<td> </td>

<td valign="top">[Value Expressions](#Value-Expressions)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lot-dates`](#index-_002d_002dlot_002ddates):</td>

<td> </td>

<td valign="top">[Lot dates](#Lot-dates)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lot-dates`](#index-_002d_002dlot_002ddates-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lot-notes`](#index-_002d_002dlot_002dnotes):</td>

<td> </td>

<td valign="top">[Lot notes](#Lot-notes)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lot-notes`](#index-_002d_002dlot_002dnotes-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lot-prices`](#index-_002d_002dlot_002dprices):</td>

<td> </td>

<td valign="top">[Commodity prices](#Commodity-prices)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lot-prices`](#index-_002d_002dlot_002dprices-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lot-prices`](#index-_002d_002dlot_002dprices-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lot-prices`](#index-_002d_002dlot_002dprices-3):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lot-tags`](#index-_002d_002dlot_002dtags):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lots`](#index-_002d_002dlots):</td>

<td> </td>

<td valign="top">[Lot notes](#Lot-notes)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lots`](#index-_002d_002dlots-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lots`](#index-_002d_002dlots-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--lots-actual`](#index-_002d_002dlots_002dactual):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--market`](#index-_002d_002dmarket):</td>

<td> </td>

<td valign="top">[Commodities and Currencies](#Commodities-and-Currencies)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--market`](#index-_002d_002dmarket-1):</td>

<td> </td>

<td valign="top">[Complete control over commodity pricing](#Complete-control-over-commodity-pricing)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--market`](#index-_002d_002dmarket-2):</td>

<td> </td>

<td valign="top">[Primary and secondary commodities](#Primary-and-secondary-commodities)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--market`](#index-_002d_002dmarket-3):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--market`](#index-_002d_002dmarket-4):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--market`](#index-_002d_002dmarket-5):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--market`](#index-_002d_002dmarket-6):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--market`](#index-_002d_002dmarket-7):</td>

<td> </td>

<td valign="top">[Primary commodities](#Primary-commodities)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--master-account <var>STR</var>`](#index-_002d_002dmaster_002daccount-STR):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--meta <var>TAG</var>`](#index-_002d_002dmeta-TAG):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--meta-width <var>INT</var>`](#index-_002d_002dmeta_002dwidth-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--monthly`](#index-_002d_002dmonthly):</td>

<td> </td>

<td valign="top">[Reporting monthly expenses](#Reporting-monthly-expenses)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--monthly`](#index-_002d_002dmonthly-1):</td>

<td> </td>

<td valign="top">[Generating a monthly register](#Generating-a-monthly-register)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--monthly`](#index-_002d_002dmonthly-2):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--monthly`](#index-_002d_002dmonthly-3):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--monthly`](#index-_002d_002dmonthly-4):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--monthly`](#index-_002d_002dmonthly-5):</td>

<td> </td>

<td valign="top">[Budgeting](#Budgeting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-aliases`](#index-_002d_002dno_002daliases):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-aliases`](#index-_002d_002dno_002daliases-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-color`](#index-_002d_002dno_002dcolor):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-pager`](#index-_002d_002dno_002dpager):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-pager`](#index-_002d_002dno_002dpager-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-pager`](#index-_002d_002dno_002dpager-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-revalued`](#index-_002d_002dno_002drevalued):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-rounding`](#index-_002d_002dno_002drounding):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-titles`](#index-_002d_002dno_002dtitles):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--no-total`](#index-_002d_002dno_002dtotal):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--now <var>DATE</var>`](#index-_002d_002dnow-DATE):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--now <var>DATE</var>`](#index-_002d_002dnow-DATE-1):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--now <var>DATE</var>`](#index-_002d_002dnow-DATE-2):</td>

<td> </td>

<td valign="top">[Date Functions](#Date-Functions)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--only <var>FIXME</var>`](#index-_002d_002donly-FIXME):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--options`](#index-_002d_002doptions):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--output <var>FILE</var>`](#index-_002d_002doutput-FILE):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--output <var>FILE</var>`](#index-_002d_002doutput-FILE-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--output <var>FILE</var>`](#index-_002d_002doutput-FILE-2):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pager <var>FILE</var>`](#index-_002d_002dpager-FILE):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pager <var>FILE</var>`](#index-_002d_002dpager-FILE-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pager <var>FILE</var>`](#index-_002d_002dpager-FILE-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--payee <var>VEXPR</var>`](#index-_002d_002dpayee-VEXPR):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--payee-width <var>INT</var>`](#index-_002d_002dpayee_002dwidth-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--payee=code`](#index-_002d_002dpayee_003dcode):</td>

<td> </td>

<td valign="top">[Working with multiple funds and accounts](#Working-with-multiple-funds-and-accounts)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pedantic`](#index-_002d_002dpedantic):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pedantic`](#index-_002d_002dpedantic-1):</td>

<td> </td>

<td valign="top">[Error Checking and Calculation Options](#Error-Checking-and-Calculation-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pedantic`](#index-_002d_002dpedantic-2):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pending`](#index-_002d_002dpending):</td>

<td> </td>

<td valign="top">[Transaction state](#Transaction-state)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pending`](#index-_002d_002dpending-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--percent`](#index-_002d_002dpercent):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--percent`](#index-_002d_002dpercent-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--percent`](#index-_002d_002dpercent-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--period <var>PERIOD_EXPRESSION</var>`](#index-_002d_002dperiod-PERIOD_005fEXPRESSION):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--period <var>PERIOD_EXPRESSION</var>`](#index-_002d_002dperiod-PERIOD_005fEXPRESSION-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--period <var>PERIOD_EXPRESSION</var>`](#index-_002d_002dperiod-PERIOD_005fEXPRESSION-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--period <var>PERIOD_EXPRESSION</var>`](#index-_002d_002dperiod-PERIOD_005fEXPRESSION-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--period-sort <var>VEXPR</var>`](#index-_002d_002dperiod_002dsort-VEXPR):</td>

<td> </td>

<td valign="top">[Reporting monthly expenses](#Reporting-monthly-expenses)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--period-sort <var>VEXPR</var>`](#index-_002d_002dperiod_002dsort-VEXPR-1):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--period-sort <var>VEXPR</var>`](#index-_002d_002dperiod_002dsort-VEXPR-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--period-sort <var>VEXPR</var>`](#index-_002d_002dperiod_002dsort-VEXPR-3):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--permissive`](#index-_002d_002dpermissive):</td>

<td> </td>

<td valign="top">[Balance verification](#Balance-verification)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--permissive`](#index-_002d_002dpermissive-1):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pivot <var>TAG</var>`](#index-_002d_002dpivot-TAG):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pivot <var>TAG</var>`](#index-_002d_002dpivot-TAG-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pivot <var>TAG</var>`](#index-_002d_002dpivot-TAG-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--plot-amount-format <var>FORMAT_STRING</var>`](#index-_002d_002dplot_002damount_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--plot-amount-format <var>FORMAT_STRING</var>`](#index-_002d_002dplot_002damount_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--plot-amount-format <var>FORMAT_STRING</var>`](#index-_002d_002dplot_002damount_002dformat-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--plot-amount-format <var>FORMAT_STRING</var>`](#index-_002d_002dplot_002damount_002dformat-FORMAT_005fSTRING-3):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--plot-total-format <var>FORMAT_STRING</var>`](#index-_002d_002dplot_002dtotal_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--plot-total-format <var>FORMAT_STRING</var>`](#index-_002d_002dplot_002dtotal_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--plot-total-format <var>FORMAT_STRING</var>`](#index-_002d_002dplot_002dtotal_002dformat-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--plot-total-format <var>FORMAT_STRING</var>`](#index-_002d_002dplot_002dtotal_002dformat-FORMAT_005fSTRING-3):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--prepend-format <var>FORMAT_STRING</var>`](#index-_002d_002dprepend_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--prepend-width <var>INT</var>`](#index-_002d_002dprepend_002dwidth-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--price`](#index-_002d_002dprice):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--price`](#index-_002d_002dprice-1):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--price-db <var>FILE</var>`](#index-_002d_002dprice_002ddb-FILE):</td>

<td> </td>

<td valign="top">[Commodities and Currencies](#Commodities-and-Currencies)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--price-db <var>FILE</var>`](#index-_002d_002dprice_002ddb-FILE-1):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--price-db <var>FILE</var>`](#index-_002d_002dprice_002ddb-FILE-2):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--price-db <var>FILE</var>`](#index-_002d_002dprice_002ddb-FILE-3):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--price-exp <var>INT</var>`](#index-_002d_002dprice_002dexp-INT):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--price-exp <var>INT</var>`](#index-_002d_002dprice_002dexp-INT-1):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--price-exp <var>INT</var>`](#index-_002d_002dprice_002dexp-INT-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pricedb-format <var>FORMAT_STRING</var>`](#index-_002d_002dpricedb_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pricedb-format <var>FORMAT_STRING</var>`](#index-_002d_002dpricedb_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--pricedb-format <var>FORMAT_STRING</var>`](#index-_002d_002dpricedb_002dformat-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--prices-format <var>FORMAT_STRING</var>`](#index-_002d_002dprices_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--prices-format <var>FORMAT_STRING</var>`](#index-_002d_002dprices_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--prices-format <var>FORMAT_STRING</var>`](#index-_002d_002dprices_002dformat-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--prices-format <var>FORMAT_STRING</var>`](#index-_002d_002dprices_002dformat-FORMAT_005fSTRING-3):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--primary-date`](#index-_002d_002dprimary_002ddate):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--quantity`](#index-_002d_002dquantity):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--quantity`](#index-_002d_002dquantity-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--quantity`](#index-_002d_002dquantity-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--quarterly`](#index-_002d_002dquarterly):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--quarterly`](#index-_002d_002dquarterly-1):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--quarterly`](#index-_002d_002dquarterly-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--raw`](#index-_002d_002draw):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--real`](#index-_002d_002dreal):</td>

<td> </td>

<td valign="top">[Working with multiple funds and accounts](#Working-with-multiple-funds-and-accounts)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--real`](#index-_002d_002dreal-1):</td>

<td> </td>

<td valign="top">[Virtual postings](#Virtual-postings)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--real`](#index-_002d_002dreal-2):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--real`](#index-_002d_002dreal-3):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--real`](#index-_002d_002dreal-4):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--recursive-aliases`](#index-_002d_002drecursive_002daliases):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--register-format <var>FORMAT_STRING</var>`](#index-_002d_002dregister_002dformat-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--register-format <var>FORMAT_STRING</var>`](#index-_002d_002dregister_002dformat-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--register-format <var>FORMAT_STRING</var>`](#index-_002d_002dregister_002dformat-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--register-format <var>FORMAT_STRING</var>`](#index-_002d_002dregister_002dformat-FORMAT_005fSTRING-3):</td>

<td> </td>

<td valign="top">[Format String Basics](#Format-String-Basics)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--related`](#index-_002d_002drelated):</td>

<td> </td>

<td valign="top">[Reporting monthly expenses](#Reporting-monthly-expenses)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--related`](#index-_002d_002drelated-1):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--related`](#index-_002d_002drelated-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--related`](#index-_002d_002drelated-3):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--related-all`](#index-_002d_002drelated_002dall):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--revalued`](#index-_002d_002drevalued):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--revalued-only`](#index-_002d_002drevalued_002donly):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--revalued-total <var>FIXME</var>`](#index-_002d_002drevalued_002dtotal-FIXME):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--rich-data`](#index-_002d_002drich_002ddata):</td>

<td> </td>

<td valign="top">[The `convert` command](#The-convert-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--rich-data`](#index-_002d_002drich_002ddata-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--script <var>FILE</var>`](#index-_002d_002dscript-FILE):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--seed <var>INT</var>`](#index-_002d_002dseed-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--sort <var>VEXPR</var>`](#index-_002d_002dsort-VEXPR):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--sort <var>VEXPR</var>`](#index-_002d_002dsort-VEXPR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--sort <var>VEXPR</var>`](#index-_002d_002dsort-VEXPR-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--sort-all <var>FIXME</var>`](#index-_002d_002dsort_002dall-FIXME):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--sort-xacts <var>VEXPR</var>`](#index-_002d_002dsort_002dxacts-VEXPR):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--start-of-week <var>INT</var>`](#index-_002d_002dstart_002dof_002dweek-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--strict`](#index-_002d_002dstrict):</td>

<td> </td>

<td valign="top">[Keeping it Consistent](#Keeping-it-Consistent)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--strict`](#index-_002d_002dstrict-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--strict`](#index-_002d_002dstrict-2):</td>

<td> </td>

<td valign="top">[Error Checking and Calculation Options](#Error-Checking-and-Calculation-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--strict`](#index-_002d_002dstrict-3):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--subtotal`](#index-_002d_002dsubtotal):</td>

<td> </td>

<td valign="top">[Reporting monthly expenses](#Reporting-monthly-expenses)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--subtotal`](#index-_002d_002dsubtotal-1):</td>

<td> </td>

<td valign="top">[An overall balance summary](#An-overall-balance-summary)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--subtotal`](#index-_002d_002dsubtotal-2):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--subtotal`](#index-_002d_002dsubtotal-3):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--subtotal`](#index-_002d_002dsubtotal-4):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--subtotal`](#index-_002d_002dsubtotal-5):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--tail <var>INT</var>`](#index-_002d_002dtail-INT):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--tail <var>INT</var>`](#index-_002d_002dtail-INT-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--time-colon`](#index-_002d_002dtime_002dcolon):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--time-report`](#index-_002d_002dtime_002dreport):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total <var>VEXPR</var>`](#index-_002d_002dtotal-VEXPR):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total <var>VEXPR</var>`](#index-_002d_002dtotal-VEXPR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total <var>VEXPR</var>`](#index-_002d_002dtotal-VEXPR-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total <var>VEXPR</var>`](#index-_002d_002dtotal-VEXPR-3):</td>

<td> </td>

<td valign="top">[Variables](#Variables)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total <var>VEXPR</var>`](#index-_002d_002dtotal-VEXPR-4):</td>

<td> </td>

<td valign="top">[Format Expressions](#Format-Expressions)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total-data`](#index-_002d_002dtotal_002ddata):</td>

<td> </td>

<td valign="top">[Visualizing with Gnuplot](#Visualizing-with-Gnuplot)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total-data`](#index-_002d_002dtotal_002ddata-1):</td>

<td> </td>

<td valign="top">[The `register` command](#The-register-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total-data`](#index-_002d_002dtotal_002ddata-2):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total-data`](#index-_002d_002dtotal_002ddata-3):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total-data`](#index-_002d_002dtotal_002ddata-4):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--total-width <var>INT</var>`](#index-_002d_002dtotal_002dwidth-INT):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--trace <var>INT</var>`](#index-_002d_002dtrace-INT):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--trace <var>INT</var>`](#index-_002d_002dtrace-INT-1):</td>

<td> </td>

<td valign="top">[Debug Options](#Debug-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--truncate <var>CODE</var>`](#index-_002d_002dtruncate-CODE):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--unbudgeted`](#index-_002d_002dunbudgeted):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--unbudgeted`](#index-_002d_002dunbudgeted-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--unbudgeted`](#index-_002d_002dunbudgeted-2):</td>

<td> </td>

<td valign="top">[Budgeting](#Budgeting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--uncleared`](#index-_002d_002duncleared):</td>

<td> </td>

<td valign="top">[Transaction state](#Transaction-state)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--uncleared`](#index-_002d_002duncleared-1):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--uncleared`](#index-_002d_002duncleared-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--uncleared`](#index-_002d_002duncleared-3):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--unrealized`](#index-_002d_002dunrealized):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--unrealized-gains <var>STR</var>`](#index-_002d_002dunrealized_002dgains-STR):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--unrealized-losses <var>STR</var>`](#index-_002d_002dunrealized_002dlosses-STR):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--unround`](#index-_002d_002dunround):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--value-expr <var>VEXPR</var>`](#index-_002d_002dvalue_002dexpr-VEXPR):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--values`](#index-_002d_002dvalues):</td>

<td> </td>

<td valign="top">[`tags`](#tags)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--values`](#index-_002d_002dvalues-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--verbose`](#index-_002d_002dverbose):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--verbose`](#index-_002d_002dverbose-1):</td>

<td> </td>

<td valign="top">[Debug Options](#Debug-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--verify`](#index-_002d_002dverify):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--verify`](#index-_002d_002dverify-1):</td>

<td> </td>

<td valign="top">[Debug Options](#Debug-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--verify-memory`](#index-_002d_002dverify_002dmemory):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--verify-memory`](#index-_002d_002dverify_002dmemory-1):</td>

<td> </td>

<td valign="top">[Debug Options](#Debug-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--version`](#index-_002d_002dversion):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--version`](#index-_002d_002dversion-1):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--version`](#index-_002d_002dversion-2):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--version`](#index-_002d_002dversion-3):</td>

<td> </td>

<td valign="top">[Debug Options](#Debug-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--weekly`](#index-_002d_002dweekly):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--weekly`](#index-_002d_002dweekly-1):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--weekly`](#index-_002d_002dweekly-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--weekly`](#index-_002d_002dweekly-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--wide`](#index-_002d_002dwide):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--wide`](#index-_002d_002dwide-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--wide`](#index-_002d_002dwide-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--yearly`](#index-_002d_002dyearly):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--yearly`](#index-_002d_002dyearly-1):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--yearly`](#index-_002d_002dyearly-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`--yearly`](#index-_002d_002dyearly-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-A`](#index-_002dA):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-A`](#index-_002dA-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-A`](#index-_002dA-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-a <var>STR</var>`](#index-_002da-STR):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-a <var>STR</var>`](#index-_002da-STR-1):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-B`](#index-_002dB):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-B`](#index-_002dB-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-B`](#index-_002dB-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-b <var>DATE</var>`](#index-_002db-DATE):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-b <var>DATE</var>`](#index-_002db-DATE-1):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-c`](#index-_002dc):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-C`](#index-_002dC):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-C`](#index-_002dC-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-c`](#index-_002dc-1):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-C`](#index-_002dC-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-D`](#index-_002dD):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-D`](#index-_002dD-1):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-D`](#index-_002dD-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-D`](#index-_002dD-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-d <var>EXPR</var>`](#index-_002dd-EXPR):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-d <var>EXPR</var>`](#index-_002dd-EXPR-1):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-E`](#index-_002dE):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-E`](#index-_002dE-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-E`](#index-_002dE-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-e <var>DATE</var>`](#index-_002de-DATE):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-e <var>DATE</var>`](#index-_002de-DATE-1):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-f <var>FILE</var>`](#index-_002df-FILE):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-f <var>FILE</var>`](#index-_002df-FILE-1):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-f <var>FILE</var>`](#index-_002df-FILE-2):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-F <var>FORMAT_STRING</var>`](#index-_002dF-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-F <var>FORMAT_STRING</var>`](#index-_002dF-FORMAT_005fSTRING-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-F <var>FORMAT_STRING</var>`](#index-_002dF-FORMAT_005fSTRING-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-G`](#index-_002dG):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-G`](#index-_002dG-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-G`](#index-_002dG-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-h`](#index-_002dh):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-h`](#index-_002dh-1):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-H`](#index-_002dH):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-h`](#index-_002dh-2):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-I`](#index-_002dI):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-i <var>FILE</var>`](#index-_002di-FILE):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-i <var>FILE</var>`](#index-_002di-FILE-1):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-j`](#index-_002dj):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-J`](#index-_002dJ):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-j`](#index-_002dj-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-J`](#index-_002dJ-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-j`](#index-_002dj-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-J`](#index-_002dJ-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-L`](#index-_002dL):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-L`](#index-_002dL-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-L`](#index-_002dL-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-l <var>EXPR</var>`](#index-_002dl-EXPR):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-l <var>EXPR</var>`](#index-_002dl-EXPR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-l <var>EXPR</var>`](#index-_002dl-EXPR-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-M`](#index-_002dM):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-M`](#index-_002dM-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-M`](#index-_002dM-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-n`](#index-_002dn):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-n`](#index-_002dn-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-n`](#index-_002dn-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-O`](#index-_002dO):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-O`](#index-_002dO-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-O`](#index-_002dO-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-o <var>FILE</var>`](#index-_002do-FILE):</td>

<td> </td>

<td valign="top">[Basic Options](#Basic-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-o <var>FILE</var>`](#index-_002do-FILE-1):</td>

<td> </td>

<td valign="top">[Basic options](#Basic-options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-P`](#index-_002dP):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-P`](#index-_002dP-1):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-P`](#index-_002dP-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-P`](#index-_002dP-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-p <var>PERIOD_EXPRESSION</var>`](#index-_002dp-PERIOD_005fEXPRESSION):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-p <var>PERIOD_EXPRESSION</var>`](#index-_002dp-PERIOD_005fEXPRESSION-1):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Q`](#index-_002dQ):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Q`](#index-_002dQ-1):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Q`](#index-_002dQ-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-R`](#index-_002dR):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-r`](#index-_002dr):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-R`](#index-_002dR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-R`](#index-_002dR-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-r`](#index-_002dr-1):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-s`](#index-_002ds):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-s`](#index-_002ds-1):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-s`](#index-_002ds-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-s`](#index-_002ds-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-S <var>VEXPR</var>`](#index-_002dS-VEXPR):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-S <var>VEXPR</var>`](#index-_002dS-VEXPR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-S <var>VEXPR</var>`](#index-_002dS-VEXPR-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-t <var>EXPR</var>`](#index-_002dt-EXPR):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-t <var>EXPR</var>`](#index-_002dt-EXPR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-t <var>EXPR</var>`](#index-_002dt-EXPR-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-T <var>VEXPR</var>`](#index-_002dT-VEXPR):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-T <var>VEXPR</var>`](#index-_002dT-VEXPR-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-T <var>VEXPR</var>`](#index-_002dT-VEXPR-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-U`](#index-_002dU):</td>

<td> </td>

<td valign="top">[Report Filtering](#Report-Filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-U`](#index-_002dU-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-U`](#index-_002dU-2):</td>

<td> </td>

<td valign="top">[Report filtering](#Report-filtering)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-V`](#index-_002dV):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-v`](#index-_002dv):</td>

<td> </td>

<td valign="top">[Global Options](#Global-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-V`](#index-_002dV-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-V`](#index-_002dV-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-v`](#index-_002dv-1):</td>

<td> </td>

<td valign="top">[Debug Options](#Debug-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-W`](#index-_002dW):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-w`](#index-_002dw):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-W`](#index-_002dW-1):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-W`](#index-_002dW-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-W`](#index-_002dW-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-w`](#index-_002dw-1):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-X <var>COMMODITY</var>`](#index-_002dX-COMMODITY):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Y`](#index-_002dY):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Y`](#index-_002dY-1):</td>

<td> </td>

<td valign="top">[Grouping Options](#Grouping-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Y`](#index-_002dY-2):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Y`](#index-_002dY-3):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-y <var>DATE_FORMAT</var>`](#index-_002dy-DATE_005fFORMAT):</td>

<td> </td>

<td valign="top">[Output Customization](#Output-Customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-y <var>DATE_FORMAT</var>`](#index-_002dy-DATE_005fFORMAT-1):</td>

<td> </td>

<td valign="top">[Report Options](#Report-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-y <var>DATE_FORMAT</var>`](#index-_002dy-DATE_005fFORMAT-2):</td>

<td> </td>

<td valign="top">[Output customization](#Output-customization)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Z <var>INT</var>`](#index-_002dZ-INT):</td>

<td> </td>

<td valign="top">[Commodity Reporting](#Commodity-Reporting)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Z <var>INT</var>`](#index-_002dZ-INT-1):</td>

<td> </td>

<td valign="top">[Session Options](#Session-Options)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`-Z <var>INT</var>`](#index-_002dZ-INT-2):</td>

<td> </td>

<td valign="top">[Commodity reporting](#Commodity-reporting)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_symbol-2">=</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`=`](#index-_003d):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_symbol-3">~</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`~`](#index-_007e):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-A">A</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`A`](#index-A):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`abs`](#index-abs):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`account`](#index-account):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`accounts`](#index-accounts):</td>

<td> </td>

<td valign="top">[Keeping it Consistent](#Keeping-it-Consistent)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`accounts`](#index-accounts-1):</td>

<td> </td>

<td valign="top">[`accounts`](#accounts)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`alias`](#index-alias):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`amount_expr`](#index-amount_005fexpr):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`ansify_if`](#index-ansify_005fif):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`apply account`](#index-apply-account):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`apply tag`](#index-apply-tag):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`args`](#index-args):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`assert`](#index-assert):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-B">B</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`b`](#index-b):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`bal`](#index-bal):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`balance`](#index-balance):</td>

<td> </td>

<td valign="top">[Balance Report](#Balance-Report)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`balance`](#index-balance-1):</td>

<td> </td>

<td valign="top">[The `balance` command](#The-balance-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`balance`](#index-balance-2):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`bucket`](#index-bucket-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`bucket`](#index-bucket-2):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-C">C</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`C`](#index-C):</td>

<td> </td>

<td valign="top">[Commodity equivalences](#Commodity-equivalences)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`C`](#index-C-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`capture`](#index-capture):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`ceiling`](#index-ceiling):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`check`](#index-check):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`cleared`](#index-cleared):</td>

<td> </td>

<td valign="top">[Cleared Report](#Cleared-Report)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`comment`](#index-comment):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`comment`](#index-comment-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`commodities`](#index-commodities):</td>

<td> </td>

<td valign="top">[`commodities`](#commodities)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`commodity`](#index-commodity-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`convert`](#index-convert):</td>

<td> </td>

<td valign="top">[The `convert` command](#The-convert-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`csv`](#index-csv):</td>

<td> </td>

<td valign="top">[The `csv` command](#The-csv-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`csv`](#index-csv-1):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-D">D</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`D`](#index-D):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`define`](#index-define):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`draft`](#index-draft):</td>

<td> </td>

<td valign="top">[`xact`](#xact)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-E">E</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`echo`](#index-echo):</td>

<td> </td>

<td valign="top">[`echo`](#echo)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`emacs`](#index-emacs):</td>

<td> </td>

<td valign="top">[The `lisp` command](#The-lisp-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`emacs`](#index-emacs-1):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`end`](#index-end):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`entry`](#index-entry):</td>

<td> </td>

<td valign="top">[`xact`](#xact)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`equity`](#index-equity):</td>

<td> </td>

<td valign="top">[Archiving Previous Years](#Archiving-Previous-Years)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`equity`](#index-equity-1):</td>

<td> </td>

<td valign="top">[The `equity` command](#The-equity-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`equity`](#index-equity-2):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`eval <var>VEXPR</var>`](#index-eval-VEXPR):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`expr`](#index-expr):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`expr <var>VEXPR</var>`](#index-expr-VEXPR):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-F">F</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`fixed`](#index-fixed):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`floor`](#index-floor):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`format`](#index-format):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`format <var>FORMAT_STRING</var>`](#index-format-FORMAT_005fSTRING):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`format_date`](#index-format_005fdate):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`format_datetime`](#index-format_005fdatetime):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-G">G</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`generate`](#index-generate):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`get_at`](#index-get_005fat):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-H">H</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`h`](#index-h):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`help`](#index-help):</td>

<td> </td>

<td valign="top">[Getting help](#Getting-help)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-I">I</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`I`](#index-I):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`i`](#index-i):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`include`](#index-include):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`int`](#index-int):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`is_seq`](#index-is_005fseq):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-J">J</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`join`](#index-join):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`justify`](#index-justify):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-L">L</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`lisp`](#index-lisp):</td>

<td> </td>

<td valign="top">[The `lisp` command](#The-lisp-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`lisp`](#index-lisp-1):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-M">M</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`market`](#index-market):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-N">N</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`N`](#index-N):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`nail_down`](#index-nail_005fdown):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-O">O</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`O`](#index-O):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`o`](#index-o):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`org`](#index-org):</td>

<td> </td>

<td valign="top">[Emacs `org` Mode](#Emacs-org-Mode)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-P">P</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`P`](#index-P):</td>

<td> </td>

<td valign="top">[Transactions and Comments](#Transactions-and-Comments)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`P`](#index-P-1):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`parse <var>VEXPR</var>`](#index-parse-VEXPR):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`payee`](#index-payee):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`payees`](#index-payees):</td>

<td> </td>

<td valign="top">[Payee metadata tag](#Payee-metadata-tag)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`payees`](#index-payees-1):</td>

<td> </td>

<td valign="top">[`payees`](#payees)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`percent`](#index-percent):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`period <var>PERIOD_EXPRESSION</var>`](#index-period-PERIOD_005fEXPRESSION):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`pricedb`](#index-pricedb):</td>

<td> </td>

<td valign="top">[`prices` and `pricedb` commands](#prices-and-pricedb-commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`pricedb`](#index-pricedb-1):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`pricemap`](#index-pricemap):</td>

<td> </td>

<td valign="top">[The `pricemap` command](#The-pricemap-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`prices`](#index-prices):</td>

<td> </td>

<td valign="top">[`prices` and `pricedb` commands](#prices-and-pricedb-commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`prices`](#index-prices-1):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`print`](#index-print):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`print`](#index-print-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`print`](#index-print-2):</td>

<td> </td>

<td valign="top">[Archiving Previous Years](#Archiving-Previous-Years)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`print`](#index-print-3):</td>

<td> </td>

<td valign="top">[The `print` command](#The-print-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`print`](#index-print-4):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`print`](#index-print-5):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-Q">Q</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`quantity`](#index-quantity):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`query`](#index-query):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`quoted`](#index-quoted):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-R">R</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`reg`](#index-reg):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`register`](#index-register):</td>

<td> </td>

<td valign="top">[Register Report](#Register-Report)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`register`](#index-register-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`register`](#index-register-2):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`register`](#index-register-3):</td>

<td> </td>

<td valign="top">[Payee metadata tag](#Payee-metadata-tag)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`register`](#index-register-4):</td>

<td> </td>

<td valign="top">[The `register` command](#The-register-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`register`](#index-register-5):</td>

<td> </td>

<td valign="top">[Generating a monthly register](#Generating-a-monthly-register)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`register`](#index-register-6):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`reload`](#index-reload):</td>

<td> </td>

<td valign="top">[`reload`](#reload)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`round`](#index-round):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`rounded`](#index-rounded):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`roundto`](#index-roundto):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-S">S</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`S`](#index-S):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`script`](#index-script):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`scrub`](#index-scrub):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`select`](#index-select):</td>

<td> </td>

<td valign="top">[`select`](#select)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`should_bold`](#index-should_005fbold):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`source`](#index-source):</td>

<td> </td>

<td valign="top">[`source`](#source)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`stat`](#index-stat):</td>

<td> </td>

<td valign="top">[`stats`](#stats)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`stats`](#index-stats):</td>

<td> </td>

<td valign="top">[`stats`](#stats)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`str`](#index-str):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`strip`](#index-strip):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-T">T</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`tag`](#index-tag):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`tags`](#index-tags-1):</td>

<td> </td>

<td valign="top">[`tags`](#tags)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`template`](#index-template):</td>

<td> </td>

<td valign="top">[Pre-Commands](#Pre_002dCommands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`test`](#index-test):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`top_amount`](#index-top_005famount):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`total_expr`](#index-total_005fexpr):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`to_amount`](#index-to_005famount):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`to_balance`](#index-to_005fbalance):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`to_boolean`](#index-to_005fboolean):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`to_date`](#index-to_005fdate):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`to_datetime`](#index-to_005fdatetime):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`to_int`](#index-to_005fint):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`to_mask`](#index-to_005fmask):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`to_sequence`](#index-to_005fsequence):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`to_string`](#index-to_005fstring):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`trim`](#index-trim):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`truncatedstring`](#index-truncatedstring):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-U">U</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`U`](#index-U):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`unround`](#index-unround):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`unrounded`](#index-unrounded):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-V">V</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`value_date`](#index-value_005fdate):</td>

<td> </td>

<td valign="top">[Miscellaneous](#Miscellaneous)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-X">X</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`xact`](#index-xact):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`xact`](#index-xact-1):</td>

<td> </td>

<td valign="top">[`xact`](#xact)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`xact`](#index-xact-2):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`xml`](#index-xml):</td>

<td> </td>

<td valign="top">[The `xml` command](#The-xml-command)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`xml`](#index-xml-1):</td>

<td> </td>

<td valign="top">[Basic Reporting Commands](#Basic-Reporting-Commands)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

<tr>

<th><a name="Commands-_0026-Options-Index_fn_letter-Y">Y</a></th>

<td></td>

<td></td>

</tr>

<tr>

<td></td>

<td valign="top">[`Y`](#index-Y):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`year`](#index-year):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td></td>

<td valign="top">[`year`](#index-year-1):</td>

<td> </td>

<td valign="top">[Command Directives](#Command-Directives)</td>

</tr>

<tr>

<td colspan="4">

* * *

</td>

</tr>

</tbody>

</table>

<table>

<tbody>

<tr>

<th valign="top">Jump to:  </th>

<td>[**-**](#Commands-_0026-Options-Index_fn_symbol-1)   [**=**](#Commands-_0026-Options-Index_fn_symbol-2)   [**~**](#Commands-_0026-Options-Index_fn_symbol-3)    
[**A**](#Commands-_0026-Options-Index_fn_letter-A)   [**B**](#Commands-_0026-Options-Index_fn_letter-B)   [**C**](#Commands-_0026-Options-Index_fn_letter-C)   [**D**](#Commands-_0026-Options-Index_fn_letter-D)   [**E**](#Commands-_0026-Options-Index_fn_letter-E)   [**F**](#Commands-_0026-Options-Index_fn_letter-F)   [**G**](#Commands-_0026-Options-Index_fn_letter-G)   [**H**](#Commands-_0026-Options-Index_fn_letter-H)   [**I**](#Commands-_0026-Options-Index_fn_letter-I)   [**J**](#Commands-_0026-Options-Index_fn_letter-J)   [**L**](#Commands-_0026-Options-Index_fn_letter-L)   [**M**](#Commands-_0026-Options-Index_fn_letter-M)   [**N**](#Commands-_0026-Options-Index_fn_letter-N)   [**O**](#Commands-_0026-Options-Index_fn_letter-O)   [**P**](#Commands-_0026-Options-Index_fn_letter-P)   [**Q**](#Commands-_0026-Options-Index_fn_letter-Q)   [**R**](#Commands-_0026-Options-Index_fn_letter-R)   [**S**](#Commands-_0026-Options-Index_fn_letter-S)   [**T**](#Commands-_0026-Options-Index_fn_letter-T)   [**U**](#Commands-_0026-Options-Index_fn_letter-U)   [**V**](#Commands-_0026-Options-Index_fn_letter-V)   [**X**](#Commands-_0026-Options-Index_fn_letter-X)   [**Y**](#Commands-_0026-Options-Index_fn_letter-Y)  </td>

</tr>

</tbody>

</table>

<div class="footnote">

* * *

#### Footnotes

### [(1)](#DOCF1)

In some special cases, it automatically balances this transaction for you.

### [(2)](#DOCF2)

This also means if you misspell an account it will end up getting counted separately from what you intended. The provided Emacs major mode provides for automatically filling in account names.

### [(3)](#DOCF3)

You can track _anything_, even time or distance traveled. As long as it cannot be created or destroyed inside your accounting system.

</div>

* * *
