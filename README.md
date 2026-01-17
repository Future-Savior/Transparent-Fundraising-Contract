# AidVaultLite — Transparent Donation Escrow (Monad Testnet)

## Live Demo / Links
- **Live Demo (Replit)**: https://monad-connect--wowgiao.replit.app
- **Contract (Monad Testnet)**: `0x595f0D1fc18D5C15D768461c3DD1d956d0fC1141`
- **Explorer (MonadVision)**: https://testnet.monadvision.com/address/0x595f0D1fc18D5C15D768461c3DD1d956d0fC1141

---

## 项目简介
AidVaultLite 是一个**去中心化募捐托管合约**（Donation Escrow）。  
捐款**直接进入链上合约托管**，达到目标金额后才允许放款到受益人地址；全过程可在区块浏览器上公开审计，减少中心化募捐平台的“黑箱”问题。

---

## 解决的痛点
传统募捐常见问题是资金流向不透明：捐款人无法快速验证“钱是否到达受益人/是否被挪用”。  
本项目用链上合约提供：
- **公开可审计的资金托管**
- **规则自动执行（达到目标才放款）**

---

## 功能特点（MVP）
- **链上托管**：捐款进入合约，而不是平台账户
- **透明可审计**：所有交易可在 MonadVision 查看
- **达标放款**：`totalDonated >= goal` 才能 `withdrawToBeneficiary`
- **退款机制**：未达标且符合条件时可 `refund`（MVP 演示用）

---

## 演示流程（Demo Script）
1. 打开 Live Demo，连接 MetaMask 并切到 **Monad Testnet (Chain ID 10143)**
2. 输入金额（例如 `0.005`）点击 **Donate**（可多次捐款）
3. 达到 `goal` 后点击 **Withdraw to Beneficiary**
4. 点击页面的 Explorer 链接，在 MonadVision 中核对：
   - `Donate` 交易
   - `WithdrawToBeneficiary` 交易
   - 合约余额变化

---

## 合约接口（简要）
- `donate()`：捐款（payable）
- `withdrawToBeneficiary()`：达标后放款到受益人
- `refund()`：符合条件时退款
- `goal() / totalDonated() / beneficiary() / donated(address)`：只读查询

---

## Network
- **Network**: Monad Testnet
- **Chain ID**: 10143
- **Native Token**: MON

---

## 限制与未来工作
- 本项目为黑客松 MVP，**不解决链下身份真实性验证**（受益人是否真实、物资是否发放等）
- 未来可加入：多签审批、里程碑拨款、项目审核/证明机制、反滥用策略等

---

## 安全提示
仅用于测试网演示。不要用于真实资金环境。
