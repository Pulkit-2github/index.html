# BachatKaro — your affiliate deals site

A free, self-contained website (`index.html`) for sharing your EarnKaro affiliate
links from Flipkart, Myntra, Ajio, mCaffeine, The Derma Co, Croma, The Man
Company, Shopsy and credit cards — with search, category filters, WhatsApp
sharing, and optional auto-sync from a Google Sheet.

Everything is in **one file**, so hosting it is just uploading that one file.

---

## 1. See it work right now
Just double-click `index.html` (or open it in a browser). It loads with demo
deals so you can see exactly how it looks and behaves before touching anything.

---

## 2. Add your real deals — pick ONE option

### Option A (easiest, recommended): a Google Sheet
No coding, ever. You just fill in a spreadsheet and the site updates itself.

1. Create a new Google Sheet with **exactly** these column headers in row 1:
   `category | brand | name | mrp | price | image | link | tag`
   - `category`: e.g. `Fashion`, `Beauty`, `Electronics` (or add your own — new
     categories automatically get their own filter button on the site)
   - `mrp`: original price (number only, no ₹ symbol)
   - `price`: your discounted/deal price (number only)
   - `image`: a direct image URL (optional — leave blank to use the built-in
     placeholder art)
   - `link`: your EarnKaro affiliate link for that product
   - `tag`: optional badge text like `Bestseller` or `Hot Deal` (optional)
2. Fill in one row per product.
3. Click **File → Share → Publish to web**. Under "Link", choose your sheet
   tab, set the format to **CSV**, and click **Publish**. Copy the link it
   gives you.
4. Open `index.html` in any text editor, find this line near the top of the
   `<script>` section:
   ```js
   SHEET_CSV_URL: "",
   ```
   and paste your link between the quotes.
5. Save the file. Every time you edit the Google Sheet, the live site picks up
   the change automatically the next time someone loads the page — no
   re-uploading needed.

### Option B: edit the code directly
If you'd rather not use a spreadsheet, open `index.html`, find the
`DEMO_DEALS` array (also near the top of the `<script>` section), and edit it
directly — it's a plain list of `{ category, brand, name, mrp, price, image,
link, tag }` entries. Copy an existing line, change the values, done.

Credit cards work the same way, in the `CREDIT_CARDS` array just below.

---

## 3. Put your site online for free

Any of these work well and cost nothing:

**GitHub Pages**
1. Create a free GitHub account and a new repository.
2. Upload `index.html` to it.
3. Go to the repo's Settings → Pages → set the source to your main branch.
4. Your site is live at `https://yourusername.github.io/repo-name`.

**Netlify (drag-and-drop, no account needed to try)**
1. Go to app.netlify.com/drop
2. Drag the folder containing `index.html` onto the page.
3. Netlify gives you a live URL instantly. Free accounts let you add a custom
   subdomain and keep it long-term.

**Vercel** works the same way if you prefer it — import the file/folder and
deploy.

Once live, share that URL anywhere: WhatsApp status, Instagram bio, Telegram
channel, etc.

---

## 4. A few things worth knowing

- **Affiliate disclosure**: the footer already includes one. Keep it — most
  ad networks, EarnKaro's terms, and Indian ASCI guidelines expect a clear
  disclosure when you're earning a commission on links you share.
- **Images**: the demo uses simple placeholder icon art (no external image
  files), so nothing ever breaks or looks unfinished. When you're ready, the
  easiest real photos to use are the ones EarnKaro shows you on its own "Make
  Links" / deals page when you pick a product — they're provided specifically
  for sharing.
- **Discounts are calculated automatically** from the `mrp` and `price` you
  enter — you never need to work out the percentage yourself.
- **New categories appear automatically.** Add a product with a category that
  doesn't exist yet (e.g. `Home`), and a matching filter pill shows up on the
  site without any code changes.
