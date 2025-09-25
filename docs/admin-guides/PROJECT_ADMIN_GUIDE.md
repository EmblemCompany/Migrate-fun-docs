# Project Admin Guide - Migrate.Fun Platform

## Table of Contents

1. [Overview](#overview)
2. [Before You Begin](#before-you-begin)
3. [Step-by-Step Setup Guide](#step-by-step-setup-guide)
4. [Migration Types](#migration-types)
5. [Managing Your Migration](#managing-your-migration)
6. [Post-Migration Actions](#post-migration-actions)
7. [Troubleshooting](#troubleshooting)
8. [FAQ](#faq)

---

## Overview

The Migrate.Fun Platform enables project administrators to migrate their community from an old token to a new token while automatically creating liquidity pools. This guide will walk you through the entire process.

### Key Benefits

- ✅ Automated token migration
- ✅ Automatic liquidity pool creation
- ✅ Built-in security features
- ✅ Support for multiple DEXs (Raydium, Meteora, PumpSwap)
- ✅ Optional user protection mechanisms

---

## Before You Begin

### Prerequisites

#### 1. **Existing Liquidity Pool**

You must have an existing liquidity pool containing your old token on one of these platforms:

- Raydium (CPMM)
- Meteora
- PumpSwap (pump.fun)

#### 2. **New Token**

You need either:

- An existing new token mint address, OR
- Token details to create a new token (name, symbol, supply)

#### 3. **Wallet Requirements**

- Sufficient SOL for:
  - Platform creation fee (typically 1 SOL)
  - Transaction fees (~0.01 SOL)
  - Token creation (if creating new token: ~0.1 SOL)
- New tokens for distribution (if using existing token)

#### 4. **Planning Your Migration**

Decide on:

- **Migration dates**: Start and end times
- **Exchange rate**: How many new tokens per old token
- **Migration fee**: Platform takes 3.75% of total liquidity migrated
- **Protection type**: Unprotected (trust-based) or Protected (with safeguards)

---

## Step-by-Step Setup Guide

### Step 1: Connect Your Wallet

1. Navigate to the migration platform
2. Click "Connect Wallet"
3. Choose your wallet (Phantom, Solflare, etc.)
4. Approve connection

### Step 2: Enter Your Pool Information

#### Finding Your Pool ID

1. Go to your DEX platform (Raydium/Meteora/PumpSwap)
2. Find your token's liquidity pool
3. Copy the pool address/ID

#### In the Platform

1. Paste your pool ID in the "Pool ID" field
2. Click "Fetch Pool Info"
3. Verify the detected tokens are correct
4. Select which token is the quote token (usually SOL or USDC)

### Step 3: Configure Your New Token

#### Option A: Create New Token

1. Select "Create New Token"
2. Enter token details:
   - **Name**: Full token name (e.g., "Hustle Token")
   - **Symbol**: Token ticker (e.g., "HSTL")
   - **Supply**: Total supply (e.g., 1,000,000,000)
   - **Decimals**: Usually 9 for Solana tokens
3. Click "Create Token"
4. Approve the transaction

#### Option B: Use Existing Token

1. Select "Use Existing Token"
2. Enter your new token mint address
3. The platform will verify the token exists

### Step 4: Set Migration Parameters

#### Basic Settings

- **Project ID**: Unique identifier (max 16 characters, no spaces)
- **Project Name**: Display name (max 32 characters)
- **Exchange Rate**: How many new tokens per 1 old token
  - Example: 1.5 = users get 1.5 new tokens for each old token
  - Maximum: 1000x (1000 new per 1 old)

#### Migration Period

- **Start Date/Time**: When migration begins
  - Can be immediate or scheduled
  - Cannot be more than 1 hour in the past
- **End Date/Time**: When migration ends
  - Minimum: 1 hour from start
  - Recommended: 7-30 days

#### Fees

- **Platform Fee**: Fixed at 3.75% of total liquidity migrated
  - Automatically deducted from swap proceeds
  - Goes to platform treasury

### Step 5: Choose Protection Level

#### Unprotected Migration (Default)

- **For**: Established projects with community trust
- **Admin Access**: Can withdraw immediately after migration ends
- **Best When**: You have an established reputation

#### Protected Migration

Protected migrations ensure meaningful community participation before proceeding. [Detailed Guide →](../platform-overview/04-PROTECTED_MIGRATIONS.md)

- **For**: New projects or those wanting extra security
- **Features**:
  - Set target migration percentage (50-95%)
  - Automatic evaluation at deadline
  - Refunds if target not met
  - 90-day claim period protection
- **Admin Access**: Must wait 90 days OR get platform admin approval

**To Enable Protection:**

1. Check "Enable Protected Migration"
2. Set target percentage (e.g., 75% of supply must migrate)
3. Platform calculates target amount automatically

### Step 6: BONK.fun Integration (Optional)

If you want to split LP tokens with BONK.fun:

1. Check "Enable BONK.fun Integration"
2. The split is automatically set to:
   - 90% for BONK.fun official recipient
   - 10% for project admin
   - These percentages are hardcoded and cannot be changed

### Step 7: Review and Create

1. Review all settings carefully
2. Check estimated costs:
   - Platform fee
   - Gas fees
   - Token creation (if applicable)
3. Click "Create Migration Project"
4. Approve all transactions in your wallet

### Step 8: Deposit New Tokens

After project creation:

1. You'll be prompted to deposit new tokens
2. Enter the amount to deposit
   - Must cover all potential migrations
   - Formula: `old_token_supply × exchange_rate`
3. Approve token transfer
4. Click "Deposit Tokens"

### Step 9: Initialize Project

Final step to activate:

1. Click "Initialize Project"
2. This will:
   - Create MFT (receipt) token
   - Activate the migration
   - Start accepting user migrations

---

## Migration Types

### Standard Migration

- Users migrate at will during the period
- Receive MFT tokens as receipts
- Can claim new tokens after migration ends

### Percentage-Based Migration (Protected)

- Has a target percentage goal
- Evaluated at deadline
- If successful: Proceeds to pool creation
- If failed: Users get refunds

### BONK.fun Enhanced Migration

- Creates pool with fixed 90/10 split (hardcoded)
- BONK.fun gets 90% of LP tokens to official recipient
- Project admin gets 10% of LP tokens
- Both portions locked via NFTs
- Split percentages and recipient address are hardcoded for security

---

## Managing Your Migration

### During Migration Period

#### Monitor Progress

- Check dashboard for:
  - Total migrated
  - Number of participants
  - Time remaining
  - Current percentage (if protected)

#### Pause/Resume (If Needed)

- Platform admin can pause if issues arise
- Contact support for emergency assistance

#### Communication

- Keep community informed of progress
- Share migration link
- Post regular updates

### After Migration Ends

#### Finalize Swap

Once migration period ends:

1. Navigate to your project dashboard
2. Click "Finalize Swap"
3. Set slippage tolerance (usually 0.5-1%)
4. This will:
   - Sell collected old tokens for SOL/USDC
   - Create new liquidity pool
   - Lock LP tokens

#### Pool Creation Options

- **Standard Raydium**: Creates CPMM pool
- **BONK.fun**: Creates with split LP tokens

---

## Post-Migration Actions

### Admin Dashboard Overview

The Admin Panel provides comprehensive control over your migration project through various stages:

#### Available Actions by Stage

1. **After Project Creation**

   - **Deposit New Tokens**: Fund the migration with new tokens
   - **Initialize Project**: Activate the migration to start accepting users

2. **During Migration Period**

   - **Monitor Progress**: View real-time migration statistics
   - **Track Participants**: See number of users who have migrated
   - **View Remaining Time**: Countdown to migration end

3. **After Migration Ends**
   - **Finalize Swap**: Execute market sell and create liquidity pool
   - **Lock LP Tokens**: Secure liquidity for 90 days
   - **Create Merkle Tree**: Set up claims for non-migrators
   - **Emergency Withdraw**: Access funds in special circumstances
   - **Recover Unclaimed**: Retrieve unclaimed tokens after claims period

### For Unprotected Migrations

#### Immediate Actions (After Migration Ends)

- **Finalize Swap**: Sell collected old tokens and create new pool
- **Emergency Withdraw**: Can withdraw immediately if swap fails
- **Recover Unclaimed**: Access unclaimed tokens right away

#### LP Token Management

- LP tokens automatically locked for 30 days
- Will be released to admin wallet after lock period
- For BONK.fun: Both portions locked via Raydium NFTs

### For Protected Migrations

#### Evaluation (At Deadline)

Protected migrations have a target percentage that must be met:

1. **Automatic Evaluation**

   - System checks total migrated vs target amount
   - Occurs automatically at migration deadline
   - No admin action required

2. **If Successful (Target Met)**

   - Migration proceeds normally
   - Finalize swap available
   - Create liquidity pool
   - Enter 90-day claims period

3. **If Failed (Target Not Met)**
   - Migration marked as failed
   - Pool creation blocked
   - Users can claim SOL refunds
   - Proportional to migration amount

#### Refund Process (Failed Migrations)

When a protected migration fails:

1. **Automatic SOL Recovery**

   - Old tokens sold for SOL/USDC
   - Proceeds allocated for refunds
   - Proportional distribution

2. **User Refund Claims**

   - Users claim via Refund Panel
   - Receives share of recovered SOL
   - Based on tokens migrated
   - One-time claim only

3. **Admin Actions**
   - Cannot create pool
   - Cannot withdraw funds
   - Must wait for refund period
   - Can recover after claims expire

#### 90-Day Claims Period

For successful protected migrations:

- Users have 90 days to claim tokens
- Admin cannot withdraw during this period
- After 90 days: Admin can recover unclaimed
- Applies to both MFT and merkle claims

#### Emergency Access

- Platform admin can enable emergency withdraw
- Allows immediate access to funds for true emergencies
- Bypasses 90-day wait period
- Must be enabled by platform administrator
- Should be rare exception

---

## Admin Panel Functions Guide

### Core Administrative Functions

#### 1. Deposit New Tokens

**When**: After project creation, before initialization
**Purpose**: Fund the migration vault with new tokens
**Process**:

1. Navigate to Admin Panel
2. Find your project in the list
3. Click "Deposit New Tokens"
4. Enter amount to deposit
5. Approve token transfer
6. Confirm transaction

**Important**: Deposit enough to cover all potential migrations (old_supply × exchange_rate)

#### 2. Initialize Project

**When**: After depositing new tokens
**Purpose**: Activate migration and create MFT tokens
**Process**:

1. Ensure new tokens are deposited
2. Click "Initialize Project"
3. This creates MFT (receipt) tokens
4. Migration becomes active for users

#### 3. Finalize Swap

**When**: After migration period ends
**Purpose**: Sell old tokens and create liquidity pool
**Process**:

1. Wait for migration period to end
2. Click "Finalize Swap"
3. Set slippage tolerance (0.5-1% typical)
4. System executes market sell
5. Creates new Raydium pool with proceeds

**Pool Creation Details**:

- Uses collected SOL/USDC from swap
- Pairs with deposited new tokens
- Creates CPMM or AMM v4 pool based on selection
- LP tokens go to program vault

#### 4. Lock LP Tokens

**When**: After pool creation
**Purpose**: Secure liquidity for 30 days
**Process**:

**Standard Projects**:

1. Click "Lock LP Tokens"
2. LP tokens locked via StreamFlow
3. 30-day vesting period
4. Released to admin after period

**BONK.fun Projects**:

1. Click "Lock LP for BONK.fun"
2. 90% locked for BONK.fun official recipient (hardcoded address)
3. 10% locked for project admin
4. Both use Raydium NFT locks
5. Split percentages cannot be modified (hardcoded for security)

#### 5. Emergency Withdraw

**When**: Special circumstances only
**Purpose**: Recover funds when normal flow fails
**Available For**:

- **Unprotected**: After migration ends
- **Protected**: After 90 days OR with platform approval

**Process**:

1. Navigate to Emergency section
2. Select token type (old/new/SOL)
3. Click "Emergency Withdraw"
4. Funds sent to admin wallet

**Valid Use Cases**:

- Pool creation failure
- Liquidity issues
- Technical problems
- Platform-approved emergencies

#### 6. Recover Unclaimed Tokens

**When**: After claims period expires
**Purpose**: Retrieve tokens not claimed by users
**Timing**:

- **Unprotected**: Immediately after migration
- **Protected**: After 90-day claims period

**Process**:

1. Wait for eligible period
2. Click "Recover Unclaimed"
3. Remaining tokens sent to admin
4. Includes both old and new tokens

---

## Merkle Tree Claims System

### Merkle Claims Overview

For users who miss the migration deadline, you can create a merkle tree-based claims system allowing them to claim tokens within a 90-day window.

### Creating a Merkle Tree Snapshot

#### Merkle Claims Prerequisites

- Migration period must be ended
- No existing merkle tree for the project
- Backend claims API must be running

#### Process

1. **Navigate to Claims Snapshot**

   - Go to Admin Panel
   - Select "Create Claims Snapshot"

2. **Take Snapshot**

   - System identifies all non-migrated token holders
   - Includes partial migrators (remaining balance)
   - Excludes DEX pools, burn addresses
   - Shows preview of eligible recipients

3. **Set Penalty Rate (Optional)**

   - Slide to set distribution percentage (0-100%)
   - 100% = full tokens, 50% = half tokens
   - Quick select buttons: 25%, 50%, 75%, 100%
   - Penalty encourages timely migration

4. **Review Recipients**

   - Table shows addresses and amounts
   - Can manually exclude addresses
   - Categories shown (User, LP Pool, Unknown)
   - Export to CSV for records

5. **Create Merkle Tree**
   - Click "Create Merkle Tree"
   - **WARNING**: This is permanent!
   - Cannot change after creation
   - Uploads to claims backend
   - Generates merkle root on-chain

#### Post-Creation

- Users can claim via Claims Panel
- 90-day expiration period
- Admin recovers unclaimed after expiry
- Merkle proofs verified on-chain

### Merkle Tree Management

#### Viewing Status

- Check if merkle tree exists
- View creation timestamp
- See total claimable amount
- Monitor claim progress

#### Claims Monitoring

- Track number of claims
- View remaining unclaimed
- Export claim history
- Check individual claim status

---

## Platform Admin Functions

### Emergency Override Powers

Platform administrators have special privileges for protected migrations:

#### Toggle Emergency Withdraw

**Purpose**: Enable project admin to withdraw during claims period
**When to Use**:

- Project admin needs emergency access
- Technical issues preventing normal flow
- Verified emergency situations

**Process**:

1. Platform admin reviews request
2. Executes `toggle_project_emergency_withdraw`
3. Sets `enabled = true`
4. Project admin can now use emergency withdraw

**Security Notes**:

- Only for protected migrations
- Bypasses 90-day wait
- Should be rare exception
- All actions logged on-chain

### Platform Configuration

Platform admins can update global settings:

#### Update Platform Fees

- Modify project creation fee
- Adjust platform fee percentage
- Change treasury address
- Pause/unpause platform

#### Claim Platform Fees

- Withdraw accumulated platform fees
- Transfer from treasury to admin
- Track fee collection metrics

---

## Backend Integration

### Claims API Endpoints

The backend provides REST APIs for merkle tree management:

#### Key Endpoints

1. **Upload Snapshot**

   ```text
   POST /api/claims/upload
   Body: CSV with addresses and amounts
   ```

2. **Get Merkle Proof**

   ```text
   GET /api/merkle/proof/:address/:epoch
   Returns: Array of proof hashes
   ```

3. **Verify Proof**

   ```text
   POST /api/merkle/verify
   Body: { address, epoch, amount }
   ```

4. **Get Claim Amount**

   ```text
   GET /api/claims/:address/:epoch
   Returns: Claimable amount
   ```

### Database Schema

- **merkle_trees**: Stores tree data and roots
- **claims**: Tracks individual claims
- **distributions**: Maps addresses to amounts
- **epochs**: Project-specific claim periods

---

## Security Best Practices

### For Project Admins

1. **Private Key Security**

   - Use hardware wallets
   - Never share private keys
   - Use multisig if possible

2. **Transaction Verification**

   - Always verify transaction details
   - Check addresses carefully
   - Use small test amounts first

3. **Timing Considerations**

   - Plan migration periods carefully
   - Cannot extend once started
   - Consider time zones

4. **Communication**
   - Keep community informed
   - Provide clear instructions
   - Have support channels ready

### For Protected Migrations - Security

1. **Target Setting**

   - Set realistic targets (60-80%)
   - Consider community size
   - Account for inactive wallets

2. **Emergency Planning**

   - Document emergency procedures
   - Have platform admin contact
   - Prepare contingency plans

3. **Claims Period**
   - 90 days is mandatory
   - Cannot be shortened
   - Plan accordingly

---

## Troubleshooting

### Common Issues

#### "Insufficient Balance"

- **Cause**: Not enough SOL for fees
- **Solution**: Add more SOL to wallet (minimum 0.2 SOL recommended)

#### "Pool Not Found"

- **Cause**: Invalid pool ID or unsupported DEX
- **Solution**: Verify pool ID, ensure pool is on supported platform

#### "Invalid Exchange Rate"

- **Cause**: Rate too high or zero
- **Solution**: Set rate between 0.0001 and 1000

#### "Migration Already Exists"

- **Cause**: Project ID already used
- **Solution**: Choose different project ID

#### "Token Program Mismatch"

- **Cause**: Mixing SPL and Token-2022
- **Solution**: Ensure both tokens use same program

### Transaction Failures

#### During Creation

1. Check wallet has enough SOL
2. Verify all inputs are valid
3. Try refreshing and reconnecting wallet
4. Use different RPC if timeout occurs

#### During Finalization

1. Increase slippage tolerance
2. Wait for less network congestion
3. Ensure pool has sufficient liquidity

---

## FAQ

### General Questions

**Q: How much does it cost to create a migration?**
A: Platform fee (usually 0.1 SOL) + transaction fees (~0.01 SOL) + token creation if needed (~0.1 SOL)

**Q: Can I extend the migration period?**
A: No, dates are fixed once set. Plan accordingly.

**Q: What happens to unmigrated tokens?**
A: They remain with original holders. Platform doesn't force migration.

**Q: Can I cancel a migration?**
A: No, migrations cannot be cancelled once created.

### Technical Questions

**Q: Which wallets are supported?**
A: Phantom, Solflare, and other Solana-compatible wallets

**Q: Can I migrate from Token-2022 to SPL?**
A: No, both tokens must use the same program (both SPL or both Token-2022)

**Q: What's the maximum migration period?**
A: 365 days, but 7-30 days is recommended

**Q: How are LP tokens locked?**
A: Via StreamFlow vesting (standard) or Raydium NFT locks (BONK.fun)

### Security Questions

**Q: Are user funds safe?**
A: Yes, all funds are held in program-controlled vaults

**Q: Can admin access funds early?**
A:

- Unprotected: After migration ends
- Protected: After 90 days or with platform approval

**Q: What if migration fails?**
A: For protected migrations, users get automatic refunds

**Q: How is the exchange rate enforced?**
A: Smart contract automatically calculates and distributes tokens

---

## Best Practices

### Before Launch

- ✅ Test on devnet first if possible
- ✅ Announce migration dates in advance
- ✅ Prepare FAQ for your community
- ✅ Have support channels ready

### During Migration

- ✅ Post daily updates
- ✅ Monitor progress regularly
- ✅ Address user concerns quickly
- ✅ Keep documentation updated

### After Migration

- ✅ Finalize swap promptly
- ✅ Announce pool creation
- ✅ Share pool address with community
- ✅ Plan LP token unlock date

---

## Support & Resources

### Getting Help

- **Documentation**: [Platform Docs]
- **Twitter**: @MigrateFun

### Useful Links

- [Raydium Pools](https://raydium.io/liquidity/pools)
- [Meteora Pools](https://app.meteora.ag/pools)
- [PumpSwap](https://pump.fun)
- [Solana Explorer](https://explorer.solana.com)

### Emergency Contacts

For urgent issues during migration:

- Platform Admin: [Contact Info]
- Technical Support: [24/7 Hotline]

---

## Glossary

**DEX**: Decentralized Exchange (Raydium, Meteora, etc.)

**LP Tokens**: Liquidity Provider tokens representing pool ownership

**MFT**: Migration Fungible Token - receipt tokens for migrants

**PDA**: Program Derived Address - secure on-chain vaults

**Protected Migration**: Migration with user safeguards and evaluation

**Quote Token**: The base currency (SOL or USDC) in a pool

**Slippage**: Acceptable price change during swap execution

**Unprotected Migration**: Trust-based migration with immediate admin access

---

## Appendix: Checklists

### Pre-Migration Checklist

- [ ] Pool ID obtained
- [ ] New token ready or details prepared
- [ ] Exchange rate calculated
- [ ] Migration dates selected
- [ ] Community notified
- [ ] Wallet funded with SOL
- [ ] Support channels ready
- [ ] Backend claims API running (if using merkle)
- [ ] Emergency contacts established

### Launch Day Checklist

- [ ] Create migration project
- [ ] Deposit new tokens
- [ ] Initialize project
- [ ] Verify migration is active
- [ ] Share migration link
- [ ] Post announcement
- [ ] Monitor first transactions
- [ ] Check admin panel access
- [ ] Verify all settings correct

### Post-Migration Checklist

- [ ] Migration period ended
- [ ] Finalize swap executed
- [ ] Pool created successfully
- [ ] LP tokens locked
- [ ] Merkle tree created (if needed)
- [ ] Community notified
- [ ] Pool address shared
- [ ] Documentation updated
- [ ] Monitor claims activity
- [ ] Set calendar reminder for 90 days

### Emergency Response Checklist

- [ ] Identify the issue
- [ ] Document the problem
- [ ] Contact platform admin if needed
- [ ] Request emergency withdraw toggle
- [ ] Execute emergency withdraw
- [ ] Communicate with community
- [ ] File incident report
- [ ] Plan recovery steps

---
