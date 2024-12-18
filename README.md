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
![image](https://github.com/user-attachments/assets/32144fc2-4d36-4dc1-b589-bed2de6d5157)




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
**Table: Fighter of Headliner**

![image](https://github.com/user-attachments/assets/90e6e88b-cf3d-4c87-a945-1150ec5f195b)

**Table: Social Media Following**

![image](https://github.com/user-attachments/assets/72190035-241e-4da3-bd64-4a7276fcf172)

**Table: Title Reign**

![image](https://github.com/user-attachments/assets/c05e3a71-479b-4d42-ac6a-f336492d156a)

**Table: Head Coaches**

![image](https://github.com/user-attachments/assets/6cf076f8-247d-49c6-a1e7-74928a2a450a)

**Table: Fight Stats**

![image](https://github.com/user-attachments/assets/52cc7d2e-85ea-4435-98b9-727d328266c6)

**Table: PPV Main Event**

![image](https://github.com/user-attachments/assets/0c40d09c-20ac-4737-8f43-891362f3e44d)

**Table: Ref**

![image](https://github.com/user-attachments/assets/14e59732-a5c4-4f59-9d5d-4d06e062c998)

**Table: Venue**

![image](https://github.com/user-attachments/assets/12debf4e-de6f-4df6-88bf-d01d8a0ef864)

**Table: Commentary Crew**

![image](https://github.com/user-attachments/assets/24ce7a82-d1c2-4c41-8c40-d05f96f6c21f)


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

**5. Query 5: Fighters that are above average height in their weight class and have atleast one title defense**

This query shows the fighters that are above average height in their own respective weight class, and have atleast one title defense. This is a very useful statistic that answers the question of how much of an advantage it is to be a taller fighter in your weight class. A lot of great fighters have been above average height in their weight class so it is cool to see.

<img width="816" alt="query5" src="https://github.com/user-attachments/assets/c173803e-9786-43d6-96a0-99c47b1a44e7">




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
