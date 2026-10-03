# Patent Office Action: test PDFs

Example office-action PDFs for trying the **Upload PDF** tab of
[Patent Office Action AI](https://github.com/Abhishek2005-Siva/patent-office-action-ai), which scores how
strong an examiner's rejection is, estimates the chance of overcoming it, and drafts a response letter.

> **These are synthetic.** The text was written to mirror real MPEP / 37 CFR rejection phrasing, but it is
> not a real USPTO document, and the application numbers and cited patents are made up. Each page says so
> in its footer. Please don't use them as legal references.

## The files

| PDF | Rejections | What it shows |
|---|---|---|
| [example_office_action_multi_rejection.pdf](example_office_action_multi_rejection.pdf) | § 102 and § 103, claims 1, 2, 6, 7, 8 | A realistic mix: one strong anticipation rejection and an obviousness rejection built on three references |
| [example_office_action_weak_103.pdf](example_office_action_weak_103.pdf) | § 103, claims 1-3 | A weak rejection with no stated motivation to combine, so the odds of overcoming it are good |
| [example_office_action_strong_103.pdf](example_office_action_strong_103.pdf) | § 103, claims 1-5 | A strong rejection that spells out the motivation to combine |

## What the app should report

Template mode (no API key) gives these numbers, so you can check the app is working:

| PDF | Rejection strength | Chance of overcoming | Statutes | Rejected claims | Cited references |
|---|---|---|---|---|---|
| multi_rejection | 71 / 100 | 20% | § 102, § 103 | 1, 2, 6, 7, 8 | US 6,777,888 · US 7,888,999 · US 8,999,000 |
| weak_103 | 2 / 100 | 75% | § 103 | 1-3 | US 5,111,222 · US 6,222,333 |
| strong_103 | 86 / 100 | 20% | § 103 | 1-5 | US 7,444,555 · US 8,555,666 |

## How to use them

1. Download a PDF (open it on GitHub and use the download button).
2. In the app, open **Upload PDF** and choose the file.
3. Click **Analyze**.

Scores come from a transparent heuristic, not a trained model, and the response letter is a draft. This is
not legal advice.

## Regenerating

The PDFs are built from plain-text samples by
[`scripts/make_sample_pdfs.py`](https://github.com/Abhishek2005-Siva/patent-office-action-ai/blob/main/scripts/make_sample_pdfs.py)
in the main repository.
