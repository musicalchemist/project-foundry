# User-facing application profile

Use for web/mobile/full-stack products, directories, social tools, productivity apps, research interfaces, news/media, coupons, and ecommerce. Define the primary user journey and smallest useful version before selecting a stack.

Choose languages/frameworks/database/hosting from existing skills, supported libraries, deployment needs, accessibility, cost, and maintenance capacity. Consider a simpler existing tool before building custom infrastructure. Use a modular design with business rules separated from UI and external services where useful.

Specify identities, roles, object ownership, tenant boundaries, and data lifecycle. Enforce authorization server-side and test cross-user/cross-tenant access. Include input validation, safe uploads, session/logout behavior, rate limits, error handling, and privacy-aware logs. Use established providers/libraries for authentication and payment handling when appropriate; verify webhook authenticity and idempotency.

Build one journey through the actual UI/API/database. Check empty/loading/error/offline states, keyboard use, accessibility, responsive behavior, and mobile device constraints. Add integration tests for persistence and a few end-to-end checks for high-value journeys. A frontend-only demo needs a clear boundary before real data or users.

Plan migrations, background jobs, retry/idempotency, and external-service failure. For mobile, consider permissions, local storage, connectivity, supported devices, distribution, and compatibility. Add production guidance when operating for users.

Use domain overlays selectively: moderation/reporting and abuse controls for social content; editorial workflow and media rights for news; eligibility/expiry/redemption rules for coupons; consented business data sources for directories; payment reconciliation, inventory, refunds, and tax/fulfillment requirements for ecommerce. Investigate current obligations for the actual jurisdiction and use case rather than inventing a universal compliance checklist.
