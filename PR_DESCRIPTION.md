# Plugin Submission

## Plugin information

- **Author**: ellanzhang1989
- **Plugin name**: amap_tools
- **Version**: 0.0.3
- **Source repository**: https://github.com/Ellanzhang1989/dify-amap-tools
- **Contact**: zhanglinlin@saidetech.com

## Submission type

- [x] New plugin
- [ ] Version update

## What changed

Amap Tools — China location tools (geocoding, reverse geocoding, POI keyword
search, city weather) via the Amap (Gaode) Web Service API, with the user's
own API key.

This is the **corporate-entity version** of the plugin currently published
under the personal account `ellan1989` (marketplace page:
https://marketplace.dify.ai/plugin/ellan1989/amap_tools, original PRs #3438
and #3547). Following the Dify Community Operations team's guidance (Sherry
Zhao, email thread on the partner application by Saide Technology /
赛德科技), we are migrating the plugin to our corporate account. The team
confirmed the system does not support author ownership transfer, and
recommended resubmitting under the corporate account and then retiring the
personal-account listing. We will request the takedown of the personal
version once this one is live.

The plugin itself is functionally identical to #3547 (0.0.2); changes are
author/org fields, contact email (zhanglinlin@saidetech.com), source repo,
and version bump to 0.0.3.

## Risk level

- [x] Low risk
- [ ] Medium risk
- [ ] High risk

Read-only GET requests to a single declared API domain
(`restapi.amap.com` in `manifest.yaml` `network.domains`); no file, shell,
database, or arbitrary-URL capabilities. Independent third-party integration
with Amap, clearly labeled as not affiliated with Amap in the README.

## Required checks

- [x] I have read and followed the [Marketplace submission requirements](https://github.com/langgenius/dify-plugins/blob/main/docs/plugin-submission-requirements.md).
- [x] I have read and comply with the Plugin Developer Agreement.
- [x] I tested this plugin on Dify Community Edition and Dify Cloud, or documented any limitation below.
- [x] The package contains only files needed at runtime.
- [x] The package does not contain secrets, local credentials, `.env` files, `.git` directories, virtual environments, caches, logs, or IDE files.
- [x] The package does not contain executables or bundled binaries, or I explained why they are required below.
- [x] The plugin README includes setup steps, usage instructions, required APIs or credentials, connection requirements, and the source repository link.
- [x] The plugin includes `PRIVACY.md` or a hosted privacy policy, and `manifest.yaml` references it.
- [x] All user-facing text is primarily in English, with any localized README files following the [i18n guidance](https://docs.dify.ai/en/develop-plugin/features-and-specs/plugin-types/multilingual-readme).

## Security and privacy notes

None. The plugin forwards only user-provided input (address, coordinates,
keyword, adcode) to the official endpoint `https://restapi.amap.com` and
returns the result; nothing is stored or sent anywhere else. Users bring
their own Amap API key (free tier available). See PRIVACY.md.

## Local validation

Ran the official validator from langgenius/dify-marketplace-toolkit on the
exact uploaded archive:

```
python validator/validate-difypkg.py ellanzhang1989/amap_tools/amap_tools-0.0.3.difypkg --output-dir ./validation-report
```

Result: **0 blocking failures** — all blocking checks PASS. The package
includes the explicit provider `tools` list and JSON-Schema `output_schema`
format introduced in #3547, which resolved the earlier production
"package decode failed" issue (see #3529).

## Reviewer notes

- Migration from `ellan1989` to the corporate account `ellanzhang1989`
  (Saide Technology), per Community Operations guidance; the personal-account
  listing will be retired after this one is live.
- Dependencies pinned (dify-plugin==0.10.2, httpx==0.28.1).
