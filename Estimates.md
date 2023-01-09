# Estimation process

By default, the audit includes four types of work:

1. **Preliminary research** – the study of the project, its documentation, a first quick review of the code base, and compiling the list of integrations. In addition, we check both the web and our knowledge base for similar projects, their prior audits, and relevant exploits.
2. **The audit itself** – this part includes both manual code review (the most important part of the audit) and analysis with several security tools, both proprietary and publicly available.
3. The preparation of the **private report**.
4. **Re-check** – the check of the fixes that the dev team applied based on the recommendations from the private report and update of the private report to the public version.

We base our estimation on the amount of code and its features. On average, during the manual review, auditors check **~200 lines** of the Solidity code daily. The actual speed depends on the complexity, quality, and style of the code, the number of integrations, and the complexity of the scope. We try to take all these factors into account during the project estimation. All other works take around 50% of the time needed for the manual review.

**The simplified formula for the estimate is:**
`Cost of the audit = Number of lines of code / 200 * 1.5 * the cost of one working day of the team.`
Of course, the real estimate often varies from the number obtained by this formula based on the factors listed above.

Usually, our estimate is precise and doesn’t deviate from the actual time spent on the project by more than 10%. If we underestimate the amount of work, we use our reserves (free of charge). If we complete main tasks faster than expected, we perform additional checks on the project.

In rare cases, the estimate deviates significantly (up to 25%). This happens, for example, if the code contains too many problems, and the report preparation and the re-check require extra effort. We discuss such cases separately.
