SKYDESIGNCLOUD WEBSITE - DEPLOY NOTES
Files: index.html (whole site), 404.html, og-image.jpg (link preview), robots.txt, sitemap.xml,
CNAME (GitHub Pages only), _headers (Cloudflare Pages only).

CONTACT FORM
By default the forms open a ready-to-send email to contact@skydesigncloud.com.
For direct delivery: create a free form at formspree.io that forwards to contact@skydesigncloud.com,
then in index.html find  formEndpoint:""  and paste your URL, e.g. formEndpoint:"https://formspree.io/f/abcdwxyz".

OPTION A (recommended): Cloudflare Pages
1. Upload these files to a GitHub repo (index.html at the top level).
2. Cloudflare dashboard > Workers & Pages > Create > Pages > Connect to Git. Build command: none. Output directory: /
3. Add custom domain skydesigncloud.com (and www). Cloudflare Pages applies _headers automatically.
4. SSL/TLS mode: Full (strict). Turn on Always Use HTTPS.

OPTION B: GitHub Pages + Cloudflare
Add domain in repo Settings > Pages, set DNS records to the GitHub IPs with the grey cloud (DNS only) until
the HTTPS certificate is issued, then switch to proxied (orange) and use SSL mode Full. _headers is ignored here;
add security headers with Cloudflare Rules > Transform Rules.

EMAIL WARNING
If you move the nameservers from Hostinger to Cloudflare, copy ALL email records (MX, SPF, DKIM, DMARC)
from Hostinger DNS into Cloudflare DNS (DNS only) BEFORE switching, or contact@skydesigncloud.com will stop receiving mail.
