# capstone-project-2025
This project simulates such a system: participants will create an intelligent, data-driven pricing engine for 14 parking spaces using real-time data streams, basic economic theory, and ML models built from scratch, using only numpy, pandas libraries.
Project Objective
My goal is to build a dynamic pricing model for each parking space such that:
• The price is realistically updated in real-time based on:
– Historical occupancy patterns
– Queue length
– Nearby traffic
– Special events
– Vehicle type
– Competitor parking prices
• It starts from a base price of $10
• The price variation is smooth and explainable, not erratic
• Optional: The system suggests rerouting vehicles to nearby lots if the current lot
is overburdened.
Core Requirements
Pricing Logic Implementation
• You must implement all pricing models from scratch (only Python, Pandas,
Numpy, Pathway).
Pricing Model Stages
You will build three models, increasing in complexity and intelligence.

2

Model 1: Baseline Linear Model
A simple model where the next price is a function of the previous price and current
occupancy:
• Linear price increase as occupancy increases
• Acts as a reference point
Example:

Pricet+1 = Pricet + α ·

Occupancy
Capacity 
Model 2: Demand-Based Price Function
A more advanced model where you:
• Construct a mathematical demand function using key features:
– Occupancy rate
– Queue length
– Traffic level
– Special day
– Vehicle type
Example demand function:
Demand = α·

Occupancy
Capacity 

+β·QueueLength−γ·Traffic+δ·IsSpecialDay+ε·VehicleTypeWeight

Use this demand value to adjust prices:

Pricet = BasePrice · (1 + λ · NormalizedDemand)

• Ensure demand is normalized and price variations are smooth and bounded (e.g.,
not more than 2x or less than 0.5x base).
Note: The example pricing functions provided in the models above are linear and
serve as simple baselines. Participants are encouraged to design and implement more
effective and sophisticated pricing strategies.
Model 3 (Optional): Competitive Pricing Model
This model adds location intelligence and simulates real-world competition:
• Calculate geographic proximity of nearby parking spaces using lat-long.
• Determine competitor prices and factor them into your own pricing.
Competitive logic:
• If your lot is full and nearby lots are cheaper → suggest rerouting or reduce price
• If nearby lots are expensive → your price can increase while still being attractive
This model encourages creativity and business thinking along with technical skills.
