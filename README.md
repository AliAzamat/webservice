# RealEst — Salesforce Web-to-Lead & Web-to-Case Forms

**Two static HTML forms for a fictional real-estate company that post directly into Salesforce: a lead-capture form that creates Leads and a support form that creates Cases, each redirecting to a branded thank-you page.**

Salesforce's Web-to-Lead and Web-to-Case features let a plain HTML form create CRM records without any backend. This repo contains the styled public-facing forms; the thank-you pages live in two companion repos.

## Pages

| File | Salesforce endpoint | Fields | Redirects to |
|---|---|---|---|
| `web-to-lead.html` | `WebToLead` | Salutation, first and last name, email, phone, company, city, state, country | [thankslead](https://github.com/AliAzamat/thankslead) |
| `index.html` | `WebToCase` | Name, email, phone, subject, issue type (Mechanical, Electrical, Electronic, Structural, Other), description | [thankstocase](https://github.com/AliAzamat/thankstocase) |

Each form posts to `webto.salesforce.com` with the org's ID in a hidden field and a `retURL` pointing at the matching thank-you page on GitHub Pages. Styling is in `web-to-lead.css` and `web-to-case.css`.

## Using it

Open either HTML file in a browser, or serve the folder with any static host (the redirect URLs assume GitHub Pages under `aliazamat.github.io`). To point the forms at a different Salesforce org, replace the hidden `oid` / `orgid` values and the `retURL` targets.

## Notes

- Submissions go straight to Salesforce, so there's no spam protection (reCAPTCHA can be enabled in the Web-to-Lead/Case settings) and no client-side validation beyond required fields.
- Page titles are still the default "Document".
