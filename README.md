# AutoOnboard

## Overview

AutoOnboard is an identity automation workflow that uses Microsoft Forms and Power Automate to provision new users in Entra ID with no manual administrator interaction.

The flow collects onboarding data, normalizes identity attributes, creates the user account, assigns management relationships, and notifies stakeholders automatically.

---

## 🧾 1. Create an Onboarding Form (Microsoft Forms)

<img width="958" height="499" alt="image" src="https://github.com/user-attachments/assets/bcb79036-f9a7-4739-bd59-e98741c4fc58" />


<img width="959" height="533" alt="IAMonb" src="https://github.com/user-attachments/assets/ad1d6177-f6e8-4a7c-94ea-2fc8c84df61f" />

---

- Create a form that collects new employee fields such as:

First name / Last name

Job title / Department (optional)

Manager email

Start date (optional)

Personal email (optional)

Any access/role request fields you want to use later



## ⚡ 2. Build the Power Automate Flow (Trigger + Response Intake)
---

<img width="959" height="533" alt="Iamonb1" src="https://github.com/user-attachments/assets/fbe1a827-8c9c-4755-808e-4be74a8ab3ee" />

---

- Create a new automated cloud flow

- Trigger: When a new response is submitted (Microsoft Forms)

- Add Action: Get response details

## 🔧 3. Normalize Identity Inputs  + Build User Values (UPN, Display Name, Mail Nickname)

---

<img width="958" height="532" alt="IAMonb4" src="https://github.com/user-attachments/assets/22a1dbe6-93e1-49d2-9988-e2669dcaa13c" />

<img width="959" height="497" alt="IAMonb5" src="https://github.com/user-attachments/assets/188a9293-e087-4297-ad09-da4c0a845a6d" />

---

- Create variables (or compose actions) to build:

Display Name (e.g., First Last)

UPN (e.g., first.last@domain.com)

Mail Nickname (must be valid, often first.last without @domain.com)

Password (temporary password if creating cloud-only users)

- This is where you format inputs so user creation won’t fail on schema rules.

## 🧪 4. Test the End-to-End Automation

---

<img width="959" height="530" alt="IAMonb6" src="https://github.com/user-attachments/assets/370f4c19-ce0f-4ea1-b113-db3f25642065" />
<img width="956" height="500" alt="IAMonb8" src="https://github.com/user-attachments/assets/df7f7cc6-8c54-4daf-8f9b-e76665078d70" />

---

- Submit a new onboarding request through the Microsoft Form.

- Power Automate automatically ingests the form response.

- Confirm the flow executes identity actions in Power Automate without manual input.

- Confirm Stakeholders are notified upon successful completion.

     *Testing was redone w/ the Full Name: "KG Red" in Forms

## ✅ 5. Validate Results in Entra ID
---

<img width="956" height="497" alt="IAMonb9" src="https://github.com/user-attachments/assets/219b1096-0fe1-41b2-8a9c-258e2d70beb6" />
<img width="959" height="499" alt="IAMonb10" src="https://github.com/user-attachments/assets/7d10c733-10b8-4a82-958a-add87c16b485" />

---

- Confirm the user exists in Entra ID with the expected:

UPN + display name

Manager relationship

Account enabled state

Group Membership

---

## 📁 Outcome

This workflow demonstrates how identity lifecycle tasks can be automated using native Microsoft tooling to reduce administrative overhead and enforce consistent onboarding standards.
