# Experiment No. 1: Developing an AI Agent with PEAS Description

**Name:** Shrivarshan PG
**Register Number:** 212225240146

---

# Aim

To identify the PEAS (Performance Measure, Environment, Actuators, Sensors) description for a Medicine Prescribing Agent and develop a simple AI agent using Python.

---

# Theory

A Medicine Prescribing Agent is an intelligent agent that monitors the temperature of patients in different hospital rooms. If a patient's temperature is greater than **98.5°F**, the patient is considered to have a fever, and the agent prescribes medicine.

The agent starts from a randomly selected room, visits every room, checks the patient's temperature, and prescribes medicine whenever required.

The agent's performance is evaluated based on:

- Reward for successfully treating patients.
- Penalty for moving between rooms.

---

# PEAS Description

| Component | Description |
|-----------|-------------|
| **Performance Measure** | Treat unhealthy patients while minimizing unnecessary movement |
| **Environment** | Hospital rooms containing patients |
| **Actuators** | Move between rooms, prescribe medicine |
| **Sensors** | Room location, patient temperature |

---

# Design Steps

### Step 1: Identify the Input

- Patient temperature
- Hospital rooms

### Step 2: Identify the Output

- Display whether the patient is healthy or has a fever.
- Prescribe medicine if the patient's temperature is greater than **98.5°F**.

### Step 3: Develop the PEAS Description

The Medicine Prescribing Agent is designed using:

- Performance Measure
- Environment
- Actuators
- Sensors

### Step 4: Implement the AI Agent

- Store patient temperatures in different rooms.
- Randomly select the order of room visits.
- Check each patient's temperature.
- Prescribe medicine if the patient has a fever.

### Step 5: Measure Performance

- Decrease performance for every movement between rooms.
- Increase performance whenever medicine is prescribed.

---

# Python Program

```python
import random

# ----------------------------
# STEP 1: Input
# ----------------------------

rooms = {
    "Room 1": 98,
    "Room 2": 102,
    "Room 3": 99,
    "Room 4": 101,
    "Room 5": 97
}

performance = 0

print("Patient Temperatures")
print("----------------------")
for room, temp in rooms.items():
    print(room, ":", temp, "°F")

# ----------------------------
# STEP 2: Output
# ----------------------------

print("\nChecking Patients...\n")

# Random starting room
room_names = list(rooms.keys())
random.shuffle(room_names)

for room in room_names:

    print("Agent moved to", room)
    performance -= 1

    temperature = rooms[room]

    if temperature > 98.5:
        print("Temperature:", temperature)
        print("Patient has Fever")
        print("Medicine Prescribed")
        performance += 10
    else:
        print("Temperature:", temperature)
        print("Patient is Healthy")

    print()

# ----------------------------
# STEP 5: Performance
# ----------------------------

print("----------------------")
print("Final Performance =", performance)
```

---

# Sample Output

```
Patient Temperatures
----------------------
Room 1 : 98 °F
Room 2 : 102 °F
Room 3 : 99 °F
Room 4 : 101 °F
Room 5 : 97 °F

Checking Patients...

Agent moved to Room 3
Temperature: 99
Patient has Fever
Medicine Prescribed

Agent moved to Room 5
Temperature: 97
Patient is Healthy

Agent moved to Room 2
Temperature: 102
Patient has Fever
Medicine Prescribed

Agent moved to Room 1
Temperature: 98
Patient is Healthy

Agent moved to Room 4
Temperature: 101
Patient has Fever
Medicine Prescribed

----------------------
Final Performance = 25
```

> **Note:** The order of rooms changes every time because the agent visits the rooms randomly.

---

# Output Screenshot

<img width="1117" height="725" alt="Screenshot 2026-07-24 105319" src="https://github.com/user-attachments/assets/90c90399-a261-4483-b449-692f7c64ef91" />
Example:

```

```

---

# Result

The PEAS description of the Medicine Prescribing Agent was successfully developed. The AI agent correctly visited hospital rooms in random order, identified patients with fever, prescribed medicine, and calculated the performance based on movement and treatment.
