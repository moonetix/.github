# Contributing

These rules apply to every repository under github.com/moonetix that does not have its own CONTRIBUTING.md.

## Before you write code

- **Small fixes** (a typo, a broken link, an obvious one-line bug): open a pull request directly.
- **Bigger changes** (a new feature, a new dependency, anything that touches how rewards are credited or reversed): open an issue first. We agree on the approach there, so your work does not end in a rejected pull request.
- **Security problems:** do not open an issue. Follow [SECURITY.md](SECURITY.md).

## Pull requests

- One change per pull request. A bug fix and a refactor are two pull requests.
- The tests must pass. Each README says how to run them, and CI runs the same commands.
- Changed behavior needs a test that fails without your change.
- Repositories without dependencies stay that way. If a dependency is unavoidable, pin an exact version and explain why in the pull request.
- Update the README when you change how something is set up or run.

## Fake keys only

Use these values in code, tests, fixtures, issues and screenshots:

| Variable | Value |
| --- | --- |
| `MOONETIX_APP_ID` | `demoapp0000000000000001` |
| `MOONETIX_LINK_SALT` | `test_link_salt_not_secret` |
| `MOONETIX_POSTBACK_KEY` | `test_postback_key_not_secret` |

Never commit a real link hash salt, postback secret key or user ID, not even in a test you plan to remove later. Git history keeps it.

## Rules the code must keep

These examples move real money. A pull request that weakens one of these rules will not be merged:

1. The offerwall link is signed on the server, for the signed-in user. A user ID from the client is never trusted.
2. The postback hash is checked first, with a constant-time comparison.
3. Each `transaction_id` is credited once, enforced by the database, not only by a check in code.
4. Status 2 takes back only what was credited for that transaction.
5. The handler answers 2xx only after the change is stored.
6. Rewards are only for completed offers. Nothing rewards joins, invites, likes, reviews or other engagement, and users must be 16 or older.

## Writing style

US English and short sentences. Use a plain hyphen, never an em or en dash. No emojis. Comment code only where the reason is not obvious from the code.

## License

By contributing, you agree that your contribution is released under the license of the repository you contribute to.
