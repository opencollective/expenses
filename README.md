# expenses
Submit expenses over Nostr

Deliverable: a new "Expenses" tab next to "Posts" in https://chorus.community (https://github.com/andotherstuff/chorus).

Instead of the focus being on the content, the focus should be on adding a picture or attaching a file.
Content should only be a one-liner with #tags and combo tags #price:€100.33 (like on txinfo.xyz, improving the UX with a dedicated interface to enter those tags and combotags can come later).

By piggy backing on that Nostr infrastructure, we can reuse the same mechanism for approval from the collective's moderators and make use of the blossom file storage (https://github.com/hzrd149/blossom).
We can then make it easy for anyone to develop an agent that could listen for new submissions and add missing/extra metadata (imagine a bot that would send the receipt picture to a LLM and return more information about it, in the same way that agents are now adding comments to a pull requests).

Another agent could listen to new approved expenses and automatically send them eCash or Bitcoin or whatever token (or submit a proposal to the SAFE of the collective).

## v1

The equivalent of a new "Posts" tab on chorus.community and on opencollective.xyz/:collectiveSlug/expenses.

## v2

- Expense page to view the log of all posts (Nostr notes that are in the thread) about a given expense (defined by the id of the first nostr note that is the root of the thread), with a summary at the top.
Eg. I submitted an expense quickly, then later on, someone else (or an agent, or myself) adds another note to add more metadata or update the description. The top should show the summary of the latest version.

- Bot to automatically pay an expense when approved when there is enough USDC / eCash in the collective.

- Offramp for people to exchange their USDC / eCash to USD (we can start with ourselves with Open Collective Inc. on opencollective.xyz/opencollective).

## About privacy

Everything is public. So don't upload invoices that contain private information about the buyer. Receipts are ok.
For invoices, I'd recommend sending it through other means to the fiscal host (or whoever is accounting for it in their books) and add a tag #[invoice:REFERENCE] to help with reconciliation.
