# Deep Learning Optimization Algorithm for Efficient Automotive Powertrain Control
A simulation of an ML controlled ECU with advanced throttle restriction for fuel efficiency

# Abstract
- With heightened concerns over the environmental impacts of internal combustion engines (ICEs), many automobile manufacturers have curtailed development of internal combustion engines in favor of alternative fuel vehicles. Alternatively, manufacturers have devoted large amounts of resources to redesign existing ICEs for improved efficiency. Both of these solutions are costly and time-consuming. Meanwhile, the advancement of deep learning algorithms provides the opportunity for a new avenue of automotive optimization. The focus of this study is on the application of deep learning algorithms specifically in engine control units (ECUs), which can significantly improve performance, efficiency, and reliability alike.
- The objective of this study is to demonstrate the potential for a machine learning model to optimize internal combustion engines. A Python script was written to simulate the essential qualities of a commercial engine; a PyTorch neural network was trained to operate its inputs to optimize efficiency. After several hundred training cycles, the model attempted to optimize engine performance given fictitious environment data. Engine performance was recorded in various formats, notably fuel consumption. These results were holistically evaluated against simulated data of human inputs.
- The results show promise for AI controlled ECU systems to improve fuel efficiency of ICEs, without the steep development costs of full engine redesign.

# Introduction
- Various proposed solutions to the environmental impacts of ICEs are expensive and time-consuming (Ghadikolaei et. al, 2021)
- The use of an adaptive deep learning algorithm to handle inputs from sensors and outputs to engine control may increase engine efficiency, reducing environmental impacts
- Such integration has not been well-studied due to hardware limitations, which are slowly being overcome (Yokoyama et. al, 2019)
- Research question is thus as follows: “To what extent can deep learning algorithms optimize the efficiency and performance of an internal combustion engine?”

# Methodology
- Abstracted Python simulation of ICE with inputs: air temperature, air pressure, fuel-air-ratio, engine speed, displacement, and throttle control; outputs: predicted horsepower, torque, and fuel burnt per 4 engine cycles
- Python simulation adjusted to emulate performance of 4-cylinder Honda D16A engine
- Use PyTorch to create 3x5x1 neural network using ReLU training function, accepts inputs: air temperature, air pressure, engine speed; output(s): predicted throttle control
- Neural network trained in 500 epochs of 250 randomized scenarios of engine simulation (normalized data), with torque to fuel-consumption ratio used as loss function
- Fictitious scenario of 2-hour uphill drive, linearly decreasing temperature, linearly decreasing air pressure, and linearly decreasing engine speed created
- Recorded minute-wise fuel burn of neural network throttle decision in the scenario, compared with fuel burn of constant (70%) throttle input, emulating various  human driver behaviors (see Jupyter notebook)

# Findings
- Under the provided scenario (see Jupyter notebook), the 70% constant throttle required 0.284 litres of fuel to complete the designated task, while the AI throttle control required 0.172 litres
- As such, the AI controlled powertrain was roughly 39.5% percent more fuel efficient
- Since required torque was greatly reduced near the end of the simulated drive, fuel consumption decreased drastically for both systems
- Simulations with various human driver behaviors further support this conclusion

# Discussion
- The results show promise for AI controlled ECU systems to improve fuel efficiency of ICEs
- More sophisticated simulations and neural networks may provide more accurate results
- AI engine control algorithms may serve as an easy-access, near-future solution to augment and complement alternative fuel technologies
- It allows for improved efficiency and performance without intensive redesign of existing ICEs

# References
- Fang, K., Shenton, T., & Mottershead, J. (2012). Optimal Test Signal Design and estimation for dynamic powertrain calibration and Control (thesis).
- Fletcher, T., Kalantzis, N., Cary, M., Lygoe, B., Pezouvanis, A., & Ebrahimi, K. (2020). Automated engine calibration validation for Real World Driving Conditions. International Journal of Powertrains, 9(4), 345. https://doi.org/10.1504/ijpt.2020.111251
- Ghadikolaei, M. A., Wong, P. K., Cheung, C. S., Zhao, J., Ning, Z., Yung, K.-F., Wong, H. C., & Gali, N. K. (2021). Why is the world not yet ready to use alternative fuel vehicles? Heliyon, 7(7). https://doi.org/10.1016/j.heliyon.2021.e07527
- Milojevi, S., Bodza, S., Cimniak, V., Angerbauer, M., Rether, D., Grill, M., & Bargende, M. (2022). Data-driven modeling: An AI toolchain for the powertrain development process. SAE Technical Paper Series. https://doi.org/10.4271/2022-01-0158
- Reitz, R. D., Ogawa, H., Payri, R., Fansler, T., Kokjohn, S., Moriyoshi, Y., Agarwal, A., Arcoumanis, D., Assanis, D., Bae, C., Boulouchos, K., Canakci, M., Curran, S., Denbratt, I., Gavaises, M., Guenthner, M., Hasse, C., Huang, Z., Ishiyama, T., … Zhao, H. (2019). Ijer editorial: The future of the internal combustion engine. International Journal of Engine Research, 21(1), 3–10. https://doi.org/10.1177/1468087419877990
- Winsel, T., Ayeb, M., Theuerkauf, H. J., Pischinger, S., Schernus, C., & Lütkemeyer, G. (2004). Hil-calibration of SI engine cold start and warm-up using neural real-time model. SAE Technical Paper Series. https://doi.org/10.4271/2004-01-1362
- Yokoyama, N., & Moriyama, Y. (n.d.). Technology Development of AI Application for In-vehicle Control ECU. DENSO TEN Technical Review, 3(6). 
