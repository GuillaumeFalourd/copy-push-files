# Copy & Push Files action

[![Security Pipeline](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/security_pipeline.yml/badge.svg)](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/security_pipeline.yml) [![Super Linter](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/super-linter.yml/badge.svg)](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/super-linter.yml) [![Gitleaks](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/gitleaks.yml/badge.svg)](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/gitleaks.yml)

[![Action test on Ubuntu](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/ubuntu_action_test.yml/badge.svg)](https://github.com/GuillaumeFalourd/copy-push-files/actions/workflows/ubuntu_action_test.yml)

GitHub Action to copy & push contents (files / directory) from a repository to another :octocat:

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
      # [...] --> steps with actions or commands updating repository files
      - uses: GuillaumeFalourd/copy-push-files@v1
```

### `2️⃣ Full`: Commit and Push with `customized` parameters

```yaml
    steps:
      - uses: actions/checkout@v2.3.4
      # [...] --> steps with actions or commands updating repository files
      - uses: GuillaumeFalourd/copy-push-files@v1
        with:
          email: ${{ github.actor }}[bot]@users.noreply.github.com
          name: ${{ github.actor }}
          commit_message: your_message
          target_branch: branch_name
          source_files: file1.txt file2.txt dir1 dir2
          remote_repository: https://github.com/<owner>/<repo> # public repository
          access_token: ${{ github.token }} # need PAT if private repo
```

* * *

## ▶️ Action Inputs

Field | Mandatory | Default Value | Observation
------------ | ------------  | ------------- | -------------
**email** | NO | `${{ github.actor }}@users.noreply.github.com` | Github user email <br/> _e.g: `octocat@github.com`_
**name** | NO | `${{ github.actor }}` | Github username <br/> _e.g: `octocat`_
**commit_message** | NO | `Commit performed using Copy and Push Files action` | Commit message
**target_branch** | YES | `copy-push-files-branch` | Branch to push the contents on the other repository
**target_dir** | YES | `repository root` | Directory to push the contents on the other repository
**source_files** | YES | `.` | Files to add separated by space <br/> _e.g: `file1 file2 directory1 directory2/file3`_
**remote_repository** | NO | `-` | Repository url to push the code <br/> _e.g: `https://github.com/<owner>/<repo>`_
**access_token** | NO | `${{ github.token }}` | [Personal Access Token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) is necessary if push to another repository

* * *

## 🤝 Contributing

☞ [Guidelines](https://github.com/GuillaumeFalourd/copy-push-files/blob/main/CONTRIBUTING.md)

## 🏅 Licensed

☞ This repository uses the [Apache License 2.0](https://github.com/GuillaumeFalourd/copy-push-files/blob/main/LICENSE)
