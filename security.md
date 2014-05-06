# Preventing XSS and CSRF

It's about **trust**.

Vulnerabilities are antithetical to trust.

Prevention > Repair

Two common types of attacks:

- XSS (cross-site scripting)
- CSRF (cross-site request forgery)


## XSS

An injection attack, driven by user-controlled inputs

A "garbage-in, garbage-out" approach is maybe not such a good idea when it comes to security.

The user can place arbitrary HTML and JS on your page.

Example--what happens if you have:

    <h1>Hello <%- user.name -%></h1>

and `user.name` is a script tag that directs to a malicious site?

### Three-part approach:

1. **Validate input**

   Best case: compare against an *allow list* of known good values

   But not everything can be validated against an allow list--e.g., human names.

   Maybe in that case don't allow `'<>'` to prevent HTML tags

2. **Sanitize output**

   aka filtering, normalizing, escaping

   goal: prevent user-controlled input from breaking out of its context

   means: convert unsafe markup to safe markup

   HTML entity-encoding takes markup characters and turns it into display characters


   **js attacks**

   not safe to interpolate json straight into script tags
   need to escape characters so that `<` becomes something like `\x39`

   But JS sanitization doesn't save you from `innerHTML`


   Query Param Attack

   Sanitizing via URI-escaping
   `&` becomes `%26`


   **Tools**

   [https://www.npmjs.org/package/secure-filters]()


   **Don't sanitize input!** It permanently modifies the data. Instead: validate input, sanitize output.


3. **Enable content security policy**

   Validation can't cover everything, and sanitization can't catch everything...

   Pages define an `Allow-List` of what features and their origins are permissible.

   Served as a HTTP header (or use a `<meta>` HTML tag)

   `self` keyword means the origin server, e.g., `script-src 'self'`

Defense in depth - a combination of these approaches is the safest way to go.


## CSRF

Exploits the fact that you are logged in to some *other* site with a cookie, session, or whatever.

How do we fix this? We need to assert that the user actually intended to perform an action.

### CSRF token

Put into any forms a unique, *secret* anti-CSRF token that's tied to the user's login cookie.

Validate the anti-CSRF token, which since it is a secret, the attacker doesn't know and can't put on their site.

### Other ideas

Be a good HTTP citizen: actions that change application state should be `POST / PUT / PATCH / DELETE` - e.g., not a `GET`

Assert that the user meant to do it: e.g. send to a page to confirm, or require re-entry of password
