A reusable GitHub Action workflow for checking formatting of Move projects using `movefmt`.

# About Us
MoveBit is a security audit company for the Move ecosystem, with a vision to make the Move ecosystem the most secure Web3.

The MoveBit team consists of security leaders in academia and enterprise world, with 10 years of security experience, and is the first blockchain security company to leverage formal verification in the Move ecosystem.

## ✅ Usage

To use this workflow in your Move project:

### 1. Create a `.github/workflows/format.yml` file in your aptos move project:

```yaml
name: MoveFmt CI

on:
  push:
    branches: [your_branch_name]
  pull_request:
    branches: [your_branch_name]


jobs:
  format-check:
    uses: movebit/movefmt-workflow/.github/workflows/format-check.yml@main
```

### 2. What it does
- Checks out your repo
- Downloads the `movefmt` binary
- Runs `movefmt --emit="diff"` to check formatting

If any files are not correctly formatted, the CI will fail and show the diff.

---

## 📦 Requirements
- Your Move project should be compatible with `movefmt`
- Ensure the formatting rules are correctly configured in your repo

## 🔧 Customization
You can customize:
- Create `movefmt.toml` in root dir for your repo to customize formatting config