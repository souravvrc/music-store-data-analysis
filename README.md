# 🎵 Music Store SQL Analysis

A comprehensive SQL analysis project on a digital music store database, exploring customer behavior, sales performance, and music trends using PostgreSQL.

---

## 📊 Database Schema

The project uses a relational database with **11 tables** modelling a real-world music store:

```
Artist ──< Album ──< Track >── Genre
                  └──< PlaylistTrack >── Playlist
                        │
                   InvoiceLine
                        │
                     Invoice >── Customer >── Employee
                                 MediaType
```

| Table | Description |
|-------|-------------|
| `artist` | Music artists |
| `album` | Albums linked to artists |
| `track` | Individual tracks with price, duration, genre |
| `genre` | Music genres |
| `media_type` | Audio format types |
| `playlist` | User playlists |
| `playlist_track` | Junction table for playlists and tracks |
| `invoice` | Customer purchase invoices |
| `invoice_line` | Line items within each invoice |
| `customer` | Store customers |
| `employee` | Store employees with hierarchy |

![Database Schema](musicdbschema.png)

---

## 🔍 Analysis Questions & Queries

The project answers **15 business questions** across three difficulty levels:

### 🟢 Easy
| # | Question |
|---|----------|
| Q1 | Who is the senior most employee based on job title? |
| Q2 | Which countries have the most invoices? |
| Q3 | What are the top 3 values of total invoice? |
| Q4 | Which city has the best customers? (for a promotional Music Festival) |
| Q5 | Who is the best customer? (highest total spend) |

### 🟡 Moderate
| # | Question |
|---|----------|
| Q6 | Return email, name & genre of all Rock Music listeners, ordered by email |
| Q7 | Top 10 rock artists by track count |
| Q8 | All tracks longer than the average song length |
| Q9 | Amount spent by each customer on each artist |

### 🔴 Advanced
| # | Question |
|---|----------|
| Q10 | Most popular music genre per country |
| Q11 | Top spending customer per country |
| Q12 | Most popular artists by purchase count |
| Q13 | Most popular songs by purchase count |
| Q14 | Average revenue by music genre |
| Q15 | Most popular countries for music purchases |

---

## 💡 Key SQL Concepts Used

- **Joins** — `INNER JOIN` across multiple tables
- **Subqueries** — nested `SELECT` statements for filtering
- **CTEs** — `WITH` clauses for readable multi-step logic
- **Window Functions** — `ROW_NUMBER() OVER(PARTITION BY ...)` for per-group rankings
- **Aggregations** — `SUM`, `COUNT`, `AVG`, `ROUND`
- **String functions** — `LIKE`, `CONCAT`
- **Sorting & Limiting** — `ORDER BY`, `LIMIT`

---

## 🗂️ Project Structure

```
music-store-sql-analysis/
│
├── musicdbschema.png      # Entity-Relationship Diagram
├── dbquery.txt            # DDL — table creation & foreign keys
├── Analysis.sql           # All 15 analysis queries
└── README.md              # Project documentation
```

---

## 🚀 Getting Started

### Prerequisites
- PostgreSQL (v12 or higher recommended)
- pgAdmin or any SQL client

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/souravvrc/music-store-data-analysis.git
   cd music-store-sql-analysis
   ```

2. **Create the database**
   ```sql
   CREATE DATABASE music_store;
   ```

3. **Run the schema script**
   ```bash
   psql -U postgres -d music_store -f dbquery.txt
   ```

4. **Import the data**  
   Load your CSV data files into the respective tables using `COPY` or pgAdmin's import tool.

5. **Run the analysis**
   ```bash
   psql -U postgres -d music_store -f Analysis.sql
   ```

---

## 📌 Sample Insights

- 🏆 **Best Customer City** — Identified by summing all invoice totals per city
- 🎸 **Top Rock Artists** — Ranked by number of rock tracks in the catalog
- 🌍 **Genre by Country** — Each country's most-purchased genre found using window functions
- 💰 **Top Spender per Country** — Per-country ranking of customers by total spend

---

## 🛠️ Tech Stack

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

> *Built to practice and demonstrate real-world SQL querying skills on a structured relational database.*
