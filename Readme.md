# **Encryptix Protocol Documentation**  
*Revolutionizing event ticketing with Web3 technology*

---

## Related Repositories

- **Frontend Repository**  
  This is the repository containing the frontend code for the Encryptix platform. It's built using Next.js and provides the user interface for interacting with the protocol.  
  [Frontend Repo Link](https://github.com/Encryptx-labs/encryptx-client)

- **Contract Repository**  
  This repository includes all the smart contract code for the Encryptix protocol, handling all the on-chain logic.  
  [Contract Repo Link](https://github.com/Encryptx-labs/encryptx-contracts)

- **Hyperlane Config Repository**  
  This repository contains the Hyperlane configuration for cross-chain communication, enabling secure and private ticketing across multiple chains.  
  [Hyperlane Config Repo Link](https://github.com/Encryptx-labs/hyperlane)

- **Mailer**  
  This repository contains the mailer code for mailing QR codes.  
  [Mailer Repo Link](https://github.com/Encryptx-labs/mailer)

---

## **Overview**  
The Encryptix Protocol is an innovative event ticketing platform leveraging blockchain technology to bring transparency, security, and user empowerment. By eliminating intermediaries and introducing account abstraction through Privy, Encryptix simplifies ticket issuance, transfer, and resale.

This documentation provides a deep dive into the architecture, technical components, and implementation details to help developers and stakeholders understand the protocol thoroughly.

---

## **Features**  
- **Decentralized Ticketing**: Complete transparency in ticket creation, sales, and resales.  
- **Account Abstraction**: Users interact seamlessly with blockchain through Privy's embedded wallet solution.  
- **Social Login**: Simple authentication via email, social accounts, or existing wallets through Privy.  
- **User-Friendly Interface**: Built on **Next.js** for a smooth and intuitive frontend experience.  
- **Secure Transactions**: Leveraging blockchain immutability to prevent fraud and forgery.  

---

## **Architecture**  

### **High-Level Architecture**  
The Encryptix Protocol architecture consists of three major components:  
1. **Frontend (Next.js)**:  
   - Provides a seamless user experience for event organizers and attendees.  
   - Includes features for ticket creation, transfer, and resale.  

2. **Smart Contracts**:  
   - Powers the core functionality of ticket management, ownership transfers, and resale royalties.  
   - Built with **Solidity**, leveraging ERC-721 for unique ticket representation.  

3. **Privy Integration**:  
   - **Embedded Wallets**: Provides secure, user-friendly wallet solution using account abstraction.  
   - **Authentication**: Handles user authentication through various social logins and existing wallets.  
   - **Transaction Management**: Simplifies transaction signing and management.  

---

### **Detailed Architecture Flow**  
Below is an overview of the workflow:  

1. **Ticket Issuance**:  
   - Event organizers deploy an ERC-721 smart contract to mint unique tickets.  
   - Metadata includes event details, seat number, and royalty terms for resales.

2. **Wallet Creation and Authentication**:  
   - Users can log in using email, social accounts, or existing wallets through Privy.  
   - Each user gets an embedded wallet powered by account abstraction.  
   - Wallets are non-custodial and fully controlled by users.  

3. **Transaction Management**:  
   - Users interact with the protocol through Privy's simplified transaction interface.  
   - Account abstraction enables advanced transaction features like batching and sponsored transactions.  

4. **Secondary Market**:  
   - Tickets can be resold securely within the platform.  
   - Royalties for organizers and creators are automated via smart contracts.  

---

## **Tech Stack**  

### **Backend**  
- **Smart Contracts**:  
  - Written in Solidity.  
  - Implements ERC-721 for NFT-based tickets.  
  - Manages royalties, ownership, and event metadata.

### **Frontend**  
- **Framework**: Built with **Next.js** for fast, modern web applications.  
- **UI/UX**: Responsive design and intuitive ticketing interface.  
- **Integration**: Direct connection with blockchain via ethers.js and Privy SDK.  

### **Authentication & Wallet**  
- **Privy**:  
  - Handles user authentication and wallet creation.  
  - Implements account abstraction for improved UX.
  - Manages transaction signing and execution.

### **Blockchain**  
- Supports **EVM-compatible chains** to ensure broad accessibility.  

---

## **Setup and Installation**  

### **Prerequisites**  
1. **Node.js** (v16 or later)  
2. **npm** or **yarn**  
3. **Privy API Keys** (obtain from Privy Dashboard)  
4. **EVM-compatible testnet** credentials (e.g., Goerli, Polygon Testnet)  

### **Clone the Repository**  
```bash
git clone https://github.com/your-repository/Encryptix.git
cd Encryptix
```

### **Install Dependencies**  
```bash
npm install
# or
yarn install
```

### **Configure Privy**  
1. Create a `.env.local` file in the root directory
2. Add your Privy API keys:
```env
NEXT_PUBLIC_PRIVY_APP_ID=your-app-id
```

### **Run the Application**  
#### Development Server  
```bash
npm run dev
# or
yarn dev
```
Visit `http://localhost:3000` to access the platform locally.  

#### Deploy Smart Contracts  
1. Configure `hardhat.config.js` with your network credentials.  
2. Deploy contracts:  
   ```bash
   npx hardhat run scripts/deploy.js --network <network_name>
   ```  

---

## **Demo Video**  
[Watch the Demo](#)  
*(Replace with actual link)*  

---

## **Use Cases**  
- **Event Organizers**: Create and distribute tickets transparently.  
- **Attendees**: Securely purchase and transfer tickets.  
- **Secondary Markets**: Resale with guaranteed royalties for creators.  

---

## **Future Scope**  
- Expand compatibility to additional blockchains.  
- Introduce more robust analytics for event organizers.  
- Collaborate with partners for ticket verification at venues.  
- Implement advanced account abstraction features.
