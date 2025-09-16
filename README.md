# 🏦 Vietnam Banks & E-wallets
> *A comprehensive, production-ready dataset for Vietnamese financial institutions*

<div align="center">

[![NPM Version](https://img.shields.io/npm/v/vietnam-banks-and-ewallets?style=for-the-badge&logo=npm&color=CB3837)](https://www.npmjs.com/package/vietnam-banks-and-ewallets)
[![Downloads](https://img.shields.io/npm/dm/vietnam-banks-and-ewallets?style=for-the-badge&logo=npm&color=orange)](https://www.npmjs.com/package/vietnam-banks-and-ewallets)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge&logo=opensourceinitiative)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=for-the-badge&logo=github)](CONTRIBUTING.md)
[![TypeScript](https://img.shields.io/badge/TypeScript-Ready-3178c6?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)

**🚀 The ultimate Vietnamese fintech data solution**

*Complete • Self-contained • Developer-friendly • Production-ready*

---

</div>

## 🌟 Why Choose This Package?

<table>
<tr>
<td align="center">
<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/File%20Folder.png" width="50">
<br><strong>Self-Contained</strong>
<br>All assets included, no external dependencies
</td>
<td align="center">
<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Lightning.png" width="50">
<br><strong>Lightning Fast</strong>
<br>Optimized JSON structure for peak performance
</td>
<td align="center">
<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Shield.png" width="50">
<br><strong>Type Safe</strong>
<br>Full TypeScript definitions included
</td>
<td align="center">
<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Globe%20Showing%20Asia-Australia.png" width="50">
<br><strong>Always Updated</strong>
<br>Latest Vietnamese banking data
</td>
</tr>
</table>

## 🎯 Features That Matter

> **💡 Built for developers, by developers**

- 🏦 **50+ Vietnamese Banks** - Complete coverage of major financial institutions
- 💳 **Popular E-wallets** - MoMo, ZaloPay, ShopeePay, and more
- 🖼️ **High-Quality Logos** - Crisp, scalable assets for all your UI needs
- 📱 **Mobile-First** - Perfect for fintech apps and payment integrations
- 🔍 **Easy Search** - Find banks by code, BIN, or name instantly
- 🚀 **Zero Dependencies** - Lightweight and fast, no bloat
- 📦 **Tree Shakeable** - Import only what you need

## ⚡ Quick Start

### Installation

```bash
# Using npm
npm install vietnam-banks-and-ewallets

# Using yarn
yarn add vietnam-banks-and-ewallets

# Using pnpm
pnpm add vietnam-banks-and-ewallets
```

### Basic Usage

```javascript
import { banks, ewallets } from 'vietnam-banks-and-ewallets';

// 🔍 Find a bank by code
const vietcombank = banks.find(bank => bank.code === 'VCB');
console.log(vietcombank);
// Output: { name: "Ngân hàng...", shortName: "Vietcombank", code: "VCB", ... }

// 💳 Get all e-wallets
const allEwallets = ewallets;
console.log(`Found ${allEwallets.length} e-wallets`);

// 🏦 Search banks by BIN
const bankByBIN = banks.find(bank => bank.bin === '970436');
```

### Advanced Usage

```javascript
import { banks, ewallets, findBankByBIN, searchBanks } from 'vietnam-banks-and-ewallets';

// 🎯 Smart search
const techcombank = searchBanks('Techcombank')[0];
const momoWallet = ewallets.find(wallet => wallet.code === 'MOMO');

// 🔄 Dynamic bank detection from card number
const detectBank = (cardNumber) => {
  const bin = cardNumber.substring(0, 6);
  return findBankByBIN(bin);
};

// 🎨 Use logos in your React components
const BankLogo = ({ bankCode }) => {
  const bank = banks.find(b => b.code === bankCode);
  return <img src={bank?.logo} alt={bank?.shortName} />;
};
```

## 📊 Data Structure

### 🏦 Bank Object
```typescript
interface Bank {
  name: string;         // "Ngân hàng thương mại cổ phần Ngoại thương Việt Nam"
  shortName: string;    // "Vietcombank"
  code: string;         // "VCB"
  bin: string;          // "970436"
  logo: string;         // "./assets/logos/banks/vcb.png"
  swiftCode?: string;   // "BFTVVNVX"
  website?: string;     // "https://www.vietcombank.com.vn"
}
```

### 💳 E-wallet Object
```typescript
interface Ewallet {
  name: string;         // "Ví điện tử MoMo"
  shortName: string;    // "MoMo"  
  code: string;         // "MOMO"
  logo: string;         // "./assets/logos/ewallets/momo.png"
  website?: string;     // "https://momo.vn"
  appStore?: string;    // App Store download link
  playStore?: string;   // Google Play download link
}
```

## 🗂️ Project Structure

```
vietnam-banks-and-ewallets/
├── 📁 assets/
│   └── 🖼️ logos/
│       ├── 🏦 banks/           # Bank logos (PNG/SVG)
│       └── 💳 ewallets/        # E-wallet logos (PNG/SVG)
├── 📁 data/
│   ├── 📄 banks.json          # Complete bank dataset
│   └── 📄 ewallets.json       # E-wallet dataset
├── 📁 src/
│   ├── 📄 index.ts            # Main export file
│   └── 📄 types.ts            # TypeScript definitions
├── 📄 README.md
├── 📄 package.json
└── 📄 LICENSE
```

## 🎨 Logo Usage Examples

### React Component
```jsx
import { banks } from 'vietnam-banks-and-ewallets';

const PaymentMethod = ({ bankCode }) => {
  const bank = banks.find(b => b.code === bankCode);
  
  return (
    <div className="payment-method">
      <img 
        src={bank.logo} 
        alt={bank.shortName}
        className="w-12 h-12 rounded-lg"
      />
      <span>{bank.shortName}</span>
    </div>
  );
};
```

### Vue Component
```vue
<template>
  <div class="bank-selector">
    <div 
      v-for="bank in banks" 
      :key="bank.code"
      class="bank-option"
    >
      <img :src="bank.logo" :alt="bank.shortName" />
      {{ bank.shortName }}
    </div>
  </div>
</template>

<script>
import { banks } from 'vietnam-banks-and-ewallets';

export default {
  data() {
    return { banks };
  }
};
</script>
```

## 🌐 Supported Institutions

<details>
<summary><strong>🏦 Major Banks (Click to expand)</strong></summary>

- 🟢 **Vietcombank (VCB)** - Ngân hàng TMCP Ngoại thương Việt Nam
- 🔵 **Techcombank (TCB)** - Ngân hàng TMCP Kỹ thương Việt Nam  
- 🟠 **BIDV** - Ngân hàng Đầu tư và Phát triển Việt Nam
- 🔴 **VietinBank (CTG)** - Ngân hàng TMCP Công thương Việt Nam
- 🟣 **ACB** - Ngân hàng TMCP Á Châu
- *...and 40+ more banks*

</details>

<details>
<summary><strong>💳 E-wallets & Digital Payments (Click to expand)</strong></summary>

- 🎯 **MoMo** - Vietnam's #1 super-app
- ⚡ **ZaloPay** - Zalo's payment platform
- 🛒 **ShopeePay** - Shopee's digital wallet
- 💙 **VNPay** - Leading payment gateway
- 🏪 **GrabPay** - Grab's payment solution
- *...and more digital wallets*

</details>

## 🤝 Contributing

We love contributions! Here's how you can help make this project even better:

### 🐛 Found a Bug?
- Open an issue with detailed steps to reproduce
- Include screenshots if UI-related

### 🏦 Missing a Bank/E-wallet?
- Fork the repository
- Add the institution data to the appropriate JSON file
- Include a high-quality logo (PNG/SVG preferred)
- Submit a pull request

### 💡 Have an Improvement Idea?
- Start a discussion in the Issues section
- We're always open to new features!

### Development Setup
```bash
git clone https://github.com/your-username/vietnam-banks-and-ewallets.git
cd vietnam-banks-and-ewallets
npm install
npm run dev
```

## 📈 Usage Statistics

<div align="center">

![npm](https://img.shields.io/npm/dw/vietnam-banks-and-ewallets?style=social&logo=npm&label=Weekly%20Downloads)
![GitHub stars](https://img.shields.io/github/stars/your-username/vietnam-banks-and-ewallets?style=social)
![GitHub forks](https://img.shields.io/github/forks/your-username/vietnam-banks-and-ewallets?style=social)

</div>

## 📜 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**⭐ Star this repo if it helped you!**

Made with ❤️ for the Vietnamese developer community

[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=for-the-badge&logo=github)](https://github.com/your-username)
[![Twitter](https://img.shields.io/badge/Twitter-Follow-1da1f2?style=for-the-badge&logo=twitter)](https://twitter.com/your-username)

</div>