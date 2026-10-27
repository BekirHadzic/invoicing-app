# Invoicing App — Plan

## Goal

A simple invoicing app for someone who sends invoices to clients, for example a designer, a translator or an IT freelancer. You create an invoice in the browser, the app does the maths, numbers the invoices for you, and remembers them.

**Rule:** a small app that works beats a big app that half works. One task at a time: build it, check it in the browser, commit it.

## Technology

| Part | Choice | Why |
|---|---|---|
| The app | One file, `index.html` (HTML + CSS + JavaScript) | Runs in any browser, nothing to install. You can read every line. |
| Where invoices are saved | The browser's `localStorage` | Invoices stay there after you close and reopen the app. No server or database needed. |
| Running it on your laptop | `python -m http.server 8000`, then open http://localhost:8000 | Python is already installed. |

**Note:** the invoices live in the browser you use, not in git and not on GitHub. Use the same browser and the same address (http://localhost:8000) every time, or you won't see them.

## Features

### Bronze (required)

1. Create an invoice: client name, date, and lines with description, quantity and price.
2. Each line's amount and the invoice total are calculated.
3. Each new invoice gets the next number automatically.
4. A list of invoices, newest first, with number, client, date and total.
5. The app refuses a line without a description, or with a negative quantity or price, with a clear message.
6. Invoices are still there after you close and reopen the app.
7. A due date on each invoice, 15 days after the invoice date unless you change it.
8. Amounts shown with two decimals and the currency, for example `1.250,00 KM`.
9. Duplicate an invoice: a copy with the next number and today's date.

### Silver (optional)

- Edit an invoice, and delete one after a confirmation question.
- Mark an invoice as paid or unpaid, and see the total of unpaid invoices.
- VAT (PDV, 17%): amount without VAT, the VAT, and the total.
- A client list, to choose a saved client.
- Filter invoices by month, and export them to CSV.

### Gold (optional)

- A settings page for the business details (name, address, ID number, bank account), used on every invoice.
- Print an invoice or save it as a PDF.
- Unpaid invoices past their due date are marked overdue, with the overdue total.
- A summary: total invoiced this month and this year, and how much is still unpaid.
- The app on an Android phone (APK) or as a single .exe.

## Tasks, in order

Each task ends with: check it in the browser, then commit.

| # | Task | Check in the browser |
|---|---|---|
| 0 | Plan and `.gitignore` | — |
| 1 | `tracking.md` | — |
| 2 | Invoice form: client, date, lines (add and remove), save | Create an invoice with three lines. |
| 3 | Line amounts and invoice total | Check with a calculator. |
| 4 | Automatic invoice numbers | Create two invoices, compare their numbers. |
| 5 | Invoice list, newest first | Look at the list after creating three. |
| 6 | Validation with clear messages | Try an empty description, a negative quantity, a negative price. |
| 7 | Save to `localStorage` | Close the browser, open the app again. |
| 8 | Due date (invoice date + 15 days, can be changed) | Create one and check the date. |
| 9 | Amounts as `1.250,00 KM` | Enter a price of 1250. |
| 10 | Duplicate an invoice | Duplicate one and compare the two. |
| 11 | README, publish to GitHub | Open the repository on github.com. |

## Decisions

- **Money is calculated in cents (whole numbers).** `0.1 + 0.2` is not exactly `0.3` in JavaScript, so every amount is rounded to cents once and then added up as whole numbers.
- **Invoice numbers come from a counter** that only goes up, so a number is never used twice, even if an invoice is deleted later (Silver).
- **Dates are stored as `YYYY-MM-DD`** and shown as `DD.MM.YYYY`.

## Planning ahead for Gold (APK or .exe)

If the app has to run on an Android phone or as a single .exe later:

- Keeping everything in one HTML file makes both easier: it can be wrapped in a WebView (Android) or a small desktop shell without changing the app.
- `localStorage` belongs to one browser on one device. On a phone or in an .exe, the data is kept inside that app, not next to the file. An **export / import** of all invoices (as a JSON file) would be the way to move data between devices. That would be the first thing to add before Gold.
