# Encryptix Protocol Documentation

## Overview
Encryptix is an on-chain event ticketing platform designed for anonymous users, Web2 users, and Web3 users. It offers a seamless user experience comparable to platforms like Luma, leveraging advanced cryptographic techniques like Fully Homomorphic Encryption (FHE) and Account Abstraction (AA) to ensure privacy and interoperability.

Encryptix enables event organizers to host events and users to securely purchase tickets while maintaining anonymity or interacting through traditional Web3 wallets. For anonymous users, Encryptix ensures that their identities are hidden while allowing seamless event participation.

---

## Key Features

### 1. **Multi-User Support**
- **Web3 Users**: Standard wallet-based interaction.
- **Web2 Users**: Access via Account Abstraction (AA) and gasless transactions.
- **Anonymous Users**: Encrypted wallet addresses and secure ticket validation through FHE.

### 2. **Anonymity with FHE**
Encryptix uses Fully Homomorphic Encryption (FHE) to provide anonymity for users opting for the "Anon Ticket" option. This ensures:
- The encrypted holder address is stored on the blockchain.
- Ciphertext is securely stored off-chain using the Inco platform.
- Event organizers can verify encrypted tickets without revealing user identities.

### 3. **Decentralized Architecture**
- **Linea Blockchain**: Stores encrypted holder addresses.
- **Inco Storage**: Functions as encrypted off-chain storage, similar to IPFS but with privacy-preserving capabilities.
- **Hyperlane SDK**: Ensures secure cross-chain messaging.

### 4. **Enhanced User Experience**
- Local wallet generation for ticket holding.
- Gasless transactions for Web2 users.
- Ticket details embedded in QR codes for easy verification.

### 5. **FHE Integration**
- User identity and ticket ownership verification via re-encryption calls provided by the Inco gateway.
- Composable cryptographic operations allow users to interact seamlessly across events, win lotteries, and more.

---

## Workflow

### User Journey

1. **User Registration**:
   - Connect a wallet using Privy (for Web3 users).
   - Generate a fresh wallet locally (for anonymous users).

2. **Ticket Purchase**:
   - Approve USDC transfer for the event contract.
   - Generate a pair of public and private keys for ticket holding.
   - Encrypt the public key using the `fhevmjs` SDK.

3. **Data Storage**:
   - The encrypted holder address is stored on Linea.
   - Ciphertext is stored off-chain on Inco via Hyperlane SDK.

4. **QR Code Generation**:
   - A QR code is generated containing:
     - EIP-712 signed message.
     - Hash of ticket information.

5. **Verification**:
   - The event organizer uses Inco’s re-encrypt functionality to securely verify ticket ownership.
   - Cross-checks the QR code, signature, and ticket information.

### Organizer Workflow

1. Deploy an event contract on Linea blockchain.
2. Specify event details (e.g., name, ticket price, location).
3. Verify attendee tickets by using re-encryption calls and comparing against QR code data.
4. Conduct raffles or special activities using encrypted ticket data.

---

$1### Why Linea Blockchain is a Key Choice
Linea Blockchain plays a pivotal role in the Encryptix Protocol by serving as the backbone for storing essential credentials such as NFTs, USDC, and user-specific data. While Inco is utilized as an encrypted IPFS-like gateway for secure off-chain data storage, Linea ensures on-chain accessibility and integrity. Moreover, Linea's composability allows encrypted keys and data to be used in advanced computations, enabling unique features like secure identity management and future data retrieval without compromising privacy. By combining Linea's robust blockchain capabilities with Inco's privacy-focused encrypted storage, Encryptix provides a seamless and secure user experience.

- **Composability**:
  - FHE allows cryptographic operations to be performed directly on encrypted data.
  - Enables seamless interoperability across events.
  
- **Identity Reusability**:
  - Users can reuse their encrypted addresses (eAddresses) for interactions within an event.
  - Supports advanced functionalities like prize distribution or anonymous messaging.

- **Flexibility**:
  - Linea contracts can access unique keys and perform computations.
  - Users can retrieve results in the future without revealing sensitive data.

---

## Smart Contract Design

### Key Components

#### 1. **OriginEventContract**
Handles ticket purchases and communication with Inco and Hyperlane.
- **Features**:
  - User registration and USDC payment handling.
  - Encrypted data storage and QR code generation.
  - Cross-chain message dispatch to Inco.

#### 2. **IncoEventContract**
Manages encrypted ticket verification and raffle operations.
- **Features**:
  - Deterministic key generation for token management.
  - Secure re-encryption for ticket validation.
  - Encrypted random number generation for raffles.

### Data Structures
- **Mappings**:
  - `tokenKeyToEaddressToAmount`: Maps token keys to encrypted addresses and ticket amounts.
  - `requestIdToStruct`: Tracks origin chain and event contract details for callback handling.

- **Events**:
  - `TokenProcessed`: Emitted when a ticket purchase is completed.
  - `TokenPurchased`: Emitted when a user buys a ticket.

---

## Technical Details

### Cross-Chain Messaging
- **Hyperlane SDK**:
  - Facilitates communication between Linea and Inco.
  - Handles encrypted data transfer securely.

### FHE Integration
- **fhevmjs SDK**:
  - Generates public-private key pairs for ticket holding.
  - Encrypts public keys for storage.

- **TFHE Library**:
  - Performs re-encryption for ticket validation.
  - Supports composable cryptographic operations.

### QR Code Verification
1. QR code contains:
   - Encrypted ticket data.
   - Signature for validation.

2. Organizer verifies:
   - eAddress using re-encryption.
   - User’s signed message against the QR code data.

---

## Example Use Cases

### 1. **Anonymous Event Participation**
- Users can attend events without revealing personal information.
- Participate in lotteries and receive rewards using encrypted identities.

### 2. **Seamless Web2 Integration**
- Users interact using familiar Web2 interfaces while enjoying Web3 benefits like privacy and transparency.

### 3. **Raffles and Lotteries**
- Event organizers can randomly select winners using encrypted ticket data.

---

## Future Enhancements

1. **Enhanced Interoperability**:
   - Support for additional blockchains and cross-chain messaging protocols.

2. **Anonymous Communication**:
   - Enable attendees to communicate anonymously within events using eAddresses.

3. **Dynamic Pricing Models**:
   - Allow ticket prices to adjust based on demand or time.

4. **Integration with dApps**:
   - Collaborate with DeFi and NFT platforms for ticket resales and rewards.

---

## Conclusion
Encryptix redefines event ticketing with cutting-edge cryptography and blockchain technology. By leveraging FHE, Hyperlane, and AA wallets, it creates a user-friendly platform that prioritizes privacy, security, and composability. Whether for anonymous users, Web2 adopters, or seasoned Web3 enthusiasts, Encryptix ensures a seamless and secure ticketing experience.

