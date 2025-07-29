# Deep Learning Optimization Algorithm for Automotive ECU Simulation

This repository contains a physics-based engine control unit (ECU) simulator integrated with a deep learning model that learns optimal throttle settings to maximize torque per unit fuel consumption. The model is trained and evaluated under varying environmental and mechanical conditions.

## Project Overview

The goal of this project is to simulate a realistic 4-cylinder internal combustion engine and train a lightweight neural network to optimize fuel efficiency by adjusting throttle input. The model is evaluated against a baseline of constant throttle behavior, with simulations showing significant improvements in fuel economy under dynamic conditions.

## What's Inside

- **Physics-based Engine Model:** Calculates horsepower, torque, and fuel burn based on real mechanical principles, including throttle position, air temperature, pressure, RPM, and engine displacement.
- **Neural Network Throttle Model:** A PyTorch model learns optimal throttle control using normalized inputs (temperature, pressure, RPM).
- **Training Pipeline:** Trains the model by minimizing the inverse of torque-to-fuel-burn ratio as a custom loss metric.
- **Evaluation & Visualization:**
  - Plots horsepower, torque, and fuel burn vs RPM.
  - Compares constant throttle vs AI-optimized throttle across time.
  - Visualizes torque response curves under both control strategies.

## Files

- [`ecu_sim.ipynb`](./ecu_sim.ipynb): Main code file including simulation, training, and plotting.
- [`paper.pdf`](./paper.pdf): Full write-up of the research project.
- [`abstract.pdf`](./abstract.pdf): Abstract overview of methodology and results.
- `README.md` and `LICENSE`

## Results Summary

The AI-optimized throttle profile consumed **~11.6% less fuel** compared to constant throttle over a 2-hour simulation period with dynamic driving conditions, while maintaining comparable torque outputs.

| Simulation Condition      | Fuel Burned (mL) |
|--------------------------|------------------|
| Constant Throttle (0.7)  | 283.98           |
| AI-Optimized Throttle    | 251.07           |

## Key Technologies

- Python, NumPy, PyTorch, Matplotlib
- Thermodynamic modeling
- Lightweight neural networks
- Custom loss design for energy efficiency

## Future Directions

- Integrate real-world vehicle data for fine-tuning
- Expand model input space (e.g., load, acceleration)
- Extend to hybrid or electric powertrains
- Export to embedded environments for real-time inference
