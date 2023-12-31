# pyhelper
Helpful info for writing projects on Python

Imaginate ideal project's structure like this:
```
[project]/
├── [library]/
│   ├── __init__.py
│   ├── [main_class_1].py
│   ├── [main_class_n].py
│   ├── ...
│   ├── [module_1]/
│   │   ├── __init__.py
│   │   ├── [class_1_1].py
│   │   └── [class_1_n].py
│   ├── [module_n]/
│   │   ├── __init__.py
│   │   ├── [class_n_1].py
│   │   └── [class_n_n].py
│   └── utils/
│       ├── __init__.py
│       ├── [util_1].py
│       └── [util_n].py
|
├── examples/
│   ├── [criteria_1]/
│   │   ├── [criteria_1_1]_example.py
│   │   └── [criteria_1_n]_example.py
│   ├── ...
│   └── [criteria_n]/
│       ├── [criteria_n_1]_example.py
│       └── [criteria_n_n]_example.py
|
├── docs/
│   ├── api/
│   │   ├── [main_class_1].md
│   │   └── [main_class_n].md
│   ├── examples/
│   │   ├── [criteria_1_1]_example.md
│   │   └── [criteria_n_n]_example.md
│   ├── index.md
│   ├── install.md
│   ├── license.md
│   └── ...
├── docs/
│   ├── api/
│   │   ├── level3_b_1_1/
│   │   └── level3_b_1_3/
│   ├── examples/
│   │   ├── level3_b_2_1/
│   │   └── level3_b_2_3/
│   ├── index.md
│   ├── install.md
│   ├── license.md
│   └── ...

├── .gitignore
├── LICENSE
├── README.md
├── ...
├── pyproject.toml
├── ...
├── mkdocs.yml
└── ...
```

### Documentation

Commands:
```
pip install mkdocs
pip install mkdocs-material
pip install mkdocstrings[python]

cd [project]
mkdocs new .
...
mkdocs build
mkdocs gh-deploy
```

.md Settings for modules:
```
::: [library].[module_1]
    options:
        docstring_options:
            ignore_init_summary: true
        merge_init_into_class: false
        docstring_style: google
        docstring_section_style: table
        show_root_heading: true
        heading_level: 1
        members_order: source
        show_root_members_full_path: true
        show_object_full_path: false
        show_category_heading: false
        separate_signature: false
        show_source: false
        show_submodules: false
```

.md Settings for class:
```
::: [library].[main_class_1]
    options:
        show_root_heading: true
        heading_level: 1
        members_order: source
        show_category_heading: true
        show_source: false
```

mkdocs.yml
```
site_name: vkpymusic docs

nav:
  - Home: index.md
  - API Reference:
    - [main_class_1]: api/ [main_class_1].md
    - [main_class_n]: api/ [main_class_n].md
    - .[module_1]: api/[module_1].md
    - .[module_n]: api/[module_n].md
    - .utils: api/utils.md
  - Installation: install.md
  # - Usage: usage.md
  # - Examples: examples.md
  # - Contributing: contributing.md
  # - Changelog: changelog.md
  - License: license.md

theme:
  name: material
  language: en

plugins:
  - search
  - autorefs
  - mkdocstrings
```

### 

