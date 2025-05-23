# Projectile Motion Network 

This document presents a graphical analysis of a neural network trained to predict the range of projectile motion based on initial velocity and launch angle.

## 1. Model Architecture
### The neural network consists of:
- Input layer: 2 neurons (velocity and angle)
- 3 hidden layers: 64 neurons each with ReLU activation
- Output layer: 1 neuron (range prediction) with linear activation

## 2. Training Performance
### The model was trained for 10 epochs with the Adam optimizer and the MSE loss function.

![Figure1](training_performance.jpg)

*Figure 1: Training and validation loss across epochs showing convergence.*

## 3. Prediction Accuracy
### Comparison between actual and predicted range values on test data:

![Figure2](prediction_vs_actual.jpg)

*Figure 2: Scatter plot showing strong correlation between predicted and actual range values (R² = 0.999933 ≈ 1). This indicates that the Neural Network did learn the physics.*

## 4. Error Analysis
### Distribution of prediction errors:

![Figure3](error_distribution.jpg)

*Figure 3: Histogram of prediction errors showing mean error of 0.4393 meters and standard deviation of 1.16 meters.*

## 5. 3D Surface Visualization
### Comparison between neural network predictions and theoretical physics:

![Figure4](3Dgraph.jpg)

*Figure 4: (Left) NN predictions, (Middle) Theoretical physics, (Right) Prediction errors. The neural network closely approximates the theoretical model.*

## 6. Contour Analysis
### Detailed view of range predictions across parameter space:

![Figure5](contours.jpg)

*Figure 5: Contour plots showing (Left) NN predictions, (Middle) Theoretical values, (Right) Error magnitudes.*

## 7. Slice Analysis

### Range vs Velocity at 45°

![Figure6](range_vs_velocity.jpg)

*Figure 6: Comparison at fixed angle (θ = 45°) showing the relationship between velocity and range.*

### Range vs Angle at 40 m/s

![Figure7](range_vs_angle.jpg)

*Figure 7: Comparison at fixed velocity (v = 40 m/s) showing the relationship between angle and range.*

## 8. Key Findings
1. The neural network achieved a mean absolute error of 0.86 meters on test data
2. Maximum error occurs at:
    - High velocities (>40 m/s)
    - Extreme angles (<15° or >75°)
4. The model captures the fundamental physics:
    - Quadratic dependence on velocity
    - Sinusoidal dependence on angle
    - Maximum range at 45° for the given velocity.

## 9. Future Improvements
1. Increase training data at edge cases (high velocity, extreme angles)
2. Experiment with network architecture (deeper vs wider networks)
3. Add physical constraints to the loss function
4. Include air resistance in training data

