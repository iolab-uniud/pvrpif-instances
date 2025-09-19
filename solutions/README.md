# Structure of the solution file

For each instance the solution file provides both the routes of the solutions and the feasibility checks. Hereafter, the structure of the solution *.txt* files is explained in brief.


Each file present the following blocks.

## Naming and cost

```txt
Solution for Milano_020_4_0 with cost 562.0  is feasible.
```

- Instance name: Milano_020_4_0
- Solution cost: 562.0
- Feasibility status: Indicates whether the solution satisfies all constraints.


## Overall results of the feasibility Checks

```txt
Route are feasible: True
    demand feasible: True
    time feasible: True
    right depot: True
Vehicle usage per day is within the available fleet limit: True
    num vehicles per day: {0: 2, 1: 2, 2: 2, 3: 2}
Assigned visiting schemes meet customer requirements: True
```

- Route feasibility: Indicates whether the routes are feasible.
    - demand feasible: Indicates whether constraints on demand are satisfied.
    - time feasible: Indicates whether constraints on time are satisfied.
    - time feasible: Indicates whether the routes reach the right depot.
- Fleet usage: Number of vehicles used per day does not exceed the available fleet.
    - num vehicles per day: num of vehicles used per day.
- Customer requirements: Indicates whether visiting schemes align with customers' requirements.

## Instance Information

```txt
Instance info:
MaxDuration: 149, MaxCapacity: 107
PlanningHorizon: 4, NumVehicles: 2
Index of the depot each day: {0: 0, 1: 0, 2: 0, 3: 0}
```

- MaxDuration: Maximum allowed route duration per vehicle.
- MaxCapacity: Maximum load capacity per vehicle.
- PlanningHorizon: Number of days in the planning period.
- NumVehicles: Number of vehicles available per day.
- Depot index per day: Specifies which depot is used each day.

## Daily Route Details

For each of the solution route:

```txt
Day: 0: Vehicle:0 time: 75.0  time_feasible: True  demand_feasible: True
```

- Vehicle summary:
    - day: The day on which this route is performed.
    - vehicle: Which of the available vehicles is assigned to this route.
    - time: Total route duration.
    - cost: Associated cost of the route.
    - time_feasible: Indicates whether the routes is time feasible.
    - demand_feasible: Indicates whether the routes is demand feasible.

```
          0     1     2     3     4     5     6
path    0.0  18.0  12.0  20.0   8.0  21.0   0.0
demand  0.0  20.0  51.0  77.0  97.0   0.0   0.0
time    0.0   8.0  14.0  33.0  47.0  65.0  75.0
```

- Route matrix:

    - path: index of the traversed nodes, the route is [0,18,12,20,9,21,0]
    - demand: Cumulative demand at each node, it goes to zero if an intermediate facility is visited.
    - time: Arrival time at each node.

## Assigned Visiting Schemes

This block verifies whether the assigned visiting schemes for each customer match one of the acceptable options:

```
Scheme(0): options: []  assigned: [0, 1, 2, 3]  Correct: True
Scheme(1): options: [[0, 2], [1, 3]]  assigned: [1, 3]  Correct: True

...

Scheme(22): options: []  assigned: [0, 2]  Correct: True
```

- Scheme(i): Refers to customer i.
- options: Lists acceptable combinations of days the customer can be visited.
- assigned: Actual days assigned in the solution.
- Correct: Indicates whether the assignment is valid.


> [!NOTE]  
> Both the depot (in this case node 0) and the intermediate facilities (usually the last nodes) do not have any options. Therefore, any assigned visiting scheme is considered correct.
