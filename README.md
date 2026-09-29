# AR Smart Desk website — setup guide

This folder is the complete website for **arsmartdesk.com**. It's plain HTML and CSS, with nothing to install or build.

```
index.html       Home page
design.html      Design page (CAD model)
features.html    Features page
404.html         Shown if someone visits a page that doesn't exist
style.css        All the styling for every page
favicon.svg      The little "AR" icon in the browser tab
fonts/           The two fonts the site uses (hosted with the site, no Google needed)
CNAME            Tells GitHub Pages your domain is arsmartdesk.com (don't rename or edit)
images/          Your photos go here
```

---

## Step 1 — Add your photos (about 2 minutes)

The `images/` folder currently holds grey placeholder pictures. Replace each one with your real photo, **keeping the exact same filename**.

Open each link below, right-click the image, choose "Save image as…", and save it into `images/` with the name shown. Overwrite the placeholder when asked.

| Save as | Where it's used | Link to your photo on Wix |
|---|---|---|
| `desk-closeup.jpg` | Home page | https://static.wixstatic.com/media/80744a_f410dd20b66c43a5a5a490aeb2bbbf88~mv2.jpeg |
| `cad-model.png` | Design page | https://static.wixstatic.com/media/80744a_225453cf8448480081ee723074450fe1~mv2.png |
| `benchmark-1.jpg` | Features, top (left) | https://static.wixstatic.com/media/80744a_92a48b3730be43269abce5200d68c2fc~mv2.jpg |
| `benchmark-2.jpg` | Features, top (right) | https://static.wixstatic.com/media/80744a_23f213576b4f4012be0acd3c58ccd146~mv2.jpg |
| `motorized-rails.jpg` | Features, Motorized rails | https://static.wixstatic.com/media/80744a_e5bbef644ad747e8bf3abb70a554d4c3~mv2.jpg |
| `haptic-control.jpg` | Features, Haptic control | https://static.wixstatic.com/media/80744a_1579c7ac46b74124a3429feb029aa17a~mv2.jpg |
| `footprint-mastery.jpg` | Features, Footprint mastery | https://static.wixstatic.com/media/80744a_fb9e27ced4664e4abcaea348473cfe97~mv2.jpg |
| `industrial-strength.jpg` | Features, Industrial strength | https://static.wixstatic.com/media/80744a_ef88053d4bea4661aeb31fef1bdc57b7~mv2.jpg |

If a browser saves a file as `.webp` or `.jpeg` instead of `.jpg`, rename it to match the table exactly. Filenames are case-sensitive once the site is online.

**Tip:** You can open `index.html` by double-clicking it to check everything looks right before going live.

---

## Step 2 — Buy the domain

Buy **arsmartdesk.com** from any registrar. Cloudflare Registrar, Namecheap and Porkbun all sell .com domains at around $10–15 a year and let you edit DNS records easily. Check the renewal price, not just the first-year price.

Don't buy hosting, website builders or email add-ons. You only need the domain.

---

## Step 3 — Put the site on GitHub Pages (free)

1. Create a free account at **github.com** if you don't have one.
2. Click **+** (top right), then **New repository**. Name it `arsmartdesk`, set it to **Public**, and click **Create repository**.
3. On the new repository page, click **uploading an existing file**.
4. Drag in **everything inside this folder** (all the files plus the `images` and `fonts` folders). The files must sit at the top level of the repository, not inside another folder.
5. Click **Commit changes**.
6. Go to **Settings → Pages** (left sidebar).
7. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main**, folder **/ (root)**, then **Save**.
8. Under **Custom domain**, type `arsmartdesk.com` and click **Save**. (The `CNAME` file already contains this, so it may be filled in for you.)

After a minute or two your site is live at `https://YOUR-USERNAME.github.io/arsmartdesk/`. It'll move to arsmartdesk.com once Step 4 is done.

---

## Step 4 — Point the domain at GitHub

In your registrar's dashboard, find **DNS settings** for arsmartdesk.com. Delete any existing A, AAAA or CNAME records for `@` and `www` (registrars often add "parking" records), then add these:

**Four A records** — Host/Name: `@`

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**Four AAAA records** — Host/Name: `@`

```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```

**One CNAME record** — Host/Name: `www`, Value: `YOUR-USERNAME.github.io`
(Use your real GitHub username, with no `/arsmartdesk` on the end.)

If you use Cloudflare, set each record to **DNS only** (grey cloud), not Proxied, at least until HTTPS is working.

DNS changes usually take effect within an hour but can take up to 24 hours.

---

## Step 5 — Turn on HTTPS

Back in **Settings → Pages** on GitHub, once the domain check shows a green tick, tick **Enforce HTTPS**. This option can take up to 24 hours to become available after the DNS change.

Recommended: also verify the domain under your GitHub account's **Settings → Pages → Add a domain**. This stops anyone else from claiming arsmartdesk.com on GitHub.

That's it. Both `arsmartdesk.com` and `www.arsmartdesk.com` will open your site.

---

## Editing the site later

- **Change text:** open the `.html` file on github.com, click the pencil icon, edit, and click **Commit changes**. The live site updates within a minute or two.
- **Change a photo:** upload a new file with the same name into `images/`.
- **Change colours:** they're at the top of `style.css` under `:root`. The cyan accent is `--cyan`.

Once you're done, you can cancel the Wix site or leave it on the free plan. Nothing here depends on it.
