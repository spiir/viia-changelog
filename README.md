# Viia Changelog

## 2020-03-24

### Fixed
- Fixed issue where we couldnt fetch more than 9000 transactions at a time on Danske Bank Business PSD2, due to sorting of the transaction while fetching.
- Fixed how we store a sessions in the Viia connect flow, so that an users session doesn't break if they hit the browsers back button.
- In the Viia connect flow we've stop showing accounts from the bank that have previously been connected but doesn't exsist anymore. 

## 2020-03-10

### Added

- Added IsOrphaned property to accounts view model on `v1/accounts` and `v1/accounts/{id}`
- Added IncludeOrphaned query parameter to `/v1/accounts`

## 2020-03-06

### Added

- Added affected account Ids to `ConnectionRemovedWebhook`
- New webhook added to notify about orphaned accounts [AccountsOrphanedWebhook Docs](https://docs.getviia.com/#/webhooks/types?id=accountsorphanedwebhook)
- New webhook added to notify about un-orphaned accounts [AccountsUnorphanedWebhook Docs](https://docs.getviia.com/#/webhooks/types?id=accountsunorphanedwebhook)
