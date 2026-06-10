# CloudShop Lab — Cloud Computing & DevOps (Weeks 1–7)

**Read only this file.** Follow the steps **in order**, one at a time.

---

## What to submit

Send your instructor:

1. Your **GitHub repository URL** (public or shared)
2. The completed `**REPORT.md`** file (in the repo)

**Requirements:** GitHub account · Docker Desktop · Python 3.10+

**Note:** you do **not** need an AWS account for a full **40/40** score. AWS is an optional bonus.

---

## Where to work

Open a terminal in the `**cloudshop-tp/`** folder (this is the root of your Git project).

```
TP/en/
  INSTRUCTIONS.md      ← you are here
  cloudshop-tp/        ← do all work here
    docs/              ← phases A, B, C (files to complete)
    REPORT.md          ← complete at the end
    screenshots/       ← screenshots at the end
```

---

## Step 1 — Create the Git repository

```bash
cd cloudshop-tp
git init
git branch -M main
git add .gitignore docs/ screenshots/
git commit -m "chore: init cloudshop repository"
```

Create an empty repository on GitHub, then:

```bash
git remote add origin https://github.com/YOUR_USERNAME/cloudshop-tp.git
git push -u origin main
```

---

## Step 2 — Phase A (Weeks 1 & 2)

1. Open `**docs/phase-a.md**` and answer all questions.
2. Commit **only** this file:

```bash
git add docs/phase-a.md
git commit -m "docs: phase A cloud weeks 1-2"
git push
```

---

## Step 3 — Phase B1 (Week 3, AWS architecture)

1. Open `**docs/phase-b-aws.md**` (diagram, ports, SSH commands — **no VM required**).
2. Commit:

```bash
git add docs/phase-b-aws.md
git commit -m "docs: phase B1 AWS architecture"
git push
```

---

## Step 4 — Phase B2 (Week 4, multi-cloud)

1. Open `**docs/phase-b-multicloud.md**` and complete the table.
2. Commit:

```bash
git add docs/phase-b-multicloud.md
git commit -m "docs: phase B2 multicloud"
git push
```

---

## Step 5 — Phase C (Week 5, DevOps pipeline)

1. Open `**docs/phase-c.md**` (pipeline diagram + 3 questions).
2. Commit:

```bash
git add docs/phase-c.md
git commit -m "docs: phase C devops pipeline"
git push
```

---

## Step 6 — Flask API (Weeks 6 & 7)

Create `**app.py**` at the root of `cloudshop-tp/`:

```python
from flask import Flask, jsonify

app = Flask(__name__)

@app.get("/")
def home():
    return jsonify({"message": "Hello from CloudShop", "status": "ok"})

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

Create `**requirements.txt**`:

```
flask==3.1.0
```

Local test: `python -m pip install -r requirements.txt` then `python app.py` → [http://localhost:5000](http://localhost:5000)

Commit:

```bash
git add app.py requirements.txt
git commit -m "feat: add flask api"
git push
```

---

## Step 7 — Docker (Week 7)

Create `**Dockerfile**`:

```dockerfile
FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY app.py .
EXPOSE 5000
CMD ["python", "app.py"]
```

Create `**.dockerignore**`:

```
__pycache__
.venv
.git
```

Local test:

```bash
docker build -t cloudshop-api .
docker run --rm -p 5000:5000 cloudshop-api
```

→ Take a screenshot of [http://localhost:5000](http://localhost:5000) (save it in `screenshots/` at Step 9).

Commit:

```bash
git add Dockerfile .dockerignore
git commit -m "feat: add dockerfile"
git push
```

---

## Step 8 — GitHub Actions CI (Week 6)

Create the folder and file `**.github/workflows/ci.yml**`:

```yaml
name: CI CloudShop
on:
  push:
    branches: [main]
jobs:
  test-and-build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: "3.10"
      - run: pip install -r requirements.txt
      - run: python -c "import app; print('OK')"
      - run: docker build -t cloudshop-api .
```

Commit and push:

```bash
git add .github/workflows/ci.yml
git commit -m "ci: add github actions pipeline"
git push
```

On GitHub → **Actions** tab → confirm the pipeline is **green**.  
→ Screenshot goes in `screenshots/` at Step 9.

In `**REPORT.md`**, also answer: *“Is GitHub Actions closer to PaaS or IaaS?”* (5 lines).

---

## Step 9 — Final report (Phase F)

1. Complete `**REPORT.md*`* (names, GitHub URL, `git log --oneline`, “Take-home summary” section).
2. Add screenshots to `**screenshots/**` (green CI + local Docker).
3. Commit:

```bash
git add REPORT.md screenshots/
git commit -m "docs: final report"
git push
```

---

## Checklist before submission

- **At least 9 commits** (Steps 1–9)
- GitHub Actions pipeline **green**
- `docker run` tested locally
- `REPORT.md` completed with repository URL
- `git log --oneline` pasted in the report

---

## AWS bonus (+5 pts, optional)

If you create a real AWS VM: add a section in `REPORT.md` (IP, screenshots, **instance terminated**). A dedicated commit is not required.

---

## Troubleshooting


| Problem            | Solution                                        |
| ------------------ | ----------------------------------------------- |
| `pip` not found    | `python -m pip install -r requirements.txt`     |
| Docker won't start | Open Docker Desktop                             |
| Red CI             | Read logs on GitHub Actions; test locally first |
| No AWS account     | Fine — the path without AWS is enough for 40/40 |


---

*GSDUI · L2 · Cloud Computing & DevOps*