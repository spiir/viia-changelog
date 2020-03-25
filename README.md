# Viia Changelog

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
