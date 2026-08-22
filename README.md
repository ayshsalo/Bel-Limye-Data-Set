# Bèl Limyè — Med Spa & Day Spa Business Dataset

A synthetic Med Spa & Day Spa business dataset built to support business and financial data analysis. Includes appointment-level service records and monthly esthetician performance summaries, designed for practicing dashboard building and portfolio projects in spa and wellness analytics.

![Excel](https://img.shields.io/badge/format-.xlsx-217346?logo=microsoft-excel&logoColor=white)
![Rows](https://img.shields.io/badge/services%20rows-895-6B3FA0)
![Timeframe](https://img.shields.io/badge/timeframe-Oct%202025%20--%20Mar%202026-B79FD4)
![License](https://img.shields.io/badge/license-synthetic%20data-lightgrey)

---

## Preview

**Seasonality is built into the data** — October and March are modeled as the slow season, December and January as peak season:

<img width="1440" height="672" alt="monthly_volume" src="https://github.com/user-attachments/assets/33b7bb26-6e2f-45ab-a45e-700d2b6a2f66" />

**Six esthetician archetypes drive realistic, distinguishable patterns** in the data — upsell behavior, retail attach rate, booking style, and more:

<img width="1520" height="736" alt="esthetician_archetypes" src="https://github.com/user-attachments/assets/d6e85443-aa88-4427-b576-e2f1a659a82f" />

---

## What's in the workbook

`Bel_Limye_Esthetician_Dataset.xlsx` has three sheets:

| Sheet | Contents |
|---|---|
| **README** (in-file) | Design notes and column definitions |
| **Services** | 895 appointment-level records — patient, date, service, esthetician, pricing, add-ons, retail, and treatment outcome |
| **Esthetician_Monthly_Summary** | 36 rows (6 estheticians × 6 months) rolling up the Services sheet live with `SUMIFS`/`COUNTIFS` formulas |

## Sample rows (Services)

| Appointment ID | Patient ID | Date | Service | Tier | Structure | Esthetician | Assessment | Add-On | Price | Retail |
|---|---|---|---|---|---|---|---|---|---|---|
| APT0001 | P0028 | 2025-10-02 | Chemical Peel | Luxe | Single | Priya Anand | No Change: Advance 1 More Treatment | None | $169.28 | $0 |
| APT0002 | P0194 | 2025-10-02 | IPL Photofacial | VIP | Single | Simone Achille | Advance: Next Treatment | None | $308.40 | $169.07 |
| APT0003 | P0067 | 2025-10-03 | Hydrating Facial | Regular | Single | Simone Achille | Change Treatment - Maintenance | None | $92.18 | $0 |
| APT0004 | P0081 | 2025-10-03 | HydraFacial with LED | VIP | Package (1) | Priya Anand | Advance: Next Treatment | None | $212.50 | $0 |
| APT0006 | P0022 | 2025-10-04 | Chemical Peel | Luxe | Package (1) | Simone Achille | Advance: Next Treatment | Hand & Foot Mask | $140.25 | $0 |
| APT0008 | P0031 | 2025-10-05 | IPL Photofacial | VIP | Package (1) | Devona Fitzgerald | Change Treatment - Maintenance | Dermaplane, Arm Massage | $255.00 | $0 |
| APT0012 | P0071 | 2025-10-06 | Deep Cleanse Facial | Regular | Single | Simone Achille | No Change: Advance 1 More Treatment | None | $96.40 | $250.15 |
| APT0013 | P0105 | 2025-10-06 | Sensitivity Facial | Regular | Single | Priya Anand | Advance: Next Treatment | Hand & Foot Mask | $99.89 | $48.20 |

## Column glossary

**Services sheet**

| Column | Description |
|---|---|
| `Appointment_ID` | Unique row key |
| `Patient_ID` | Client identifier — repeats across a client's visits |
| `Patient_Gender` | Female / Male / Non-binary |
| `Date_Received` | Appointment date |
| `Service_ID` / `Services_Completed` | Treatment code and name (10 services) |
| `Service_Tier` | Regular / Luxe / VIP |
| `Patient_Concern_ID` | One of 20 med-spa/esthetics concerns |
| `Service_Structure` | Single Service or Package Service |
| `Package_Session_Number` | 1–6, or "Not Applicable" for single services |
| `Esthetician_ID` / `Esthetician_Name` | One of 6 estheticians (see archetypes below) |
| `Esthetician_Requested` | Whether the client specifically requested this esthetician |
| `Treatment_Assessment` | Visit outcome (advance, no change, or change treatment — maintenance/corrective) |
| `Add_On` | Scalp Treatment, Hand & Foot Mask, Arm Massage, Dermaplane, or a combination of 2 |
| `Service_Price` / `Add_On_Price` / `Retail_Revenue` | Visit-level revenue components |
| `Rebook_Flag` | Whether the client's *next* visit was with the same esthetician |
| `Main_Esthetician_To_Date` | Whether this esthetician has performed >60% of this client's visits so far |

**Esthetician_Monthly_Summary sheet** — appointment counts, package bookings, rebook rate, revenue (service/add-on/retail), retail attach rate, and average appointments per day/week/month, all as live formulas by esthetician and month.

## Esthetician archetypes

| Esthetician | Archetype |
|---|---|
| Jasmine Cole | Client Loyalist — has one client who exclusively sees her |
| Marcus Reign | No Back-to-Back — never sees the same client twice in a row |
| Devona Fitzgerald | Upsell Champion — highest add-on attach rate |
| Theo Brantley | Basic Service Specialist — mostly Regular-tier services |
| Priya Anand | Retail Powerhouse — highest retail attach rate & spend |
| Simone Achille | Steady Performer — consistent volume; requests swing month to month |

## Suggested uses

- Practice pivot tables, DAX/Power Query, or Google Sheets QUERY formulas
- Build a Med Spa KPI dashboard (revenue, retention, rebook rate, retail attach)
- Portfolio project demonstrating business & financial data analysis for the wellness industry

---

*This is a synthetic dataset generated for analysis practice and portfolio use — it does not represent a real business or real clients.*
