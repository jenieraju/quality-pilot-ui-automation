# Luminai UI Automation

Standalone Playwright UI automation repo for the **Luminai** QualityPilot project.

Same layout QualityPilot uses when it raises a PR into an automation repo.

## Setup

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
playwright install chromium
cp .env.example .env   # set QP_BASE_URL / QP_USERNAME / QP_PASSWORD
```

## Run

```bash
set -a; source .env; set +a
pytest tests/qualitypilot -v
```

Headed:

```bash
QP_HEADED=1 pytest tests/qualitypilot -v
```

## Layout

```
tests/qualitypilot/
  conftest.py      # page / base_url / username / password fixtures
  qp_login.py      # login helpers
  test_*.py        # UI tests exported from QualityPilot
```

Credentials are never committed — use env vars only.
