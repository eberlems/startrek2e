# startrek2e – Star Trek 2nd Edition Plugin for LackeyCCG

This repository contains the LackeyCCG plugin for the Star Trek CCG Second Edition game, hosted at [trekcc.org](https://www.trekcc.org).

---

## How to Update the Plugin – Step by Step

> **Prerequisites:** Basic Git knowledge (creating branches, replacing files, opening pull requests) and a text editor.

### 1. Create a Branch

Create a new branch based on the `playable` branch:

```bash
git checkout playable
git pull
git checkout -b update/my-update
```

---

### 2. Download New Card Data

Download the latest card data from the official source:

👉 [https://www.trekcc.org/lackey/2020.php](https://www.trekcc.org/lackey/2020.php)

Then replace the following two files in the repository with the downloaded versions:

| File | Contents |
|---|---|
| `sets/Virtual.txt` | Data for virtual card sets |
| `sets/Physical.txt` | Data for physical card sets |

---

### 3. Add New Card Images

Place any new card images into the following folder:

```
sets/setimages/general/
```

> **Important:** Images must be in **JPG format** and exactly **357 × 499 pixels** in size.

---

### 4. Update the Required Files

Update each of the following files:

#### `changelog.txt`
Briefly describe what changed in this update (e.g. new cards, bug fixes).

#### `formats.txt`
Add the new expansion as a new entry.

#### `uninstall.txt`
- Set the date to **yesterday**
- List all images that were replaced or removed

#### `version.txt`
- Increment the version number
- Add a short description of the changes

#### `updatelist.txt`
- Set the **current date** at the very top of the file

---

### 5. Regenerate the Checksum

Run the following command from the root of the repository to update the checksum of `updatelist.txt`:

```bash
./mkupdate plugins/startrek2e/updatelist.txt
```

> This tells LackeyCCG that a new update is available.

Replace the updatelist.txt with the generated updatelistNEW.txt

---

### 6. Open a Pull Request

Commit all changed files and open a pull request against the `playable` branch:

```bash
git add .
git commit -m "Update: <short description of changes>"
git push origin update/my-update
```

Then open a pull request on GitHub from your branch into `playable`.

---

## Summary – Checklist

- [ ] Created a branch from `playable`
- [ ] Replaced `sets/Virtual.txt`
- [ ] Replaced `sets/Physical.txt`
- [ ] Added new images (357×499 JPG) to `sets/setimages/general/`
- [ ] Updated `changelog.txt`
- [ ] Added new expansion to `formats.txt`
- [ ] Updated `uninstall.txt` with date (yesterday) and replaced images
- [ ] Updated `version.txt` with new version number and description
- [ ] Set date at the top of `updatelist.txt`
- [ ] Regenerated checksum with `./mkupdate`
- [ ] Replace updatelist.txt with updatelistNEW.txt
- [ ] Opened a pull request
