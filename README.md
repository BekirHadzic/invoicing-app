# Salty Invoices

A simple invoicing app for freelancers (designers, translators, IT services) who send invoices to clients: create an invoice, and the app does the maths, numbers it and remembers it.

## Features

- Create an invoice with a client, a date and any number of lines (description, quantity, price)
- Each line's amount and the invoice total are calculated as you type
- Invoice numbers count up automatically (INV-0001, INV-0002, …)
- A list of all invoices, newest first, with number, client, date, due date and total
- Clear messages when a line has no description, or a negative quantity or price
- Invoices are saved in the browser and are still there after you close it
- A due date 15 days after the invoice date, which you can change
- Amounts shown as `1.250,00 KM`
- Duplicate an invoice: a copy with the next number and today's date
- Works on a phone screen as well as on a computer

## How to run

You need Python (any version 3). In a terminal, in this folder:

```
python -m http.server 8000
```

Then open http://localhost:8000 in your browser. Stop the server with `Ctrl+C`.

Your invoices are saved in that browser, for that address. Use the same browser and http://localhost:8000 each time to see them. They are never uploaded to GitHub.

## How it's built

One file, [index.html](index.html): plain HTML, CSS and JavaScript, no libraries and no build step. Invoices are stored in the browser's `localStorage`.

- [PLAN.md](PLAN.md): goal, features and the order they were built in
- [tracking.md](tracking.md): which features are done
