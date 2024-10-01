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

![image](https://github.com/user-attachments/assets/dd87befa-b490-4aa8-bb3e-05c2398271c3)

**Table: Loser of Headliner**

![image](https://github.com/user-attachments/assets/05ea4c32-143b-4428-9d56-eb32a29199e8)

**Table: Social Media Following**

![image](https://github.com/user-attachments/assets/da00079b-f4bf-4123-b5d5-96f9274053b8)

**Table: Fight Kit**

![image](https://github.com/user-attachments/assets/03f9e5bd-a73a-4d80-8ecf-cc8d13249001)

**Table: Title Reign**

![image](https://github.com/user-attachments/assets/2489457e-d8ef-4aa2-9929-758e66db04a2)


**Table: PPV**

![image](https://github.com/user-attachments/assets/12ef78d8-f57e-4cc3-9221-c7b04ff08c67)

**Table: Fight Stats**

![image](https://github.com/user-attachments/assets/15597a1c-f36a-4642-b003-8d1d6683c15e)

**Table: Commentary Crew**

![image](https://github.com/user-attachments/assets/6896e85b-d083-46c5-9ccc-3fbae6ee6ad2)

**Table: Ref**


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

**Database Information**
----------------------------
Name of the database: 
Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format:
