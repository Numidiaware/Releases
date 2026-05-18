# 📦 Numidiaware Release Hub

Welcome to the **Numidiaware Release Hub**. This repository serves as the central, automated distribution center for all Numidiaware software products. 

It acts as a **headless CMS / Database** for the [Numidiaware Solutions Website](https://github.com/Numidiaware/solutions), providing real-time versioning data, release notes, and secure binary downloads.

---

## 🏗️ Architecture

This repository is **100% automated** by GitHub Actions. **Do not manually edit the JSON files**, as they will be overwritten by the CI/CD pipeline.

**The Pipeline Flow:**
1. A new release is published in one of our private source-code repositories (e.g., *PC Control Suite*).
2. A GitHub Action inside the private repo triggers instantly.
3. The compiled `.exe` is securely uploaded to **this** repository's [Releases Tab](../../releases).
4. The Action updates `registry.json` and the product's specific `releases.json` with the new patch notes, file sizes, and SHA-256 checksums.
5. The public website fetches the JSON files and renders the updates instantly.

---

## 📂 Repository Structure

```text
Numidiaware/releases/
├── registry.json                        # Master index of all available apps
└── apps/
    ├── pc-control-suite/
    │   ├── icon.svg                     # App logo
    │   └── releases.json                # Full version history & changelog
    └── folder-comments/
        ├── icon.svg
        └── releases.json