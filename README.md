# Currency Rate Sync for Business Central (USD → CAD)

This Power Automate flow automatically updates or creates **Currency Exchange Rates** in Dynamics 365 Business Central (Table 330) for **USD → CAD** on a daily basis.

- If a record exists for **today**, it updates the rate.
- If no record exists, it creates a new one for **today**.

---

## Features
- **Daily automation** via Recurrence trigger.
- Fetches live **USD → CAD** exchange rate from API.
- Uses **local time** to ensure correct "Starting Date".
- Supports both **Update** and **Create** logic.
- Works with a **custom API page** in Business Central for cleaner data operations.

---

## Prerequisites
- Dynamics 365 Business Central environment.
- Power Automate license.
- A custom API page for Currency Exchange Rates (AL file required).
- Proper permissions in Business Central (e.g., `SUPER` role or equivalent).

---

## Flow Steps
1. **Recurrence** – Trigger the flow daily.
2. **HTTP** – Fetch the USD → CAD rate from the API.
3. **Parse JSON** – Read and extract the `USDCAD` value.
4. **Compose (Today)** – Generate today’s date in local time (`yyyy-MM-dd`).
5. **FindUSD** – Search BC for the latest USD record.
6. **Condition** – Check if a record for today already exists:
   - **Yes → Update record** with new rate.
   - **No → Create record** for today with new rate.

---

## How to Use
1. Publish the custom API page in your BC environment.
2. Import or build the flow in Power Automate using the steps above.
3. Set the **Recurrence** schedule as needed.
4. Verify that records update/create correctly in BC Currency Exchange Rates.

---

## License
This solution is provided as-is for internal or personal use only.

---

## Flow Screen Clip

<img width="566" height="816" alt="{30B6A04C-7C89-406E-A67B-B2D5080B0886}" src="https://github.com/user-attachments/assets/ed3dc765-f5a0-4bbf-a9f0-20f92f61f483" />
