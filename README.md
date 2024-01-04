# Machine-learning-based reduced order modeling for time-dependent problems

Solving parametrized partial differential equations (PDEs) such as the incompressible Navier-Stokes equations can be computationally demanding, especially for high fidelity solutions and varying parameter values. Exploiting intrinsic similarities among parameter-dependent solutions can significantly reduce computational costs.

Reduced Order Modeling (ROM): Techniques like Proper Orthogonal Decomposition (POD) or Dynamic Mode Decomposition (DMD) extract dominant modes from the solution space, enabling the representation of high-dimensional solutions with reduced computational resources.

Transfer Learning and Machine Learning (ML): ML algorithms can learn patterns and correlations between different parameter values from previously solved solutions. Once trained, these models can predict solutions for new parameter values with significantly lower computational cost compared to solving the PDEs directly.

This project combined reduced-basis (RB) methods with a regression-based approach to achieve a complete decoupling of the offline and online stages, enhancing computational efficiency further. The experiments were done on viscous Burgers' equation.

$$u_t + uu_x − \frac{\nu}{50\pi}u_{xx} = 0$$

### Offline Stage:
1. Generate Reduced Basis: Solve the parametrized PDE for a selected set of parameter values spanning the parameter space.
2. Build Regression Model: Train a fully-connected neural network using the solutions obtained in step 1 as input data and corresponding parameter values as output labels.
### Online Stage:
3. Use Reduced Basis: Project the parametrized PDE onto the reduced basis generated in the offline stage.
4. Regression Prediction: Use the trained neural network or regression model to predict the solution corresponding to new parameter values based on the reduced basis coefficients.


Some prediction samples:
![NN_rb_mu=5 0_t=0 51953125](https://github.com/nataliepham6720/ROM_pde/assets/112508461/2e5d111a-e87e-43b5-8b83-54689eaf7d06)

![NN_rb_mu=5 0_t=0 203125](https://github.com/nataliepham6720/ROM_pde/assets/112508461/c6175438-89b9-4799-b83d-37269a279837)


![NN_rb_mu=5 0_t=0 0234375](https://github.com/nataliepham6720/ROM_pde/assets/112508461/fb4c00f8-5f24-4924-9e39-c0e85dbf472f)


