# Minimal Documentation

If you're short on time to prepare extensive project documentation before the audit, consider using the following questionnaire to craft a basic project description.

## High level description

Business description of the project, one-two sentences. E.g.:

> Lending system for governance tokens, where suppliers can earn interest and borrowers can get voting power cheaply.

### Token description

For non-utility tokens, please provide additional information:

* `name`, `symbol`, and `decimals`.
* `totalSupply` if predetermined.
* initial token distribution if it is hardcoded within the contract.
* extra features (anything beyond ERC20 Standard or Open Zeppelin implementation).

## Main actors, actions, flows

List of roles and their main actions. E.g.:

> * Suppliers can deposit and withdraw governance tokens to the pools.
> * Borrowers can "borrow" tokens for fee, extend loan duration, and return their loans.
> * Liquidators can forcibly close loan positions that have consumed their fee. Liquidators receive a small reward for each closed loan.
> * Owner of the system (multisig) can adjust settings and pause the system.

## Technical details

Design and architecture choices, clever tricks and hacks, complex logic, etc. E.g.:

> * The contracts are not upgradable, we will have to deploy new versions of the system if we decide to.
> * The token pool is an entry point for all users and holds all tokens that are not utilized right now.
> * Suppliers receive xTokens when they deposit governance tokens (similar to Compound's cTokens).
> * Borrowers don't receive governance tokens, they become delegatee of the borrowed tokens. To achieve it, the pool deploys a minimal proxy (ERC-1167) for each loan, that holds borrowed tokens and interacts with the according governance system. When the loan is closed, the tokens return to the pool.

## Deployed contracts

Number of deployed contracts, connections between them. E.g.:

> * We deploy a separate `Pool` and an `xToken` for each governance token we support.
> * Each `Pool` has a `LoanLogic` contract that knows how to interact with specific governance system. Every `LoanProxy` deployed by the `Pool` has `LoanLogic` contract as its target for delegatecall.
> * Additionally, we have a `FeeLogic` contract that is common for all `Pool`s. It is used to determine the rate at which the fee provided by the borrower is consumed and therefore the loan "expires" and can be liquidated.

<!-- markdownlint-disable-file MD013 -->
<!-- markdownlint-configure-file { "MD007": { "indent": 4 } } -->
