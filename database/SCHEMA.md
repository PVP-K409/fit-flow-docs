# Database schema

## Entity-Relationship Diagram

```mermaid
erDiagram
    Users {
        string userId PK
        string name
        string email
        string levelId FK
        int points
        string inventory
        int age
        int height
        int weight
        string gender
    }

    Activities {
        string activityId PK
        string name
        string description
        int points
    }

    Steps {
        string stepId PK
        string userId FK
        string timestamp
        string activityId FK
        double distance
        double caloriesBurned
    }

    Goals {
        string goalId PK
        string userId FK
        string activityId FK
        int target
        date startDate
        date endDate
        string status
    }

    GoalsStatus {
        string userId PK
        string goalId PK
        int currentProgress
        datetime lastUpdated
    }

    Levels {
        string levelId PK
        string name
        int requiredPoints
    }

    Inventory {
        string itemId PK
        string name
        string type
    }

    Animals {
        string animalId PK
        string name
        string species
        string imageUrl
    }

    Decorations {
        string decorationId PK
        string name
        string type
        string imageUrl
    }

    Rewards {
        string rewardId PK
        string name
        string description
        int pointsRequired
    }

    Users ||--o{ Goals : "has"
    Users ||--o{ GoalsStatus : "has"
    Goals ||--|| Activities : "relates to"
    Users ||--|| Levels : "has a"
    Users |o--|{ Inventory : "contains"
    GoalsStatus }|--|| Goals : "updates"
    Users ||--o{ Steps : "has"
    Inventory }|--o{ Animals : "contains"
    Inventory }|--o{ Decorations : "contains"
```
