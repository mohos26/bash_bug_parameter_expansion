# 🐞 Bash Bug: Extra Space in Parameter Expansion

In July 2025, I discovered a subtle bug in Bash related to parameter expansion when combining a variable with a quoted string and a trailing `$`.

## 💡 The Bug

```bash
export S=" "
echo $S"hello"$
```

### 🔴 Actual Output:
```
 hello$
```

### ✅ Expected Output:
```
hello$
```

This unexpected space suggests a bug in how Bash parses or expands variables when combined with quoted strings and special symbols.

---

## 🧾 Report

I reported this bug to the GNU Bash maintainers through Savannah. The official bug ID is:

- 🔗 [Bug #67358 on Savannah](https://savannah.gnu.org/bugs/?67358)

The issue was confirmed and fixed in the development branch by **Chet Ramey**, the Bash maintainer.

---

## 🔐 Verified Developer Response (PGP Signed)

Chet Ramey responded with two digitally signed messages confirming the bug and its fix.

You can find the original signature files here:

- [chet-response-1.asc](chet-response-1.asc)
- [chet-response-2.asc](chet-response-2.asc)

You can verify the signatures using GPG:

```bash
gpg --verify chet-response-1.asc
gpg --verify chet-response-2.asc
```

---

## 📂 Files

- `test_case.sh` – Minimal test case showing the bug
- `report.txt` – Full bug report as submitted
- `links.md` – References to Bash and bug tracker
