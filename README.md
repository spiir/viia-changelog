# Viia Changelog

## 2020-04-14

### Fixed
- The account balance is updated four times a day instead of three, so it matches the update interval of transactions.
- When we fetch transactions from several accounts in one bank, we no longer fetch in parallel. As the parallel calls could sometimes mess up the sessions with the bank, it could result in end users losing their connection and having to reconnect to the bank. Unfortunately, this will impact the performance for end users with several accounts.

## 2020-04-01

### Added
- Sometimes, an account that has been connected to Viia will disapear from the bank. That means the end user is not getting new transactions from the specific account. When this happens, we now show the end user which account is missing and what they can do to get back on track.

## 2020-03-24

### Fixed
- Due to the sorting of transactions at the same time of fetching, we had problems fetching 9000 transactions on Danske Bank Business PSD2, which has now been fixed. 
- To make sure a user's session does not break in case the user hits the browser's back button, we've fixed how we store sessions in the Viia connect flow. 
- We've stopped showing bank accounts in the Viia connect flow that have previously been connected but that do not exist anymore. 

## 2020-03-10

### Added

- We've added IsOrphaned property to accounts view model on `v1/accounts` and `v1/accounts/{id}`
- We've also added IncludeOrphaned query parameter to `/v1/accounts`

## 2020-03-06

### Added

- We've added affected account Ids to `ConnectionRemovedWebhook`
- To notify about orphaned accounts, we added a new webhook [AccountsOrphanedWebhook Docs](https://docs.getviia.com/#/webhooks/types?id=accountsorphanedwebhook)
- We've also added a new webhook to notify about un-orphaned accounts [AccountsUnorphanedWebhook Docs](https://docs.getviia.com/#/webhooks/types?id=accountsunorphanedwebhook)
