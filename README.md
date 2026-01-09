# Test Case: Poetry Fallback - project.requires-python

## Package Manager
Poetry

## Python Version Detection
- **Source**: project.requires-python (fallback within pyproject.toml)
- **Expected Version**: >=3.11
- **Note**: tool.poetry.dependencies.python is ABSENT

## Files Present
- pyproject.toml with:
  - [tool.poetry.dependencies] - NO python field (missing)
  - [project] requires-python = ">=3.11" (SHOULD WIN)
- poetry.lock

## Test Purpose
Test Poetry's fallback behavior when tool.poetry.dependencies.python is missing but project.requires-python exists.
According to Poetry priority: tool.poetry.dependencies.python FIRST, then project.requires-python.
