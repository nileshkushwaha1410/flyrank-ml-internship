# FlyRank Search Intelligence Capstone — Refresh / Content Opportunity Scoring

## Repo layout

```
work/
  notebooks/
    w01_research_question.ipynb   (yours — carry over from Week 1)
    w02_task_framing.ipynb        (yours — carry over from Week 2)
    w03_data_contract.ipynb       (yours — carry over from Week 3)
    w04_baseline_score.ipynb      (yours — carry over from Week 4)
    w05_model.ipynb               (this file — Week 5 model vs. baseline)
  outputs/
    baseline_action_score.csv     (from Week 4)
    model_action_score.csv        (written by w05_model.ipynb)
submission/
  paper_url.txt                   (one line: the direct URL of your deployed paper)
```

## Before running `w05_model.ipynb`

1. Accept the dataset gate at
   https://huggingface.co/datasets/FlyRank/internship-warehouse in your browser.
2. Generate a **read** token and paste it into the `CREATE SECRET` cell.
3. Check real date coverage before trusting the hardcoded window constants —
   run the eligibility + leakage-check cells first and adjust `FEATURE_START` /
   `FEATURE_MID` / `FEATURE_END` / `LABEL_START` / `LABEL_END` if too few
   clients have data in that range.
4. `MIN_TRAILING_IMPRESSIONS`, `POSITION_WORSENING_THRESHOLD`, and
   `CLICK_DROP_THRESHOLD` are judgment calls — the notebook says so; adjust
   and note your reasoning for the paper's Methodology section.

## Deploying the paper

Simplest path — GitHub Pages from this repo:

1. Put the paper (see `paper/index.html` once built) at the repo root or in `/docs`.
2. Repo Settings → Pages → Deploy from branch → `main` → `/ (root)` or `/docs`.
3. Copy the resulting `https://<you>.github.io/<repo>/` URL into
   `submission/paper_url.txt` — that file is the only thing that gets graded.

## Public-safety checklist before publishing

- No client names, domains, raw URLs, or query strings — only the dataset's
  own pseudonymous `client_*` / `content_*` hash IDs.
- No claim that this reverse-engineers or proves causal impact on Google's
  algorithm — keep to "associated with", "observed", "directional".
- Acknowledgments section credits `https://flyrank.ai` and the dataset name.
