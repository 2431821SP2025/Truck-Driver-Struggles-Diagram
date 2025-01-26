# Truck Driver Struggles Diagram

This diagram represents the relationships and processes involved in a truck driver's workflow, focusing on the challenges of finding loads, dealing with brokers, managing expenses, and delivering loads.

```mermaid
erDiagram
    TRUCK_DRIVER {
        string Name
        int ExperienceYears
        float Profit
    }
    BROKER {
        string Name
        int CommissionPercentage
    }
    CLIENT {
        string Name
        string LoadDescription
    }
    LOAD {
        string Destination
        float Weight
    }
    SHIPPER {
        string Name
        string Location
    }
    RECEIVER {
        string Name
        string Location
    }
    EXPENSES {
        float FuelCost
        float MaintenanceCost
        float TollCost
    }

    TRUCK_DRIVER ||--|| BROKER : "Finds Load Through"
    BROKER ||--|{ CLIENT : "Manages Loads From"
    CLIENT ||--|| LOAD : "Requests Delivery Of"
    LOAD ||--|| SHIPPER : "Picked Up From"
    LOAD ||--|| RECEIVER : "Delivered To"
    TRUCK_DRIVER ||--|{ EXPENSES : "Incurs During Trip"
    TRUCK_DRIVER ||--|| LOAD : "Delivers"
    EXPENSES ||--|{ TRUCK_DRIVER : "Reduces Profit"

