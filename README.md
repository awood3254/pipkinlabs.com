# pipkinlabs.com placeholder site

Plain HTML, no build step. Files:

- `index.html`: the coming-soon page (Pipkin Labs + MochiBoost card + contact + company details)
- `privacy.html`: short website privacy notice
- `assets/`: logos, Mochi, favicon (resized from Branding/Claude - Brand_Assets.zip)
- `CNAME`: tells GitHub Pages which domain to serve

## Before you go live

1. Company number (17517786) and registered office are filled in and match Companies House (checked 27 Oct 2026).
2. **Email.** Set up `hello@pipkinlabs.com` in Porkbun: Domain Management > pipkinlabs.com > Email > Email Forwarding, and forward it to your normal inbox. It's free.

## Recommended hosting: GitHub Pages (free, HTTPS included)

1. On github.com, create a new **public** repository, e.g. `pipkinlabs.com`.
2. Click "uploading an existing file" and drag in everything from this folder (including `assets/` and `CNAME`). Commit.
3. Repo **Settings > Pages**: Source = "Deploy from a branch", Branch = `main`, folder `/ (root)`. Save.
4. In **Porkbun > Domain Management > pipkinlabs.com > DNS**, delete any existing ALIAS/A/CNAME records for the root and `www` (often Porkbun's parking page), then add:

   | Type  | Host  | Answer                   |
   |-------|-------|--------------------------|
   | A     | (blank) | 185.199.108.153        |
   | A     | (blank) | 185.199.109.153        |
   | A     | (blank) | 185.199.110.153        |
   | A     | (blank) | 185.199.111.153        |
   | CNAME | www   | `<your-github-username>.github.io` |

5. Back in **Settings > Pages**, the custom domain should show `pipkinlabs.com`. Once the DNS check passes (minutes to a few hours), tick **Enforce HTTPS**.

Don't touch the MX records if you've set up email forwarding.

To update the site later: edit the file on GitHub, commit, and it redeploys in about a minute.

## Alternative: Porkbun Static Hosting ($30/yr after a 15-day trial)

Fewer DNS steps since the domain is already there, but it costs money for something GitHub does free.
Domain Management > click the house icon in the "Website" column for pipkinlabs.com > Static Hosting > Start Trial, then upload the files with the built-in editor. Guide: https://kb.porkbun.com/article/137-how-to-set-up-static-hosting
