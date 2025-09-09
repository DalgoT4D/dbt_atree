# dbt_atree

A dbt (data build tool) project for data transformations using uv as the package manager.

## Prerequisites

- Python 3.11 or higher
- uv package manager (https://docs.astral.sh/uv/getting-started/installation/)

## Setup

1. **Clone this repository**:
   ```bash
   git clone <repository-url>
   cd dbt_atree
   ```

2. **Install dependencies**:
   ```bash
   uv sync
   ```

3. **Configure dbt profile**:
   - Copy the example profiles file:
     ```bash
     cp profiles.yml.example profiles.yml
     ```
   - Edit `profiles.yml` to configure your database connection

4. **Test the setup**:
   ```bash
   # Activate the virtual environment
   source .venv/bin/activate
   
   # Test dbt connection
   dbt debug
   
   # Run the example models
   dbt run
   ```

## Project Structure

```
models/             # SQL model files
example/        # Example models
macros/             # Jinja2 macros
tests/              # Data tests
seeds/              # CSV files for seeding
snapshots/          # Snapshot models
analyses/           # Analytical SQL files
dbt_project.yml     # dbt project configuration
profiles.yml.example    # Example database connection profiles
pyproject.toml          # Project dependencies (managed by uv)
uv.lock                 # Dependency lock file
README.md               # This file
```

## Common Commands

```bash
# Activate virtual environment
source .venv/bin/activate

# Run models
dbt run

# Run tests
dbt test

# Generate documentation
dbt docs generate
dbt docs serve

# Debug connection
dbt debug

# Clean build artifacts
dbt clean
```

## Development

This project uses:
- **uv** for Python package management
- **dbt-core** for data transformations
- **dbt-duckdb** as the default database adapter (lightweight, file-based)

To add new dependencies:
```bash
uv add <package-name>
```

To update dependencies:
```bash
uv sync --upgrade
```