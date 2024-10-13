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
The goal of this project is to model and build a relational database that captures the main details surronding UFC events, fighters, and associated statistics. The central entity in this data model is the PPV (Pay-Per-View) event, which acts as the main event for the UFC organization. Each PPV is composed of various **headliner fights** , featuring a **winner** and **loser** , whose specific details are recorded. Additionally, we are interested in tracking other important aspects such as the **venue, commentary crew, and social media following** of the UFC fighers. Furthermore, we aim to perform functional queries on this data to provide valuable insights into UFC operations, fight statistics, and fighter performances. 

**Data Model**
------------------------------
![image](https://github.com/user-attachments/assets/794f07a8-7aae-4202-bd45-b55349b7808a)



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

1. Query 1: what happened in the biggest ppv of all time?
This is important information to know, especially newcomers to ufc. we are able to see who participated in the biggest ppv ever, as well as the outcome and stats.
![image](https://github.com/user-attachments/assets/bfd58d5f-5ed8-4155-954d-36eb209d1f0a)

2. Query 2: Who are the Refs, How much experience, which has the highest Total PPVs?
This query shows the most popular refs in the UFC. There are 3 Reoccurring Refs in the top 10 PPVs, Herb dean being the most popular with over 11 million total PPVS. Each ref has over 20 years of experience. The ref has a big influence on the fight, because an inexperienced ref would not know when to stop the fight or know all the rules.  
![image](https://github.com/user-attachments/assets/f5e28738-2b72-48c4-a76b-85940cdb3b3a)

3. Query 3: PPV Events with Above Average Significant Strikes from the Winner:
This query will show the most exciting PPV events by having only the fights with above average significant strikes. It shows the card number of the UFC Event and PPV Buys as well. This is important because the UFC promoters would probably want to see a correlation between more strikes being thrown and more PPV buys.
![image](https://github.com/user-attachments/assets/9fe58d5a-81db-4966-a79a-c3623fec8291)

4. Query 4: Headshots to Significant strikes ratio and winner of each card:
This query shows the headshot percentage of significant strikes for each of the winners and their UFC Event Card. This could be helpful because it shows which fighters are most accurate in hitting headshots, and therefore are most likely to get knockouts.
![image](https://github.com/user-attachments/assets/8cb4936a-756e-4ea9-bb39-77d104b66cae)

5. Query 5: Fight Winners with the highest social media following:
This query shows the fighters that won their fights with the highest social media following in descending order. This could be useful in determining which fighters have the biggest outreach and will sell the most PPV's.

![image](https://github.com/user-attachments/assets/44e6ca84-8a97-43dc-b0bd-4ecc78ab98db)

6. Query 6: Which Finishing Round has highest PPV numbers:
This query shows which fight length had highest PPV buys. This is helpful because it shows what length of time people are most engaged watching the fights for. Most viewers probably don't want to spend their money on a super quick finish but also don't want a long 25 minute fight with a decision. 

![image](https://github.com/user-attachments/assets/bb1a07a9-275c-4d37-8466-79bf828dd6aa)

7. Query 7: <img width="598" alt="Screenshot 2024-10-13 at 7 17 29 PM" src="https://github.com/user-attachments/assets/be5ca871-c0e4-46ed-8b8e-7e8ad32926df">


8. Query 8

10. Query 9: Determine which city has held the most of these events.
This would be useful to help determine where the UFC should hold events in the future.

![image](https://github.com/user-attachments/assets/23b201eb-d394-42b0-93b2-8bb34f246809)


11. Query 10: List all the fighters on the highest selling PPV's alphabetically
This would be useful for the UFC to know who their top selling fighters are.

![image](https://github.com/user-attachments/assets/883a6e74-356e-4b70-91a5-9ecb27176794)


**Database Information**
----------------------------
Name of the database: 
Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format:
