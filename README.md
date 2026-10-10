# BUS5001 Assessment 3

This repository contains supporting documentation and experiment
evidence for **BUS5001 Assessment 3**. The assessment explores
conversational incident reporting, cloud security, LLM-based ESG message
triage, and NotebookLM as an academic assistant for sustainability
sources.

## Repository contents

  ----------------------------------------------------------------------------------------------------
  Folder                                               Question                Contents
  ---------------------------------------------------- ----------------------- -----------------------
  [`Q1-Dialogflow/`](Q1-Dialogflow/)                   Q1 -- Sustainability    README documenting the
                                                       Incident Reporting      Dialogflow ES
                                                       Assistant               prototype, intents,
                                                                               tested conversations,
                                                                               and limitations.
                                                                               Screenshots and the
                                                                               demo-video link are
                                                                               included in the written
                                                                               report.

  [`Q2-Cloud-Security/`](Q2-Cloud-Security/)           Q2 -- Cloud Security    README summarising the
                                                       Evaluation              2024 Snowflake
                                                                               customer-account breach
                                                                               case study, shared
                                                                               responsibility, and
                                                                               recommended security
                                                                               controls.

  [`Q3-ESG-Message-Triage/`](Q3-ESG-Message-Triage/)   Q3 -- ESG Message       LLM experiment
                                                       Triage                  notebook, structured
                                                                               LLM results, rule-based
                                                                               baseline results, and
                                                                               experiment log.

  [`Q4-NotebookLM/`](Q4-NotebookLM/)                   Q4 -- NotebookLM        NotebookLM notebook
                                                       Evaluation              link, experiment log,
                                                                               observed results, and
                                                                               critical evaluation.
  ----------------------------------------------------------------------------------------------------

## Question summaries

### Q1 -- Sustainability Incident Reporting Assistant

A Dialogflow ES chatbot prototype demonstrates a conversational pathway
for reporting sustainability-related incidents. The documented tests
cover starting a report, providing a location, confirming or cancelling
the demonstration, requesting human assistance, and handling an
unrecognised message.

**Important scope note:** The chatbot is a prototype. It is not
connected to a live ticketing system or facilities-management service,
and it does not create official reports or real escalation alerts.

### Q2 -- Cloud Security Evaluation

A case study analyses the 2024 compromises involving customer Snowflake
accounts, including credential theft and customer-side security
weaknesses. It discusses cloud shared responsibility and recommends
controls such as multifactor authentication, least privilege, secure
credential management, access restrictions, monitoring, and
incident-response planning.

This is a secondary-source case study, not a live cloud deployment or an
independent forensic investigation.

### Q3 -- ESG Message Triage Using an LLM API

A small experiment uses the Cohere API and the `command-r-08-2024` model
to classify three sustainability-related messages into structured triage
fields. The LLM outputs are compared with a Python rule-based baseline
and checked for valid JSON and permitted field values.

**Important scope note:** The sample is small and is not sufficient to
establish general model accuracy. Outputs should be reviewed by a human
before any operational use. API credentials must never be committed to
the repository.

### Q4 -- NotebookLM Evaluation

NotebookLM was evaluated using two sources: GRI Standards and the United
Nations' 17 Sustainable Development Goals. Activities included
generating a source-grounded summary, a 10-question quiz, a mind map,
and an Audio Overview. The observed quiz result was 9/10 (90%).

**NotebookLM link:** [Open the Q4 NotebookLM
notebook](https://notebook.google.com/notebook/27675f74-eec7-46d2-b773-35240b9b9410)

Please check that the notebook's sharing settings allow the teaching
team to access it.

## Reproducing the Q3 experiment

1.  Open `Q3-ESG-Message-Triage/ESG_Message_Triage.ipynb` in Google
    Colab or a compatible Jupyter environment.
2.  Configure the `COHERE_API_KEY` secret in the runtime environment. Do
    not hard-code or publish the key.
3.  Run the notebook cells in order.
4.  Review the generated JSON and CSV files and compare the LLM output
    with the rule-based baseline.
5.  Consult the Q3 `experiment-log.md` for the test cases, observations,
    and limitations.

If the notebook or output files are not yet present in the folder,
upload the actual files generated during the experiment before
submitting the repository link.

## Evidence and assessment report

The written assessment report contains the detailed question responses
and screenshots, including Dialogflow configuration and conversations,
Q3 model outputs and baseline comparison, and Q4 NotebookLM outputs. The
repository provides supporting documentation and experiment artifacts,
especially for Q3 and Q4.

The Q1 demonstration video should be linked in the written report using
the Echo360 or Microsoft Stream share link required by the assessment
instructions.

## Responsible use and limitations

-   Prototypes and experiments documented here are for assessment and
    demonstration purposes; they are not production systems.
-   LLM classifications and NotebookLM-generated content can be
    incorrect and should be checked.
-   Do not commit API keys, access tokens, personal data, or
    confidential information.
-   Check that notebook, video, and repository links are accessible to
    the teaching team before submission.
-   Verify reference details and ensure the written report follows the
    assessment's required citation style.

## External resources

-   [Dialogflow ES
    documentation](https://cloud.google.com/dialogflow/es/docs)
-   [Cohere API documentation](https://docs.cohere.com/)
-   [NotebookLM Help](https://support.google.com/notebooklm/)
-   [GRI Standards](https://www.globalreporting.org/standards/)
-   [United Nations Sustainable Development
    Goals](https://sdgs.un.org/goals)

------------------------------------------------------------------------

*Prepared as a supporting repository for BUS5001 Assessment 3.*
