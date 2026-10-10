# Q2 -- Cloud Security Evaluation: Snowflake Customer-Account Breaches

## Overview

This folder documents the cloud-security analysis prepared for Question
2 of BUS5001 Assessment 3. The case study examines the 2024
customer-account compromises associated with threat activity tracked by
Mandiant as **UNC5537**.

The analysis focuses on the distinction between a compromise of customer
credentials and a breach of the cloud provider's own underlying service.
Based on the sources discussed in the report, the incidents involved
stolen customer credentials being used to access customer Snowflake
environments; the report does not claim that Snowflake's core enterprise
environment was itself breached.

## Case-study summary

Mandiant reported that threat actors used credentials stolen through
infostealer malware to access customer Snowflake instances. A
contributing factor was that some affected accounts did not have
multifactor authentication (MFA) enabled. Previously stolen credentials
could therefore remain useful when they had not been rotated or
otherwise invalidated.

The report discusses the potential exposure of data at multiple
organisations and the public reporting of incidents by organisations
including Ticketmaster and Santander. Claims about the incident should
be interpreted carefully: exposure of customer data in a customer's
cloud account is not, by itself, proof that the cloud provider's own
infrastructure was compromised.

## Shared-responsibility analysis

Cloud security is a shared responsibility. The provider secures the
underlying cloud service, while customers remain responsible for
correctly configuring and protecting their own accounts, identities,
permissions, data, and integrations. The precise division of
responsibilities depends on the service and configuration.

For this case, the main customer-side controls include enforcing MFA,
using least-privilege access, rotating compromised credentials,
restricting access by trusted network locations where appropriate,
monitoring activity, and preparing an incident-response process.

## Recommended controls

1.  **Enforce MFA:** Require MFA for all human users and privileged
    accounts. Prefer phishing-resistant methods where available.
2.  **Apply least privilege:** Remove unnecessary users and permissions,
    review service accounts, and limit access to sensitive datasets.
3.  **Manage credentials securely:** Rotate exposed credentials, avoid
    shared accounts, use a secrets manager, and prevent credentials from
    being stored in unsafe locations.
4.  **Restrict and monitor access:** Where supported and appropriate,
    use trusted network or IP allow lists. Enable relevant audit logs
    and alert on unusual logins, downloads, or access patterns.
5.  **Prepare incident response and data governance:** Maintain a tested
    response plan, know who owns each response task, classify sensitive
    data, and periodically review account security settings.

## Architecture and scope

The written assessment includes a conceptual diagram showing users and
customer identities accessing a Snowflake customer environment, with
security controls such as MFA, least-privilege permissions, network
restrictions, and audit monitoring around the environment. The diagram
is an explanatory model, not a deployed cloud architecture.

No live cloud infrastructure was created for this question. The work is
a case-study evaluation based on published incident reporting and
security guidance.

## Limitations

This is a secondary-source case study rather than a forensic
investigation. The analysis depends on information made public by the
cited organisations and should not be read as a complete account of
every affected customer's configuration. Recommendations must be checked
against the current capabilities and configuration of the relevant
service before implementation.

## Assessment evidence

The Q2 analysis, conceptual architecture diagram, and references are
included in the written BUS5001 Assessment 3 report. This folder
provides a concise record of the case study and the principal security
recommendations.

## References

-   Mandiant. (2024). *UNC5537 targets Snowflake customer instances for
    data theft and extortion*.
    https://cloud.google.com/blog/topics/threat-intelligence/unc5537-snowflake-data-theft-extortion
-   Snowflake. (2024). *Security updates and guidance related to recent
    customer account compromises*. https://www.snowflake.com/en/blog/
-   Ticketmaster. (2024). *Publicly reported data security incident
    information*. https://www.ticketmaster.com/

Reference details and access dates should be verified against the exact
sources cited in the final assessment report. The links above are
provided as starting points and may lead to general pages rather than
the precise article used.
