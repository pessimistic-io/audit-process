# The audit process at Pessimistic

A security audit of smart contracts is one of the most crucial steps your team can take to ensure maximum project security. Our goal is to assist you in achieving this high level of security. In this document, we will outline what your team can do before, during, and after the audit to maximize the positive impact of our collaboration.

## Before the audit

### Documentation

We expect to see documentation that describes the purpose and behavior of the contract, including its interactions and main design choices. The more comprehensive the information provided, the higher the quality of the audit we can deliver. A lack of detailed documentation can render the identification of many logical issues nearly impossible, even with the assistance of the development team. This is particularly true for complex or non-trivial formulas.

If the project has no documentation or it is clearly insufficient, we will note this as a medium severity issue in the audit report.

For inspiration, you can refer to the [Compound project's documentation](https://compound.finance/docs/) as an example.

Here is a [questionnaire](https://hackmd.io/@pessimistic/Bks2dqSSY/) compiled by our team to assist you in creating a minimal project description.

### Project setup

Developing secure contracts is nearly impossible without the use of additional libraries, tools, and frameworks. Hardhat and Foundry are among the most commonly used options.

Furthermore, these tools are only fully effective when every developer or auditor can reproduce all steps, such as compiling, testing, and deploying contracts. Achieving this level of consistency requires dependency management tools like yarn or npm, as different versions of dependencies can behave inconsistently.

We strongly recommend setting up your project properly. Utilize dependency management tools (yarn/npm), testing frameworks (Foundry/Hardhat), linters (solhint), etc. Review the repositories of well-established teams for examples of excellent project setups.

If you have the time or expertise, consider using simple security tools like [Slither](https://github.com/crytic/slither)+[Slitherin](https://github.com/pessimistic-io/slitherin?tab=readme-ov-file#slitherin-by-pessimisticio) or [SemGrep](https://github.com/Decurity/semgrep-smart-contracts). Early detection of issues leads to improved code quality.

### Tests

Our reports always note the availability of tests and code coverage. We highly recommend covering the code with tests and ensuring that all tests pass and the code coverage is sufficient. As an extra measure, consider fuzzing with [Foundry](https://book.getfoundry.sh/forge/fuzz-testing) or [Echidna](https://github.com/crytic/echidna). Our [article on fuzzing](https://blog.pessimistic.io/confession-about-fuzzing-5e50437fdd8f) might help you understand how much effort it might take.

Please describe the environment in which you run tests and the list of commands that worked for you in your README file.

### NatSpec comments

We recommend providing the code with detailed NatSpecs. Depending on the complexity of the code, the lack of comments makes the code hard to interact with.

### Code freeze

Code freeze is very important for the effectiveness and efficiency of the audit. Switching commits at the last moment or during the audit causes delays, cost increases, and may compromise audit integrity. 

**Please complete the development process before the audit begins to avoid chaos and time/cost increase.**

> Here is a useful article from Consensys on [how to prepare for an audit process](https://consensys.net/diligence/blog/2019/09/how-to-prepare-for-a-smart-contract-audit/).
---

## During the audit

### Introduction to the project

As the first step of the audit, our team will briefly scan the entire repo (code, tests, and other project files) and any available documentation.

### Communication

To quickly finish onboarding, we will arrange a call with the development team. We will ask questions about the project business model, high-level architecture, and critical features of the contracts. This step becomes crucial if the project documentation seems insufficient or the project is large and/or non-standard.

During the audit, the audit team may ask clarifying questions via Telegram chats, emails, or additional calls. The effectiveness of the audit depends on the quality of this communication, and we expect high cooperation and reasonable reply times to achieve the best results.

### Tests

If, for any reason, tests do not run, fail, or produce inconsistent results, we will ask you for instructions on how to start them and a description of the environment. We may also need screenshots of your results on the number of tests passed and a zip file with the code coverage report. We compare our results with yours and may include your data in the report.

If the project has no tests or the coverage is insufficient, we will note this as a medium severity issue in the report.

### Preliminary results of the audit (private report)

As the first deliverable, we will send you a private version of the PDF report with audit results and recommendations for fixes. In many cases, we recommend scheduling a call between the auditing team and the developers to go through the report and discuss anything unclear.

### Fixes and recheck

We expect to receive the code fixed based on our recommendations from the private report within an agreed period. It can vary depending on the project size, the number of issues found, and our schedule, but it is typically 5-10 working days. Please provide comments on the issues you are not going to fix. We will put these comments into the public version of the audit report.

If you have any doubts or need further clarification about the corrections being made, please feel free to compile all questions into one message or document and send it to us. We will gather the project team to discuss and provide extensive comments or suggest another call for a detailed discussion.

If, for any reason, the development team has difficulties implementing our recommendations and an additional call does not improve the situation, we can consider paid consulting or recommend experienced development teams at your request.

### Timeline

If we do not receive the fixed code within the agreed period, there are two options to proceed: the recheck can be canceled, and the private report will be considered as a final deliverable; or the recheck will be considered as a new separate project, planned within a new timeframe, and require additional fees. 

Please keep in mind that the longer the delay since the initial audit, the fewer details the auditor remembers about the project. After several weeks of work on other projects, another deep dive into the codebase may require extra effort. Note that at some point reviewing just the changes becomes ineffective, and a full audit may be required.

### What is included in the recheck step

Please note that only one review (recheck) of fixes is included in the agreement budget by default. For the recheck, we expect to receive only one final commit that will contain all fixes applied based on our recommendations.

The recheck step does not include checks for logic updates, math changes, new features, major refactoring (more than 10% lines of the code), or contract system redesign. We will estimate all these changes as an additional scope and let you know about the cost of this extra work and the new possible schedule.

Occasionally, we discover issues that were only partially fixed. In this case, we notify you and give you an opportunity to fix them. This additional recheck is free if it does not take more than 1 hour of the audit team.

### Final (public) report

Once we receive a final commit with fixes based on the private report, we will recheck them within an agreed period (typically 5-10 working days). As a result, you will receive a final/public report with notes of corrections.

You can see the examples of our public reports here: <https://github.com/pessimistic-io/audits>.

**This is the final step in our audit process** 🎉

We would love to publish the final report on our GitHub and make an announcement in social networks, so we will ask you for permission and a suitable date.

### Additional code updates and checks

Any new project changes or new versions of code will be evaluated and may be audited for an additional fee on a new schedule. We perform these works as an hourly job with the report update or as a new separate project. This depends on the number and quality of amendments, the scope of the audit, and the amount of time that has passed since the initial audit was completed.

If you find any issue that is not covered in the audit report, please share your findings with us. We will analyze it and help you remediate potential problems at the highest priority.

---

## After the audit

A security audit is one of the most crucial steps to project security. However, performing an audit can never be considered a final step. We strongly encourage you to take these additional measures to achieve maximum project security. 

We will be glad to assist you in implementing any of the measures listed below. We have internal expertise, a set of proprietary and open-source products, and a network of trusted partners offering these services. In many cases, they are ready to offer exclusive conditions for our customers.

*   Getting more eyes to look at your code and architecture:

    * Perform economic audit, if it is relevant to your project:
        * [Gauntlet](https://gauntlet.network/)
        * [Chaos Labs](https://chaoslabs.xyz/)
        * [Giants](https://gnts.ai)
    * Formal verification
        * [Certora](https://www.certora.com/)
    * Setting up a public bug bounty program 
        * [Immunefi](https://immunefi.com/)
        * [Hackenproof](http://hackenproof.com)

    * Setting up a bug hunting competition 
        * [code4rena](https://code4rena.com/)
        * [Sherlock](https://www.sherlock.xyz/)
        * [Hats Finance](https://hats.finance/)
* Setting up monitoring for the smart contract system
    * Monitoring smart contract attacks: 
        * [Pessimistic Spotter](https://spotter.pessimistic.io/) -- This is an easy-to-use and free-of-charge telegram bot that will help you to set up a monitoring within a couple of minutes.
    
    * Monitoring of smart contract activity:
        * [OpenZeppelin Defender](https://defender.openzeppelin.com/)
        * [Tenderly](https://tenderly.co/monitoring)
* Set up the processes:
    * Setting up security master plan. Great examples of such plans: 
        * [Babylon Finance](https://docs.babylon.finance/security/security) 
        * [Yearn](https://github.com/yearn/yearn-security)
    * Set up an incident response procedure. This might help: 
        * [Tenderly War Room](https://tenderly.co/war-room)
        * [What to do after you've been hacked](https://medium.com/immunefi/what-to-do-after-youve-been-hacked-8d2e838a2d65) by Immunefi
    * Add your contacts into the known lists of security contacts
        * <https://github.com/crytic/blockchain-security-contacts>
        * <https://github.com/Consensys/blockchainSecurityDB>
        * <https://blog.openzeppelin.com/smart-contract-security-registry/>
    
    * Secure the keys of the privileged users as much as you can. Consider setting up a multisignature wallet (like Safe). This article might be useful
        * [10 Rules for the Secure Use of Cryptocurrency Hardware Wallets](https://blog.trailofbits.com/2018/11/27/10-rules-for-the-secure-use-of-cryptocurrency-hardware-wallets/)

* In case something really dangerous happens, use this bot to connect to security experts: 

    * [Seal 911 Bot](https://t.me/seal_911_bot) -- This bot is created by trusted members of [ETH Security Community](https://t.me/ETHSecurity) 

* Consider insurance:
    * [Nexus Mutual](https://nexusmutual.io/)
    * [Atomica](https://www.atomica.org/)

