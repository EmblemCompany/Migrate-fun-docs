# Migration FAQ - Migrate.Fun

## Frequently Asked Questions for Migrators

### General Questions

#### What is Migrate.Fun?

Migrate.Fun is a secure platform that helps token projects migrate from old tokens to new tokens. As a user, you exchange your old tokens for new ones through an automated process.

#### What are MFT tokens?

MFT (Migration Fungible Tokens) are receipt tokens you receive when migrating. After the migration period ends, you burn MFT 1:1 to claim your new tokens.

#### Is it safe?

Yes. All tokens are held in program-controlled vaults. Admins cannot access funds until after proper procedures are followed. Smart contracts enforce all rules automatically.

#### Do I need to migrate immediately?

No, you can migrate anytime during the active period (usually 7-30 days). However, migrating earlier ensures you don't miss the deadline.

---

### Migration Process

#### How do I migrate my tokens?

1. Connect your wallet to the platform
2. Select the migration project
3. Enter the amount to migrate
4. Approve the transaction
5. Receive MFT tokens as receipt

#### Can I migrate multiple times?

Yes! You can migrate in portions. All migrations accumulate, and you receive MFT for each migration.

#### What's the exchange rate?

The exchange rate is set by the project admin and displayed in the migration panel. For example, 1.5 means you get 1.5 new tokens per old token.

#### Are there fees?

- Users pay NO migration fees (exact exchange rate honored)
- Platform fee: 3.75% of total liquidity migrated (deducted from pool liquidity, not from users)
- Gas fees: ~0.01 SOL per transaction

---

### Claiming New Tokens

#### When can I claim new tokens?

After the migration period ends and the admin finalizes the swap. This usually happens within 24 hours of migration ending.

#### How do I claim?

1. Go to the Claims panel
2. Enter amount of MFT to burn
3. Approve transaction
4. Receive new tokens 1:1

#### How long do I have to claim?

90 days from when migration ends. Don't wait too long!

#### What if I miss the 90-day window?

Unclaimed tokens return to the project admin. Contact the project team directly for assistance.

---

### Merkle Claims (Missed Migration)

#### What if I missed the migration deadline?

If the admin creates a merkle tree, you can still claim within 90 days, though possibly with a penalty rate.

#### How do merkle claims work?

1. Check eligibility in Merkle Claims panel
2. System generates proof automatically
3. Exchange old tokens for new tokens
4. May have reduced rate (e.g., 75% instead of 100%)

#### Why is there a penalty?

To encourage timely migration during the active period. The penalty rate is set by the project admin.

---

### Protected Migrations

#### What is a protected migration?

A migration with a target percentage (e.g., 75% of supply must migrate). If the target isn't met, users get refunds instead. [Learn more about Protected Migrations →](../platform-overview/04-PROTECTED_MIGRATIONS.md)

#### What happens if migration fails?

1. Admin sells collected old tokens for SOL
2. SOL is distributed proportionally to migrators
3. You claim your share of SOL refund

#### How do refunds work?

Your refund = (your_tokens / total_migrated) × total_SOL_recovered

---

### Technical Issues

#### My tokens aren't showing in wallet

Add the custom token:

1. Copy new token mint address from platform
2. Add custom token in wallet
3. Refresh to see balance

#### Transaction failed

- Check you have enough SOL for fees (0.02 recommended)
- Try again during less network congestion
- Increase priority fee if needed

#### "Insufficient Balance" error

- Verify you have old tokens to migrate
- Check you're on the right wallet
- Ensure tokens aren't staked elsewhere

#### Wallet won't connect

- Try different browser
- Clear cache and cookies
- Update wallet extension
- Try different wallet (Phantom, Solflare)

---

### Security Questions

#### Can the admin steal my tokens?

No. Smart contracts enforce:

- Fixed exchange rates
- Automatic token distribution
- Time-locked LP tokens
- Protected vault system

#### What if the project is a scam?

- Check project legitimacy before migrating
- Verify official links
- Protected migrations offer refunds if targets aren't met
- Platform enforces security rules regardless

#### Are my MFT tokens valuable?

MFT tokens are only valuable for claiming new tokens from the specific project. They have no other use or market value.

---

### Special Situations

#### I only want to migrate some tokens

That's fine! Migrate any amount you want. You can always migrate more later during the active period.

#### I accidentally sent tokens to wrong address

Blockchain transactions are irreversible. Always double-check addresses. Contact support for guidance.

#### The migration period ended but I still have old tokens

Check if merkle claims are available. If not, you'll need to contact the project team directly.

#### I have tokens in multiple wallets

You need to migrate from each wallet separately. Each wallet tracks its own migration.

---
