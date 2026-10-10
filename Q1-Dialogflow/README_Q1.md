# Q1 -- Sustainability Incident Reporting Assistant

## Overview

This folder documents the Question 1 prototype for the BUS5001
Assessment 3. The prototype is a Dialogflow ES chatbot called
**Sustainability Incident Reporting Assistant**. It demonstrates how a
university or organisation could collect basic information about
sustainability-related incidents and direct users toward an appropriate
next step.

The chatbot is a demonstration prototype. It does **not** create an
official incident ticket, notify a facilities team, or submit a report
to an operational system.

## Platform

-   **Tool:** Google Dialogflow ES
-   **Prototype name:** Sustainability Incident Reporting Assistant
-   **Purpose:** Demonstrate conversational collection and handling of
    sustainability incident reports

## Intents implemented

  -----------------------------------------------------------------------
  Intent                              Purpose
  ----------------------------------- -----------------------------------
  `Report_Sustainability_Incident`    Recognises a user who wants to
                                      report a sustainability-related
                                      incident, such as a water leak.

  `Ask_Incident_Location`             Responds to or collects information
                                      about where the incident occurred.

  `Confirm_Incident_Report`           Demonstrates the confirmation step
                                      when the user agrees to proceed.

  `Cancel_Incident_Report`            Handles a user's decision to cancel
                                      the demonstration report.

  `Escalate_To_Facilities`            Provides a pathway for a user who
                                      requests human assistance from
                                      facilities.

  Default Welcome                     Greets the user and introduces the
                                      chatbot.

  Default Fallback                    Responds when the chatbot cannot
                                      confidently match the user's
                                      message to an available intent.
  -----------------------------------------------------------------------

## Test scenarios

The following example conversations were tested in the Dialogflow
prototype:

  -----------------------------------------------------------------------
  Test                    User input              Expected demonstration
                                                  behaviour
  ----------------------- ----------------------- -----------------------
  1\. Start a report      "I want to report a     Recognises the
                          water leak"             incident-reporting
                                                  request and identifies
                                                  the water-leak
                                                  category.

  2\. Provide a location  "The issue happened in  Responds to the
                          Building A"             incident-location
                                                  information.

  3\. Confirm             "Yes, submit the        Displays a confirmation
                          report"                 response for the
                                                  demonstration. The
                                                  message makes clear
                                                  that no formal report
                                                  is submitted to an
                                                  external system.

  4\. Cancel              "No, cancel the report" Displays a cancellation
                                                  response.

  5\. Request a person    "I need human help"     Provides the facilities
                                                  escalation pathway. No
                                                  real alert or ticket is
                                                  created.

  6\. Unrecognised        An unrelated joke or    Uses the Default
  message                 irrelevant request      Fallback response.
  -----------------------------------------------------------------------

## Scope and limitations

This prototype demonstrates conversational intent recognition and basic
incident-reporting dialogue. It is not connected to a live
facilities-management platform, ticketing system, email service, or
database. Therefore, confirmation and escalation messages are
illustrative only.

Before operational use, the chatbot would need secure storage, input
validation, privacy notices, access controls, a real ticketing or
reporting integration, and a tested human-escalation process. The
prototype should also be evaluated with a wider range of user
expressions and accessibility needs.

## Assessment evidence

Screenshots of the Dialogflow configuration and tested conversations are
included in the written assessment report. The Q1 demonstration video
should be linked in the report using the Echo360 or Microsoft Stream
share link required by the assessment instructions.

## Reproduction notes

To review the prototype, open the Dialogflow ES agent and inspect the
intents listed above. Use the test scenarios to verify the main
reporting, confirmation, cancellation, escalation, and fallback paths.

This README describes the prototype's demonstrated scope; it does not
claim that an incident was submitted to a live organisational system.
