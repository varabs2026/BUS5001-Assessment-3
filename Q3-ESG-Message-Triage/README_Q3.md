# Q3 -- ESG Message Triage Using an LLM API

## Overview

This folder contains the code and experiment outputs for Question 3 of
BUS5001 Assessment 3. The experiment evaluates an API-based large
language model (LLM) for classifying short ESG and
sustainability-related messages, then compares its outputs with a simple
Python rule-based baseline.

The experiment uses the Cohere API with the `command-r-08-2024` model.
The API key is read from the Colab secret named `COHERE_API_KEY`; it
must not be committed to this repository.

## Objective

The aim is to test whether an LLM can assign structured triage fields to
short messages so that a message can be directed to an appropriate team.
The experiment is a small proof of concept, not a production
incident-management system.

## Input examples

Three example messages were evaluated:

1.  "There is a water leak in Building C that has been running all
    morning."
2.  "The accessible entrance near the main building has been blocked for
    two days."
3.  "One of our suppliers may not meet our sustainability policy. Please
    investigate."

These examples cover a facilities-related issue, an accessibility issue,
and a supplier-sustainability concern.

## LLM output fields

The experiment asks the model to return structured JSON using permitted
fields such as:

-   `category`
-   `urgency`
-   `sentiment`
-   `requires_follow_up`
-   `assigned_team`
-   `sensitivity`

The response is checked for valid JSON and for values that comply with
the experiment's permitted fields. The model's output is then compared
with the rule-based baseline.

## Observed results

  ----------------------------------------------------------------------------------------------------------------
  Message          LLM category                Urgency    Sentiment    Follow-up   Assigned team     Sensitivity
  ---------------- --------------------------- ---------- ------------ ----------- ----------------- -------------
  Water leak in    `WATER`                     `HIGH`     `NEGATIVE`   `Y`         `FACILITIES`      `LOW`
  Building C                                                                                         

  Blocked          `ACCESSIBILITY`             `HIGH`     `NEGATIVE`   `Y`         `ACCESSIBILITY`   `LOW`
  accessible                                                                                         
  entrance                                                                                           

  Supplier may not `SUPPLIER_SUSTAINABILITY`   `MEDIUM`   `NEGATIVE`   `Y`         `PROCUREMENT`     `LOW`
  meet                                                                                               
  sustainability                                                                                     
  policy                                                                                             
  ----------------------------------------------------------------------------------------------------------------

For the three tested messages, the LLM and the rule-based baseline
agreed on category, urgency, and assigned team. The baseline assigned
`MEDIUM` sensitivity to the supplier-sustainability message, while the
LLM assigned `LOW`. This difference is a useful example of why
sensitivity labels should be reviewed against a clearly defined policy
rather than accepted automatically.

All three LLM responses passed the experiment's JSON and permitted-field
validation checks.

## How to reproduce

1.  Open `ESG_Message_Triage.ipynb` in Google Colab or a compatible
    Jupyter environment.
2.  Configure the `COHERE_API_KEY` secret in the environment used to run
    the notebook. Do not place the key directly in notebook cells or in
    a committed file.
3.  Run the notebook cells in order.
4.  Inspect the saved outputs:
    -   `esg_llm_results.json`
    -   `esg_llm_results.csv`
    -   `esg_rule_based_results.csv`
5.  Compare the LLM results with the baseline and review the validation
    checks.

The notebook and output files should be uploaded to this folder for the
repository to serve as complete experiment evidence.

## Limitations and responsible use

The experiment contains only three messages, so it cannot establish
general accuracy or reliability. Results may change with different
wording, prompts, model versions, or API behaviour. A rule-based system
can be transparent but may miss messages that do not contain expected
keywords. An LLM can interpret more varied language but may misclassify
urgency, category, or sensitivity.

The outputs should therefore be treated as recommendations requiring
human review. Before real deployment, the system would need a larger and
representative test set, documented evaluation metrics, clear category
and sensitivity definitions, privacy controls, access restrictions,
error handling, monitoring, and a human escalation path. Sensitive
information should not be sent to an external API unless permitted by
the organisation's privacy and data-governance requirements.

## Evidence files

Keep these experiment artifacts in this folder:

-   `ESG_Message_Triage.ipynb` --- notebook containing the
    implementation and test procedure.
-   `esg_llm_results.json` --- structured LLM results.
-   `esg_llm_results.csv` --- tabular LLM results.
-   `esg_rule_based_results.csv` --- rule-based baseline results.
-   `experiment-log.md` --- experiment setup, test cases, outputs, and
    comparison notes.

Do not upload API keys, access tokens, or other secrets. Screenshots of
the notebook and outputs can remain in the written assessment report if
they are already included there.

## Architecture context

The written report discusses a conceptual cloud workflow in which
incoming messages are validated, passed to an LLM endpoint, checked
against an allowed schema, and routed for human review. The architecture
is proposed for discussion only; this repository experiment does not
demonstrate a deployed Azure workflow.

## References

-   Cohere. *API documentation*. https://docs.cohere.com/
-   Google Colab. *Frequently asked questions and notebook
    documentation*. https://colab.research.google.com/
