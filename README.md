# Coming-soon pages

One small web server (nginx in Docker) that serves a coming-soon page for each domain.
It looks at the domain the visitor typed and shows the matching folder in `sites/`.

| Domain | Page |
|---|---|
| smokieslocalguide.com | `sites/smokieslocalguide.com/` (designed page, "More info" emails info@smokieslocalguide.com) |
| easttncs.com, kgene.me, kgenemyers.com, rocinantestudio.com | `sites/<domain>/` (basic "Coming soon") |
| anything else | `sites/default/` |

Deployed with Coolify (build pack: Dockerfile, port 80). To change a page: edit it, commit, push,
then click **Redeploy** in Coolify.

To add a domain: copy one of the basic folders to `sites/<newdomain>/`, change the name inside,
add a line for it in `nginx.conf`, add the domain in Coolify, and point its DNS at the server.

When Smokies Local Guide goes live, remove its two domains from this app in Coolify first.
