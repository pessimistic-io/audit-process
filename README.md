# The audit process at Pessimistic

Interactions between developers and auditors

## Before the audit

### Documentation

We expect to see the documentation that would describe the purpose and behavior of the contract, its interactions, and main design choices. The more information we have, the better quality of the audit we can provide.

To get inspired, you may see an example of the [Compound documentation](https://compound.finance/docs/).

And a [questionnaire](https://hackmd.io/@pessimistic/Bks2dqSSY/) compiled by our team will help you compose a minimal project description.

### Project setup

Developing secure contracts without additional libraries, tools, and frameworks is nearly impossible. Hardhat and Truffle are the most common options.

Even more, tools work at 100% effectiveness only when all developers (or auditors) can reproduce all steps, i.e., compiling, testing, and deploying contracts. One cannot achieve it without dependency management tools (e.g., yarn/npm) since different versions of dependencies don't behave identically.

We highly recommend setting up a project properly. Use dependency management tools (yarm/npm), testing frameworks (hardhat/truffle), linters (solhint), etc. Please take a look at repos of well-known teams; most of them have excellent project setup.

### Tests

Our reports always note the availability of tests and code coverage. We highly recommend covering the code with tests and ensuring that all tests pass and the code coverage is sufficient.

Please describe the environment in which you run tests and the list of commands that worked for you in your README file.

### NatSpec comments

We recommend providing the code with detailed NatSpecs. Depending on the complexity of the code, the lack of comments makes the code hard to interact with.

### Scope of work

We can audit the entire provided repository or a particular smart contract. We will prepare a cost and time proposal based on the provided list of contracts to be analyzed.

### Code freeze

AWe start review only after the final commit is confirmed according to our rules. Please complete the development process before the audit begins to avoid chaos and time/cost increase.

> Here is a useful article from Consensys on [how to prepare for an audit process](https://consensys.net/diligence/blog/2019/09/how-to-prepare-for-a-smart-contract-audit/).
---

## During the audit

### Introduction to the project

At the start of the project, our team will review the provided materials: any documentation and the entire repo (code, tests, and other project files).

### Communication

We will arrange a call with the development team to learn the project business model, high-level architecture, and critical features of the contracts. This step becomes crucial if the project documentation seems insufficient or the project is large and/or non-standard.

During the audit, the audit team may ask clarifying questions via Telegram chats/emails/additional calls.

### Tests

Tests are crucial for code security, so we always note the availability of tests and code coverage in our reports. We highly recommend covering the code with tests and ensuring that all tests pass and the code coverage is sufficient.

If, for some reason, tests do not run, fail, or the results are inconsistent, we will ask you for instructions on how to start them and a description of the environment. We may also need screenshots of your results on the number of tests passed and a zip file with the code coverage report. We need this to compare our results with yours or to include your data in the report.

If the project has no tests or the coverage is insufficient, this will be noted as a medium severity issue in the report according to our classification.

### Preliminary results of the audit (private report)

As a result of the audit, we will send you a private version of the PDF report with audit results and recommendations for fixes. We recommend scheduling a call between the auditing team and the developers to go through the report and discuss anything that is unclear from the report.

### Fixes and recheck

We expect to receive the code fixed based on our recommendations from the private report within 10 working days. Please provide comments on the issues you are not going to fix. We will put these comments into the public version of the audit report.

If you have any doubts or need further clarification about the corrections being made, please feel free to compile all questions into one message or document and send it to us. We will gather the project team together to discuss and provide extensive comments or suggest you another call for a detailed discussion.

If for some reason, the development team has difficulties implementing our recommendations and an additional call does not improve the situation, we can consider paid consulting or recommend experienced development teams at your request.

### Timeline

If, for some reason, your team cannot provide the fixes within 10 working days, please let us know your prediction for the final code availability date as soon as possible. We need this information to better plan our timeline and reschedule the project recheck. Otherwise, the recheck date can become unpredictable and will be delayed until a suitable slot appears in the project auditor’s schedule.

If we do not receive the updated code within a reasonable time (10 to 20 working days), the recheck may take more time and require an additional fee. The longer the delay since the initial audit, the fewer details the auditor remembers about the project. Another deep dive into the project may require extra effort after several weeks of work on other projects. In many cases, reviewing only the difference between the updated and initial code is not safe, so we thoroughly review even minor code updates.

### What is included in the recheck step

Please note that only one review (recheck) of fixes is included in the agreement budget. We expect to receive only one final commit with all fixes for us to check.

The recheck step does not include checks for logic updates, new features, major refactoring, or architecture changes. We will estimate all these changes as an additional scope, and we will let you know about the cost of this extra work and the new possible schedule.

It happens that during recheck we see that several issues were fixed partly. In this case, we will notify you and give you an opportunity to fix them. We will provide this additional recheck for free if it does not take more than 1 hour for our team.

If the codebase contains new features, changes in math or logic updates, this will be evaluated as extra hourly work.

### Final (public) report

Once we receive a final commit with fixes based on the private report, we will recheck them within 10 working days. As a result, you will receive a final/public report with notes of corrections.

You can see the examples of our public reports here: <https://github.com/pessimistic-io/audits>.

**This is the final step in our audit process** 🎉

We would love to publish this report on our GitHub, so we will ask you for permission to publish and check with you for a suitable date.

### Additional code updates and checks

Any new project changes or new versions of code will be evaluated and may be audited for an additional fee on a new schedule. We perform these works as an hourly job with the report update or as a new separate project with a report from scratch. This depends on the number and quality of amendments, the scope of the audit, and the amount of time that has passed since the initial audit was completed.

If during the additional testing you find any issues that were not covered in the audit report, please report them to us, so we can review them and provide you with the information on how to remediate them in the best possible way.

---

## After the audit

A security audit is one of the most crucial steps to project security. However, performing an audit can never be considered a final step. We strongly encourage you to take these additional measures to achieve maximum project security. We will be glad to consult you regarding all the items listed below:

* Perform additional independent audit
* Perform economic audit, if this is relevant for the project ([gauntlet.network](https://gauntlet.network/), incentivai.co)
* Setting up security master plan (great examples are here: <https://docs.babylon.finance/security/security>, <https://github.com/yearn/yearn-security>)
* Setting up a public bug  bounty program (immune.fi, hackenproof.com)
* Setting up monitoring for the smart contract system (Forta, Tenderly, Parsiq, Defender etc). Here is the nice explainer video from OpenZeppelin: <https://www.youtube.com/watch?v=RkNJfKad3Q4>
* Consider insurance (e.g. [nexus mutual](https://nexusmutual.io/), <https://www.sherlock.xyz/>)
* Set up an incident response procedure (this might help: <https://tenderly.co/war-room/>, <https://medium.com/immunefi/what-to-do-after-youve-been-hacked-8d2e838a2d65>)
* Add your contacts into the known lists of security contacts (<https://github.com/crytic/blockchain-security-contacts>, <https://consensys.github.io/blockchainSecurityDB/>, <https://blog.openzeppelin.com/smart-contract-security-registry/>)
* Secure the keys of the privileged users as much as you can. Consider setting up a multisignature wallet (like Gnosis Safe). This article might be useful: <https://blog.trailofbits.com/2018/11/27/10-rules-for-the-secure-use-of-cryptocurrency-hardware-wallets/>.

---

