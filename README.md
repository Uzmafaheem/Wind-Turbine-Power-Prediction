# Wind-Turbine-Power-Prediction

## Wind Turbine Power Forecasting Using Attention-Enhanced RNNs

### Project Overview
- Accurate forecasting of wind turbine power output is crucial for renewable energy firms to optimize energy production, schedule maintenance, and manage grid integration. Traditional RNN models often struggle to capture sudden wind pattern changes and long-term dependencies, leading to less reliable predictions.
- This project demonstrates how to integrate an attention mechanism into an RNN to improve prediction accuracy and interpretability. Attention allows the model to focus on critical time steps in historical data, weighing recent or significant fluctuations more heavily, providing insights into which parts of the sequence are most influential.
- 
### Tools and Libraries
 - Python Libraries: numpy, pandas, matplotlib, scikit-learn, tensorflow/keras
 - Key Concepts: RNN, LSTM, Attention Mechanism, Sequence Modeling, Time-Series Forecasting
   
### Build the Attention-Enhanced RNN
- Use the Functional API in Keras to construct the model.
- Add one or more LSTM layers with return_sequences=True for attention.
- Insert Dropout layers to prevent overfitting.
- Implement a custom attention layer that:
      - Computes alignment scores
      - Produces attention weights
      - Generates a context vector for final prediction
      - Add a Dense layer to produce the output
  
### Key Takeaways
- Attention Mechanism: Enables the RNN to dynamically prioritize important time steps, improving prediction accuracy.
- Temporal Understanding: Sequence modeling captures both short-term fluctuations and long-term trends.
- Interpretability: Attention weights offer actionable insights for energy operators.
- Real-World Impact: Enhanced forecasts allow better maintenance scheduling, grid integration, and energy optimization.
- 
### Key insight:
- High Predictive Accuracy
   - The model achieved R² = 0.9665, indicating it explains over 96% of the variance in wind turbine power output.
   - RMSE = 245.61 kW suggests a relatively small average deviation between predicted and actual values, which is impressive given the variability in wind power.

- Attention Mechanism Effectiveness
  - The attention layer allows the model to dynamically focus on the most influential past time steps in the sequence.
  - Visualizations show which time steps the model prioritizes, improving interpretability for operational decisions (e.g., maintenance scheduling, grid management).
- Prediction Anomalies at Zero Output
  - The sample with actual power = 0 kW was predicted as -29.87 kW, highlighting that the model may struggle with edge cases, particularly zero or near-zero outputs.
  - This suggests a need for additional handling of low-power events, such as using a thresholded loss function or augmented training data to cover zero-output periods.

- Training Dynamics
   - The training/validation loss curves (loss: 0.0059, val_loss: 0.0050) indicate stable convergence with minimal overfitting, thanks to dropout and early stopping.
- Overall Impact
     - Integrating attention improves both forecast accuracy and interpretability, enabling data-driven operational decisions.
     - While minor errors exist for extreme low-output periods, the model is robust for predicting typical wind power outputs and can be further refined with additional feature engineering or specialized loss functions.
