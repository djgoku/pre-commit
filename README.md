## Git Pre-commit for Terraform

### Setup

Run the following commands in your shell to start using this.

``` shell
pip install pre-commit
git clone https://github.com/djgoku/pre-commit.git ~/.githooks
git config --global core.hooksPath ~/.githooks
chmod +x ~/.githooks/pre-commit
```

### Usage

Each time you run `git commit` globally the `~/.githooks/pre-commit` shell
script will run. On success you will get the normal enter commit_msg dialog. On
failure the `pre-commit` output will show which hook failed and why.

### Example

``` shell
djgoku$ git commit
Trim Trailing Whitespace.................................................Passed
Detect AWS Credentials...................................................Passed
Detect Private Key.......................................................Failed
hookid: detect-private-key

Private key found: test

Check for merge conflicts................................................Passed
Terraform fmt........................................(no files to check)Skipped
Terraform docs.......................................(no files to check)Skipped
Terraform validate without variables.................(no files to check)Skipped
Terraform validate with variables....................(no files to check)Skipped
No-tabs checker..........................................................Passed
```

### Current Hooks

*  https://github.com/pre-commit/pre-commit-hooks
** trailing-whitespace
** detect-aws-credentials
** detect-private-key
** check-merge-conflict
* https://github.com/antonbabenko/pre-commit-terraform
** terraform_fmt
** terraform_docs
** terraform_validate_no_variables
** terraform_validate_with_variables
* https://github.com/Lucas-C/pre-commit-hooks
** forbid-tabs
