# vue-router: every query-only link is `aria-current="page"`

Live: https://zlotnika.github.io/aria-current-demo/#/?edit=2

`RouterLink` sets `aria-current="page"` from `isExactActive`, which matches the route record and params but [ignores the query](https://router.vuejs.org/guide/essentials/active-links.html). Every link that differs from the current URL only by its query (rows that open `?edit=<id>`, filter links, "clear filters") is marked as the current page at once. On this page that's 9 links. axe-core reports no violation.

One static `index.html`, Vue 3.5 and vue-router 5 from unpkg. Context: [dequelabs/axe-core#5442](https://github.com/dequelabs/axe-core/issues/5442).
