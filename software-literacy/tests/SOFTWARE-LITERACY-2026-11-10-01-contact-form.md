# Software Literacy Test 01: Adding a Website Contact Form

**Date:** 2026-11-10  
**Skill:** Software Literacy  
**Test type:** Non-specialist software decision; explanation, trade-offs, and decision authority  
**Scenario selected by assistant:** A person asks an AI to add a contact form to an existing website.

## Scenario

User request:

> Add a contact form to my website. I want submissions sent to my email.

Assume the user has not claimed to be a programmer and has not asked to learn programming. The AI should make the hidden software choices legible without turning the request into a coding lesson.

## Example response under test

A contact form is straightforward to add. The important choice is **where the messages go after someone presses Send**.

There are three practical routes:

### 1. Use a hosted form service

The form appears on your website, but another service receives and manages the submissions, then forwards them to your email.

- **Good for:** getting a basic form working quickly, with little maintenance.
- **Trade-offs:** possible monthly limits or fees; the messages pass through another company's service; you depend on that provider.
- **What to check:** where the provider stores data, who can access it, its retention policy, spam controls, and what happens if email forwarding fails.

### 2. Add form handling to your website

Your website sends the submission to a small server-side component (the part that runs behind the visible website). That component validates the message and sends an email. It may also store a copy.

- **Good for:** more control over the process and room for custom behaviour.
- **Trade-offs:** more setup and ongoing maintenance. Someone must keep the server-side component and its email connection working and secure.
- **What to check:** where any stored messages live, who can access them, how spam is limited, and how failures are logged.

### 3. Open the visitor's email app

A simple form can prepare an email and ask the visitor's device to open their email application.

- **Good for:** a very lightweight approach with little infrastructure.
- **Trade-offs:** it relies on the visitor having an email app configured. It is not a dependable way to collect messages from every visitor, and the website cannot reliably confirm delivery.

## My initial recommendation

For a basic public contact form, I would first compare a reputable hosted form service with the existing website's hosting features. I would not build a custom backend unless the site needs special handling or the existing setup makes that the simpler long-term option.

Before choosing, one decision matters: **will the form collect only ordinary contact details and a message, or will people be asked to submit sensitive information?**

That changes what is appropriate. If sensitive information is involved, we should not casually send it through an unknown third-party form provider or ordinary email.

## What I would do before changing the website

I would inspect the existing project and hosting setup first. I would report:

- which platform or framework the site uses;
- whether it already has a form-handling feature;
- whether the hosting provider supports server-side functions or built-in form collection;
- which files and services would need changing;
- whether the proposed route adds a new provider, account, recurring cost, or data store.

I would not assume the site needs a new database. I would not add one just because databases are a familiar way for developers to store form submissions.

## What the technical terms mean here

- **Frontend:** the part of the website visitors see and interact with. The visible form belongs here.
- **Backend:** the part that receives and processes the submission behind the website.
- **Hosting:** the service or computer that makes the website available online.
- **Data retention:** how long messages are kept and when they are deleted.
- **Spam protection:** checks that reduce automated or abusive submissions. These checks can also block genuine visitors if configured badly.
- **Deployment:** putting the change onto the live website, where visitors can use it.

The terms are included so the user can recognise them later, not because the user needs to learn implementation details to request the feature.

## What must be checked after implementation

These are separate claims:

1. **Generated:** the AI wrote the form and any supporting code.
2. **Runs:** the website loads and the form appears.
3. **Tested:** a test submission was sent through the actual configured route.
4. **Delivery checked:** the message arrived at the intended email address.
5. **Failure behaviour checked:** invalid input, spam controls, and an unavailable email service were considered or tested.
6. **Privacy and access checked:** the user knows which service stores the messages, who can access them, and how long they remain there.

A form appearing on the page does not prove that messages are delivered. A successful test email does not prove that every future message will arrive.

## Software Literacy assessment

- **Goal first:** Pass. The response addresses the contact-form outcome rather than teaching HTML or a programming language.
- **Plain language plus real terms:** Pass. Technical terms are explained in context and retained for recognition.
- **Consequential choices exposed:** Pass. Storage, third-party processing, email delivery, spam, cost, and maintenance are visible.
- **Appropriate decision boundary:** Pass. The user retains the decision about sensitive information and the acceptable data-handling route.
- **Inspect before prescribing:** Pass as a stated next action. The example does not pretend to have inspected an actual repository or hosting account.
- **Execution versus verification:** Pass. The response distinguishes a visible form from tested submission and confirmed delivery.
- **No forced curriculum:** Pass. No coding lesson or quiz is imposed.
- **Recommendation quality:** Partial. The hosted-service route is a reasonable initial comparison, but a real recommendation depends on the existing site's platform, hosting, data sensitivity, and cost constraints.
- **User comprehension:** Not tested. No actual non-specialist participant evaluated or used the explanation.

## Failure modes to watch

1. Explaining the options clearly but failing to inspect the actual project before implementation.
2. Saying "secure" without specifying which risks or controls were checked.
3. Treating email forwarding as guaranteed delivery.
4. Adding a database or a new service without establishing that it is needed.
5. Making the explanation so long that the user must become a project manager just to request a simple feature.
6. Mistaking the user's ability to repeat a definition for understanding the consequences of a decision.

## Limitations

This is a constructed scenario and a self-assessed response. It does not test a real website, actual provider terms, implementation, email delivery, security, or user comprehension. There is no skill-disabled baseline or independent evaluator. The test demonstrates a proposed interaction pattern; it does not establish that the skill improves software outcomes.

## Next useful probe

Use an actual existing repository and a small proposed change. Test whether the assistant inspects the project, identifies the affected files and dependencies, explains the consequential choices, and then distinguishes what it changed from what it genuinely tested. This would probe the skill beyond a well-written explanation.
