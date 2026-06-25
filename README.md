# World-Cup-Database

A PostgreSQL + Bash project built for the freeCodeCamp Relational Database Certification.  
It creates a World Cup database, loads match data automatically, and runs analytical SQL queries.

---

## 📌 Project Summary

This project uses match data from the final rounds of the FIFA World Cup (2014–2018).  
You will:

- Create a PostgreSQL database (`worldcup`)
- Build two tables: `teams` and `games`
- Insert data from `games.csv` using a Bash script
- Run SQL queries to generate insights
- Export the final database as `worldcup.sql`

---

## 🗄️ Database Schema

### **teams**
- `team_id` — SERIAL, primary key  
- `name` — VARCHAR, unique, not null  

### **games**
- `game_id` — SERIAL, primary key  
- `year` — INT  
- `round` — VARCHAR  
- `winner_id` — FK → teams  
- `opponent_id` — FK → teams  
- `winner_goals` — INT  
- `opponent_goals` — INT  

All columns are **NOT NULL**.

---

## ⚙️ Scripts

### **insert_data.sh**
- Inserts 24 unique teams  
- Inserts 32 games  
- Automatically assigns foreign keys  
- Reads directly from `games.csv`  

### **queries.sh**
- Outputs totals, averages, winners, and filtered team lists  
- Matches `expected_output.txt` exactly  

---

## ▶️ How to Run

Create the database:

- psql --username=freecodecamp --dbname=postgres
- CREATE DATABASE worldcup;
- \c worldcup

Run the scripts:

- chmod +x insert_data.sh queries.sh
- ./insert_data.sh
- ./queries.sh



Export the database:

- pg_dump -cC --inserts -U freecodecamp worldcup > worldcup.sql



---

## 🧰 Technologies Used
- PostgreSQL  
- Bash scripting  
- Linux CLI  

---

## 🏆 Certification Project
This repository completes the **World Cup Database** project from the  
freeCodeCamp Relational Database Certification.