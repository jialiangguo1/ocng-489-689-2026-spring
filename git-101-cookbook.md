# Git Cookbook (OCNG 489/689)

## Workflow

1. Generate SSH key and add it to GitHub
2. Fork the class repo
3. Clone your fork
4. Add a file, commit, and push to your fork
5. Open a pull request
6. Pull to sync

---

## 1. Set up SSH

Generate a key:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Press Enter for the defaults.

Show your public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy that output.

On GitHub:

* go to **Settings**
* go to **SSH and GPG keys**
* click **New SSH key**
* paste the key and save

Test the connection:

```bash
ssh -T git@github.com
```

---

## 2. Fork the class repository

Open the class repo in GitHub:

```text
https://github.com/odsl/ocng-489-689-2026-spring
```

Click **Fork**.

This creates your own copy, for example:

```text
https://github.com/YOUR_USERNAME/ocng-489-689-2026-spring
```

---

## 3. Clone your fork

Clone your own fork, not the main class repo:

```bash
git clone git@github.com:YOUR_USERNAME/ocng-489-689-2026-spring.git
cd ocng-489-689-2026-spring
```

Add the class repo as `upstream`:

```bash
git remote add upstream git@github.com:odsl/ocng-489-689-2026-spring.git
```

Check remotes:

```bash
git remote -v
```

You should see:

* `origin` = your fork
* `upstream` = class repo

---

## 4. Add a file, commit, and push

Create a file:

```bash
echo "My first contribution" > test.txt
```

Check status:

```bash
git status
```

Stage the file:

```bash
git add test.txt
```

Commit:

```bash
git commit -m "Add test file"
```

Push to your fork:

```bash
git push origin main
```

---

## 5. Open a pull request

On GitHub:

* open your fork
* click **Contribute**
* click **Open pull request**

Make sure:

* base repository = `odsl/ocng-489-689-2026-spring`
* base branch = `main`
* head repository = your fork
* compare branch = `main`

Then submit the pull request.

---

## 6. Sync your fork

After the class repo changes, sync your local copy.

First get changes from the class repo:

```bash
git pull upstream main
```

Then push the updated version to your fork:

```bash
git push origin main
```

---

## Minimal command list

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
cat ~/.ssh/id_ed25519.pub
ssh -T git@github.com

git clone git@github.com:YOUR_USERNAME/ocng-489-689-2026-spring.git
cd ocng-489-689-2026-spring
git remote add upstream git@github.com:odsl/ocng-489-689-2026-spring.git

echo "My first contribution" > test.txt
git add test.txt
git commit -m "Add test file"
git push origin main

git pull upstream main
git push origin main
```


> Edit locally, commit to your fork, push to GitHub, open a pull request, then sync from upstream.
