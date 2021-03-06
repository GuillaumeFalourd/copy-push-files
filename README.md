# Copy & Push Files action

[![Action test on Ubuntu](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/ubuntu-action-test.yml/badge.svg)](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/ubuntu-action-test.yml) [![Action test on MacOS](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/macos-action-test.yml/badge.svg)](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/macos-action-test.yml) [![Action test on Windows](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/windows-action-test.yml/badge.svg)](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/windows-action-test.yml)

[![Security Pipeline](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/security-pipeline.yml/badge.svg)](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/security-pipeline.yml) [![Gitleaks](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/gitleaks.yml/badge.svg)](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/gitleaks.yml)

![](https://user-images.githubusercontent.com/22433243/148292745-102e17fe-9277-46e9-ab52-468be5cf3240.png)

☞ GitHub Action to copy & push contents (files / directory) from a repository to another :octocat:

_**Note**: This action is supported on **all runners** operating systems (`ubuntu`, `macos`, `windows`)_

* * *

## 📚 Usage

[![Public workflows that use this action.](https://img.shields.io/endpoint?url=https%3A%2F%2Fapi-endbug.vercel.app%2Fapi%2Fgithub-actions%2Fused-by%3Faction%3DGuillaumeFalourd%2Fcopy-push-files%26badge%3Dtrue)](https://github.com/search?o=desc&q=GuillaumeFalourd+copy-push-files+path%3A.github%2Fworkflows+language%3AYAML&s=&type=Code)

### ⚠️ Requirements

- The [`actions/checkout`](https://github.com/marketplace/actions/checkout) is mandatory to use this action, as it will be necessary to access the repository files.

### `1️⃣ Minimal`: Commit and Push with `default` parameters

```yaml
    steps:
      - uses: actions/checkout@v2.3.4
      - uses: GuillaumeFalourd/copy-push-files@v1
        with:
          source_files: file1 file2 directory1 directory2/file3
          remote_repository: https://github.com/<owner>/<repo>
          access_token: ${{ secrets.ACCESS_TOKEN }}
```

### `2️⃣ Full`: Commit and Push with `customized` parameters

```yaml
    steps:
      - uses: actions/checkout@v2.3.4
      - uses: GuillaumeFalourd/copy-push-files@v1
        with:
          email: ${{ github.actor }}[bot]@users.noreply.github.com
          name: ${{ github.actor }}
          commit_message: your_message
          target_branch: branch_name
          source_files: file1 file2 directory1 directory2/file3
          remote_repository: https://github.com/<owner>/<repo>
          access_token: ${{ secrets.ACCESS_TOKEN }}
```

* * *

## ▶️ Action Inputs

Field | Mandatory | Default Value | Observation
------------ | ------------  | ------------- | -------------
**email** | NO | `${{ github.actor }}@users.noreply.github.com` | Github user email <br/> _e.g: `octocat@github.com`_
**name** | NO | `${{ github.actor }}` | Github username <br/> _e.g: `octocat`_
**commit_message** | NO | `Commit performed using Copy and Push Files action` | Commit message
**target_branch** | NO | `copy-push-files-branch` | Branch to push the contents on the other repository
**target_dir** | NO | `repository root` | Directory to push the contents on the other repository
**source_files** | YES | N/A  | Files to add separated by space <br/> _e.g: `file1 file2 directory1 directory2/file3`_
**remote_repository** | YES | N/A | Repository url to push the code <br/> _e.g: `https://github.com/<owner>/<repo>`_
**access_token** | YES | N/A | [Personal Access Token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) is necessary to push to another repository

* * *

## 🤝 Contributing

☞ [Guidelines](https://github.com/GuillaumeFalourd/copy-push-files/blob/main/CONTRIBUTING.md)

## 🏅 Licensed

☞ This repository uses the [Apache License 2.0](https://github.com/GuillaumeFalourd/copy-push-files/blob/main/LICENSE)
