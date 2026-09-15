# RISW Workshop 2026 — Code and Example Project

This repository contains the slides and example code notebooks demonstrated in the RISW
Workshop, along with a biomedical agentic pipeline example project, its tutorial
video, a recorded demo, and slides.

**Jump to:** [Workshop notebooks](#workshop-notebooks) ·
[Example project](#example-project) · [Tutorial video](#tutorial-video) ·
[Recorded demo](#recorded-codex-run) · [Demo Slides](#editable-presentation) ·
[Run the project](#run-the-example-project)

## Workshop notebooks

Use these notebooks to revisit the code examples shown during the workshop.

| Notebook | Topics demonstrated |
| --- | --- |
| [Section 1: Introduction to LLMs](Section_1_Intro_to_LLM.ipynb) | API calls, system prompts, temperature, LangChain, and local model inference |
| [Section 2: Statistical Domain Adaptation](Section_2__Statistical_Domain_Adaptation.ipynb) | Prompt engineering, retrieval-augmented generation (RAG), and supervised fine-tuning |

Open the notebooks in Jupyter or VS Code and follow their setup cells before
running the examples.

## Example project

[Explore the biomedical agentic pipeline](Agentic%20Pipeline%20Demo/).
This project brings skills, tools, hooks, state, and agent coordination together
in an analysis workflow:

**Analysis question → SAP extraction → Data checks → Analysis gate → ANCOVA → Result review**

The fictional study uses synthetic data to demonstrate two outcomes: stopping
when required endpoint data are missing, and completing the analysis when the
data checks pass.

| Project material | Where to find it |
| --- | --- |
| Statistical analysis plan (SAP) | [SAP.md](Agentic%20Pipeline%20Demo/SAP.md) |
| Example datasets | [data/](Agentic%20Pipeline%20Demo/data/) |
| Analysis and workflow skills | [skills/](Agentic%20Pipeline%20Demo/skills/) |
| Data protection and result review hooks | [hooks/](Agentic%20Pipeline%20Demo/hooks/) |

## Tutorial video

Learn how to build the example project, then see it run in Codex.

https://github.com/user-attachments/assets/b553f652-0ef9-4425-8ba3-c73d1812152e

## Recorded Codex run

Watch Codex use the project to check data, run the allowed analysis, and review
the results.

https://github.com/user-attachments/assets/6ce917b2-1d21-4576-9447-b7a791a22f75

## Editable presentation

[Open the PowerPoint deck](videos/RISW_Biomedical_Pipeline_Tutorial.pptx)
for the project tutorial, with editable slides and speaker notes.

## Run the example project

The project uses Python 3.11 or newer with NumPy, pandas, and SciPy.

```text
python -m pip install numpy pandas scipy
```

From the `Agentic Pipeline Demo` directory, run the missing-endpoint example:

```text
python skills/biomed-analysis-workflow/scripts/run_biomed_analysis_workflow.py --sap SAP.md --subject-data data/adsl.csv --efficacy-data data/adeff_results.csv --output-dir output/blocked
```

For the complete-endpoint example, select `data/adeff_week24_pass.csv` and use
a separate output directory, such as `output/week24`. Inspect the data checks,
analysis result, and final review in the generated workflow manifest.

To use the project through an agent conversation, see the
[biomedical analysis workflow skill](Agentic%20Pipeline%20Demo/skills/biomed-analysis-workflow/SKILL.md)
and the [recorded demo](#recorded-codex-run).

## Data and sharing

The example project's SAP and datasets are fictional and synthetic. Preserve
the supplied source files when running analyses; the results are educational
examples, not clinical evidence.

Generated outputs remain local and are excluded from Git. Keep credentials,
personal data, and machine-specific files out of shared contributions.
