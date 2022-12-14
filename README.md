# Comment on PR via GitHub Action

A GitHub action to comment on the relevant open PR when a commit is pushed.

## Usage

- Requires the `GITHUB_TOKEN` secret.
- Requires the comment's message in the `msg` parameter.
- Supports `push` and `pull_request` event types.

### Sample workflow

```yaml
name: comment-on-pr example
on: pull_request
jobs:
  example:
    name: sample comment
    runs-on: ubuntu-latest
    steps:
      - name: comment PR
        uses: danielhs1/comment-on-pr@v1.3.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          msg: results.md
          check_for_duplicate_msg: false  # OPTIONAL
          delete_prev_regex_msg: "[0-9]"  # OPTIONAL
          duplicate_msg_pattern: "[A-Z]"  # OPTIONAL
```
