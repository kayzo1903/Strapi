Perfect — you’re running into a **very common Strapi on Render issue** ✅

Let’s break it down clearly 👇

---

### 🧠 What’s happening

The error says:

> `Error: Knex: run $ npm install pg --save`
> `Cannot find module 'pg'`

Strapi uses the **`pg` (PostgreSQL)** package to connect to your database.
However, Render didn’t find it installed in your project — so the build fails when Strapi tries to connect to Postgres.

---

### 💡 The fix

You need to **install `pg` locally and redeploy** so Render includes it in your dependencies.

#### Step 1: Open your project folder

In your Strapi project directory, run:

```bash
npm install pg
```

> This installs the PostgreSQL client library needed by Knex and Strapi.

---

#### Step 2: Commit and push to GitHub

After installation, commit the updated `package.json` and `package-lock.json`:

```bash
git add package.json package-lock.json
git commit -m "Add pg dependency for PostgreSQL"
git push origin main
```

---

#### Step 3: Redeploy on Render

Render will automatically detect the new commit and rebuild the app.
It will now install `pg` during build and successfully connect to your Postgres database.

---

### ✅ Bonus tip

To prevent future issues, make sure your `DATABASE_CLIENT` in `.env` is lowercase:

```
DATABASE_CLIENT=postgres
```

(You currently have `PostgreSQL`, which can cause issues — it must be exactly `postgres`.)

---

Would you like me to show you a **clean example `.env` file** for your Strapi + Render setup (that’s known to work)?
