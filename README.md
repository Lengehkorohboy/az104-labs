# AZ-104: Microsoft Azure Administrator Labs

Personal lab exercises, scripts, and notes while studying for the **AZ-104: Microsoft Azure Administrator** certification.

## 📋 Progress Tracker

Exam objective areas (weights per Microsoft's current exam skills outline — verify against the latest study guide before your exam):

- [ ] **Manage Azure identities and governance** — `01-identities-governance/`
- [ ] **Implement and manage storage** — `02-storage/`
- [ ] **Deploy and manage Azure compute resources** — `03-compute/`
- [ ] **Implement and manage virtual networking** — `04-networking/`
- [ ] **Monitor and maintain Azure resources** — `05-monitor-maintain/`

Check off each box as you complete and commit the corresponding lab.

## 📁 Repository Structure

```
az104-labs/
├── README.md
├── .gitignore
├── 01-identities-governance/
│   ├── notes.md
│   └── scripts/
├── 02-storage/
│   ├── notes.md
│   └── scripts/
├── 03-compute/
│   ├── notes.md
│   └── scripts/
├── 04-networking/
│   ├── notes.md
│   └── scripts/
└── 05-monitor-maintain/
    ├── notes.md
    └── scripts/
```

## 📝 Lab Notes Format

Each `notes.md` inside a topic folder follows this template:

```markdown
# Lab: <Title>

**Objective:** What this lab covers and why it matters for the exam.

**Azure services used:** e.g., VMs, VNets, NSGs, Storage Accounts

## Steps
1. ...
2. ...

## Commands / Scripts
See `scripts/` folder for the full script.

## Key Takeaways
- Concept 1
- Gotcha or exam tip

## Cleanup
Commands used to delete resources and avoid ongoing charges.
```

## ⚠️ Security Notes

- Never commit subscription IDs, tenant IDs, client secrets, or connection strings.
- Use environment variables, Azure Key Vault, or a local `.env` file (already excluded via `.gitignore`) for any credentials.
- Always run cleanup commands after each lab to avoid unexpected Azure charges.

## 🔧 Prerequisites

- An active Azure subscription (Free Trial or Pay-As-You-Go works fine for labs)
- [Azure CLI](https://learn.microsoft.com/cli/azure/install-azure-cli) or Azure Cloud Shell
- (Optional) [Azure PowerShell module](https://learn.microsoft.com/powershell/azure)
- Git installed locally

## 📚 Resources

- [Microsoft Learn: AZ-104 study guide](https://learn.microsoft.com/certifications/exams/az-104)
- [Azure documentation](https://learn.microsoft.com/azure/)
