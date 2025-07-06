# 🥗 Diet Manager CLI

**Diet Manager** is a command-line nutrition tracking tool built to help users manage their dietary habits effectively. It supports personalized calorie goals, food logging (including composite meals), and real-time feedback — all while demonstrating solid object-oriented design principles and extensible architecture.

---

## 🚀 Features

### 🧾 Food Database
- **Basic Foods**: Define foods with name, keywords, and calories per serving.
- **Composite Foods**: Create new foods by combining existing ones.
- **Extensible**: Easy to add nutrients (e.g., protein, carbs) or integrate external APIs.

### 📅 Daily Logs
- Log food intake by date
- Modify or delete entries
- Unlimited undo during session using the Command pattern

### 🎯 Diet Goals
- Configure personal profile (age, height, weight, gender, activity level)
- Choose calorie calculation method (Harris-Benedict or Mifflin-St Jeor)
- Get real-time calorie surplus/deficit feedback

---

## 🧠 Design Overview

### Key Design Principles

- **Low Coupling & High Cohesion**: Modular manager classes and clean separation between UI, logic, and data models.
- **Command Pattern**: Encapsulates user actions like `AddFoodCommand` and `DeleteFoodCommand`, supporting undo functionality.
- **Composite Pattern**: Treat basic and composite foods uniformly.
- **Separation of Concerns**: CLI handles input/output; core logic is isolated in backend modules.

### Class Responsibilities

- `Food`, `BasicFood`, `CompositeFood`: Represent food entities
- `UserProfile`: Stores and computes personal dietary data
- `FoodDiary`: Manages daily food logs
- `ProfileManager`, `FoodDatabaseManager`: Handle core operations
- `DietAssistantCLI`: Command-line interface and user interaction

---

## 📐 Scalability

The project is designed to scale easily:

- **Add More Nutrients**: Extend `Food` and update calorie/nutrient calculations
- **Support External APIs**: Adapter + Factory Pattern for third-party food sources (e.g., USDA)
- **Add More Calorie Formulas**: Easily extend with new calculation methods
- **Efficient Data Handling**: Uses shared pointers and lazy loading for memory optimization

---


## 🛠️ Built With

- **Language**: C++
- **Concepts Used**: OOP, Design Patterns (Command, Composite, Façade), CLI app structure

---

## 📌 Future Improvements

- Timestamped food entries for more granular analysis
- Decoupled service layer for improved testability
- GUI or web-based frontend

---

## 📂 Getting Started

Clone the repository and compile using your preferred C++ toolchain:

```bash
git clone https://github.com/your-username/diet-manager-cli.git
cd diet-manager-cli
make
./diet_manager
