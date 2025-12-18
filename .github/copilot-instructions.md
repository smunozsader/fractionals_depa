# AI Agent Instructions - Fractional Ownership Project

## Project Overview
This is a fractional ownership (tiempo compartido) system for a vacation property in Mérida, Yucatán. The business model involves selling 4 packages of 13-week access periods, with rental income distribution to non-using owners.

## Technical Stack
- **Platform**: Web application with mobile accessibility
- **Accessibility**: MUST adhere to WCAG 2.1 AA standards (minimum)
  - Keyboard navigation throughout
  - Screen reader compatibility (ARIA labels, semantic HTML)
  - Color contrast ratios (4.5:1 for text, 3:1 for UI components)
  - Responsive design for mobile/tablet/desktop
  - Touch targets minimum 44×44px
  - Text resizable to 200% without loss of functionality
- **Target users**: Include people with disabilities (visual, motor, cognitive)

## Core Business Model
- **Property**: 100m² apartment in north Mérida, sleeps 4 people
- **Ownership Structure**: 4 packages × 13 weeks each = 52 weeks/year
- **Package Price**: $900,000 MXP per fractional ownership
- **Revenue Model**: Property rented to third parties, annualized returns distributed to owners
- **Usage Rule**: Owners choose either rental income OR property usage (up to 13 weeks), not both

## Critical Business Requirements

### Week Distribution Strategy
**Key Challenge**: Distribute 52 weeks fairly among 4 owners ensuring equitable access to high/low seasons.

**CHOSEN SOLUTION**: **Sistema de Rotación Serpiente (Snake/Zig-Zag System)**

This alternating order system guarantees maximum equity:
- **Round 1**: Ticket A → B → C → D (normal order)
- **Round 2**: Ticket D → C → B → A (inverted order)
- **Round 3**: Ticket A → B → C → D (normal order)
- **Round 4**: Ticket D → C → B → A (inverted order)
- Pattern continues through all 52 weeks

**Resulting Distribution**:
- Tickets A & B: 13 weeks each (7 high + 3 medium + 3 low season)
- Tickets C & D: 13 weeks each (6 high + 4 medium + 3 low season)
- The 1-week difference in high season is mathematically inevitable (26÷4=6.5) but compensated by an extra medium season week

**Mérida Seasonal Breakdown**:
- **High Season (26 weeks)**: Dec-Mar, Jul-Aug - optimal weather, major holidays, highest rates
- **Medium Season (14 weeks)**: Apr-May, Oct-Nov - pleasant weather, moderate demand
- **Low Season (12 weeks)**: Late May, Jun, Sep - rainy season, lower rates

**Annual Rotation**: To ensure long-term fairness, rotate the initial order each year:
- Year 1: A→B→C→D starts
- Year 2: B→C→D→A starts
- Year 3: C→D→A→B starts
- Year 4: D→A→B→C starts

**Why Snake System**:
- No owner has permanent advantage (all pick first and last equally)
- Mathematically perfect equity
- Transparent and auditable
- Minimizes conflicts
- Weeks distributed throughout year (not concentrated blocks)

### Financial Calculations
**Rental Rate Benchmarks** (100m² property, north Mérida, 4 pax):
- High Season: $2,500 MXN/night
- Medium Season: $1,800 MXN/night
- Low Season: $1,200 MXN/night

**Three Financial Scenarios** (assumes 28% operational expenses):

1. **Conservative** (70% high / 50% medium / 40% low occupancy):
   - Gross Income: $447,020 MXN/year
   - Net Income: $321,854 MXN/year
   - Per Ticket: $80,464 MXN (8.94% ROI)

2. **Moderate** (80% high / 65% medium / 50% low occupancy):
   - Gross Income: $529,060 MXN/year
   - Net Income: $380,923 MXN/year
   - Per Ticket: $95,231 MXN (10.58% ROI)

3. **Optimistic** (90% high / 75% medium / 60% low occupancy):
   - Gross Income: $602,280 MXN/year
   - Net Income: $433,642 MXN/year
   - Per Ticket: $108,410 MXN (12.05% ROI)

**Operational Expense Categories** (~28% of gross):
- Property management fee (15-20% of gross)
- Maintenance and repairs
- Utilities (water, electricity, internet)
- Insurance (property + liability)
- Property taxes (predial)
- Cleaning services
- Platform fees (Airbnb/Booking commissions)
- Reserve fund contribution (5% of net annually)

**Income Distribution**:
- Only tickets whose weeks were rented receive proportional income
- If owner uses a week, they forfeit that week's rental income
- Annual settlements paid in January for previous year
- Quarterly financial statements to all copropietarios

### Owner Rights Management
**Three Usage Models per Owner**:
1. **Pure Investment**: Rent all 13 weeks → Full ROI (8.94%-12.05% annually)
2. **Mixed Use**: Use some weeks, rent others → Proportional income
3. **Pure Personal Use**: Use all 13 weeks → No cash income but ~$180,000-$230,000 MXN value equivalent (20-25% indirect ROI)

**Reservation Process**:
- Annual calendar published November 1 for following year
- Owners must notify intent to use assigned weeks **60 days in advance**
- Deadline: November 1 of prior year for full-year planning
- Unclaimed weeks (not notified by deadline) → Automatically enter rental pool
- Late claims not accepted after deadline

**Week Exchanges** (permitted between owners):
- Must be mutually agreed in writing
- Notify fiduciary and property manager
- Valid for specific year only (doesn't affect future calendars)
- Example: Ticket A swaps Week 10 with Ticket C's Week 30

**Week 53 Rule** (leap years):
- Option 1: Automatically rented, income split equally among 4 tickets
- Option 2: Rotates (Year 1→A, Year 2→B, Year 3→C, Year 4→D)

## Domain-Specific Terminology
- **Paquete/Ticket**: Fractional ownership package (13 weeks)
- **Usufructo**: Right to use the property
- **Rendimiento**: Annual return/yield from rental income
- **Temporada alta/baja**: High/low season periods
5. Property management features (maintenance scheduling, cleaning coordination)
6. Guest services integration (check-in/check-out, amenities, support)

## Additional Revenue Models to Explore
Beyond basic fractional ownership + rental income, investigate:
- **Premium services**: Concierge, airport transfers, stocked fridge on arrival
- **Dynamic pricing**: Higher rental rates during peak demand periods
- **Extended stays**: Discounted rates for 2+ week bookings from third parties
- **Corporate packages**: Offer to companies for employee benefits
- **Experience bundles**: Partner with local tours/restaurants (Mérida cenotes, haciendas)
- **Upgrade options**: Allow owners to "buy" additional weeks from others
- **Referral program**: Bonus weeks or income for bringing new fractional owners
- **Last-minute deals**: Reduce prices for unsold weeks approaching date
- **Pax**: Guests/occupancy capacity (4 pax = sleeps 4)

## Development Priorities
When building features, prioritize:
1. Fair week distribution algorithm (the "Salomonic" division)
2. Booking/reservation system with owner vs. third-party rental tracking
3. Financial tracking and ROI calculation system
4. anguage: Spanish (UI/documents should support es-MX)

### Legal & Regulatory Framework
**Action Required**: Research and document these regulations:
- **PROFECO** (Procuraduría Federal del Consumidor): Consumer protection for timeshares
  - NOM-029-SCFI-2010: Mexican standard for timeshare services
  - 5-day cooling-off period for contracts
  - Mandatory disclosures about ownership terms
- **Fractional Ownership Law**: Differentiate from traditional timeshare (may have different regulations)
- **Rental Income Tax**: SAT (Servicio de Administración Tributaria) requirements
  - Income reporting obligations for owners
  - Withholding requirements for rental payments
- **Tourism Registry**: Registro Nacional de Turismo requirements for short-term rentals
- **Condominium Regime**: If property is in a building, HOA regulations
- **Foreign Ownership**: If allowing non-Mexican investors (fideicomiso/bank trust in restricted zones
## Legal Structure & Data Model

### Fideicomiso Inmobiliario (Recommended Structure)
**Why Fideicomiso over Traditional Timeshare**:
- Grants **real property rights** (not just usage rights)
- Bank trustee holds formal title, issues 4 equal fiduciary rights
- Each right is sellable, inheritable, and appreciates with property value
- Differentiates from tiempo compartido tradicional (better legal protection)
- Required for foreign investors in restricted zones

**Each Fiduciary Right Includes**:
- 25% patrimonial participation in property
- 13 specific weeks annually per snake calendar
- Proportional share of rental income (for weeks rented)
- Voting rights in coproprietario assemblies
- Right of first refusal when another owner sells
- Inheritance rights (transferable to heirs)
- Sale rights (with preference to existing owners)

**Internal Regulations (Reglamento Interno)**:
- Snake system calendar and rotation rules
- Reservation/usage procedures
- Maintenance fee distribution
- Conflict resolution mechanisms
- Quorum requirements for major decisions
- Sale/transfer protocols
- Property manager obligations
- Emergency reserve fund rules (6 months operating expenses)

### Data Entities Needed
- **Owners/Tickets** (4): Identity, contact, fiduciary right details, payment status
- **Week Allocations** (52): Week number, dates, season, assigned owner, rotation year
- **Reservations**: Type (owner/third-party), dates, guest info, check-in/out status
- **Financial Records**: Weekly income, expenses, distributions, ROI calculations
- **Seasonal Calendar**: Week classifications (Alta/Media/Baja), base rates, demand factors
- **Property Manager**: Company info, contract terms, performance KPIs
- **Maintenance Log**: Repairs, cleaning schedule, inspections, costs

## Mexican Market Context
- Currency: MXP (Mexican Pesos)
- Location: Mérida, Yucatán (tourism/vacation market)
- Legal framework: Mexican fractional ownership regulations apply
- Language: Spanish (UI/documents should support es-MX)

## Implementation Phases

**Phase 1 - Research & Validation** (4-6 weeks):
- Benchmark rental rates on Airbnb/Booking for comparable north Mérida properties
- Analyze real occupancy data by season
- Quote 3+ property management companies
- Estimate precise operating expenses (predial, utilities, insurance)
- Validate investor appetite via surveys/focus groups

**Phase 2 - Legal & Financial Structure** (6-8 weeks):
- Hire notary specialized in real estate fideicomisos
- Structure fideicomiso with fiduciary bank
- Draft detailed internal regulations (reglamento interno)
- Build financial model with sensitivity analysis
- Establish 6-month reserve fund

**Phase 3 - Marketing Materials** (4 weeks):
- Create 15-20 slide pitch deck
- Develop interactive digital brochure with property renders
- Produce virtual tour video
- Design customizable ROI calculator for investor profiles
- Prepare FAQ document
- Draft template contracts (legal review)

**Phase 4 - Investor Acquisition** (8-12 weeks):
- Identify and qualify prospects
- Individual presentations
- Facilitate due diligence process
- Negotiate and close 4 ticket sales
- Execute coproprietario onboarding

**Phase 5 - Operational Launch** (ongoing):
- Contract property manager with proven track record
- Set up Airbnb/Booking/VRBO profiles
- Professional property photography
- Implement dynamic pricing strategy
- Establish quarterly KPI monitoring and reporting

## Target Investor Profile

**Demographics**:
- Age: 35-55 years
- Household income: $100,000+ MXN/month
- Location: CDMX, Monterrey, Guadalajara, or foreigners with Yucatán ties

**Behavioral**:
- Already travel to Mérida 2+ times annually
- Seeking portfolio diversification beyond traditional instruments
- Value family vacation experiences
- Medium-long term horizon (5+ years)
- Appreciate transparency in returns

**Psychographic**:
- Prefer tangible assets over purely financial investments
- Value flexibility (usage vs. income choice)
- Seek like-minded coproprietario community
- Appreciate professional management (minimal operational involvement)

## Risk Mitigation

**Reserve Fund**: 6 months operating expenses cushion
- Covers low occupancy periods, unexpected repairs, manager transitions
- Capitalize with 5% of annual net income until target reached

**Comprehensive Insurance**:
- Civil liability for third-party damages
- Structural damage, fire, flood coverage
- Contents/furniture/equipment insurance

**Protection Clauses**:
- Right of first refusal among coproprietarios before external sales
- Defined dispute resolution via arbitration
- Quarterly independent financial audits
- Documented process for removing non-compliant owner

**Revenue Diversification**:
- Multiple OTA platforms (not just one)
- Relationships with local travel agencies
- Direct booking client list
- Corporate partnership opportunities

## Avoid
- Generic timeshare solutions (this has unique ROI distribution model)
- Assuming US/European vacation patterns (use Mexican calendar)
- Overlooking the mutual exclusivity of usage vs. income distribution
