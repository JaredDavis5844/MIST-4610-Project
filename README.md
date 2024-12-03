# MIST-4610-Project
MIST 4610 Project 2 (Query Weary)

**Team Members:**
------------------------------
1. Jared Davis @jareddavis
2. Gavin Roth @gavinroth
3. Akshay Kannan @akshaykannan
4. Luke Bell @lukebell
5. Luke Morris @lukemorris

**Problem Description:**
------------------------------
The goal of this project is to model and build a relational database that captures the main details surronding UFC events, fighters, and associated statistics. The central entity in this data model is the PPV (Pay-Per-View) Main Event, which is the final fight of the night for the UFC Event. Each PPV is composed of various **headliner fights** , featuring multiple fighters whose specific attributes are recorded. Additionally, we are interested in tracking other important aspects such as the **venue, commentary crew, and social media following** of the UFC fighers. Furthermore, we aim to perform functional queries on this data to provide valuable insights into UFC operations, fight statistics, and fighter performances. 

**Data Model**
------------------------------
![image](https://github.com/user-attachments/assets/3250e197-94d2-4929-bc90-11ce419b4c45)



**Explanation of Data Model:**

Our model is based on the structure of a UFC event management system. At the base of the model is the PPV Main Event entity, which each represent an individual UFC fight. Each PPV Main Event involves several entities, including fighters, commentary crew, venues, referees, and detailed statistics about the fights. Each fighter in the PPV has a corresponding social media following, title reign history, head coach, and fight kit.

* PPV Main Event: This entity is the central focus, capturing the event's details like the card number, date, PPV buys, and gate revenue. A one-to-many relationship exists between the PPV and the venue where the event takes place, as each PPV event occurs in a specific venue. It also has a many-to-many relationship with Fighters of Headliner as there can be multiple fighters on each main event and each fighter can be on multiple different PPVs. 

* Fighters of Headiner: Each fighter has attributes such as name, country of origin, fighting style, record (wins/losses), and physical characteristics (e.g., height, reach, weight class). Each fighter has a relationships with Title Reign, Social Media following, Fight Hit, and Head Coach entities. Fighters have a many-to-many relationship with PPV Main event.

* Fight Stats: Detailed statistics for each fight are recorded, including rounds, time, significant strikes, and control time. These statistics provide insight into the performance of each fighter during the event.

* Fight Kit: This entity tracks the gear used by each fighter during the fight, such as the short color and glove color. A fighter's gear is uniquely identified for each fight, and there is a one-to-one relationship between the fight kit and the fighters.

* Title Reign: Title reigns are significant for champions, with attributes such as the number of defenses and the date of the title's win. Each title reign is linked to the fighter's history of holding the belt, showing when and how long a fighter has held a title.

* Venue: Venues are physical locations where UFC events are held. Each venue has attributes like the city, country, capacity, and the type of venue (e.g., indoor, outdoor). There is a many-to-one relationship between the venue and the PPV event, as each PPV takes place at one venue.

* Commentary Crew: The commentary crew provides real-time analysis of the event. Each member of the crew is recorded with attributes such as their name, experience, and years commentating. A PPV event has a one-to-many relationship with the commentary crew, as several commentators typically cover each event.

* Social Media Following: This entity tracks the social media influence of fighters, including their Instagram followers, YouTube subscribers, and Twitter followers. Social media metrics help measure a fighter's popularity outside the octagon.

* Referees: Referees officiate the fights, and their experience and performance (e.g., points deducted from fighters) are tracked. There is a one-to-many relationship between referees and PPV events, as a referee can officiate multiple events but each fight has a single referee.

* PPV Main Event Has Fighters of Headliner: This entitiy identifies which fighter fought in which event, whether they won or lost the event, and whether the challenger (underdog in the fight) won or lost.

**Key Relationships:**

* Fighters ↔ Fight Kit: Fighters wear one set of specific gear (fight kit) during each event, so a one-to-one relationship exists between these entities.
* Fighters ↔ Title Reign: Fighters may have title reigns that are tracked for championships they hold or defend, creating a one-to-one relationship.
* PPV ↔ Venue: A PPV event occurs at one specific venue and one venue can host many PPV events creating a many-to-one relationship.
* PPV ↔ Commentary Crew: One commentary crew can work on multiple PPVs. Each PPV only has one commentary crew, creating a one-to-many relationship.
* Fighters ↔ Social Media Following: Each fighter has an associated social media following, creating a one-to-one relationship.
* PPV ↔ Referees: Each fight within a PPV event has one referee, so there is a one-to-many relationship between referees and the PPV.
* PPV ↔ Fight Stats: Fight statistics are tied to each PPV event to analyze fighter performance.
* Fighter ↔ Head Coach: Each fighter has one head coach, a head coach can mentor multiple fighters. This represents a one-to-many relationship between fighters and head coaches.

**Data Dictionary**
------------------------------
**Table: Winner of Headliner**

![image](https://github.com/user-attachments/assets/ff0cadea-c1b8-4bcd-8187-9b95f1cc815e)


**Table: Loser of Headliner**

![image](https://github.com/user-attachments/assets/57461bba-96b2-4f86-aa0c-8cf1907ee46d)


**Table: Social Media Following**

![image](https://github.com/user-attachments/assets/91315b65-c214-403b-a8af-35af4f77c2b6)


**Table: Fight Kit**

![image](https://github.com/user-attachments/assets/5fe77501-1470-4f1f-8bdc-b3178489864e)


**Table: Title Reign**
	
![image](https://github.com/user-attachments/assets/20cb46ee-2667-40fe-bcf7-0568db852650)


**Table: PPV**

![image](https://github.com/user-attachments/assets/b8c9d75e-8b3e-4f11-b31f-7453182ea4b9)


**Table: Fight Stats**

![image](https://github.com/user-attachments/assets/9ae08720-0a40-4882-b9dd-645834af6f9b)


**Table: Commentary Crew**
	
![image](https://github.com/user-attachments/assets/32954916-2a2e-4c67-976b-de389fe6f658)


**Table: Ref**

![image](https://github.com/user-attachments/assets/d9017823-d081-49a4-8bd5-94d843d935d3)

**Table: Venue**

![image](https://github.com/user-attachments/assets/12debf4e-de6f-4df6-88bf-d01d8a0ef864)

**Table: Loser_of_Headliner_idLoser_of_Headliner**

![image](https://github.com/user-attachments/assets/c962d0e3-ebb5-43c3-b8b6-e248ce48573b)

**Table: Winner_of_Headliner_idWinner_of_Headliner**

![image](https://github.com/user-attachments/assets/334d95ab-5059-447a-80f5-e241e5d8711b)

**Table: Commentary_Crew_idCommentary_Crew**

![image](https://github.com/user-attachments/assets/70361ebf-a1a5-4dde-a16e-19ebedd0b6f5)


**Queries:**
------------------------------

**1. Query 1: Coaches of Fighters with Most Wins

This query shows the coaches who coach the fighters with the most wins. Being able to familiarize with the biggest coaches is helpful for new UFC fans. You can also use these stats to determine who the best coach of all time is, and open up debates.

<img width="1220" alt="Screenshot 2024-11-20 at 7 54 32 PM" src="https://github.com/user-attachments/assets/7e98d26e-eb56-4594-a71b-5d0870f87244">


**2. Query 2: Total Overall Stats

This query combines data from many tables to present an overall stats structure. Being able to see different fighters' stats is very helpful to know how they like to fight, and how their fight style sells.

<img width="1227" alt="Screenshot 2024-11-20 at 8 16 23 PM" src="https://github.com/user-attachments/assets/f6a2b065-a9e6-4ac2-9c82-4261b97bb492">



**3. Query 3: PPV Events with Above Average Significant Strikes from the Winner:**

This query will show the most exciting PPV events by having only the fights with above average significant strikes. It shows the card number of the UFC Event and PPV Buys as well. This is important because the UFC promoters would probably want to see a correlation between more strikes being thrown and more PPV buys.

![image](https://github.com/user-attachments/assets/9fe58d5a-81db-4966-a79a-c3623fec8291)


**4. Query 4: Headshots to Significant strikes ratio and winner of each card:**

This query shows the headshot percentage of significant strikes for each of the winners and their UFC Event Card. This could be helpful because it shows which fighters are most accurate in hitting headshots, and therefore are most likely to get knockouts.

![image](https://github.com/user-attachments/assets/8cb4936a-756e-4ea9-bb39-77d104b66cae)


**5. Query 5: Fight Winners with the highest social media following:**

This query shows the fighters that won their fights with the highest social media following in descending order. This could be useful in determining which fighters have the biggest outreach and will sell the most PPV's.

![image](https://github.com/user-attachments/assets/44e6ca84-8a97-43dc-b0bd-4ecc78ab98db)



**Tableau Visualization 1:**

This bar graph shows the top 5 UFC fighters by how many Instagram followers they have. This is useful to see which fighters bring in the most attention.

![output (5)](https://github.com/user-attachments/assets/e293d41f-0390-4d26-9fb7-f78ad2991138)


**Tableau Visualization 2:**

This bar graph shows the average number of PPV buys associated with each venue. This can tell us where the UFC usually holds its most exciting fights.

![output (6)](https://github.com/user-attachments/assets/0a718c14-54b8-4e09-bc6a-2463f2314322)

**Tableau Visualization 3:**

This line graph displays the number of PPV buys for each event through time. Our oldest piece of data was in 2008 and our most recent took place in 2024. There are two big spikes and those represent UFC 200 which was a massive event at the time, and UFC 229, which was the fight between Conor McGregor and Khabib Nurmagomedov which is considered the biggest fight in the history of the organization.

![image](https://github.com/user-attachments/assets/32faca22-b2d8-4207-b34c-2bc912e1d3c7)





**Database Information**
----------------------------
Name of the database: cs_gcr34350

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q1
