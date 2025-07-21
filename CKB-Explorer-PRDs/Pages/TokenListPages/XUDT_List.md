## 1. Page Overview

XUDT List displays the list of all XUDT (eXtended User Defined Token) assets on the CKB blockchain. It provides key metadata and analytics indicators for each token, allowing users to browse, sort, and filter tokens based on various attributes such as transaction activity, address count, and creation date.

### 1.1 Goals

* **(P0)** Provide an overview list of all XUDT tokens deployed on the chain.
* **(P0)** Display key metrics including 24hr transaction count, holder address count, and token creation date.
* **(P1)** Use visual tags to indicate token properties like "Limited Supply", "Layer 1 Asset", or "Layer 2 Asset".
* **(P0)** Offer a link for developers to submit token metadata.

## 2. Version History / Requirement Tracking

| Version | Date       | Status  | Notes                                   |
| ------- | ---------- | ------- | --------------------------------------- |
| v1.0    | 2025-07-16 | Drafted | Initial version based on wireframe      |

## 3. Page Constitution

### 3.1 Header Area

* Page title: **"XUDT List"**
* Top-right link: **"Submit Token Info"**
  * For user to submit Token info, see [submit token info](../../UserStories/Submit%20Token%20Info.md)


### 3.2 Token Table Layout

#### Table Columns

-  **Symbol & Name** 
   -  Displays the token symbol and full name (may include hash),
   -  Clicking will lead to the Token Detail page
- **Tags** Tag-style indicators showing token characteristics, with a filter icon for tag-based filtering. If you choose multiple tags, the logic here would be "OR" which means any item meet one of the tag will show here.
  - Issued on Bitcoin
  - Issued on CKB
  - Supply Limited
  - Utility

- **24hr Transaction** :The number of transactions involving this token in the past 24 hours
- **Address Count** :The number of unique addresses currently holding the token 
- **Created Time** :The date when the token was first created (format: `yyyy.MM.dd`)

#### Sorting

* Columns **24hr Transaction**, **Address Count**, and **Created Time** support ascending/descending sorting
* Default sort: descending by 24hr Transaction

### 3.3 Token Row Item Format

Each row includes:

* Token symbol and full name (shown in two lines)
* One or more tags indicating the token’s traits
* Corresponding metrics:

  * 24hr transaction volume
  * Number of holder addresses
  * Date of token creation


### 3.4 Footer Area

see [footer](../../GeneralComponents/Footer.md)