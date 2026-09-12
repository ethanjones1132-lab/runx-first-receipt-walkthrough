# Kai CSV Profiler compatibility test

This repository now also keeps a reproducible native Windows compatibility test of Kai CSV Profiler 0.2.4rc1, alongside the existing execution-receipt walkthrough. The test concerns the software wheel included in this repository. The Windows workflow is the commissioning author's exact test, with only our Taskmarket worker address substituted.

The unchanged wheel and its root LICENSE are supplied by Kai under MIT; that LICENSE applies to the Kai package. Existing walkthrough files retain their previous licensing status. Source: https://tangled.org/kairesearch.tngl.sh/kai-csv-profiler/tree/kai-dev .

Commission: Taskmarket TSK-JDT6W9DG. This is an AI-assisted software compatibility report, with no claim of manual human testing. Only synthetic CSV fixtures are processed in a disposable GitHub-hosted Windows runner. No account access or computing service is offered to the requester. The operator retains control of the account and repository.

The workflow runs manually, at most ten minutes, without repository secrets or host credentials. It tests ordinary UTF-8 input, malformed CSV, a missing file, an unapproved path, and a parent-directory escape. GitHub artifact attestation binds the observations to this workflow and commit. A complete functional failure is reported as observed; it is never hidden or repaired in the commissioned test.

Retain the original wheel, commit, workflow, and run through at least 2026-09-15T12:05:38.481Z.
