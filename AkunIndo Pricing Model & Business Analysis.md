# AkunIndo Pricing Model & Business Analysis

## Cost Analysis Per User

### Infrastructure Costs

#### 1. Supabase (Database + Auth + Storage)
- **Free Tier**: 2 organizations, 500MB database, 1GB storage, 50K monthly active users
- **Pro Tier**: $25/month per organization
- **Estimated per user**: 
  - Light users (10 receipts/month): ~$0.05/month
  - Average users (50 receipts/month): ~$0.15/month
  - Heavy users (200 receipts/month): ~$0.50/month

#### 2. Mistral AI OCR Processing
- **Cost**: $1 per 1000 pages (as per documentation)
- **Estimated per user**:
  - Light users: $0.01/month (10 receipts)
  - Average users: $0.05/month (50 receipts)
  - Heavy users: $0.20/month (200 receipts)

#### 3. API Hosting (Vercel)
- **Free Tier**: 100GB bandwidth, serverless functions
- **Pro Tier**: $20/month for team
- **Estimated per user**: ~$0.02/month (negligible with serverless)

#### 4. Image Storage & Processing
- **Storage**: ~500KB per receipt after optimization
- **Bandwidth**: Download for exports/viewing
- **Estimated per user**:
  - Light users: 5MB storage + 10MB bandwidth = ~$0.01/month
  - Average users: 25MB storage + 50MB bandwidth = ~$0.05/month
  - Heavy users: 100MB storage + 200MB bandwidth = ~$0.20/month

### Total Infrastructure Cost Per User

| User Type | Receipts/Month | Database | OCR | Hosting | Storage | **Total Cost** |
|-----------|----------------|----------|-----|---------|---------|----------------|
| Light | 10 | $0.05 | $0.01 | $0.02 | $0.01 | **$0.09** |
| Average | 50 | $0.15 | $0.05 | $0.02 | $0.05 | **$0.27** |
| Heavy | 200 | $0.50 | $0.20 | $0.02 | $0.20 | **$0.92** |

### Additional Operational Costs
- Customer support: ~$0.50/user/month (estimated)
- Development & maintenance: ~$0.30/user/month (amortized)
- Marketing & sales: ~$0.20/user/month
- **Total operational**: ~$1.00/user/month

### Break-Even Analysis
**Minimum revenue needed per user**: $1.27/month (average user + operations)

---

## Business Model Proposals

### Model 1: Freemium with Receipt Limits

#### Pricing Tiers
1. **Free Tier**
   - 10 receipts/month
   - Basic features only
   - No customer support
   - Manual export only
   - **Cost**: $0.09/user
   - **Revenue**: $0 (marketing investment)

2. **Starter** - Rp 49,000/month (~$3.20 USD)
   - 50 receipts/month
   - All features
   - Email support
   - Excel/CSV export
   - **Margin**: $3.20 - $1.27 = $1.93/user (60% margin)

3. **Professional** - Rp 99,000/month (~$6.50 USD)
   - 200 receipts/month
   - Priority support
   - WhatsApp Bot integration
   - Advanced export options
   - **Margin**: $6.50 - $1.92 = $4.58/user (70% margin)

4. **Business** - Rp 199,000/month (~$13 USD)
   - Unlimited receipts
   - Phone support
   - API access
   - Multi-user (coming in v2)
   - **Margin**: $13 - $3.00 = $10/user (77% margin)

#### Sustainability Strategy
- **Conversion target**: 10% free → paid
- **Distribution**: 70% free, 20% starter, 8% professional, 2% business
- **Average revenue per user (ARPU)**: $1.54/month
- **Break-even at**: ~5,000 total users (500 paid)

---

### Model 2: Pay-Per-Receipt Bundle

#### Pricing Structure
1. **Starter Pack** - Rp 29,000 (~$1.90 USD)
   - 30 receipt credits
   - Valid for 3 months
   - **Per receipt**: $0.063
   - **Margin**: 70% after costs

2. **Value Pack** - Rp 79,000 (~$5.20 USD)
   - 100 receipt credits
   - Valid for 6 months
   - **Per receipt**: $0.052
   - **Margin**: 75% after costs

3. **Business Pack** - Rp 149,000 (~$9.80 USD)
   - 250 receipt credits
   - Valid for 12 months
   - **Per receipt**: $0.039
   - **Margin**: 80% after costs

#### Sustainability Strategy
- **No monthly commitment** (lower barrier for SMEs)
- **Prepaid model** improves cash flow
- **Usage-based** aligns cost with value
- **Average purchase**: 2.5 packs/year = $4.30/user/year
- **Break-even at**: ~3,000 active users

---

### Model 3: Ecosystem Partnership Model

#### Core Offering
1. **Basic App** - FREE
   - Unlimited manual entry
   - 20 OCR receipts/month
   - Funded by partnerships

2. **Premium Features** - Rp 39,000/month (~$2.60 USD)
   - Unlimited OCR
   - Advanced exports
   - Priority processing

#### Revenue Streams
1. **Accounting Software Partnerships**
   - Revenue share: $0.50/user/month from partners
   - Integration with Jurnal.id, Zoho Books, etc.

2. **Financial Services Referrals**
   - Business loans: $20-50 per successful referral
   - Business insurance: $10-30 per policy
   - Payment processing: 0.1% of transaction volume

3. **Educational Content**
   - Accounting courses: Rp 199,000 (~$13)
   - Tax compliance guides: Rp 99,000 (~$6.50)
   - Commission: 30% to AkunIndo

#### Sustainability Strategy
- **Diversified revenue** reduces dependency on subscriptions
- **Value-added services** increase customer lifetime value
- **Target ARPU**: $2.80/month (subscription + partnerships)
- **Break-even at**: ~2,000 active users

---

## Recommended Approach

### Phase 1: Freemium Launch (Months 1-6)
- Start with **Model 1** (Freemium)
- Focus on user acquisition
- Validate product-market fit
- Target: 5,000 users, 10% conversion

### Phase 2: Optimize & Expand (Months 7-12)
- Introduce **Model 2** (Pay-per-receipt) as alternative
- A/B test pricing points
- Add partnership integrations
- Target: 15,000 users, 15% paid

### Phase 3: Ecosystem Growth (Year 2+)
- Implement **Model 3** partnerships
- Launch team features
- Expand to neighboring markets
- Target: 50,000 users, $3+ ARPU

---

## Key Success Metrics

1. **Customer Acquisition Cost (CAC)**: Keep under $5/user
2. **Monthly Churn Rate**: Target <5% for paid users
3. **Lifetime Value (LTV)**: Achieve 3:1 LTV/CAC ratio
4. **Gross Margin**: Maintain 70%+ on paid tiers

## Risk Mitigation

1. **OCR Cost Overrun**
   - Implement smart caching
   - Batch process during off-peak
   - Consider local OCR for simple receipts

2. **Storage Costs**
   - Aggressive image compression
   - Tiered storage (hot/cold)
   - Automatic cleanup after exports

3. **Price Sensitivity**
   - Offer annual discounts (20% off)
   - Student/NGO pricing
   - Referral rewards program

---

*These models are designed for the Indonesian market's price sensitivity while ensuring sustainable unit economics. The key is starting simple, validating willingness to pay, and expanding revenue streams over time.*