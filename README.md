# Pydoc-Markdown

Added trailing comma in argument parsing in `docspec-python` + custom formatting style.

Install:

```powershell
pip install git+https://github.com/GreenK173/pydoc-markdown
```

The working directory of the repo needs to contain the following two files.

`.style.yapf`:

```powershell
[style]
based_on_style = facebook
# split_all_top_level_comma_separated_values = true
split_arguments_when_comma_terminated = true
```

`pydoc-markdown.yml`:

```yaml
loaders:
  - type: python
    search_path: ["./src"]

renderer:
  type: markdown
  filename: "api.md"
  insert_header_anchors: False
  code_headers: True
  descriptive_class_title: "Class "
  descriptive_module_title: True
  add_method_class_prefix: True
  add_member_class_prefix: True
  add_full_prefix: True
  classdef_with_decorators: False
  signature_with_decorators: False
  format_code_style: ".style.yapf"
  header_level_by_type: {
    "Module": 2,
    "Class": 3,
    "Method": 4,
    "Function": 4,
    "Variable": 4,
  }

```

The doc generator is run from the console simply by typing `pydoc-markdown`.
