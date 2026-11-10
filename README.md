# Sendify Summer Internship 2027: The One-Shot Prompt Challenge

## About This Challenge

Complete this challenge to apply for a summer internship as a Software Engineer at Sendify. **No CV or cover letter required.** Show us what you can build.

This year there's a twist: **you don't submit code. You submit a prompt.**

We'll give your prompt to a current AI model, once, with no follow-up messages. That model has to build a working web app that books real shipments through the Sendify API. If the app works, your prompt works.

Writing a prompt that reliably produces working software means you have to understand the problem well: the API, the booking flow, the edge cases, and what a good user experience looks like. That's what we're testing.

## The Task

Write a prompt that **one-shots** a frontend for booking shipments with the Sendify API.

The generated app must let a user do these three things:

1. **Book a domestic parcel.** Sweden → Sweden, a standard parcel delivered to the receiver's address.
2. **Book a shipment to Norway.** Sweden → Norway. Norway is outside the EU, so the shipment needs customs information.
3. **Book a domestic service point shipment.** Sweden → Sweden, delivered to a parcel shop or pickup point the user chooses.

### Requirements for the generated app

- **All input comes from the user.** The person using the app types in sender, receiver, package details, customs details, and so on. Nothing is hardcoded except sensible defaults.
- **The API key is entered in the app.** Don't put your API key in the prompt. We'll test with our own key.
- **The booking actually happens.** A flow is complete when the shipment is booked in Sendify and the app shows the result: at least the tracking number and a way to open the shipping label.
- **The user can choose a price.** Show the available carrier options and prices, and let the user pick one before booking.
- **Errors are shown clearly.** If the API rejects something (a missing field, an invalid postal code, an expired price), the user should see what went wrong and be able to fix it.

### Requirements for your prompt

- **One shot.** We send your prompt once. No follow-up messages, no "now fix the bug".
- **No pasted application code.** Your prompt can include short examples (a request body, a field list), but not the app's source code. We want the model to write the app.
- **It must say how to run the result.** Your prompt should make the model produce run instructions (for example `npm install && npm run dev`, or "open `index.html`"). We'll follow those instructions exactly.
- **Any stack.** React, Vue, plain HTML, anything that runs in a browser. Your choice; be ready to explain it.

## How We Evaluate

We run your prompt with one of the latest models from Anthropic or OpenAI, such as **Claude Fable 5.2** in Claude Code or **OpenAI Astra** in Codex. The model has internet access, so it can read the API docs itself.

Because AI output varies between runs, **we run your prompt [3] times.** We then try all three booking flows on each generated app against our staging environment.

| | What we look at |
|---|---|
| **Must have** | The app starts using the generated instructions. All three flows end in a booked shipment with a tracking number and label. |
| **Reliability** | How many of the runs produce a fully working app. |
| **Correctness** | The right API flow for each case: customs data for Norway, a real service point selection for parcel shops. |
| **Usability** | Could someone at Sendify use this without reading the code? Clear forms, validation, and error messages. |
| **The prompt itself** | Clear, well structured, and precise. Long isn't better. Every line should earn its place. |

Test your prompt yourself before submitting. Run it several times and fix the prompt, not the output.

## Getting Started

### 1. Create a staging account

Sign up at **https://se.sendify-staging.com/sign-up**

- **Company name:** `<Your first and last name> Internship 2027`, e.g. `Anna Andersson Internship 2027`
- **Organisation number:** `9203230819`

Staging is a test environment. No real parcels are picked up, and nothing is charged.

### 2. Create an API key

In your staging account, go to **Settings → API** and create a key. You'll use it to test the apps your prompt generates.

### 3. Read the API docs

**https://api.sendify.com/**

## Submission

Email your prompt to **internship@sendify.com**:

- **Subject:** `Summer Internship 2027 – <Your name>`
- **In the email:** a few lines about who you are, what you study, and that you're applying for the summer internship.
- **Attach:** your prompt as a `.md` or `.txt` file. This file is exactly what we'll give the model.
- **Optional:** a short note on how you developed and tested your prompt.

**Deadline:** December 31, 2026. We'll reply to everyone within two weeks of the deadline, by January 14, 2027.

## What Happens Next

If your prompt meets our criteria, we'll invite you to an interview. Be ready to:

- **Walk us through your prompt.** Why is each part there? What did you try that didn't work?
- **Explain the API flow.** What happens in each step, and why do Norway and service point shipments need different handling?
- **Discuss the generated code.** Run your own prompt and read what comes out. We'll look at it together.
- **Talk about improvements.** How would you make the prompt more reliable? What would you change in the app with more time?

This is your prompt. Own it, and be ready to reason about every line.

## Questions?

Reach out if you're stuck or something in staging isn't working:

- Email: internship@sendify.com
- Discord: https://discord.gg/BBcjpBpWp

---

Good luck! We're excited to see what you come up with.
