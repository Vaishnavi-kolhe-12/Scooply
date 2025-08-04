# MCP Pokémon Battle Simulation Server

This project implements an MCP (Model Context Protocol) server with two main capabilities:

1. **Pokémon Data Resource** – Provides detailed information about any Pokémon.
2. **Battle Simulation Tool** – Simulates battles between two Pokémon with type effectiveness and stat-based mechanics.

---

## 📁 Project Structure

├── main.py # Entry point (FastAPI app)

├── pokemon_data.py # Pokémon data logic (GET /pokemon/{name})

├── battle.py # Battle simulation logic (POST /battle)

├── requirements.txt # Python dependencies

└── README.md # Project documentation

---

## ⚙️ Installation
1. Install **Python 3.8 or higher**.
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
3. Run the FastAPI server using Uvicorn:

    uvicorn main:app --reload


---

🌐 API Endpoints
1. GET /pokemon/{name}
Description: Returns detailed data about the specified Pokémon.
Example:curl http://127.0.0.1:8000/pokemon/pikachu
Sample Response:
{
  "name": "pikachu",
  "types": ["electric"],
  "stats": {
    "hp": 35,
    "attack": 55,
    "defense": 40,
    "special_attack": 50,
    "special_defense": 50,
    "speed": 90
  },
  "abilities": ["static", "lightning-rod"],
  "moves": ["quick-attack", "thunderbolt", "iron-tail", "electro-ball"],
  "evolution": "raichu"
}



2. POST /battle
Description: Simulates a turn-based battle between two Pokémon.
Request Body:
{
  "pokemon1": "pikachu",
  "pokemon2": "charmander"
}
Example:
curl -X POST http://127.0.0.1:8000/battle \
-H "Content-Type: application/json" \
-d '{"pokemon1": "pikachu", "pokemon2": "charmander"}'
Sample Response:
{
  "winner": "pikachu",
  "log": [
    "Pikachu used Thunderbolt. It's super effective!",
    "Charmander fainted!",
    "Pikachu wins!"
  ]
}

---

🔧 Features Implemented
Pokémon data lookup:
  Base stats (HP, Attack, etc.)
  Types
  Abilities
  Moves
  Evolution info

Battle Simulation:
  Type effectiveness
  Stat-based damage
  Speed-based turn order
  Status effects: Burn, Paralysis, Poison
  Detailed battle logs
  Winner determination


---
📦 Requirements
Python 3.8+
FastAPI
Uvicorn


---
📘 About MCP
  The Model Context Protocol (MCP) allows this server to act as a bridge between LLMs and Pokémon data/simulation tools, enabling contextual interaction through structured resources and tools.
  More info: https://modelcontextprotocol.io/introduction

---

✅ How LLMs Can Use This
  Query /pokemon/{name} to retrieve stats, abilities, moves, and evolution data.
  Use /battle to simulate a turn-based battle between any two Pokémon and get the winner and full battle log.

---

🖥️ How to Run This Project (Step-by-Step)

  Open VS Code or any code editor of your choice.


  Open the project folder that contains:
    main.py
    pokemon_data.py
    battle.py
    requirements.txt
    README.md


  Open the Terminal in VS Code:
    From the menu: Terminal > New Terminal


  Install dependencies:
    pip install -r requirements.txt


  Start the server:
    uvicorn main:app --reload

  
  Once the server starts, open your browser and go to:
    http://127.0.0.1:8000/docs

  
  🧪 Test Examples
    Try GET /pokemon/pikachu
    Try POST /battle with:
       {
          "pokemon1": "pikachu",
          "pokemon2": "charmander"
       }
---
<img width="1500" height="800" alt="image" src="https://github.com/user-attachments/assets/04576d58-c921-48b4-a49b-4e0ca0b7b641" />
<img width="1500" height="800" alt="image" src="https://github.com/user-attachments/assets/afd155f8-233b-4895-b85a-433bb6c9f51a" />
<img width="1500" height="800" alt="image" src="https://github.com/user-attachments/assets/d4d0a0f2-83eb-4399-a33d-4acae987b5fd" />
<img width="1500" height="800" alt="image" src="https://github.com/user-attachments/assets/c4ce5966-8e45-46ab-ba0f-8d48ef576090" />
<img width="1500" height="800" alt="image" src="https://github.com/user-attachments/assets/9c296160-6bff-4162-bdb5-f77abcd76b01" />
<img width="1500" height="800" alt="image" src="https://github.com/user-attachments/assets/723a5da1-f358-4e8d-887a-b3333c5377e7" />












