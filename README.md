# 8B Education Investments

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

8B Education Investments (legally 8B Finance, Inc., trading as 8B) is a New York headquartered
education-finance company founded in 2017 by Lydiah Kemunto Bosire. It helps African students pay
for degrees at universities outside Africa through a student-loan marketplace and eligibility
comparison tool, an income-share and guarantee backed lending program originated with partner
banks including Nelnet Bank, a University Reserve admissions product, and a free community
platform offering scholarships, courses, forums, events and job listings.

- Website: https://www.8b.africa/
- About: https://www.8b.africa/about-8b/
- Loan FAQ: https://www.8b.africa/studentloans/financing-faq/

## What this profile found

8B publishes **no developer program, no API reference and no OpenAPI**. It does, however, serve
three real machine-readable documents, all captured here verbatim or as probed evidence:

- **`llms.txt`** at https://www.8b.africa/llms.txt (HTTP 200) — a well-formed llms.txt generated
  by Yoast SEO v28.4.
- **An OAuth 2.0 authorization-server metadata document** (RFC 8414) at
  `/.well-known/oauth-authorization-server` (HTTP 200) — authorization code with mandatory PKCE
  S256, refresh tokens, public clients, one scope (`mcp`).
- **An OAuth 2.0 protected-resource metadata document** (RFC 9728) at
  `/.well-known/oauth-protected-resource` (HTTP 200) — naming a **Model Context Protocol endpoint**
  at `https://www.8b.africa/wp-json/mcp/mcp-oauth-server`.

That MCP endpoint is live and reachable. An anonymous `tools/list` returns **HTTP 401** with a
conformant `WWW-Authenticate: Bearer` challenge pointing back at the resource metadata, so the tool
surface is auth-gated and was **not** enumerated — no tool names or schemas are recorded here,
because none were observed.

**Authorship is platform, not provider.** The MCP server is registered by the WordPress MCP Adapter
plugin family running on 8B's WP Engine hosted WordPress install (three servers are exposed:
`mcp-oauth-server`, `mcp-adapter-default-server` and `amelia-mcp-server`). What is genuinely 8B's is
the operation — the endpoint, the OAuth issuer and the data behind them are all on 8B's own host.
The WordPress core `wp-json` REST API is deliberately **not** registered as an 8B API; it is the
CMS platform's own surface, not a product 8B publishes.

The community host `my.8b.africa` publishes a Cloudflare **Content Signals Policy** in its
`robots.txt` (`search=yes,ai-train=no,use=reference`) and disallows seven AI crawlers including
ClaudeBot. That policy is honoured: nothing from that host is stored in this repository.

No security.txt, no api-catalog, no agent card, no status page, no changelog, no SDKs, no CLI, no
GitHub organization and no published rate limits or API plans were found on any host.
