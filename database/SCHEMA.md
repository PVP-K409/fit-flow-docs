# Database schema

```mermaid
erDiagram
    User {
        string userId PK
        string levelId FK
        string name
        string email
        int points
        string inventory
        int age
        int height
        int weight
        string gender
    }

    Step {
        string stepId PK
        string userId FK
        int initial 
        int current
        date date
    }

    Activity {
        string activityId PK
        string name
        string description
        int points
    }

    Goal {
        string goalId PK
        string userId FK
        string activityId FK
        int target
        date startDate
        date endDate
        int currentProgress
        date lastUpdated
    }

    Level {
        string levelId PK
        string name
        int requiredPoints
    }

    Inventory {
        string userId PK
        string itemId PK
        string name
        string type
    }

    Animal {
        string itemId PK
        string name
        string species
        string resourceId
        int price
    }

    Decoration {
        string itemId PK
        string name
        string type
        string resourceId
        int price
    }

    Reward {
        string rewardId PK
        string name
        string description
        int pointsRequired
    }

    User ||--o{ Goal : "has"
    Goal ||--|| Activity : "relates to"
    User ||--|| Level : "has a"
    User |o--|{ Inventory : "contains"
    User ||--o{ Step : "has"
    Inventory }|--o{ Animal : "contains"
    Inventory }|--o{ Decoration : "contains"
```
