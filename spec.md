# Spec — booking-inquiry form (Lancaster Furnished Housing site)

## Inputs

Guest fills a Squarespace form on each unit page + a general Contact form.

## Fields

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Name | text | yes | |
| Email | email | yes | |
| Phone | tel | no | strongly encouraged |
| Property / unit | select | yes | prefilled from the unit page; "not sure" option routes to a portfolio question |
| Move-in date | date | yes | mid-term only (30+ days) — copy should state this |
| Length of stay | select | yes | 1–3 mo / 3–6 mo / 6+ mo / not sure |
| Guests (incl. pets) | text | no | pet policy differs per unit — capture it here |
| Message | textarea | no | |

## Outputs

- Email to `LancasterFurnishedHousing@gmail.com` with subject
  `Inquiry: <unit> — <move-in date> (<name>)`.
- Auto-reply (friendly, 1 business day SLA, mid-term stay explanation, link to The West End page).

## Guardrails

- No financial fields (deposits collected only after a lease is signed — TurboTenant/Zelle).
- Consent checkbox + privacy line (name/contact used only for the inquiry).
- Filter out nightly (<30 day) requests with copy, not rejection logic.
- `fair-housing-compliance-overlay` review before publishing the form copy.
