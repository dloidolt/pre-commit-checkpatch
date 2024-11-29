# Linux Kernel Coding Style Pre-commit Hook

This [pre-commit](https://pre-commit.com/) hook ensures C files adhere to the
Linux kernel coding standards using [`checkpatch.pl`](https://www.kernel.org/doc/html/latest/dev-tools/checkpatch.html),
helping maintain code quality and consistency.

## Installation

To add this pre-commit hook to your project, add the following configuration to
your `.pre-commit-config.yaml` file (assuming that you installed pre-commit and
run `pre-commit install` in your repository):

```yaml
repos:
  - repo: 'https://github.com/dloidolt/pre-commit-checkpatch'
    rev: v0.1.0
    hooks:
      - id: checkpatch-files
```

## Customization Options

For a complete list of available arguments, have a look at the [checkpatch documentation](https://www.kernel.org/doc/html/latest/dev-tools/checkpatch.html).

### Ignoring Specific Warnings

To adjust ignored warnings you can customize the arguments passed to
`checkpatch.pl`:

```yaml
repos:
  - repo: 'https://github.com/dloidolt/pre-commit-checkpatch'
    rev: v0.1.0
    hooks:
      - id: checkpatch-files
        args:
          - '--ignore=SPDX_LICENSE_TAG,PREFER_DEFINED_ATTRIBUTE_MACRO'
```

### In-Place Fixes

Enable automatic in-place fixes by adding the `--fix-inplace` argument to `args`:

```yaml
repos:
  - repo: 'https://github.com/dloidolt/pre-commit-checkpatch'
    rev: v0.1.0
    hooks:
      - id: checkpatch-files
        args:
          - '--fix-inplace'
```

## License

This project is licensed under the [GPL-2.0 License](LICENSE).
