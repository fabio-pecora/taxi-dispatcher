# 🚕 Taxi Dispatcher Simulation

A NetLogo-based simulation that models a taxi dispatch system in an urban environment. The simulation evaluates how different dispatching strategies affect passenger wait times in the presence of traffic congestion.

## 🧠 Objective

To simulate a realistic city grid with ride requests and varying traffic levels, and compare multiple dispatch strategies (Random, Nearest, Smart, and Super-Smart) based on how efficiently they reduce passenger wait time.

## 🏙️ Environment

- The city is modeled as a grid.
- Streets are placed every 5 patches horizontally and vertically.
- Only street patches are navigable by taxis.
- Traffic levels range from 1 (no traffic) to 4 (severe congestion), dynamically distributed across the grid.

## 🚖 Agents

### Taxis
- Start at random street locations
- Navigate based on traffic and assigned requests
- Change color depending on state:
  - **Black**: idle
  - **Green/Blue/Cyan**: en route to pickup
  - **Red**: carrying passenger

### Ride Requests
- Randomly generated with pickup and drop-off coordinates
- Stored in a global list
- Visualized as green (pickup) and red (drop-off) patches

## ⚙️ Dispatch Strategies

### 1. Random
Assigns available taxis to ride requests without considering distance or traffic. Inefficient but simple.

### 2. Nearest
Assigns the closest taxi (Euclidean distance) to each request. Ignores traffic but improves over Random.

### 3. Smart
Each taxi chooses the closest 3 requests and picks the one with the lowest traffic at the pickup point.

## 📊 Performance Metric

**Average Wait Time**:  
Calculated as the time (in ticks) between a ride request and pickup. This is tracked across all rides to evaluate strategy performance.

## 🧪 Experiment

We ran multiple trials for each dispatch strategy to compare average wait times.

## ▶️ How to Run

1. Open the project in NetLogo.
2. Chose the parhamaters you want (strategy, # taxies, etc..).
3. Press **Setup** to initialize the environment.
4. Press **Go** to start the simulation.
5. Observe taxi behavior and traffic, and monitor `average_wait_time`.

## 📌 Future Work
- Implement Dijkstra or A* for true shortest path routing
- Add dynamic traffic changes
- Introduce passenger behavior (cancellation, impatience)
- Integrate traffic lights and intersection rules

## 🛠️ Tools

- NetLogo 6.3.0+
- Language: NetLogo (Logo-based agent modeling language)
