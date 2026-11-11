# Security policy

Please report security problems privately. Do not open a public issue, discussion or pull request for them.

## How to report

- **GitHub private vulnerability reporting.** Open the Security tab of the affected repository and click **Report a vulnerability**. Only you and the maintainers can see the report.
- **Email.** Write to support@moonetix.com and put "Security" in the subject line.

## What to include

- The repository and the release tag or commit you tested.
- What an attacker can do, and what they need first: an account, a leaked key, a position on the network.
- Steps to reproduce or a proof of concept. A failing test is the most useful form.
- The requests, responses or log lines involved.

Replace your link hash salt, postback secret key and real user IDs with placeholders before you send anything. We never need your secrets to reproduce a problem.

Test only against your own Moonetix account and your own users. Do not access other publishers' data, and do not run load tests against moonetix.com.

## What happens next

We confirm that we received the report, reproduce it, and keep you updated while we work on a fix. Fixes land on the default branch and in the next release. When a fix matters to people running the code, we publish a GitHub security advisory and credit you, unless you prefer not to be named.

Please give us a fair chance to ship the fix before you disclose details.

## Scope

In scope:

- Code in the repositories under [github.com/moonetix](https://github.com/moonetix): the SDKs, plugins, postback handlers and example apps.
- moonetix.com and its subdomains, including docs.moonetix.com and the hosted offerwall.

Especially interesting: anything that lets someone open the offerwall as another user, forge or replay a postback, credit one transaction twice, or reverse more than was credited.

Out of scope:

- Findings from automated scanners without a demonstrated impact.
- Missing security headers or cookie flags on pages that hold no user data.
- Denial of service by volume, social engineering, and physical attacks.
- Problems in your own fork or deployment that the published code does not have.

If you find a real Moonetix key in an issue, a pull request, a fork or a gist, tell us so we can ask the owner to rotate it.
