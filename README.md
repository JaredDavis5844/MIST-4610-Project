# MIST-4610-Project
MIST 4610 Project 1 (Query Weary)

**Team Members:**
------------------------------
1. Jared Davis @jareddavis
2. Gavin Roth @gavinroth
3. Akshay Kannan @akshaykannan
4. Luke Bell @lukebell
5. Luke Morris @lukemorris

**Problem Description:**
------------------------------
The goal of this project is to model and build a relational database that captures the main details surronding UFC events, fighters, and associated statistics. The central entity in this data model is the PPV (Pay-Per-View) event, which acts as the main event for the UFC organization. Each PPV is composed of various **headliner fights** , featuring a **winner** and **loser** , whose specific details are recorded. Additionally, we are interested in tracking other important aspects such as the **venue, commentary crew, and social media following** of the UFC fighers. Furthermore, we aim to perform functional queries on this data to provide valuable insights into UFC operations, fight statistics, and fighter performances. Jared likes penis.

**Data Model**
------------------------------
![image](https://github.com/user-attachments/assets/4425907d-7e07-4897-8a02-1329e04469b9)

**Explanation of Data Model:**

Our model is based on the structure of a UFC event management system. At the base of the model is the PPV entity, which represents each major UFC event. Each of the PPV event involves several entities, including fighters, commentary crew, venues, referees, and detailed statistics about the fights.

* PPV Events: This entity is the central focus, capturing the event's details like the card number, date, PPV buys, and gate revenue. A one-to-many relationship exists between the PPV and the venue where the event takes place, as each PPV event occurs in a specific venue.

* Fighters (Winner of Headliner and Loser of Headliner): Fighters are categorized based on whether they win or lose a headliner fight. Each fighter has attributes such as name, country of origin, fighting style, record (wins/losses), and physical characteristics (e.g., height, reach, weight class). Both the winner and loser entities have relationships with Title Reign, which tracks title defenses and championship status.

* Fight Stats: Detailed statistics for each fight are recorded, including rounds, time, significant strikes, and control time. These statistics provide insight into the performance of each fighter during the event.

* Fight Kit: This entity tracks the gear used by each fighter during the fight, such as the short color and glove color. A fighter's gear is uniquely identified for each fight, and there is a many-to-one relationship between the fight kit and the fighters.

* Title Reign: Title reigns are significant for champions, with attributes such as the number of defenses and the date of the title's win. Each title reign is linked to the fighter's history of holding the belt, showing when and how long a fighter has held a title.

* Venue: Venues are physical locations where UFC events are held. Each venue has attributes like the city, country, capacity, and the type of venue (e.g., indoor, outdoor). There is a many-to-one relationship between the venue and the PPV event, as each PPV takes place at one venue.

* Commentary Crew: The commentary crew provides real-time analysis of the event. Each member of the crew is recorded with attributes such as their name, experience, and years commentating. A PPV event has a one-to-many relationship with the commentary crew, as several commentators typically cover each event.

* Social Media Following: This entity tracks the social media influence of fighters, including their Instagram followers, YouTube subscribers, and Twitter followers. Social media metrics help measure a fighter's popularity outside the octagon.

* Referees: Referees officiate the fights, and their experience and performance (e.g., points deducted from fighters) are tracked. There is a one-to-many relationship between referees and PPV events, as a referee can officiate multiple events but each fight has a single referee.

**Key Relationships:**

* Fighters (Winner/Loser) ↔ Fight Kit: Fighters wear specific gear (fight kit) during each event, so a many-to-one relationship exists between these entities.
* Fighters ↔ Title Reign: Fighters may have title reigns that are tracked for championships they hold or defend, creating a one-to-one relationship.
* PPV ↔ Venue: A PPV event occurs at a specific venue, creating a many-to-one relationship.
* PPV ↔ Commentary Crew: Multiple commentary crew members work on a single PPV event, creating a one-to-many relationship.
* Fighters (Winner/Loser) ↔ Social Media Following: Each fighter has an associated social media following, creating a one-to-one relationship.
* PPV ↔ Referees: Each fight within a PPV event has one referee, so there is a one-to-many relationship between referees and the PPV.
* PPV ↔ Fight Stats: Fight statistics are tied to each PPV event to analyze fighter performance.

**Data Dictionary**
------------------------------
**Table: Winner of Headliner**
Column Name	Description	Data Type	Size	Format	Key?
idWinner_of_Headliner	PK, unique identifier for each fighter	INT	3		PK
Name_of_Winner	Name of the fighter	VARCHAR	45		
Country_of_Origin	Fighter's country of origin	VARCHAR	45		
Language	Native language of the fighter	VARCHAR	45		
Weight_Class	The fighter’s weight class (e.g., Lightweight, Heavyweight)	INT	2		
Fighting_Style	The fighter's fighting style (Striker, Boxer, Wrestling)	VARCHAR	46		
Wins_on_Record	Number of wins recorded	INT	2		
Losses_on_Record	Number of losses recorded	INT	2		
Age	Fighter's age 	INT			
Height	Height of the fighter in meters	DECIMAL	(5,2)		
Reach	Reach of the fighter in centimeters	INT	3		
Title_Reign_idTitle_Reign	FK, relationship with the title reign table	INT	3		FK
Social_Media_Following_idSocial_Media_Following	FK, relationship with Social Media Following table	INT	3		FK
![image](https://github.com/user-attachments/assets/dd87befa-b490-4aa8-bb3e-05c2398271c3)

**Loser of Headliner**
Column Name	Description	Data Type	Size	Format	Key?
idLoser_of_Headline	PK, unique identifier for the loser in the headline event	INT	5		PK
Name	Name of the fighter	VARCHAR	45		
Country_of_Origin	Country of origin for the fighter	VARCHAR	45		
Language	Native language of the fighter	VARCHAR	45		
Weight_Class	The fighter’s weight class (e.g., Featherweight)	VARCHAR	20		
Fighting_Style	Style of fighting employed by the fighter	VARCHAR	20		
Wins_on_Record	Number of wins recorded	INT	2		
Losses_on_Record	Number of losses recorded	INT	2		
Age	Age of the fighter	INT	2		
Height	Height of the fighter in centimeters	DECIMAL	(5,2)		
Reach	Reach of the fighter in centimeters	INT	3		
Title_Reign_idTitle_Reign	FK, relationship with the title reign table	INT	3		FK
![image](https://github.com/user-attachments/assets/05ea4c32-143b-4428-9d56-eb32a29199e8)



**Queries:**
------------------------------

1. Query 1

2. Query 2

3. Query 3

4. Query 4

5. Query 5

6. Query 6

7. Query 7

8. Query 8

9. Query 9

10. Query 10
