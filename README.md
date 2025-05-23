# Arbeidstilsynet/action-parent-dir

Action to get the parent directory of a path.

## Requirements

- The action must run on a runner with `bash` available (e.g., Ubuntu runners).

## Inputs

| Name | Description | Required |
|------|-------------|----------|
| path | The path to get the parent directory for | Yes |

## Outputs

| Name | Description |
|------|-------------|
| parent_dir | The parent directory of the input path |

## Usage

```yaml
jobs:
  get-parent-dir:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Get parent directory
        uses: Arbeidstilsynet/action-parent-dir@v1
        id: get_parent_dir
        with:
          path: './some/subdir/file.txt'

      - name: Use parent directory
        run: echo "Parent dir is ${{ steps.get_parent_dir.outputs.parent_dir }}"
```
