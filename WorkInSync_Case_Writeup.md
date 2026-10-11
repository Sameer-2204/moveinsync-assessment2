# WorkInSync seat-planning and Facilities-KPI case

## Executive answer

**Seat range: 1,200 to 1,575. Recommendation: about 1,400 seats (0.7 seats per person), with managed booking rules, team anchor days, a small overflow option, and a review after 8 weeks of real check-in data.**

The hard mathematical floor is **1,200 seats**: 2,000 people each need 3 in-office days in a 5-day week, so the average daily load is `2000 x (3/5) = 1,200`. It is not the default answer, because a facility must cover the busiest day, not the average day.

| Scenario | Mon-Fri attendance profile | Peak people | Seats with 5% buffer | Note |
|---|---:|---:|---:|---|
| A. Perfectly balanced | 60% / 60% / 60% / 60% / 60% | 1,200 | 1,260 | Policy-assigned days |
| B. Managed | 50% / 65% / 65% / 65% / 55% | 1,300 | 1,365 | MODELING ASSUMPTION: team anchors / soft cap |
| C. Unmanaged | 45% / 70% / 75% / 70% / 40% | 1,500 | 1,575 | MODELING ASSUMPTION: free choice / Tue-Thu skew |
| D. Worst case | 100% / 100% / 100% / 0% / 0% | 2,000 | 2,000 | All choose the same three days |

The practical minimum is **about 1,260-1,365 seats** where attendance is balanced or managed. With unmanaged choices skewed into Tuesday-Thursday, it rises to **1,575**. The absolute ceiling is **2,000**: hybrid work provides no desk reduction if everyone chooses the same three days.

### Recommendation and implementation

Plan for **about 1,400 seats**. This is roughly a 8% buffer over the managed peak (1,300), and deliberately between the managed scenario (1,365) and the unmanaged scenario (1,575): use team anchor days and booking soft caps to keep behavior near the managed pattern; reserve overflow capacity for spikes rather than fitting out the unmanaged case. Pilot at one office, monitor real check-ins and denials, then rightsize after 8 weeks.

### Why policy matters more than random fluctuation

At 95% confidence (**assumption**, z = 1.645), independent random attendance produces about **1,236** demand: `1,200 + 1.645 x sqrt(1,200 x (1 - 60%))`. This is only about 3% above the mean. The large spread is therefore a correlated-behavior problem: teams choosing the same weekdays. The main lever is booking and policy design, not buying more desks.

## Per-office illustration

Seats cannot be pooled across countries. With the **illustrative assumption** of a 1,000/600/400 split, 65% planning peak, and 5% buffer:

| Office | Headcount | Planning peak | Buffer | Seats |
|---|---:|---:|---:|---:|
| Office 1 | 1,000 | 65% | 5% | 683 |
| Office 2 | 600 | 65% | 5% | 410 |
| Office 3 | 400 | 65% | 5% | 273 |
| **Total** | **2,000** |  |  | **1,366** |

Formula: `seats_office = MIN(headcount_office, ROUNDUP(headcount_office x planning_peak x (1 + buffer), 0))`. Country-specific working week, public holidays, and local norms are **UNKNOWN** and must be inputs, not assumed facts.

## Facilities KPI scorecard

**Targets below are illustrative and must be calibrated after a 4-8 week baseline. Any scorecard samples are SYNTHETIC / ILLUSTRATIVE.** Report each KPI by office and country once source data is available.

| Group | KPI | Definition / formula | Data source needed | Frequency | Owner | Illustrative target |
|---|---|---|---|---|---|---|
| Space efficiency | Peak-day utilization | Peak occupied seats / total seats | Check-in or badge data + seat inventory | Weekly | Facilities | 80-90%* |
| Space efficiency | Weekday utilization skew | Max weekday utilization - min weekday utilization | Check-in or badge data | Weekly | Facilities + leadership policy | Narrowing over time* |
| Space efficiency | Cost per employee-day in office | Occupancy cost / employee-days present | Occupancy cost + presence data | Monthly | Facilities + Finance | Trending down* |
| Booking quality | Seat denial rate | Failed booking attempts / booking attempts | Booking records | Weekly | Facilities | <2%* |
| Booking quality | No-show rate | Booked but not checked in / booked | Booking + check-in records | Weekly | Facilities | <10-15% with auto-release* |
| Employee experience | Workplace CSAT / eNPS | Pulse-survey score | Survey | Monthly / quarterly | Shared with leadership | >=4/5* |
| Employee experience | Team co-presence | Team anchor days meeting participation threshold / anchor days | Check-in data + team roster | Monthly | Shared with leadership | Improving* |
| Service operations | Ticket SLA adherence | Tickets resolved within SLA / total tickets | Ticket system | Weekly | Facilities | >=95%* |
| Service operations | Repeat-issue rate | Repeat tickets / total tickets | Ticket system | Monthly | Facilities | Down* |
| Safety & compliance | Critical incidents / findings | Open count and days to close | Incident and audit records | Weekly | Facilities | Zero critical open* |
| Sustainability | Energy per occupied seat-day | kWh / occupied seat-days | Utility meters + presence data | Monthly | Facilities | Down vs baseline* |
| Financial | Budget variance / rightsizing savings | Actual vs plan; space cost avoided | Finance + occupancy data | Monthly | Facilities + Finance | Within +/-5%* |

\* Every target is **illustrative, to be calibrated after a 4-8 week baseline**.

Read KPI pairs together: utilization with denial rate and CSAT; otherwise 100% utilization could conceal a poor employee experience. Booking and no-show metrics are leading indicators; CSAT and cost are lagging. The Facilities Team controls service delivery and many operational metrics, while in-office policy is shared with leadership.

## Rollout plan

1. Collect baseline data: seat inventory, booking attempts, check-ins/badge swipes, ticket data, utilities, survey data, and lease constraints.
2. Pilot team anchor days and booking soft caps at one office.
3. Review capacity, denial, no-show, co-presence, and experience after 8 weeks; rightsize only against observed peak demand.
4. Set final KPI targets from the baseline and publish office/country scorecards.

## Caveats, assumptions, and customer questions

- Given: 2,000 people, 3 in-office days, 3 offices across 3 countries. **UNKNOWN:** country names, real headcount split, working weeks, holidays, attendance history, booking/check-in systems, collaboration-space need, and lease constraints.
- Assumptions: 5-day working week, 5% buffer, 95% confidence/z=1.645, illustrative 1,000/600/400 split, and the managed/unmanaged weekday profiles. These are editable in the workbook.
- Seat count is not space planning: meeting and collaboration capacity needs observed room-usage data; no ratio is assumed here. Results are modeled estimates, not forecasts.
- Ask the customer for: the real office split; local working weeks and holidays; hybrid policy and enforcement; badge, booking and ticket data; collaboration needs; and lease constraints.

## Claims check

| Claim | Tag |
|---|---|
| Headcount, offices/countries, and three in-office days | given in case |
| Scenario outputs, statistical check, and office-seat outputs | computed |
| Working week, buffer, confidence/z, office split, B/C profiles | assumption |
| Customer data availability and country specifics | UNKNOWN / needs customer input |
