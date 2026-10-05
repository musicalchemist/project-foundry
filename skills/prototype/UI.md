# UI prototype

Use an existing development page when variants can be judged alongside realistic navigation and content. Otherwise create a clearly named local prototype route using the project's routing convention. Preserve existing authentication; use synthetic or approved read-only data and stub mutations.

Default to three structurally different variants, with at most five unless the task justifies more. Vary hierarchy, layout, and primary interaction rather than only colors. Reuse the project's component/styling tools without adding packages.

Make variants switchable with a URL parameter and a small development-only control. Preserve unrelated parameters. If arrow keys switch variants, leave input and editable controls alone. Keep prototype routes and variants out of production behavior using the project's actual build/routing mechanism; hiding a control alone is insufficient.

Return the local route and variant keys with the question each alternative probes. Record which layout or combination was chosen and why. Keep comparison evidence locally. Implement the selected design through normal app checks, then remove disposable variants within the agreed scope; no automatic commits or publication.
