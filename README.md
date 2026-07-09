# 🚗 Uber India Trip Analysis – Power BI Dashboard

An interactive multi-page Power BI dashboard analyzing 148,770 ride-hailing bookings across 7 vehicle types in India, covering trip performance, revenue, cancellations, location patterns, and operational problems.

---

## 🎯 Business Problem

Uber needs to understand why nearly 40% of bookings are lost, identify cancellation patterns by driver and customer, and pinpoint which locations and vehicle types face the most operational issues — in order to improve completion rates and revenue.

---

## 📁 Dataset

- **Source:** Uber India Trip Dataset — Kaggle
- **Size:** 148,770 bookings, 19 columns
- **Period:** 2025
- **Vehicle Types:** Auto, Go Mini, Go Sedan, Bike, Premier Sedan, eBike, Uber XL

---

## 🛠️ Tools Used

- **Power BI Desktop** — data modeling, DAX measures, multi-page dashboard design
- **Power Query** — data cleaning, time extraction, duplicate removal, error handling
- **DAX** — custom measures (cancellation rates, revenue per KM, completion rates, unaccepted bookings)

---

## 📊 Dashboard Pages (10 pages)

1. **Overview** — KPIs, quarterly trend, payment method breakdown, booking status tooltip, cancellation rates, ratings
2. **Revenue** — Revenue by vehicle type (with images), by day, by payment method, top/lowest customers by revenue and rating
3. **Location** — Distance by day, trips by hour, top/lowest pickup locations, distance by vehicle type
4. **Trips Problem** — Cancellation breakdown by customer and driver, incomplete rides analysis, problem count by vehicle type
5. **Tooltip 1** — Booking status donut chart (hover tooltip)
6. **Tooltip 2** — Cancellation rates tooltip (7% customer, 18.1% driver)
7. **Unaccepted** — 10K unaccepted bookings analysis: top/lowest pickup locations, trips per hour, by vehicle type
8. **Incompleted** — Top pickup locations by incomplete bookings with full breakdown
9. **Customer Cancellation** — Top pickup locations by customer cancellations
10. **Driver Cancellation** — Top pickup locations by driver cancellations

---

## 📌 Key Insights

### 🔢 Overall Performance
- Total booked trips: **148,770** | Completed: **91,950** | Lost: **56,817**
- **Completion rate: 61.8%** — nearly 4 out of every 10 trips are lost
- Total revenue: **$51.29M** | Revenue per KM: **$20.63**
- Overall cancellation rate: **32.18%**
- Avg customer rating: **2.72** | Avg driver rating: **2.61** — both below 3/5, indicating systemic service quality issues

### 📊 Booking Status Breakdown
| Status | Count | % |
|---|---|---|
| Completed | 92K | 61.81% |
| Cancelled by Driver | 27K | 18.10% |
| Cancelled by Customer | 10K | 7.06% |
| No Driver Found | 10K | 7.02% |
| Incomplete | 9K | 6.01% |

- **Driver-side issues (Cancelled by Driver + No Driver Found) = 25.12%** vs customer-side = **7.06%** — the platform's supply problem is **3.5x bigger** than demand-side issues
- "No Driver Found" (7.02%) is a separate issue from cancellations — these are trips where no driver accepted the booking at all, a direct indicator of supply shortage in certain areas/times

### 🚙 Revenue by Vehicle Type
- **Auto** generates the highest revenue ($12.7M) and covers the most distance (618K km) — dominant in both volume and reach
- **Go Mini** ($10.2M, 496K km) and **Go Sedan** ($9.3M, 446K km) follow closely
- **Uber XL** has the lowest revenue ($1.5M, 74K km) — premium segment with lower demand
- Auto covers **8.4x more distance** than Uber XL

### 💳 Payment Method
- **UPI dominates** with 44.94% (45K customers) — reflecting India's digital payment adoption
- **Cash** follows at 24.88% (25K) — significant offline customer segment
- Uber Wallet (11.99%), Credit Card (10.09%), Debit Card (8.1%)

### 📅 Revenue & Distance by Day
- **Monday** ($9.4M) and **Sunday** ($9.2M) are the highest revenue days
- **Sunday** has the highest total distance (362K km), Friday the lowest (350K km)
- Daily distance is remarkably consistent — suggesting steady demand throughout the week

### ⏰ Trips by Hour (Peak Analysis)
- **Peak: 6PM = 12.30K trips** — highest booking count of the day
- **9PM–10PM** also high at 10.96K trips per hour
- Secondary peak around **12PM–2PM** at 8K–9.5K trips
- **12AM–5AM** lowest demand (1.31K–1.37K trips)
- Strong evening peak suggests commuter and leisure demand concentrated after work hours

### 📍 Location Insights
- **Khandsa** — most frequent pickup location
- **Ashram** — highest revenue pickup location
- **Ghitorni Village** — lowest pickup frequency
- **Huda City Centre** — lowest revenue location
- Average distance: **16.71 km** | Total distance: **2.5M km**

### ⚠️ Trips Problem — Detailed Breakdown

**Cancellations by Customer (10,496 total):**
- High cancellations are driven by operational inefficiencies and poor customer experience (location accuracy, flexibility)
- Wrong Address: 2,362
- Change of plans: 2,352
- Driver not moving toward pickup: 2,334
- Driver asked to cancel: 2,293
- AC is not working: 1,155

**Cancellations by Driver (26,931 total):**
- Customer related issue: 6,823
- Customer was coughing/sick: 6,732
- Personal & car related issues: 6,700
- More than permitted people: 6,676

**Incomplete Rides (8,948 total):**
- Customer Demand: 3,023
- Vehicle Breakdown: 2,993
- Other Issue: 2,932

**By Location:**
- Top locations for incomplete bookings: Kanhaiya Nagar (72), Udyog Vihar (67), Lal Quila (68)
- Top locations for unaccepted bookings: Old Gurgaon (83), Pataudi Chowk (80), Paharganj (79)
- Lowest locations for unaccepted bookings: IGI Airport (41), Welcome (42), Shivaji Park (43)
- Top locations for driver cancellations: Nehru Place (189), Shivaji Park (185), GTB Nagar (183)
- Top locations for customer cancellations: Seelampur (81), Keshav Puram (79), Preet Vihar (80)

**Unaccepted Bookings Analysis (≈10K total):**
- **Peak unaccepted hour: 6PM = 884 unaccepted trips** — highest supply shortage at peak demand
- Auto has the highest unaccepted bookings by vehicle type (2.7K), followed by Go Mini (2.0K) and Go Sedan (1.9K)
- Uber XL has the lowest unaccepted bookings (0.3K) — lower demand means easier to match
- Midnight hours (12AM–5AM) show 88–106 unaccepted trips — relatively low but consistent

**Auto generate both the highest demand and the highest operational issues** across all categories (6.6K total problems and $12.7M total revenue) — expected given its volume dominance, but worth monitoring per-trip problem rates.
---

## 💡 Recommendations

1. **Address driver cancellations urgently** — at 18.1%, driver cancellations are 2.6x customer cancellations; targeting high-cancellation drivers with incentives or warnings would directly improve completion rate, and Provide training and incentives to reduce personal/car-related cancellations
2. **limits driver canncellation related by customer** — Eenforce passenger limits clearly and introduce health & safety protocols for handling sick customers to reduce the 6,732 coughing/sick-related cancellations.
3. **fix the wrong address UX issue**  — the top customer cancellation reason (2,362 cases); add location confirmation and flexible rescheduling features, and improve driver communication when delayed to reduce customer-side cancellations.
4. **Increase driver supply in Nehru Place, Shivaji Park, and GTB Nagar** — these locations have the highest driver cancellation rates, suggesting driver reluctance or supply shortage
5. **Maximize driver availability during 6PM–9PM** — peak demand reaches 12.3K trips/hour; driver shortage during this window is the biggest revenue risk
6. **Expand Auto fleet** — highest revenue ($12.7M) and distance (618K km); increasing supply improves overall platform performance
7. **Investigate low ratings** — both customer (2.72) and driver (2.61) ratings are below 3/5; a rating improvement program targeting the bottom-rated interactions could significantly improve retention
8. **Promote UPI and Uber Wallet** — strong digital payment adoption; incentivizing Uber Wallet reduces cash handling and improves trip tracking.
9. **Enforce stricter vehicle quality control** — Vehicle Breakdown accounts for 2,993 incomplete rides (33% of all incomplete trips). Uber should implement:
    (1) mandatory periodic vehicle inspections before drivers are allowed to operate.
    (2) minimum vehicle condition standards as a prerequisite for platform access.
    (3) a strike system that suspends or permanently removes drivers with repeated breakdown incidents — reducing operational failures and improving customer trust.

---

*Built by Mohammed | Power BI Portfolio Project*
