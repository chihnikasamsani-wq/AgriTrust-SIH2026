# AgriTrust — Complete Agricultural Workflow Prototype

AgriTrust is a prototype for an accessible agricultural marketplace connecting farmers, customers/buyers, logistics and authorized quality agents.

## Included workflow

1. Language selection
2. Role registration: Farmer, Customer/Buyer, Logistics, Quality Agent
3. Farmer voice assistant
4. AI-assisted extraction of crop, quantity, date, location and expected price
5. Farmer reviews and explicitly confirms submission
6. Produce becomes available to customers
7. Customer selects a specific crop listing and quantity
8. Customer can submit an offer price
9. Customer explicitly confirms the order
10. Logistics sees only customer-confirmed orders
11. Logistics accepts pickup
12. Logistics marks pickup completed
13. Quality Agent performs a quick inspection
14. Quality result: Accepted / Adjustment / Rejected
15. Payment remains pending until quality decision
16. Dispute workflow with admin resolution
17. Farmer can change their own price
18. Urgent-sale mode can notify buyers when a perishable crop is at risk of remaining unsold
19. Voice + keypad/IVR + SMS/agent workflow is represented for non-smartphone users

## Run on Windows PowerShell

Open the folder containing package.json:

```powershell
npm install
npm start
```


Open:

http://localhost:3000

## Recommended demonstration sequence

### Farmer
- Register as Farmer
- Open Talk to AgriTrust
- Say: `I have 50 kg tomatoes on Friday in Rajamahendravaram at 30 rupees`
- Review the extracted details
- Click **Confirm & Submit**

### Customer
- Open the app in another browser/incognito window
- Register as Customer / Buyer
- Select the tomato listing
- Enter quantity and offer price
- Click **Select & Submit Order**
- Click **Confirm order**

### Logistics
- Register as Logistics
- Click **Accept Pickup**
- Click **Mark Picked Up**

### Quality Agent
- Register as Quality Agent
- Record Grade A/B/C, damage percentage and decision
- Accepted releases demo payment; adjustment/rejection keeps payment on hold

### Price and perishability
- Farmer can change their own price from the submitted crop card.
- Farmer can activate **Urgent Sale** to notify buyers when a crop is at risk of remaining unsold.
- The system never silently changes the farmer's price.

## Non-smartphone concept

The prototype UI represents the intended IVR/keypad + voice + SMS/agent flow. Real telephone calls and SMS require a telecom/IVR/SMS provider. A production version should connect those channels to the same backend actions.

## Important prototype limitations

- Browser speech recognition depends on browser/device support.
- AI extraction is a local demonstration parser, not a production LLM.
- Payments are demo states; no real money is moved.
- GPS uses browser permission.
- JSON persistence is for demonstration; production should use a managed database, authentication, authorization, HTTPS, audit logs and secure payment/AI integrations.

## Pricing policy

AgriTrust does **not** fetch, import, compare against, or display market prices from external websites, APIs, government datasets, AGMARKNET, or other third-party sources.

- The farmer enters the expected price for each produce listing.
- The farmer explicitly confirms the listing before it is submitted.
- Customers can review the farmer's listed price and submit an offer.
- The farmer can change their own listing price.
- AgriTrust never silently replaces a farmer's price with an external market price.
- The prices in `data.json` are **demo listing prices only** for local testing; they are not claimed to be market prices.
