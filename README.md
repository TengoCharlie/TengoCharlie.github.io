# Home door contact page

Prepared on branch `home-door-contact` for **https://myhome.tenguriya.com**.

This is a standalone, responsive English/Hindi resident-contact page for a door QR sticker. It offers Call, WhatsApp and SMS to **+91 94628 28205**. Visitors can optionally add their name, message and current location. There are no photo uploads, emergency contact numbers, home address, or manually entered password. The QR includes an access key.

## Deploy without changing the car site

The existing car website continues to publish from `main` in `TengoCharlie/TengoCharlie.github.io`. Do not change that repository's Pages source to this branch: doing so would replace the car website.

1. Create a separate public repository for the home website, for example `home-door-contact`.
2. Copy `index.html`, `.nojekyll`, and `CNAME` from this branch into its root. The page is self-contained and requires no build or external assets.
3. Enable GitHub Pages for that new repository from its publishing branch and root directory.
4. Set its custom domain to `myhome.tenguriya.com`.
5. Add a CNAME in Squarespace: host `myhome`, target `tengocharlie.github.io`. Do not alter the car subdomain, root domain, or email records.
6. After the HTTPS certificate is ready, enable Enforce HTTPS and verify the page, both message types, and the QR from a phone. Location requires HTTPS and the visitor's permission.

GitHub Pages is enabled in TengoCharlie/home-door-contact from main. Squarespace now has myhome CNAME tengocharlie.github.io. HTTPS certificate provisioning is pending final verification. Print/mount the updated QR only after its HTTPS access link works.

## Content and privacy

`site-config.json` records the chosen domain and contact settings. This buildless page embeds its current wording and links in `index.html`; editing the JSON alone does not change the page. No data is saved to a server. The visitor reviews and sends the message in their own app. SMS support varies by device; the Copy message option is provided as a fallback.

The contact number is included in the page's links and source. This is a public contact page, not an anonymous relay service. No household address or directions are published.

## QR access gate
The current page requires the random key query parameter embedded in the updated sticker QR. Plain and incorrect links show scan instructions. This is a client-side convenience gate, not secure authentication; copied QR links also work. The contact data remains in the static HTML source.


## Door location check
After QR key validation, visitors must grant precise location within 100 metres of the owner-supplied map centre. Readings with accuracy worse than 100 metres are rejected. Denied permission and timeouts keep contacts hidden. This uses browser geolocation and local distance calculation, with no paid map API. Client-side checks can be bypassed or location-spoofed; the centre and contact data are visible in static source.
