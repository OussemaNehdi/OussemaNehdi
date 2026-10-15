# Open-source contributions

**Express** · **FastAPI** · **SolidJS** · **roadmap.sh**

### [Express](https://github.com/expressjs/express/pull/7171): request-lifecycle observability &nbsp;![shipped](https://img.shields.io/badge/shipped_via_pillarjs%2Frouter-8250df?style=flat-square)
I opened the **first PR implementing `diagnostics_channel` events for the Express request lifecycle** ([#6353](https://github.com/expressjs/express/issues/6353)). With these events, monitoring tools like OpenTelemetry, Sentry and Datadog can trace requests without monkey-patching Express. While reviewing my PR, an engineer from Sentry proposed moving the instrumentation into Express's router and using `TracingChannel`s for context propagation. **He opened [pillarjs/router#196](https://github.com/pillarjs/router/pull/196) the next day**, which cites my PR in its related work as the same feature, and the maintainers marked mine as superseded by it. It's now **merged and slated for the next release**, shipping to Express 5.

### [FastAPI](https://github.com/fastapi/fastapi/pull/15341): `AliasChoices` for request params &nbsp;![closed](https://img.shields.io/badge/closed-6e7781?style=flat-square)
My team hit this in production: `AliasChoices` validation aliases were silently ignored for `Query` / `Header` / `Cookie` / `Form` params. I fixed it with regression tests and the full suite passing. Sebastián Ramírez (FastAPI's creator) closed it because he's planning refactors in that area, **not on the merits** ([see thread](https://github.com/fastapi/fastapi/pull/15341)).

### [SolidStart](https://github.com/solidjs/solid-docs/pull/768): route file naming convention &nbsp;![merged](https://img.shields.io/badge/merged-8250df?style=flat-square)
In the early days after SolidStart's release, the routing convention described the folder-named route file convention incorrectly. People following it ended up with **routes that didn't render**, and it kept coming up in the Solid and JavaScript Discords. I corrected it: the file has to be wrapped in parentheses, e.g. `(socials).tsx`. Reviewed and approved by SolidJS core maintainer **Atila Fassina**.

### [roadmap.sh](https://github.com/nilbuild/developer-roadmap/pull/9244): "Busy Frontend" entry &nbsp;![merged](https://img.shields.io/badge/merged-8250df?style=flat-square)
roadmap.sh is one of the **top 10 most-starred repositories on all of GitHub (369k★)** and a go-to learning reference for engineers. I rewrote the "Busy Frontend" entry. It covers a fairly advanced concept, so the wrong explanation went unnoticed for a long time and confused a lot of readers.

---

### Currently building

**[Loonaris](https://github.com/Loonaris-DBaaS)**: a production-grade, multi-tenant PostgreSQL DBaaS on AWS / Kubernetes. I built a custom **PostgreSQL wire-protocol proxy** for tenant-aware routing, plus automated provisioning, replication and failover. Each tenant gets an isolated cluster in **under 30 seconds**.
