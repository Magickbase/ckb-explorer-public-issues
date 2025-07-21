## 1. Page Overview

This page is the **Transaction Details Page** in the CKB explorer. It is designed to display structured information of a single transaction, including its hash, block height, status, timestamp, and detailed input/output Cell data (such as script types, capacity, token types, and links to further info). 

![1](TransactionDetailPage_img/1.png)  

### 1.1. Goals

* **(P0)** Display basic transaction information: transaction hash, block height, confirmation status, and timestamp.
* **(P0)** Provide functionality to download raw transaction data.
* **(P0)** Display all Input/Output Cells in structured table format.
* **(P1)** Provide links to detailed views of each Cell.
* **(P1)** Identify and label token types (e.g., SUDT, NFT) in output details.
* **(P2)** Support toggle between “Professional” and “Lite” display modes.

## 2. Version History / Requirement Tracking

| Version | Date       | Status  | Notes                                                            |
| ------- | ---------- | ------- | ---------------------------------------------------------------- |
| v1.0    | 2025-07-21 | Drafted | Initial version based on wireframe design                        |
| v1.1    | 2025-07-21   |  Drafted    | Add cases for the DAO transaction|


## 3. Page Constitution

### 3.1. Header Area

![2](TransactionDetailPage_img/2.png)  


* Main title: “Transaction”
* Display transaction hash with copy button and provide download method.
* Show block height, confirmation status and number of confirmations
  *  Confirmed 
  *  Pending
  *  Rejected
* Show transaction timestamp (from the block header)


### 3.2. Transaction Detail Pannel

![3](TransactionDetailPage_img/3.png)  


Transaction Detail Pannel is composed by 2 sections:
-  Input Section: Showing the info about the input cells
-  Output Section: Showing the info about the output cells


* Table format displaying all input/output Cells:

  * `#`: Serial number
  * `Address`: Source address of the input
    *  Clickable: Jump to the [Address detail page](AddressDetail.md)
  * `Detail` (Also called `Scripts Note`): 
    * The Detail attribute is designed for showing detail of attribution of aboth Lock script and Type script of the Cell
      * The attribution of the type script
        *  If the cell is of UDT (e.g., CKB, SUDT, NFT, Spore), then the UDT name is displayed
           *  Meanwhile, the icon or names are clickable which leads user to the UDT detail page.
        *  #todo If the cell is of Nervos DAO, then the DAO Icon/name should be displayed
      * Shown with tag-style labels; 
  * `Capacity/Amount`: Capacity (CKB) or token amount
  * Rules about `Detail` and `Capacity/Amount`
  * ![4](TransactionDetailPage_img/4.png)  

    * Scripts Note refers to the annotations for the scripts in the Input/Output sections. In the prototype, this is represented by the gray rounded rectangle. Its interaction follows the Iteration 8 icon behavior.
    * For NFTs (including both DOB and non-DOB types), the Collection Name should be displayed in the Detail column. Clicking it should navigate to the corresponding NFT Collection Page.
    * For NFTs (including both DOB and non-DOB types), the ID of the item should be shown in the Amount column. If it's a DOB, clicking it should navigate to the corresponding Token Page.
    * For UDTs, the Token Name should be displayed in the Detail column. Clicking it should navigate to the corresponding Token Detail Page.
    * For UDTs, the Token Amount should be displayed in the Amount column.
      * “Cell Info” link leads to full details of the input Cell


### 3.3. Display Mode Toggle (Lite / Professional)

* Toggle switch at top-right corner
* **Professional mode**: shows full script details and technical fields
* **Lite mode**: group the transaction input/output by addresses.
    ![5](TransactionDetailPage_img/5.png) 

## Other Cases

### Case1: Nervos DAO transactions

When the transaction contains DAO related cell, we need to show different icon for the cells:
- Nervos DAO deposit
- Nervos DAO Withdraw

And we should pay attention to the position of the cells:
1. If the Nervos DAO deposit Cell is in the output, then the tx should be a `deposit` transaction
2. If the Nervos DAO deposit Cell is in the input and Nervos DAO Withdraw is in output then the tx should be a `withdraw request` transaction
3. If the Nervos DAO Withdraw Cell is in the input then the tx should be a `withdraw` transaction


Here're 3 exmaples of Nervos DAO transactions:

We should pay attention that the tooltips titles are different when hovering on  `withdraw request` transaction and `withdraw` transaction

- deposit: 
  - [tx example](https://explorer.nervos.org/transaction/0x7a2aacc857cae01bf0284a6b273ea024c50a7bbff1d3564781096dc17e1d94da)
  - ![dao_deposit](TransactionDetailPage_img/dao_deposit.png)  

- withdraw request: 
  - [tx example](https://explorer.nervos.org/transaction/0x8cacdb8f513727ef4253e3389890d5cfb5df08fee8a8844b7a9ff1beda6ceaca)
  - ![dao_withdraw_request](TransactionDetailPage_img/dao_withdraw_request.png)  

- Withdraw: 
  - [tx example](https://explorer.nervos.org/transaction/0x68de0af41d9740a80665b9e473a0853ae368e03d1267305a493a637d6274eb3f)
  - ![dao_withdraw](TransactionDetailPage_img/dao_withdraw.png)  

> The hover tooltips for the icons (based on the position of the cell) should be uniform.