# 📄 Iagon Public Audit Reports

This repository contains public audit documents related to Iagons infrastructure, security, and smart contracts. Each audit is provided as a PDF file, along with a SHA-256 checksum file for integrity verification.

## 📂 Table of Contents

| Date       | Audit Description           | File                        |
|------------|-----------------------------|-----------------------------|
| 2024 Q1    | Tech Sheet | [audits/tech-bullseye-2020.pdf](audits/tech-bullseye-2020.pdf) |

> More reports will be added here as they become available.

## 🔐 File Integrity Verification

To verify that a downloaded PDF file has not been tampered with or corrupted, you can check its SHA-256 checksum against the trusted checksum provided in the `checksums/sha256sums.txt` file.

### ✅ Steps (PowerShell CLI on Windows)

1. Open PowerShell in the folder where the PDF is located.

2. Run the following command to generate the checksum:

   ```powershell
   Get-FileHash .\audits\2024-Q1-Audit.pdf -Algorithm SHA256
   ``` 

### ✅ Steps (Linux CLI)

1. Open a terminal in the root folder of the repository or where the PDF is located.

2. Run the following command to generate the SHA-256 checksum:

   ```bash
   sha256sum audits/2024-Q1-Audit.pdf
   ```

## ➕ Adding a New Audit File

To add a new audit report to the repository:

1. Place the new PDF file in the `audits/` directory.

2. Generate its SHA-256 checksum and append it to the checksum file:

   ### On Windows (PowerShell)
   ```powershell
   Get-FileHash .\audits\2024-Q2-Audit.pdf -Algorithm SHA256 | ForEach-Object {
       "$($_.Hash.ToLower())  audits/2024-Q2-Audit.pdf" | Out-File -Append checksums\sha256sums.txt -Encoding utf8
   }
   ```

   ### On Linux/macOS
   ```bash
   sha256sum audits/2024-Q2-Audit.pdf >> checksums/sha256sums.txt
   ```

3. Add a new entry to the **Table of Contents** section in this README.

4. Commit the changes
