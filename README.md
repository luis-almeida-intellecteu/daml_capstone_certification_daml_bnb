# 🛠️ DamlBnB 🛠️

DamlBnB is a house renting application built in Daml.

### I. Overview

This project was created by using the `empty-skeleton` template. The project adopts and exemplifies the `proposal-accept` design pattern.

A Landlord may add a new house contract that can be rented out.

A Renter can create a RentingProposal contract. The Landlord can either Reject or Approve the proposal. Before the proposal is approved or rejected, the Renter may alter the number of rentees for the proposal. Upon getting approved, the House contract is updated with the new RentAgreement data, which may be cancelled at any moment by the two parties agreeing.

### II. Workflow

1. landlord creates a House contract
2. renter creates a RentingProposal contract
3. evaluator exercises ApproveProposal - the House contract is updated
4. By mutual agreement, the landlord and renter exercise CancelAgreement and finish the renting agreement

### III. Challenge(s)

* The project was created by using `empty-skeleton` and the following was removed from `daml.yaml`:

```
sandbox-options:
   - --wall-clock-time
```

and the following was added:

```
exposed-modules:
  - Main
```

### IV. Compiling & Testing

The unhappy path testing was done assuming that an Either returning a Left is an error and as such was included on the tests (test *cantCreateWithNoHouse*).

To compile and test, run the pre-written script in the `Test.daml` under /daml OR run:

```
$ daml start
```
