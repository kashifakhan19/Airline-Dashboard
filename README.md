# Airline Pricing & Market Insights – Delhi–Mumbai Route

## 📌 Overview
End-to-end analysis and Tableau dashboard for Delhi–Mumbai flights. The project answers 10 business questions on pricing, demand, market share, and operations.

## 🎯 Business Questions Covered
1) Highest & lowest average ticket prices by airline  
2) Departure time category with the highest average price  
3) Impact of flight duration on average price  
4) Price variation by number of stops for each airline  
5) Departure time slot with the most flights  
6) Airline with the largest market share  
7) Ticket price by travel class across airlines  
8) Most frequent **arrival time** bin  
9) Total ticket revenue per airline  
10) Published interactive dashboard (Tableau Public)

## 🗂️ Data (example columns)
- `date`, `airline`, `flight_no`, `source`, `destination`
- `departure_time`, `arrival_time`, `duration_minutes`
- `stops` (0/1/2+), `class` (Economy/Premium/Business)
- `price` (numeric)

## 🧹 Data Prep (Python/SQL – summary)
- Handle missing/outliers in `price` and `duration_minutes`  
- Normalize `stops` (e.g., "non-stop" → 0, "1 stop" → 1, "2+ stops" → 2)  
- Create **time bins**:  
  - `dep_slot` = {Early Morning(4–8), Morning(8–12), Afternoon(12–16), Evening(16–20), Night(20–24), Late Night(0–4)}  
  - `arr_slot` similarly  
- Ensure numeric types: `price` → float/int, `duration_minutes` → int

## 📐 Metrics & Calculations (use in Tableau)
- **Avg Ticket Price (by Airline/Slot/Stops/Class):** `AVG([price])`
- **Flights Count:** `COUNT([flight_no])` or `COUNT(*)`
- **Market Share (%):** `Flights of Airline / Total Flights`  
  - Tableau: `COUNT([flight_no]) / TOTAL(COUNT([flight_no]))`
- **Total Revenue (by Airline):** `SUM([price])`
- **Duration Bins (optional):**  
  - `< 120 min`, `120–150`, `150–180`, `> 180` (calculated field on `duration_minutes`)

## 📊 Visual Design (one view per question)
1. **Bar** – Avg Price by Airline (sorted desc)  
2. **Bar** – Avg Price by `dep_slot`  
3. **Scatter/Line** – Price vs Duration (trend line)  
4. **Clustered Bar** – Avg Price by Stops, colored by Airline  
5. **Bar** – Flights Count by `dep_slot`  
6. **Pie/Donut or Bar** – Market Share by Airline  
7. **Heatmap** – Avg Price by Airline × Class  
8. **Bar** – Flights Count by `arr_slot` (Most frequent arrival slot)  
9. **Bar** – Total Revenue by Airline  
10. **Dashboard** – KPIs + filters (Airline, Class, Stops, Slots, Date)

## 🎛️ Recommended Dashboard KPIs
- **Avg Ticket Price** (selected filters)  
- **Total Flights**  
- **Total Revenue**  
- **Top-Priced Airline** / **Best-Value Airline**  
- **Busiest Departure Slot**

 ## Dashboard
 <img width="1920" height="1200" alt="Screenshot 2025-08-17 002040" src="https://github.com/user-attachments/assets/da8afffc-09d5-44ba-8cb8-0a07c727010c" />

