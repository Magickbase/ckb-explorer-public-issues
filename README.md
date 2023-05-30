# CKB Explorer & Neuron Public Issues

[![Discord](https://img.shields.io/discord/956765352514183188?label=Discord&logo=discord&style=default&color=grey&labelColor=5865F2&logoColor=white)](https://discord.gg/N9nZ3JE2Gg)

This repo is used to manage public issues of [CKB Explorer](https://github.com/nervosnetwork/ckb-explorer) and Neuron.

## User Story list

### CKB Explorer

| SN | User Story | Description | Dir | Issue | Axure |
|----|------------|-------------|-----|-------|-------|
| 0 | General Components | Contain some common compoents | [open](CKB-Explorer-PRDs/GeneralComponents/GeneralComponents.md) | - | - |
| 1 | Export to csv | The feature,Export to csv, provides a function on such as Block page, Transaction page and so on for user to download some transaction info from block explorer | - | [#325](https://github.com/Magickbase/ckb-explorer-public-issues/issues/325) | [open](https://app.axure.cloud/app/project/o093j5/preview/9ug42i) |
| 2 | Nervos DAO | The product requirements about Nervos DAO page | [open](CKB-Explorer-PRDs/NervosDAO/NervosDAO.md) | - | - |

### Neuron

| SN | User Story | Description | Dir | Issue | Axure |
|----|------------|-------------|-----|-------|-------|
| 1 | WalletConnect availability | Whole user story for the usage of WalletConnect, ranging from the dApp to Neuron  CKB wallet | [open](Neuron-PRDs/WalletConnect/GeneralComponent.md) | [#144](https://github.com/Magickbase/neuron-public-issues/issues/144) [#153](https://github.com/Magickbase/neuron-public-issues/issues/153) [#148](https://github.com/Magickbase/neuron-public-issues/issues/148) | [open](https://vs0cjf.axshare.com/#id=owrcmb&p=%E7%AE%80%E4%BB%8B&g=1) |

## About project management

### Goals

- While reviewing the code, reviewers could quickly locate the issues then jump to the PRDs
- An overview of all product requirements, tech refactories, and so on.
- Keep PRD and related materials up to date and recording on github repo.

### Proposal 1: issue oriented and UserStory as an aspect

> Apart from the PRD.md file, Some SSD , API doc and other tech or any related files could also be attached to this repo or issue in corresponding directory.

1. PO or TO creates an _userstory issue_ on github with estimated _subissues_. Also the related material should be included in the issue.
2. After the issue is created, a new row is supposed to be appended to above table, that is User Story list, after the issue is reviewed by relevant partners.
3. Partners creates their own issues on github referring to the user story issue.
4. PO/TO updates the status of their userstory when subissues are newly attached.
5. If the modifications happen on some modules, then TO/PO can update the PRD.md file; if the modifications happen on tech side, then he/she could update the SDD.md file if necessary.

### Proposal 2: modules oriented with issues related to

1. PO or TO creates an PRD/SSD on local directory within module requrement file that is PRD.md in this case.
2. After the PRD is created and reviewed by relevant ppl , PO/TO splits the PRD.md into subtask and creates issues on github repo.
3. Optionally, a talbe could also be created like proposal 1 and be list on README.md, but the relationship between issue and PRD **must be made** whatever way the PO/TO takes.

## Recommended plugins

- [Markdown Image](https://marketplace.visualstudio.com/items?itemName=hancel.markdown-image)
  - modify plugin setting: "markdown-image.local.path": "pic"
- [markdown all in one](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- [Markdown Compact Table Formatter](https://marketplace.visualstudio.com/items?itemName=cipchk.vscode-markdown-compact-table-formatter)
- [Link Github Issues](https://marketplace.visualstudio.com/items?itemName=dt.ghlink)
  - Search issue with ```project:Magickbase/9``` or ```project:Magickbase/9 label:"userstory"```
