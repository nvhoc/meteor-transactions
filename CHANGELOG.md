Meteor + Mongo Transactions
===========================

### v1.x

- Explore Operational Transform options
- Look into support for `{multi: true}`
- Support for `upsert`
- Possible support for locking documents used in pending transactions

### v1.0

- Refactor and document code for better maintainability
- Add/improve support for other/existing mongo operators  
- Complete test coverage and security audit

### vNext

- More comprehensive test coverage

### v0.7.14

- Added `check` package as a dependency

### v0.7.13

- Closes #57 where write operations were async when they should have been sync

### v0.7.12

- Fixes a bug with the ordering of actions when trying to repair a broken commit and removes `SimpleSchema.debug = true;`

### v0.7.11

- Fixes a bug with $addToSet and $pull where inverses were not being recorded correctly

### v0.7.10

- Restores a semblance of latency compensation in some cases

### v0.7.9

- Fixes a bug where an error is thrown unnecessarily on an empty transaction

### v0.7.8

- Closes issue #49 (insert callbacks with collection2 not working) and #50 (undo of $set modifiers with multiple fields not restoring previous state correctly)

### v0.7.7

- Closes an issue (#48) in which Meteor.settings isn't defined for android builds and error gets thrown

### v0.7.6

- Closes an issue (#47) related to security, where transactions originating on the client could override the `tx.checkPermission` function on the server

### v0.7.5

- Fixes for a number of issues, the chief one being a broken rollback mechanism
- A small change in which auto committed insert transactions are not processed client side, but are sent to the server for writes, like  other transactions in `tx.start() ... tx.commit()` blocks, removing the need for allow/deny rules for inserts

### v0.7.0

- First release using new storage format for transactions and having db state recovery options

### v0.6.21

- Last stable(ish) release using naive/optimistic transactions with no db state recoverability