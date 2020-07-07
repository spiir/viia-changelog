# Viia Changelog
## 2020-07-06

### Added
- You can now skip the email page, when you are sending a end-user through the on-boarding
- You can now try our beta Payments API
- Added new state `Queued` on transactions, for now this is a feature toggle on integrator level
- One-time users can now claim their account during on-boarding
- Integrator can request all accounts, when a one-time user is onboarded
- 

### Fixed
- Fixed that some ids on activity logs could be the same, resulting in some end-users getting stuck when adding new accounts
-Invalid paging token resulted in a `Internal Server Error`, now integrator gets a `Bad Request`
- If we could't send an end-user a email, an error message i shown
- Fixed browser navigation in persistent-user onboarding flow

## 2020-05-18

### Added
- You can now initiate the Viia flows in Swedish from the sample app: sample.getviia.com
- You can now initiate the one-time flow from the sample app

### Fixed
- Fixed a bug where reserved transactions that had a date in the far future was deleted.

## 2020-05-05
### Added
- We've released a beta version of a new sign-up flow for one-time Viia users. The flow enables users to share data through Viia without having to go through the add email steps. After the data had been shared on behalf of the users, everything will be deleted within 24 hours, unless the users choose to claim their account. If you need continuous access to the users' data, you still need to use our regular flow. Read more here: https://docs.getviia.com/#/auth/one-time-flow/
- We've also added categorisation to our transactions to give a better overview of the collective transactions.


## 2020-04-22
### Fixed
- Fixed matching of transaction on Danske Bank PSD2 that would result in the user not getting new data from their account.


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
