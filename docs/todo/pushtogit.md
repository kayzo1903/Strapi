## Remove the old remote

If the link shown is incorrect (for example, still showing `yourusername/my-project.git`), remove it:

```bash
git remote remove origin
```

---

## Add your correct GitHub repo link

👉 `https://github.com/kayzo1903/Strapi.git`

So run:

```bash
git remote add origin https://github.com/kayzo1903/Strapi.git
```

---

### 🚀 4. Push 

Now push your code to GitHub:

```bash
git push -u origin main
```

### 💡 Pro Tip

If you ever want to rename your repo or fix the connection again, just repeat:

```bash
git remote remove origin
git remote add origin https://github.com/yourusername/new-repo.git
```

---
