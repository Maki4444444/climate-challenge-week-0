## Climate Challenge: Week 0

### Project Structure

climate-challenge-week0/
├── .github/
│   └── workflows/
│       └── ci.yml          # GitHub Actions CI pipeline
├── .vscode/
│   └── settings.json       # VS Code workspace settings
├── .gitignore
├── requirements.txt
├── README.md
├── src/                    # Source modules (importable Python packages)
├── notebooks/
│   ├── __init__.py
│   └── README.md           # Notebook naming conventions
├── tests/
│   └── __init__.py         # Unit tests (pytest)
└── scripts/
    ├── __init__.py
    └── README.md           # Runnable pipeline scripts

### Reproducing the Environment

#### Prerequisites

- Python **3.11** or **3.12**
- `git`
- (Optional) `conda` or `pyenv` for Python version management


#### Option A `venv` (recommended)

bash
#### 1. Clone the repository
git clone https://github.com/Maki4444444/Climate-challenge-week0.git
cd climate-challenge-week0

#### 2. Create and activate virtual environment
python -m venv venv

#### On macOS / Linux:
source venv/bin/activate

#### On Windows (PowerShell):
.\venv\Scripts\Activate.ps1

#### 3. Upgrade pip and install dependencies
pip install --upgrade pip
pip install -r requirements.txt

#### 4. Verify installation
python --version
python -c "import pandas, numpy, sklearn; print('All packages OK')"


### Option B `conda`

bash
#### 1. Clone the repository
git clone https://github.com/Maki4444444/Climate-challenge-week0.git
cd climate-challenge-week0

#### 2. Create conda environment
conda create -n climate-challenge python=3.11 -y
conda activate climate-challenge

#### 3. Install dependencies
pip install -r requirements.txt

#### 4. Verify
python --version
python -c "import pandas, numpy, sklearn; print('All packages OK')"


### Running Tests

bash
pytest tests/ -v

### CI / CD

The GitHub Actions workflow (`.github/workflows/ci.yml`) runs automatically on every push and pull request to `main`. It:

1. Sets up Python 3.11 and 3.12
2. Caches pip dependencies for speed
3. Runs `pip install -r requirements.txt`
4. Lints with `flake8`
5. Executes `pytest tests/`


### Branching Strategy

| Branch | Purpose |
|---|---|
| `main` | Stable, production-ready code |
| `setup-task` | environment setup (merged via PR) |
| `week-N-*` | saily feature/analysis branches |

All changes to `main` go through **Pull Requests**.
