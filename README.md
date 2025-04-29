# 📝 Seobaeksol Dev Blog (Hugo Source)

This is the **source repository** for [seobaeksol.github.io](https://seobaeksol.github.io),  
a multilingual technical blog powered by [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

> 📌 **Live Site:** [https://seobaeksol.github.io](https://seobaeksol.github.io)

---

## 📁 Project Structure

```
.
├── archetypes/
├── assets/
├── content/
│   ├── ko/           # Korean posts
│   └── en/           # English posts
├── layouts/
├── static/
├── themes/
│   └── PaperMod/     # Git submodule
├── hugo.toml         # Hugo configuration
├── .github/workflows/deploy.yml # GitHub Actions for auto-deploy
└── public/           # ⚠️ DO NOT TRACK (build output)
```

---

## 🚀 Deployment Workflow

This repository uses **GitHub Actions** to automatically build and deploy the blog to [`seobaeksol.github.io`](https://github.com/seobaeksol/seobaeksol.github.io).

### 🛠 Trigger:

- `main` branch push to `blog-src`

### ⚙️ What happens:

1. Hugo builds the site using `hugo --minify`
2. The `public/` directory is pushed to the `main` branch of `seobaeksol.github.io`

---

## 🧪 Local Development

```bash
# Clone with submodules
git clone --recurse-submodules https://github.com/seobaeksol/blog-src.git

# Start local dev server
hugo server -D
```

Visit: [http://localhost:1313/](http://localhost:1313/)

---

## 🌐 Multilingual Structure

- Korean posts: `content/ko/posts/`
- English posts: `content/en/posts/`

To create a bilingual post, create files with the same name in both folders:

```bash
content/ko/posts/my-article.md
content/en/posts/my-article.md
```

Hugo automatically links them as translations.

---

## 📦 Git Tips

- Do **not** track `/public/` in this repository (see `.gitignore`)
- Deployment target (`seobaeksol.github.io`) is managed separately
- To manually trigger deploy:

```bash
hugo --minify
cd public
git init
git remote add origin https://github.com/seobaeksol/seobaeksol.github.io.git
git checkout -b main
git add .
git commit -m "Manual deploy"
git push -f origin main
```

---

## 🧙 Author

**Seobaeksol**  
Dev, Writer, Explorer  
[https://seobaeksol.github.io](https://seobaeksol.github.io)

---

## 📄 License

This repository is licensed under the MIT License.
