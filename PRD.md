### General Components:



- Navbar in the header 
  ![navbar](https://user-images.githubusercontent.com/122437870/216756902-24f6e241-4bf6-4948-a269-8c5b204df7b3.png) 
  - Logo: link to the homepage
  - Home: link to the homepage
  - Nervos DAO: link to the dao page `/nervosdao`
  - Tokens: to sudt list `/tokens`
  - NFT Collections: to nft collection list `/nft-collections`
  - Charts: to chart list `/charts`
  - Faucet(testnet only): to testnet faucet `https://faucet.nervos.org/`
  - Search Field: a text field for searching, will be hidden on homepage until the window is scrolled to a proper position.
  - Chain type switch: mainnet/testnet
  - Language switch: English/Chinese
  - Dark Mode: ..........
  
- Footer

  ![footer](https://user-images.githubusercontent.com/122437870/216756905-b1ccd6c3-cac2-4a15-ab0a-36e5af3125fa.png)
  - Foundation: link to `https://nervos.org`
  - Developer
    - Docs: https://docs.nervos.org/
    - GitHub: https://github.com/nervosnetwork
    - Whitepaper: https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0002-ckb/0002-ckb.md
    - Faucet: https://faucet.nervos.org/
    - Submit Token Info: send an email with the default mail client to ckb-explorer@nervosnet.com
  - Media
    - Discord: https://discord.com/invite/nervos
    - Twitter: https://twitter.com/nervosnetwork
    - Blog: https://medium.com/nervosnetwork
    - Telegram: https://t.me/nervosnetwork
    - Reddit: https://www.reddit.com/r/NervosNetwork/
    - YouTube: https://www.youtube.com/channel/UCONuJGdMzUY0Y6jrPBOzH7A
    - Forum: https://talk.nervos.org/
   - Copyright Information：Copyright © `years` Nervos Foundation.All Rights Reserved.
   - DarkMode: .......

- Notification：A floating layer below the Navbar appears and disappears after a few seconds
 
  ![notification](https://user-images.githubusercontent.com/122437870/216756912-6bbfa700-b0a9-4271-9cdf-13e3629271e4.png)
  - Action notification: like copy text successfully
  - Network error
  - Maintainance notification
  - Reorg notification

### Homepage: https://explorer.nervos.org/

- Statistics
 
  ![statistics](https://user-images.githubusercontent.com/122437870/216756931-115062ed-c675-4fab-a630-62034f35f3c3.png)
  - Last Block: block number of the tip block
  - Average Block Time: 1 hour/(count of blocks in the past hour)
  - Mining Hash Rate:
  - Mining Difficulty:
  - Epoch: epoch number and epoch_index/epoch_length
  - Estimated Epoch Time: duration per epoch
  - Transactions per minute
  - Transactions in last 24h
  - Chart of `average block time`:average block time curve in the last 15 days
  - Chart of `hash rate`:hash rate curve in the last 15 days

- Last Block List(15 blocks)

  ![last_block_list](https://user-images.githubusercontent.com/122437870/216756992-88262faf-7673-4a0d-b653-5dbbe3a64251.png)
  - block number: link to block page `/block/{number}`
  - age: past time from now
  - miner: miner address, link to page `/address/{miner}`
  - rewards: mining reward to the miner
  - count of transactions
  - count of cells generated/destroyed in the block: count of outputs - count of inputs
  - more:link to link to block list page `/block/list`

- Transaction List(15 transactions)

  ![transaction_list](https://user-images.githubusercontent.com/122437870/216757009-1fd022c7-7515-4610-bff3-99ee69330a1a.png)
  - transaction hash: link to transaction page `/transaction/{hash}/`
  - confirmations: block height from now
  - block number: link to block page `/block/{number}`
  - age: past time from now
  - covered capacity of the transaction: sum of inputs' capacity or sum of outputs' capacity
  - count of cells generated/destroyed: count of outputs - count of inputs
  - more:link to link to transaction list page `/transaction/list`

### Block List Page: https://explorer.nervos.org/block/list

![block_list_page](https://user-images.githubusercontent.com/122437870/216757019-14aeec72-8df1-4e71-a0b4-b85afe17d099.png)

- Height: block number, link to block page `/block/{number}`
- Transactions: count of transactions in the block
- Reward: mining reward sent in the block
- Miner: address of miner, link to `/address/{miner}`
- Time

### Transaction List Page: https://explorer.nervos.org/transaction/list

![transaction_list_page](https://user-images.githubusercontent.com/122437870/216941387-fa5893e3-82cc-4681-9058-2035d6bb59f1.png)

- Transaction hash: link to transaction page `/transaction/{hash}`
- Height: number of the block which packaged the transaction, link to `/block/{number}`
- Capacity: covered capacity of the transaction, sum of inputs' capacity or sum of outputs'capacity + transaction fee
- Time

### Block Page: `/block/{number | hash}`

![block_page](https://user-images.githubusercontent.com/122437870/216757131-c067d938-72d2-41b2-ad44-90b17838ba70.png)

- Overview

  - Block hash
  - Copy button: click to copy block hash
  - Block height:link to prev/next block
  - Transactions:count of transactions
  - Size:current block size
  - Cycles:cycles required for transaction completion
  - Proposal Transactions:count of proposal transactions `proposals` of the block
  - Miner reward: first transaction of the block
  - Difficulty: `compact_target` of the block
  - Nonce: `nonce` of the block
  - Uncle Count：countof uncle blocks `uncles` of the block
  - Miner: miner address, link to `/address/{miner}`
  - Miner message: parsed from witness of the cellbase.
  - Epoch: epoch index of the block
  - Epoch start number: number of the first block in this epoch, link to `/block/{number}`
  - Block index: epoch number / epoch length
  - Timestamp
  - Transactions root: `transaction root` of the block

- Transactions
  - Reward transaction: mining reward to the miner who mined the block 11 before this one;
    - hash
    - cellbase for block 11 before this block: link to `/block/{number}`
    - rewarded miner address: link to `/address/{miner}`
  - Normal transactions
    - hash
    - input list
      - address
      - capacity
    - output list
      - address
      - capacity

### Transaction Page: `/transaction/{hash}`

![transaction_page](https://user-images.githubusercontent.com/122437870/216757154-5d1be447-1b03-4103-ae69-eb79d833ba19.png)

- Overview

  - Transaction Hash
  - Copy button: click to copy transaction hash
  - Download button: click to download raw data structure of the transaction
  - Block Height: number of block packaged this transaction, link to `/block/{number}`
  - Transaction Fee: fee of this transaction, equals to `sum(output.capacity) - sum(input.capacity)`
  - Size:current transaction size
  - Cycles:cycles required for transaction completion
  - Timestamp: timestamp of the block packaged this transaction
  - Status: `pending` or `x confirmations`, confirmations is the depth of block
  - Transaction parameters
    - Cell deps
    - Header deps
    - Witnesses

- Input Cell List

  - address toggle: switch address between deprecated format and active format
  - warning（display deprecated addresses）：displaying in deprecated address format
  - input item
    - index: index of input cell in the list, start from 0
    - right-arrow: every input cell comes from another transaction as output cell, the arrow is a link to the transaction generated this cell.
    - address: address owns this cell
    - detail: type of the cell
      - CKB Capacity: plain cell, doesn't have `type script`
      - UDT Cell: sudt cell, has `sudt type script` https://explorer.nervos.org/transaction/0x08e633b58686b8f4edeebd2b0d2104ef9e0e0e8137329ae9b06fd6866632432c
      - m-NFT: m-NFT cell, has `m-nft type script` https://explorer.nervos.org/transaction/0x2cba93481974893a6fb6c5d3c9ed37b5d526ccd2b17c706077c51900c52d9097
      - Nervos DAO: Nervos DAO cell, has `nervos dao type script` https://explorer.nervos.org/transaction/0xfbeefd2c206911e947ce4b3c0e097a5d104306228635046d044b995e47db4a5f
      - NRC 721: NRC 721 cell, has `NRC 721 type script`
    - Capacity/Amount: show sudt amount or cell capacity with `decimals formatted`. sUDT's amount is displayed prior to CKB capacity, so sUDT's capacity is shown by hovering on sudt icon in the detail column
    - Cell Info: click to show raw data structure of the cell
      - Lock Script
      - Type Script
      - Data

- Output Cell List
  - address toggle: switch address between deprecated format and active format
  - output item
    - index: index of input cell in the list, start from 0
    - address: address owns this cell
    - right-arrow/ring icon: show ring icon if this output has not been consumed in a transaction, or show the right-arrow with a link to the transaction consumed this output cell
    - detail: type of the cell
      - CKB Capacity: plain cell, doesn't have `type script`
      - UDT Cell: sudt cell, has `sudt type script`
      - m-NFT: m-NFT cell, has `m-nft type script`
      - Nervos DAO: Nervos DAO cell, has `nervos dao type script` https://explorer.nervos.org/transaction/0xfbeefd2c206911e947ce4b3c0e097a5d104306228635046d044b995e47db4a5f
      - NRC 721: NRC 721 cell, has `NRC 721 type script`
    - Capacity/Amount: show sudt amount or cell capacity with `decimals formatted`
    - Cell Info: click to show raw data structure of the cell
      - Lock Script
      - Type Script
      - Data

### Address Page: `/address/${hash}`

![iteration1](https://github.com/Magickbase/ckb-explorer-public-issues/assets/122437870/5809625b-c525-4456-a128-bd5f04db3392)

- Address

  - Address
  - Copy button: click to copy the address
  - Navigation button: click to page of deprecated address format(if exists) or active address format


- Overview

  - CKB: capacity of plain ckb cells
  - Occupied: A cell is consideres as "occupied" if the type script of this cell is not empty or the data field of this cell is not empty. Here "occupied" represents the total capacity of all occupied cells belongs to the address.
  - Nervos DAO deposit: capacity deposited into Nervos DAO
  - Nervos DAO compensation: interest earned by deposited capacity（It means dao interest + unclaimed compensation. So if you deposit dao once, it must greater than 0）
  - User defined token
    - Sudt: https://explorer.nervos.org/address/ckb1qpzuzykljldwecnuftaq9vjtzhmygqaal4z6ktsw3rylk23y09436q2q6uls60zkrl92uvcw40qrpkxed2ws4umdp3g3fzpktz34pju78wjsqqqqzqqqqqraqqqqp8gqqqqx6qqqqqgqqqqqxqqqqqr9qqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqx5qqqqqsqqqqqvqqqqqrzqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqq04v8fa
      - Icon
      - Token symbol
      - Amount
      - Click to sudt token info page, `/sudt/{hash}`
    - m-NFT/NRC721/CoTA NFT: https://explorer.nervos.org/address/ckb1qrgp752jcfnm0uemj723grpyva6zappyuj0tuge3etkpjlmjsxmq5q2v5mmdtf2yhatuxgm90tfn4ts6qxw8w4gx0jgcj
      - Icon
      - Nft collection name
      - Nft item id
      - Click to nft collection info page `/nft-collection/{hash | cota id}`
  - Live Cells: count of live cells owned by this address
  - Block Mined: count of block rewards sent to this address
  - Lock Script: raw lock script data structure
    - code hash: code hash field of this lock script, will show a script tag if exists
    - hash type: hash type field of this lock script
    - args: args field of this lock script

- Transaction List（ Here are two different lists mode for developers and novice users）

[ Professional mode]
  - Total count
  - Transaction hash
  - Block
    - Number
    - Age: time pass from mined block
  - Input list
    - Arrow: click to transaction generated this cell
    - Address: address owns this cell
    - Capacity/amount
  - Output list
    - Address: address owns this cell
    - Arrow: click to transaction consumed this cell, show a ring if cell is not consumed
    - Capacity/amount
  - Income/outcome: ckb balance change caused by this transaction

[ Lite mode]
 - Transaction hash
 - Height
 - TIme：time pass from mined block
 - Inputz&Output：All inputs and outputs in a single transaction hash
 - Capacity Change：Changes in address capacity under the transaction hash



### Sudt List Page: `/tokens`

![sudt_list_page](https://user-images.githubusercontent.com/122437870/216757195-501c3956-15dd-49b1-8e57-070a1169c313.png)

- Submit Token Info: send mail to ckb-explorer@nervosnet.com
- UAN & Name: show uan, full name and description, UAN is a special naming convention and can be found in https://github.com/nervosnetwork/rfcs/pull/335
- 2hr transactions: count of transactions happened in the last 24hrs
- Address count: count of holders(any address has hold this token will be included, even it has 0 balance now)
- Created time: time that token has been deployed on the chain

### Sudt Info Page: `/sudt/{hash}`

![sudt_info_page](https://user-images.githubusercontent.com/122437870/216757203-671f178c-d384-4328-bfde-ecbd771a7c3e.png)

- Overview

  - Icon
  - UAN: https://github.com/nervosnetwork/rfcs/pull/335
  - Hash: hash of type script of this sudt token
  - Copy button: click to copy sudt's hash type
  - Name: token name
  - Holder addresses: count of addresses held this sudt(including addresses which held but has 0 balance now)
  - Decimal
  - Issuer: address of token issuer who deployed this token, link to `/address/{address}`
  - UAN
  - Total amount: total supply of this token
  - Type script: raw data structure of sudt's type script
    - code hash: code hash field of this type script, will show a script tag if exists
    - hash type: hash type field of this type script
    - args: args field of this type script

- Transaction List
  - Total count
  - Filter: filtered by sender/receiver's address
  - Transaction hash
  - Block
    - Number
    - Age: time pass from mined block
  - Input list
    - Arrow: click to transaction generated this cell
    - Address: address owns this cell
    - Capacity/amount
  - Output list
    - Address: address owns this cell
    - Arrow: click to transaction consumed this cell, show a ring if cell is not consumed
    - Capacity/amount

### NFT Collection List Page: `/nft-collections`

![nft_collection_list_page](https://user-images.githubusercontent.com/122437870/216757215-df915e67-1f49-4d2f-b3ab-90c23d131a84.png)

- Collection Name
- Submit Token Info: send mail to ckb-explorer@nervosnet.com
- Type: m-NFT, NRC 721, CoTA
- Holder/Minted: count of holders and minted nft token item, different from the definition of holders of sudt, an address transferred its all nfts out won't not be treated as a holder
- Creator: address of NFT collection creator, link to `/address/{address}`

### NFT Collection Page: `/collections/{hash | cota id}`

![nft_collection_page](https://user-images.githubusercontent.com/122437870/216757223-34c7e8d6-dd41-44c0-b261-264b32481664.png)

- Overview

  - Icon: cover of the collection
  - Description
  - Type: m-NFT, NRC 721, CoTA
  - Holder/Minted: count of holders and minted nft token item
  - Creator: address of NFT collection creator, link to `/address/{address}`

- Activity

  - NFT: cover of nft item, with nft item id
  - Transaction hash: link to `/transaction/{hash}`
  - Action: Mint/Transfer/Burn
  - Age: datetime or past time from the transaction happened
  - From: sender's address, link to `/address/{address}`
  - To: receiver's address, link to `/address/{address}`

- Holders

  - Address: holder's address
  - Quantity: quantity of token items included in the collection held by this address

- Inventory
  - Cover: cover of token item
  - Token id: token item id
  - Owner: Address holds this token item

### NFT Token Item Page: `/nft-info/{collection hash | cota id}/{token item id}`

![nft_token_item_page](https://user-images.githubusercontent.com/122437870/216757236-db243ebb-ff4d-46b5-83f6-c699c6527de8.png)

- Overview

  - Cover: cover of token item
  - Name: collection name + token item id
  - Owner: address of its holder, link to `/address/{address}`
  - Creator: address of its collection's issuer, link to `/address/{address}`
  - Token id
  - Type: m-NFT/NRC 721/CoTA

- Activity
  - Transaction hash: link to `/transaction/{hash}`
  - Action: Mint/Transfer/Burn
  - Age: datetime or past time from the transaction happened
  - From: sender's address, link to `/address/{address}`
  - To: receiver's address, link to `/address/{address}`

### Script List Page: `/scripts`

![script_list_page](https://user-images.githubusercontent.com/122437870/216757255-10e4fd0f-c66a-424a-8a3b-d3e66a06b55b.png)

- Name
- Description
- Links: RFC, Source Code, Update message, Project website
- On-chain data
  - Code hash
  - Hash type
  - Cell out point
  - Dep type

### Charts Page: `/charts` or `/charts/{chart name}`

![charts_page](https://user-images.githubusercontent.com/122437870/216757273-43863306-66ce-4c8c-aa85-7a20929f5b07.png)

When the charts is based on time series, they are generally based on daily statistics, which mean the 
If not explictly specify the time series unit of the chart, it means the charts is generated as daily statistics.

- Block
  - Block Time Distribution: the x-axis is block intervals in seconds, and the y-axis is the frequency of occurrence in the latest 50,000 blocks.
  - Epoch Time Distribution: the x-axis is epoch intervals in hours, and the y-axis is the frequency of occurrence in the latest 500 epochs.
  - Average Block Time: average block intervals with daily & weekly *sliding smooth window*
    First calculate average block time by hour, and then calculate average daily smooth window by each timestamp with its preceding 24 hour records.
    Calculate rolling average weekly by each timestamp with its preceding 7 * 24 hour recrods.
    The x-axis of this chart is based on hour.
- Mining
  - Difficulty & Hash Rate & Uncle Rate:the x-axis is epoch number, and the y-axis is the value of difficulty & hash rate & uncle rate.
  - Epoch Time & Epoch Length:the x-axis is epoch number, and the y-axis is the value of epoch time & epoch length.
  - Difficulty:the x-axis is intervals in days, and the y-axis is the difficulty of the day.
  - Hash Rate:the x-axis is intervals in days, and the y-axis is the hash rate of the day.
  - Uncle Rate:the x-axis is intervals in days, and the y-axis is the uncle rate of the day.
  - Top Miners(Recent 7 days)：pie chart of the proportion of reported blocks according to address statistics in the last 7 days.
  - Miner Versions(Recent 7 days)：pie chart of the proportion of version numbers of miners reported in the last 7 days.
- Activities
  - Transaction Count: transaction count for per day 
  - Unique Address Used:count of addresses used accrued from 0 by day.
  - Cell Count: current total count of live cells and dead cells on chain by each day.
  - Balance Ranking: list 50 addresses that hold the most capacity.
  - Balance Distribution:shows the address count at specific balance range, and that under specific balance amount.
  - Transaction Fee:total transaction fees charged by miners per day.
- Nervos DAO
  - Total Deposit: total deposited and locked capacity on chain and deposited addresses by each day.
  - Daily Deposit: deposited capacity and deposited addresses per day
  - Deposit to Circulation Ratio: the ratio of DAO deposit to circulating supply. Where the circulating supply is equal to the total supply minus the burnt part and the unvested part.
- Economic Status
  - Total Supply:
    Total supply equals the sum of the primary issuance and the secondary issuance;
    The burnt part equals the sum of the 25% genesis issuance burnt and the burnt portion in the secondary issuance;
    The unvested part equals the portion that is locked by time lock, which will be released gradually by a predefined schedule.
    The circulating supply is equal to the total supply minus the burnt part and the unvested part.
  - Nominal DAO Compensation Rate:
    The nominal compensation rate is provided by DAO when there is no burnt portion in the secondary issuance.
    The real compensation rate is always higher than the nominal compensation rate.
  - Secondary Issuance:
    The secondary issuance is automatically divided into three parts, the compensation, the mining reward, and the treasury (burnt by now).
    They are proportional to the DAO deposit, the storage occupation, and the rest of CKBytes.
  - Inflation Rate:
    Nominal inflation rate: the inflation introduced by the primary issuance and the secondary issuance.
    Nominal APC: the anti-dilution compensation rate of Nervos DAO.
    Real inflation rate: the compound inflation rate the nominal inflation rate minus the nominal APC, which is gradual to zero.
  - Circulating Supply
    Until specific block, the total issued CKBytes minus all kinds of locked CBbytes and burnt amount.
  - Liquidity
    Circulating Supply minus current DAO total deposits.

### Other pages

- failed to search: https://explorer.nervos.org/search/fail?q=ckb1qzda0cr08m85hc8jlnfp3zer7xulejywt49kt2rr0vthywaa50xwsq22xdj8q4jdql98qkdhnqzgrsk4nqyavdcratvu
- page not found: https://explorer.nervos.org/404

### Materials

- Axure: https://x2mnhs.axshare.com/
- Figma: https://www.figma.com/file/6XNoimRDbFTTNm016rbIdU/Magickbase?node-id=3745%3A20658


### NervosDAO: https://explorer.nervos.org/nervosdao
<img width="744" alt="image" src="https://user-images.githubusercontent.com/85155313/230821053-36e8da87-28eb-4524-a584-e1ccf4752c3f.png">
<img width="754" alt="image" src="https://user-images.githubusercontent.com/85155313/230820319-9c145201-3646-4820-a521-80f6588bcb97.png">

- Dashboard
<img width="596" alt="image" src="https://user-images.githubusercontent.com/85155313/230820779-20a9522c-fd7e-4ba2-83a5-ffa4d67a778d.png">

  - Deposit: Total deposited and locked capacity. These data will be updated on 00:00 (UTC +8).
  - Claimed Compensation: Total claimed compensation by depositors.
  - Estimated APC: The estimated annual percentage rate change.
  - Addresses: The total number of the address who participate Nervos DAO. 
  - Average Deposit Time: The average deposit time of all depositors.
  - Unclaimed Compensation: The total unclaimed compensation of all depositors, this amount of CKB could be withdraw from Nervos DAO.
  - Secondary Issuance: Provide the more details about the rates of Secondary Issuance. Click [here](https://docs.nervos.org/docs/basics/concepts/economics/#secondary-issuance) to see more about Secondary Issuance.
    - Mining Reward
    - Deposit Compensation
    - Burnt

- Transaction
<img width="578" alt="image" src="https://user-images.githubusercontent.com/85155313/230821000-7aeabf81-d4b2-4271-8dc9-b5d1ad5f2093.png">
  
  - Deposit Transaction: User deposit CKB in this transaction. This kind of transaction will be marked with this icon in the reciever side.<img width="40" alt="image" src="https://user-images.githubusercontent.com/85155313/230819762-74a05785-9ce4-4ce9-9e99-de9acd09106d.png"> 
  
  - Withdraw Transaction: User withdraw CKB in this transaction. This kind of transaction will be marked with this icon in the sender side. Hover on the icon to see the user withdraw details.<img width="33" alt="image" src="https://user-images.githubusercontent.com/85155313/230819691-264956f2-45a6-4651-9d0c-b276f2a69a82.png">
  
  - Nervos DAO compensation calculation: Calculate the compensation amount users could receive from his/her deposit.This kind of transaction will be marked with this icon in the receiver side.<img width="33" alt="image" src="https://user-images.githubusercontent.com/85155313/230819691-264956f2-45a6-4651-9d0c-b276f2a69a82.png">
  
  - Nervos DAO Withdraw Request: User make a withdraw request in this transaction. This kind of transaction will be marked with this icon in the sender side.!<img width="40" alt="image" src="https://user-images.githubusercontent.com/85155313/230819762-74a05785-9ce4-4ce9-9e99-de9acd09106d.png">

- Depositors
<img width="700" alt="image" src="https://user-images.githubusercontent.com/85155313/230820647-3ef1cf34-90b1-4386-8d38-d62d314f6ed8.png">
  All the dipositors will listed below , and ranked by the total deposit amount.
