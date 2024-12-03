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
The goal of this project is to model and build a relational database that captures the main details surronding UFC events, fighters, and associated statistics. The central entity in this data model is the PPV (Pay-Per-View) Main Event, which is the final fight of the night for the UFC Event. Each PPV is composed of various **headliner fights** , featuring multiple fighters whose specific attributes are recorded. Additionally, we are interested in tracking other important aspects such as the **venue, commentary crew, and social media following** of the UFC fighers. Furthermore, we aim to perform functional queries on this data to provide valuable insights into UFC operations, fight statistics, and fighter performances. 

**Data Model**
------------------------------
![image](https://github.com/user-attachments/assets/3250e197-94d2-4929-bc90-11ce419b4c45)



**Explanation of Data Model:**

Our model is based on the structure of a UFC event management system. At the base of the model is the PPV Main Event entity, which each represent an individual UFC fight. Each PPV Main Event involves several entities, including fighters, commentary crew, venues, referees, and detailed statistics about the fights. Each fighter in the PPV has a corresponding social media following, title reign history, head coach, and fight kit.

* PPV Main Event: This entity is the central focus, capturing the event's details like the card number, date, PPV buys, and gate revenue. A one-to-many relationship exists between the PPV and the venue where the event takes place, as each PPV event occurs in a specific venue. It also has a many-to-many relationship with Fighters of Headliner as there can be multiple fighters on each main event and each fighter can be on multiple different PPVs. 

* Fighters of Headiner: Each fighter has attributes such as name, country of origin, fighting style, record (wins/losses), and physical characteristics (e.g., height, reach, weight class). Each fighter has a relationships with Title Reign, Social Media following, Fight Hit, and Head Coach entities. Fighters have a many-to-many relationship with PPV Main event.

* Fight Stats: Detailed statistics for each fight are recorded, including rounds, time, significant strikes, and control time. These statistics provide insight into the performance of each fighter during the event.

* Fight Kit: This entity tracks the gear used by each fighter during the fight, such as the short color and glove color. A fighter's gear is uniquely identified for each fight, and there is a many-to-one relationship between the fight kit and the fighters.

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

**1. Query 1: what happened in the biggest ppv of all time?**

This is important information to know, especially with newcomers to ufc. Here we are able to see who participated in the biggest ppv ever, as well as the outcome and stats.

![image](https://github.com/user-attachments/assets/bfd58d5f-5ed8-4155-954d-36eb209d1f0a)


**2. Query 2: Who are the Refs, How much experience, which has the highest Total PPVs?**

This query shows the most popular refs in the UFC. There are 3 Reoccurring Refs in the top 10 PPVs, Herb dean being the most popular with over 11 million total PPVS. Each ref has over 20 years of experience. The ref has a big influence on the fight, because an inexperienced ref would not know when to stop the fight or know all the rules.

![image](https://github.com/user-attachments/assets/f5e28738-2b72-48c4-a76b-85940cdb3b3a)


**3. Query 3: PPV Events with Above Average Significant Strikes from the Winner:**

This query will show the most exciting PPV events by having only the fights with above average significant strikes. It shows the card number of the UFC Event and PPV Buys as well. This is important because the UFC promoters would probably want to see a correlation between more strikes being thrown and more PPV buys.

![image](https://github.com/user-attachments/assets/9fe58d5a-81db-4966-a79a-c3623fec8291)


**4. Query 4: Headshots to Significant strikes ratio and winner of each card:**

This query shows the headshot percentage of significant strikes for each of the winners and their UFC Event Card. This could be helpful because it shows which fighters are most accurate in hitting headshots, and therefore are most likely to get knockouts.

![image](https://github.com/user-attachments/assets/8cb4936a-756e-4ea9-bb39-77d104b66cae)


**5. Query 5: Fight Winners with the highest social media following:**

This query shows the fighters that won their fights with the highest social media following in descending order. This could be useful in determining which fighters have the biggest outreach and will sell the most PPV's.

![image](https://github.com/user-attachments/assets/44e6ca84-8a97-43dc-b0bd-4ecc78ab98db)

**6. Query 6: Which Finishing Round has highest PPV numbers:**

This query shows which fight length had highest PPV buys. This is helpful because it shows what length of time people are most engaged watching the fights for. Most viewers probably don't want to spend their money on a super quick finish but also don't want a long 25 minute fight with a decision. 

![image](https://github.com/user-attachments/assets/bb1a07a9-275c-4d37-8466-79bf828dd6aa)

**7. Query 7: Who fought the most in the top 10 PPV's.**

This is very useful information to know who fought the most in the top 10 PPV's. Knowing this can give fans an idea of who draws more PPV buys. 

<img width="598" alt="Screenshot 2024-10-13 at 7 17 29 PM" src="https://github.com/user-attachments/assets/be5ca871-c0e4-46ed-8b8e-7e8ad32926df">


**8. Query 8: Different fighting styles.**

Showing the different fighting styles is important to understanding what Mixed Martial Arts is all about. Rather than just incorporating one kind of style like noxing, you can see there are several styles, which is what makes the UFC so unique.

<img width="590" alt="Screenshot 2024-10-13 at 7 46 50 PM" src="https://github.com/user-attachments/assets/5284a1ee-5a16-4c43-bb9d-7d565352e38d">
 

**9. Query 9: Determine which city has held the most of these events.**

This would be useful to help determine where the UFC should hold events in the future.

![image](https://github.com/user-attachments/assets/23b201eb-d394-42b0-93b2-8bb34f246809)


**10. Query 10: List all the fighters on the highest selling PPV's alphabetically**

This would be useful for the UFC to know who their top selling fighters are.

![image](https://github.com/user-attachments/assets/883a6e74-356e-4b70-91a5-9ecb27176794)

**Tableau Visualization 1:**

![output (5)](https://github.com/user-attachments/assets/e293d41f-0390-4d26-9fb7-f78ad2991138)

**Tableau Visualization 2:**

![output (6)](https://github.com/user-attachments/assets/0a718c14-54b8-4e09-bc6a-2463f2314322)




**Database Information**
----------------------------
Name of the database: cs_gcr34350

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q1
