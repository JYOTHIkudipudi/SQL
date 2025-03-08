# Cricket Team Database Updates

## Table Structure

The `Cricket_Team` table consists of the following columns:
- **Player_ID** (Primary Key, INT)
- **Player_Name** (VARCHAR, NOT NULL)
- **Age** (INT, NOT NULL)
- **Country** (VARCHAR, NOT NULL)
- **Team** (VARCHAR, NOT NULL)
- **Matches_Played** (INT, NOT NULL)
- **Runs_Scored** (INT, NOT NULL)
- **Wickets_Taken** (INT, NOT NULL)
- **Batting_Average** (FLOAT, NOT NULL)
- **Bowling_Average** (FLOAT, NOT NULL) 
  ## Creating the Table
  ```sql
  CREATE TABLE Cricket_Team (
    Player_ID INT PRIMARY KEY,
    Player_Name VARCHAR(50) NOT NULL,
    Age INT NOT NULL,
    Country VARCHAR(50) NOT NULL,
    Team VARCHAR(50) NOT NULL,
    Matches_Played INT NOT NULL,
    Runs_Scored INT NOT NULL,
    Wickets_Taken INT NOT NULL,
    Batting_Average FLOAT NOT NULL,
    Bowling_Average FLOAT NOT NULL);
     
  
## Inserting the Values 
```sql
INSERT INTO Cricket_Team (Player_ID, Player_Name, Age, Country, Team, Matches_Played, Runs_Scored, Wickets_Taken, Batting_Average, Bowling_Average) VALUES
(1, 'Virat Kohli', 35, 'India', 'RCB', 275, 12000, 4, 54.2, 0.0),
(2, 'Babar Azam', 29, 'Pakistan', 'PAK', 200, 9000, 2, 49.8, 0.0),
(3, 'Joe Root', 33, 'England', 'ENG', 225, 10500, 30, 51.3, 38.5),
(4, 'Pat Cummins', 31, 'Australia', 'AUS', 160, 900, 350, 18.5, 23.2),
(5, 'MS Dhoni', 42, 'India', 'CSK', 350, 10800, 0, 50.5, 0.0),
(6, 'Kane Williamson', 33, 'New Zealand', 'NZ', 210, 8900, 5, 52.1, 12.3),
(7, 'Jasprit Bumrah', 30, 'India', 'MI', 120, 150, 250, 9.8, 21.1),
(8, 'Rashid Khan', 26, 'Afghanistan', 'GT', 180, 1300, 400, 23.5, 17.4),
(9, 'Ben Stokes', 32, 'England', 'RR', 190, 5000, 180, 40.7, 31.6),
(10, 'Glenn Maxwell', 35, 'Australia', 'RCB', 170, 7000, 50, 41.2, 36.4),
(11, 'Shubman Gill', 24, 'India', 'GT', 85, 3500, 1, 50.2, 0.0),
(12, 'Steve Smith', 34, 'Australia', 'AUS', 220, 9500, 10, 53.5, 15.8),
(13, 'Rohit Sharma', 36, 'India', 'MI', 310, 11000, 8, 48.9, 17.2),
(14, 'David Warner', 37, 'Australia', 'DC', 295, 10850, 3, 47.6, 9.8),
(15, 'Shaheen Afridi', 24, 'Pakistan', 'PAK', 120, 400, 275, 14.3, 19.5),
(16, 'Hardik Pandya', 30, 'India', 'MI', 180, 3200, 120, 37.4, 27.9),
(17, 'Quinton de Kock', 31, 'South Africa', 'SA', 200, 8700, 0, 42.8, 0.0),
(18, 'Mohammed Shami', 34, 'India', 'GT', 170, 300, 250, 10.6, 22.4),
(19, 'Andre Russell', 36, 'West Indies', 'KKR', 190, 5100, 150, 36.9, 25.2),
(20, 'Marnus Labuschagne', 30, 'Australia', 'AUS', 115, 4700, 18, 52.7, 24.1);
``` 


## Data Update Queries

### 1. Update the team name of 'David Warner' to 'CSK'
```sql
UPDATE Cricket_Team 
SET Team = 'CSK' 
WHERE Player_Name = 'David Warner';
```

### 2. Update 5 more matches to 'Shubman Gill's' Record
```sql
UPDATE Cricket_Team 
SET Matches_Played = Matches_Played + 5 
WHERE Player_Name = 'Shubman Gill';
```

### 3. Decrease Bowling Average for Bowlers with More Than 200 Wickets
```sql
UPDATE Cricket_Team 
SET Bowling_Average = Bowling_Average - 2.0 
WHERE Wickets_Taken > 200;
```

### 4. Set Bowling Average to NULL for Players Without Wickets
```sql
UPDATE Cricket_Team 
SET Bowling_Average = NULL 
WHERE Wickets_Taken = 0;
```

### 5. Move Young Players (Age < 23) with Good Batting Records (Runs > 3000) to the National Team
```sql
UPDATE Cricket_Team 
SET Team = Country 
WHERE Age < 23 AND Runs_Scored > 3000;
```

### 6. Increase the Age of All Players from Australia by 1
```sql
UPDATE Cricket_Team 
SET Age = Age + 1 
WHERE Country = 'Australia';
```

### 7. Update 'Quinton de Kock' Age (As 36) and Team (As 'LSG')
```sql
UPDATE Cricket_Team 
SET Age = 36, Team = 'LSG' 
WHERE Player_Name = 'Quinton de Kock';
```

### 8. Increase the Bowling Average by 5% for Bowlers with Bowling Average > 25 and More Than 50 Wickets
```sql
UPDATE Cricket_Team 
SET Bowling_Average = Bowling_Average * 1.05 
WHERE Bowling_Average > 25 AND Wickets_Taken > 50;
```
