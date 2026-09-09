# Site Requirements for 152-FZ Audit

Use this as the audit checklist. Mark each item as `ok`, `issue`, `risk`, or `not checked`.

## 1. Operator

The site should clearly identify the personal data operator:

- company / sole proprietor / organization name;
- address or location;
- contact for personal data requests;
- consistency across policy, contacts, requisites, offer, footer.

Issues:

- operator missing;
- one operator in policy, another in requisites;
- generic template not tied to the real site.

## 2. Two Separate Documents

Addu audit standard requires two separate documents:

- `Политика обработки персональных данных`;
- `Согласие на обработку персональных данных`.

The policy informs the user. The consent records the user's will to allow processing.

Issues:

- only policy exists, no separate consent;
- forms link only to policy;
- consent is hidden inside policy, offer, or user agreement;
- one checkbox confirms everything at once.

## 3. Privacy / Personal Data Policy

The policy should be accessible without authorization and linked from stable site areas.

It should cover:

- operator;
- categories of personal data;
- categories of subjects;
- processing purposes;
- legal bases;
- processing actions;
- retention / termination logic;
- user rights;
- request and withdrawal process;
- general protection measures;
- third-party processors;
- cookies / analytics / pixels when used;
- cross-border transfer if relevant.

Issues:

- missing / broken / empty policy;
- placeholder or copied text;
- no purposes, data categories, retention, user rights, request procedure, cookies.

## 4. Forms and Consent

Check every form:

- callback;
- request / consultation;
- contact;
- order / checkout;
- registration / account;
- booking;
- quiz / calculator;
- file upload;
- chat / callback widget / iframe form.

Each form should have:

- personal data consent text;
- link to the policy;
- link to separate consent document;
- separate unchecked checkbox or another clear separate mechanism when consent is used;
- consent separated from offer, newsletter, and user agreement.

Issues:

- form collects name / phone / email without visible consent;
- no link to policy;
- no link to separate consent;
- checkbox is pre-checked;
- one checkbox covers personal data, offer, newsletter, and ads;
- modal form differs from static form.

## 5. Advertising and Newsletter Consent

If the site collects contacts for advertising, newsletters, SMS, messengers, or promotions, this consent should be separate from personal data processing consent.

Issues:

- lead form automatically subscribes user to ads;
- newsletter consent is bundled into the main consent;
- pre-checked advertising consent.

## 6. Cookies, Analytics, Pixels

Check for:

- Yandex Metrika;
- Google Analytics / GTM;
- VK / Meta pixels;
- Roistat / Calltouch;
- chats / callback;
- reCAPTCHA;
- other trackers.

The site should have:

- cookie notice or clear user notification;
- cookie section in policy or separate cookie policy;
- description of technical, analytical, advertising, personalization cookies;
- disclosure of external services;
- working link from cookie notice.

Issues:

- trackers are present but cookies are not disclosed;
- cookie notice link is broken;
- policy does not mention external services that actually load.

## 7. External Processors

Check if personal data goes to:

- CRM forms;
- Bitrix24 / amoCRM;
- chat / callback;
- booking / payment / delivery widgets;
- email / SMS services;
- advertising / analytics platforms.

Issues:

- external iframe collects personal data without consent;
- policy does not mention third-party processing;
- form posts to external domain without disclosure;
- foreign service or cross-border risk is not addressed.

## 8. Document Availability

Check desktop and mobile where possible:

- home;
- service/product page;
- contacts;
- requisites;
- page with form;
- checkout / registration / booking;
- modal forms.

Issues:

- policy/consent links only on home page;
- mobile version hides legal links;
- modal links are not clickable;
- different templates link to different documents.

## 9. Data Minimization

The form should not request more data than needed for its purpose.

Issues:

- callback form asks for passport/address/birthdate;
- all fields are mandatory without reason;
- sensitive data is collected without explanation.

## 10. Safe Transfer

Check visible technical basics:

- HTTPS on pages with forms;
- forms do not submit to HTTP;
- personal data is not exposed in URL parameters;
- no public CSV/XLS/logs/test pages with personal data.

Issues:

- form posts to HTTP;
- phone/email in GET URL;
- public exports or logs.

## Manual Review Only

Do not present these as proven violations from public site audit:

- Roskomnadzor notification status;
- actual database localization;
- contracts with processors;
- internal personal data documents;
- final legal wording;
- real CRM retention/deletion process;
- cross-border transfer legality.
