# Identify Entities:

Gymnasium
Member
Session
Coach
<br><br>

# Identify Relationships:

Gymnasium registers Members
Members attend Sessions
Sessions are led by Coaches
<br><br>

# Determine Attributes for Each Entity:

Gymnasium: name, address, phone number
Member: unique identifier, last name, first name, address, date of birth, gender
Session: type of sport, schedule, maximum of 20 members
Coach: last name, first name, age, specialty
<br><br>

# Define the Relationships:

The relationships between these entities based on the prompt are as follows:

Gymnasium to Member:

Relationship: A Member registers at a Gymnasium.
Cardinality: A Gymnasium can have many Members (1:N), and each Member can only register at one Gymnasium.
Member to Session:

Relationship: A Member attends a Session.
Cardinality: A Member can attend many Sessions (M:N), and a Session can have many Members, but the total number of members per session is limited to 20.
Session to Coach:

Relationship: A Session is led by one or more Coaches.
Cardinality: A Session can be led by one or two Coaches (1:2). Each Coach can lead many Sessions (1:M).

# Define Cardinalities:

One Gymnasium can have many Members, but each Member is registered at one Gymnasium.
Each Session can have many Members, and each Member can attend many Sessions.
Each Session is led by one or two Coaches, and each Coach can lead many Sessions.
<br><br>

# ER Diagram:

<br><br>

Gymnasium (1) — Registers — (M) Member
Session (M) — Attends — (M) Member
Session (M) — Leads — (M) Coach
<br><br>

[Gymnasium] --- Registers ---< [Member]
| |
| |
v v
[Session] --- Attends ---< [Member]
|
|
v
[Coach] --- Leads ---< [Session]

+------------------------+ +---------------------+ +-------------------+
| Gymnasium | | Member | | Session |
|------------------------| |---------------------| |-------------------|
| - Name | | - Member_ID (PK) | | - Type of Sport |
| - Address | | - Last Name | | - Schedule |
| - Telephone Number | | - First Name | | - Max Members |
+------------------------+ | - Address | +-------------------+
| | - Date of Birth | |
| Registers | - Gender | | Attends
| +---------------------+ |
v | v
+--------------------+ +------------------------+ +-------------------+
| Coach | | Leads | | Member |
|--------------------| |------------------------| |-------------------|
| - Last Name | | | | |
| - First Name | | | | |
| - Age | | | | |
| - Specialty | | | | |
+--------------------+ +------------------------+ +-------------------+
