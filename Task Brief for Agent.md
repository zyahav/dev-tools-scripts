📋 Task Brief for Agent — Host Debug Script on Cloudflare Pages

We have one file:
mobile-console-interceptor.min.js

Your job is to host it on Cloudflare Pages under my domain zurielyahav.com and verify it works end-to-end.

Steps
1. Create repo

Repo name: dev-tools-scripts

Structure:

dev-tools-scripts/
  public/
    debug/
      mobile-console-interceptor.min.js


Commit and push.

2. Create Cloudflare Pages project

Project name: dev-tools-scripts

Connect to the repo.

Build settings:

Build command: none

Output directory: public

After deployment, file should be at:

https://dev-tools-scripts.pages.dev/debug/mobile-console-interceptor.min.js

3. Connect custom domain

In Cloudflare dashboard → Pages → dev-tools-scripts → Custom domains

Add subdomain:

dev-tools.zurielyahav.com


Verify DNS is configured.

Final expected URL:

https://dev-tools.zurielyahav.com/debug/mobile-console-interceptor.min.js

4. End-to-end verification

Use crawl / fetch via CLI (no Playwright needed).

Confirm that:

File returns 200 OK

Content type is application/javascript

Body contains expected JavaScript code (console keyword present is enough).

5. Report back

Confirm both URLs are working:

.pages.dev

dev-tools.zurielyahav.com

Confirm file is served correctly.

When all checks are green, reply:
“Finished — interceptor hosted, domain live, tested.”

👉 That’s all. One repo, one file, one Pages project, one custom domain, verified by simple crawl.