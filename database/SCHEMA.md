# Database schema

```mermaid
erDiagram
    User {
        string userId PK
        string levelId FK
        int inventoryId
        string name
        string email
        int points
        int Xp
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
        int temp
    }

    Activity {
        string activityId PK
        string name
        string description
    }

    Goal {
        string goalId PK
        string userId FK
        string activityId FK
        int target
        int currentProgress
        int points
        int xp
        date startDate
        date endDate
        date lastUpdated
    }

    Level {
        string levelId PK
        string name
        int requiredXp
    }

    Inventory {
        int inventoryId PK
        string name
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
        int requiredXp
    }

    User ||--o{ Goal : "has"
    Goal ||--|| Activity : "relates to"
    User ||--|| Level : "has a"
    User |o--|| Inventory : "contains"
    User ||--o{ Step : "has"
    Inventory }|--o{ Animal : "contains"
    Inventory }|--o{ Decoration : "contains"
```
