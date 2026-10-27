# Tracking

Which features are done. A feature is done when it works in the browser and is committed.

## Bronze (required)

- [x] Create an invoice: client name, date, and lines with description, quantity and price
- [x] Each line's amount and the invoice total are calculated
- [x] Each new invoice gets the next number automatically
- [x] A list of invoices, newest first, with number, client, date and total
- [x] The app refuses a line without a description, or with a negative quantity or price
- [x] Invoices are still there after you close and reopen the app
- [x] A due date on each invoice, 15 days after the invoice date unless you change it
- [x] Amounts shown with two decimals and the currency, for example 1.250,00 KM
- [ ] Duplicate an invoice: a copy with the next number and today's date

## Silver

- [ ] Edit an invoice, and delete one after a confirmation question
- [ ] Mark an invoice as paid or unpaid, and see the total of unpaid invoices
- [ ] VAT (PDV, 17%): amount without VAT, the VAT, and the total
- [ ] A client list, to choose a saved client
- [ ] Filter invoices by month, and export them to CSV

## Gold

- [ ] Settings page for business details, used on every invoice
- [ ] Print an invoice or save it as a PDF
- [ ] Overdue invoices marked, with the overdue total
- [ ] Summary: invoiced this month and this year, still unpaid
- [ ] Android APK or single .exe
