

## 1. What is `uv`?

`uv` is a **fast Python package, dependency, and virtual environment manager** created by **Astral Software**, the company founded by **Charlie Marsh** — the same team behind the popular Python linter **`ruff`**.

It is designed to replace tools like:

* pip
* venv / virtualenv
* pip-tools
* poetry / pipenv

in one unified CLI — while being dramatically faster because it is written in **Rust**.

In short:

`uv = pip + venv + poetry (but simpler and faster)`

---

## 2. When and why was `uv` created?

### Who created it?

* Company: **Astral**
* Founder: **Charlie Marsh**
* Core team: Astral engineering team

### When was it introduced?

* **Initial public release:** **2024**
* **Actively developed through:** 2024–present

`uv` was created because Python developers previously needed multiple tools for:

* `venv` for environments
* `pip` for installs
* `requirements.txt` for locking
* poetry for project workflows

This created:

* slow installs
* complex tooling
* fragmented workflows

`uv` fixes this by:

* including environment management
* handling dependency resolution
* supporting lock files
* running tools directly
* supporting multiple Python versions
* installing extremely fast

It aims to become the **modern default Python workflow tool**.

---

## 3. Installation

Note: `uv` ships with a **Python runtime**, so Python does not need to be installed beforehand.

### macOS / Linux

```
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### Windows (PowerShell)

```
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Verify:

```
uv --version
```

---

## 4. Core Concepts

`uv` manages:

1. Dependencies
2. Virtual environments
3. Python versions
4. Lock files

all from one CLI.

It uses:

* `pyproject.toml` for configuration
* `uv.lock` for reproducibility
* `.venv/` for environments

This ensures deterministic builds and consistent installs.

---

## 5. Basic Workflow (Recommended)

### Step 1 — Create project

```
mkdir myproject
cd myproject
```

### Step 2 — Create virtual environment

```
uv venv
```

### Step 3 — Activate

macOS / Linux:

```
source .venv/bin/activate
```

Windows:

```
.venv\Scripts\activate
```

### Step 4 — Add dependencies

```
uv add requests
```

This automatically updates:

* pyproject.toml
* uv.lock

---

## 6. Installing Dependencies

Install one:

```
uv add pandas
```

Install multiple:

```
uv add numpy pandas matplotlib
```

Development dependencies:

```
uv add --dev pytest
```

Remove:

```
uv remove pandas
```

---

## 7. Running Code

Run scripts without manually activating environments:

```
uv run main.py
```

Run Python directly:

```
uv run python
```

Run modules:

```
uv run python -m http.server
```

---

## 8. Dependency Locking

Create lock file:

```
uv lock
```

Install from lock:

```
uv sync
```

This ensures deterministic builds.

---

## 9. Virtual Environments

Create:

```
uv venv
```

Create in custom directory:

```
uv venv .env
```

Use existing environment:

```
uv sync
```

List Python versions:

```
uv python list
```

---

## 10. Python Version Management

Install a Python version:

```
uv python install 3.12
```

List installed:

```
uv python list
```

Run with specific version:

```
uv run --python 3.12 main.py
```

This removes the need for pyenv.

---

## 11. Searching Packages

```
uv search django
```

---

## 12. Running Tools Without Installing Globally

```
uv run black .
```

This creates a temporary environment.

---

## 13. Project Files Created

Typical layout:

```
myproject/
  pyproject.toml
  uv.lock
  .venv/
  main.py
```

---

## 14. Performance

Real-world install speed comparison:

| Tool   | Install large dependency set |
| ------ | ---------------------------- |
| pip    | 30–60 seconds                |
| poetry | 20–40 seconds                |
| uv     | 2–5 seconds                  |

This speed advantage is one of the main reasons developers are switching to `uv`.

---

## 15. Comparison with Other Tools

### uv vs pip

* pip installs packages only
* uv manages environments + locking + installs

### uv vs poetry

* poetry is feature-rich but slower
* uv is simpler and faster

### uv vs conda

* conda handles non-Python binaries (useful for ML)
* uv focuses on Python ecosystem

They can coexist.

---

## 16. When Should You Use `uv`?

Best for:

* Web development
* APIs
* Automation
* Data science
* Packaging projects
* Team environments

Less ideal if:

* You depend heavily on compiled system packages and prefer conda

---

## 17. Common Mistakes and Fixes

### Mixing pip and uv

Avoid:

```
pip install ...
```

Use:

```
uv add ...
```

---

### Forgetting to sync lock file

Fix:

```
uv sync
```

---

### Creating venv manually

No need:

```
uv venv
```

---

## 18. Uninstalling `uv`

macOS/Linux:

```
rm -rf ~/.local/bin/uv
```

Windows:
Remove via install location or reinstall script flag.

---

## 19. Advanced Features

* Editable installs
* Workspaces
* PyPI mirror configuration
* Build caching
* Tool runner mode
* Reproducible environments

---

## 20. Final Summary

### Key Facts

| Item                 | Details                                            |
| -------------------- | -------------------------------------------------- |
| Name                 | uv                                                 |
| Created by           | Astral Software                                    |
| Founder              | Charlie Marsh                                      |
| First public release | 2024                                               |
| Language             | Rust                                               |
| Purpose              | Unified Python workflow tool                       |
| Replaces             | pip, venv, pip-tools, poetry (partly), pipx, pyenv |
| Status               | Actively developed                                 |

`uv` is:

* fast
* simple
* modern
* reliable

and is rapidly becoming the standard Python workflow manager.

You can safely think of it as:

**A faster, cleaner replacement for pip + venv + poetry.**

Written By: Riti Rai 

