+++
title = "How to Fix Wrong Git Author Information in Commits"
date = "2025-04-30T00:34:26+09:00"
draft = false
slug = "fix-wrong-git-author"
tags = ["git", "github", "commit", "author", "rebase"]
categories = ["Dev Log"]
+++

> ⚡ TL;DR
>
> ```bash
> git rebase -i HEAD~N
> ```
>
> or
>
> ```bash
> git rebase -i <starting-commit-hash>^
> ```
>
> ```bash
> git commit --amend --author="Name <email>"
> ```
>
> ```bash
> git rebase --continue
> ```
>
> ```bash
> git push --force
> ```
>
> ⚠️ **Warning:** Modifying commits that have already been pushed to a remote repository can cause history conflicts with collaborators. Use this only when working alone!

---

## 📝 Problem: Incorrect Git Author Information

When working on the same GitHub repository across different computers (like work and personal), you might find that your commit author information gets mixed up.  
In my case, I had **set my company account's name and email in the global configuration** for convenience, and that's where the trouble began.

As a result, my commits were being recorded with my company email, making it appear as if multiple people were contributing to the project.

I had to go through each commit to correct the author information and then update the history on GitHub. Here's how I did it:

---

## 🧩 Situation Summary

- Personal and company account information got mixed up in commits
- Wrong names appeared in GitHub Contributors
- Decided to clean up the commit history

---

## 🛠️ Solution Process

### 1. Select Commits with Interactive Rebase

```bash
git rebase -i HEAD~N
```

Or if you want to start rebasing from a specific commit:

```bash
git rebase -i abc1234^
```

> The `^` symbol means "start rebasing from the commit **before** this one."

Or if you want to rebase from the very first commit:

```bash
git rebase -i --root
```

When the list appears, change `pick` to `edit` and save.

> #### 💡 Quick Edit Tip
>
> With cursor on pick: `dw` to delete pick → `i e` to type just the 'e' of edit (just 'e' works too)
> In other words: move cursor, `dw`, `i`, `e`, then save (`:wq`) and you're done!

---

### 2. Modify Author Information

```bash
git commit --amend --author="New Name <newemail@example.com>"
```

This command overwrites the author information for that specific commit with your specified name and email.  
The author you set here only applies to **this specific commit**, so you don't need to modify your global or local settings.

---

### 3. Continue the Rebase

```bash
git rebase --continue
```

After modifying one commit, use this command to move to the next one.  
Repeat this process for all commits you want to fix.

---

### 4. Update GitHub

```bash
git push origin +main
```

Finally, you need to force push to update the remote repository with the new history.  
`+main` is equivalent to `--force` and will overwrite the existing history.

---

## 🧭 Conclusion

After this experience, I removed all global settings.  
Instead, I now manage name and email settings locally in `.git/config` for each project.  
It's a bit more work, but it's a preventive measure to avoid repeating this mistake.

---

> 🗂️ **TMI**  
> By the way... if you've already pushed commits to GitHub and they've registered you as a Contributor, fixing the commits won't change the Contributor list.  
> I ended up deleting the repository and creating a new one... 😇  
> (_This is really a last resort._)

---

This experience taught me how a small mistake can mess up your history.  
I hope this guide helps if you find yourself in a similar situation.

---

> 📚 **References**  
> This post was written with reference to [madplay's blog](https://madplay.github.io/post/change-git-author-name).
