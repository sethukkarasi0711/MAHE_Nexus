About the Problem Statement
Wrong-way driving is a critical road safety issue that leads to severe accidents, often resulting in fatalities due to high-speed head-on collisions. Existing detection systems are primarily deployed at freeway entry and exit ramps using fixed camera infrastructure. While effective in controlled environments, these systems fail to address wrong-way incidents occurring beyond ramps.
In real-world urban scenarios, wrong-way driving frequently occurs on:
One-way streets in cities
Undivided or poorly marked roads
Temporary diversions due to road construction
Campus roads and gated communities
These environments lack dedicated monitoring infrastructure, making detection and prevention extremely challenging.
Additionally, current systems:
Are location-specific and cannot track vehicles once they move beyond monitored zones
Require expensive installation and maintenance
Do not provide real-time alerts to nearby drivers
Fail to adapt to dynamic road conditions such as diversions
Therefore, there is a need for a scalable, cost-effective, and real-time solution capable of detecting wrong-way driving across diverse road networks.

Objective
The primary objective of this project is to design and develop a lightweight, scalable wrong-way detection system that:
Detects vehicles moving opposite to the permitted road direction in real time
Utilizes GPS trajectory data instead of physical roadside infrastructure
Leverages open-source map data (e.g., OpenStreetMap)
Works across urban roads, highways, and temporary road configurations
Provides early warnings (10–15 seconds) to prevent collisions
Supports multi-vehicle environments including fleets and connected mobility systems
What Is Actually Being Asked? (Human-Centered Understanding)
Consider a real-life scenario:
You are driving on a one-way road in a busy city like Bengaluru. Everything appears normal until suddenly a vehicle appears directly in your lane, moving toward you in the opposite direction. At that moment, you have only a few seconds to react.
If a system could warn you 10–15 seconds earlier, the probability of avoiding a collision increases significantly.
Core Challenge:
Detect wrong-way vehicles before they become visible threats
Provide early, actionable alerts
Achieve this without relying on expensive infrastructure
The problem is not just detection—it is about:
Timeliness
Scalability
Affordability
Adaptability to real-world complexity
Why Current Systems Fail
Existing solutions rely heavily on static infrastructure and are limited in scope.
Limitations:
Detection is restricted to specific locations (e.g., ramps)
Requires high-cost hardware installations
Urban roads lack coverage
Cannot handle temporary road changes (diversions)
No communication to nearby drivers
Proposed Approach (Core Idea)
Our system eliminates the need for roadside infrastructure by using:
Vehicle GPS data (from phones, navigation systems, or trackers)
Road direction data from OpenStreetMap
Mathematical bearing comparison
The Physics of the Solution
What is Bearing?
Bearing represents the direction of movement in degrees:
North → 0°
East → 90°
South → 180°
West → 270°
Using two GPS points, we calculate the vehicle’s movement direction.
Bearing Formula
bearing=tan−1(cos(lat1​)⋅sin(lat2​)−sin(lat1​)⋅cos(lat2​)⋅cos(Δlon)sin(Δlon)⋅cos(lat2​)​)
Detection Logic
Compare:
Vehicle Bearing vs Road Direction
Difference
Interpretation
< 30°
Correct direction
30°–150°
Uncertain (turning/merging)
> 150°
Wrong-way driving

This threshold accounts for:
Road curvature
GPS noise
Real-world driving variations
Data: Sources, Creation & Processing
Data Sources
GPS Trajectory Data
Real-time or simulated vehicle movement
OpenStreetMap (OSM)
Road geometry
One-way restrictions
Data Generation (Simulation)
Multi-vehicle GPS traces are simulated
Wrong-way vehicles are artificially injected
Normal vs abnormal movement patterns are labeled
Data Processing Steps
Map-match GPS points to road segments
Extract road direction from OSM
Compute vehicle bearing
Compare bearings
Classify movement

