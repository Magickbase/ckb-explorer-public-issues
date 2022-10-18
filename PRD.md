### General Components:

- Navbar in the header

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

- Footer

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

- Notification
  - Action notification: like copy text successfully
  - Network error
  - Maintainance notification
  - Reorg notification

### Homepage: https://explorer.nervos.org/

- Statistics
  - Last Block: block number of the tip block
  - Average Block Time: 1 hour/(count of blocks in the past hour)
  - Mining Hash Rate:
  - Mining Difficulty:
  - Epoch: epoch number and epoch_index/epoch_length
  - Estimated Epoch Time: duration per epoch
  - Transactions per minute
  - Transactions in last 24h
  - Chart of `average block time`
  - Chart of `hash rate`
- Last Block List(15 blocks)
  - block number: link to block page `/block/{number}`
  - age: past time from now
  - miner: miner address, link to page `/address/{miner}`
  - rewards: mining reward to the miner
  - count of transactions
  - count of cells generated/destroyed in the block: count of outputs - count of inputs
- Transaction List(15 transactions)
  - transaction hash: link to transaction page `/transaction/{hash}/`
  - confirmations: block height from now
  - block number: link to block page `/block/{number}`
  - age: past time from now
  - covered capacity of the transaction: sum of inputs' capacity or sum of outputs' capacity
  - count of cells generated/destroyed: count of outputs - count of inputs

### Block List Page: https://explorer.nervos.org/block/list

- Height: block number, link to block page `/block/{number}`
- Transactions: count of transactions in the block
- Reward: mining reward sent in the block
- Miner: address of miner, link to `/address/{miner}`
- Time

### Transaction List Page: https://explorer.nervos.org/transaction/list

- Transaction hash: link to transaction page `/transaction/{hash}`
- Height: number of the block which packaged the transaction, link to `/block/{number}`
- Capacity: covered capacity of the transaction, sum of inputs' capacity or sum of outputs'capacity
- Time

### Block Page: `/block/{number | hash}`

- Overview

  - Block hash
  - Block height
  - Count of transactions
  - Count of proposal transactions: `proposals` of the block
  - Miner reward: first transaction of the block
  - Difficulty: `compact_target` of the block
  - Nonce: `nonce` of the block
  - Count of uncle blocks: `uncles` of the block
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

- Overview

  - Transaction Hash
  - Copy button: click to copy transaction hash
  - Download button: click to download raw data structure of the transaction
  - Block Height: number of block packaged this transaction, link to `/block/{number}`
  - Transaction fee: fee of this transaction, equals to `sum(output.capacity) - sum(input.capacity)`
  - Timestamp: timestamp of the block packaged this transaction
  - Status: `pending` or `x confirmations`, confirmations is the depth of block
  - Transaction parameters
    - Cell deps
    - Header deps
    - Witnesses

- Input Cell List

  - address toggle: switch address between deprecated format and active format
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
  - input item
    - index: index of input cell in the list, start from 0
    - right-arrow: every input cell comes from another transaction as output cell, the arrow is a link to the transaction generated this cell.
    - address: address owns this cell
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

- Overview

  - Address
  - Copy button: click to copy the address
  - Navigation button: click to page of deprecated address format(if exists) or active address format
  - Live Cells: count of live cells owned by this address
  - Block Mined: count of block rewards sent to this address
  - Lock Script: raw lock script data structure
    - code hash: code hash field of this lock script, will show a script tag if exists
    - hash type: hash type field of this lock script
    - args: args field of this lock script

- Assets

  - CKB: capacity of plain ckb cells
  - Occupied: A cell is consideres as "occupied" if the type script of this cell is not empty or the data field of this cell is not empty. Here "occupied" represents the total capacity of all occupied cells belongs to the address.
  - Nervos DAO deposit: capacity deposited into Nervos DAO
  - Nervos DAO compensation: interest earned by deposited capacity
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

- Transaction List
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

### Sudt List Page: `/tokens`

- UAN & Name: show uan, full name and description, UAN is a special naming convention and can be found in https://github.com/nervosnetwork/rfcs/pull/335
- 2hr transactions: count of transactions happened in the last 24hrs
- Address count: count of holders(any address has hold this token will be included, even it has 0 balance now)
- Created time: time that token has been deployed on the chain

### Sudt Info Page: `/sudt/{hash}`

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

- Collection Name
- Type: m-NFT, NRC 721, CoTA
- Holder/Minted: count of holders and minted nft token item, different from the definition of holders of sudt, an address transferred its all nfts out won't not be treated as a holder
- Creator: address of NFT collection creator, link to `/address/{address}`

### NFT Collection Page: `/collections/{hash | cota id}`

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

- Name
- Description
- Links: RFC, Source Code, Update message, Project website
- On-chain data
  - Code hash
  - Hash type
  - Cell out point
  - Dep type

### Charts Page: `/charts` or `/charts/{chart name}`

When the charts is based on time series, they are generally based on daily statistics, which mean the 
If not explictly specify the time series unit of the chart, it means the charts is generated as daily statistics.

- Block
  - Block time distribution: the x-axis is block intervals in seconds, and the y-axis is the frequency of occurrence in the latest 50,000 blocks.
  - Epoch time distribution: the x-axis is epoch intervals in hours, and the y-axis is the frequency of occurrence in the latest 500 epochs.
  - Average block time: average block intervals with daily & weekly *sliding smooth window*
    First calculate average block time by hour, and then calculate average daily smooth window by each timestamp with its preceding 24 hour records.
    Calculate rolling average weekly by each timestamp with its preceding 7 * 24 hour recrods.
    The x-axis of this chart is based on hour.
- Mining
  - Difficulty & Hash Rate & Uncle Rate
  - Epoch Time & Epoch Length
  - Difficulty
  - Hash Rate
  - Uncle Rate
  - Top Miners(Recent 7 days)
- Activities
  - Transaction count per day
  - Unique address Used per day: count of addresses used accrued from 0
  - Cell count: current total count of live cells and dead cells on chain by each day.
  - Balance ranking: list 50 addresses that hold the most capacity
  - Balance distribution
  - Transaction fee
- Nervos DAO
  - Total deposit: total deposited and locked capacity on chain and deposited addresses by each day.
  - Daily deposit: deposited capacity and deposited addresses per day
  - Deposit to circulation ratio: the ratio of DAO deposit to circulating supply. Where the circulating supply is equal to the total supply minus the burnt part and the unvested part.
- Economic Status
  - Total supply:
    Total supply equals the sum of the primary issuance and the secondary issuance;
    The burnt part equals the sum of the 25% genesis issuance burnt and the burnt portion in the secondary issuance;
    The unvested part equals the portion that is locked by time lock, which will be released gradually by a predefined schedule.
    The circulating supply is equal to the total supply minus the burnt part and the unvested part.
  - Nominal DAO compensation rate:
    The nominal compensation rate is provided by DAO when there is no burnt portion in the secondary issuance.
    The real compensation rate is always higher than the nominal compensation rate.
  - Secondary issuance:
    The secondary issuance is automatically divided into three parts, the compensation, the mining reward, and the treasury (burnt by now).
    They are proportional to the DAO deposit, the storage occupation, and the rest of CKBytes.
  - Inflation rate:
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
