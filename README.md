# Semester_Project
Modeling Inter- and Intra-Driver Heterogeneity in Human Car-Following Simulation

# Introduction 

This repository implements several existing modela and propoese a Time-Varying Autoregressive (TV-AR) model for capturing behavioral heterogeneity in car-following simulation. Compared to traditional Intelligent Driver Models (IDM) and its variants, our approach better represents both:

- **Inter-driver heterogeneity**: Behavioral differences between drivers
- **Intra-driver heterogeneity**: Dynamic behavioral adaptations to changing environments

The TV-AR model provides improved accuracy in simulating realistic driver behaviors while addressing limitations of existing approaches.

# Repository Structure

## Data Processing
**File path**: `Data_processing/` Loads and preprocesses vehicle trajectory data from CSV files, performing data cleaning, downsampling, and extraction of car-following pairs. 
## Basic IDM  
**File path**: `Basic_IDM/` Implements the standard Intelligent Driver Model with enhanced multi-start calibration, comprehensive validation.
## Hierarchical IDM
**File path**: `Hierarchical_IDM/` Implements a Bayesian hierarchical IDM with LKJ prior for modeling inter-driver heterogeneity, capturing individual driving styles through vehicle-specific parameter distributions. 
## AR Model
**File path**: `AR/`  Extends the hierarchical IDM with individual autoregressive components for each vehicle, capturing short-term behavioral dependencies and temporal correlations in driving behavior.
## TV-AR Model  
**File path**: `TV-AR/`The proposed core model featuring time-varying autoregressive coefficients that evolve via block-wise random walk processes, capturing both inter-driver heterogeneity and intra-driver adaptation to changing environments.
## AR Sliding Window
**File path**: `AR_Sliding_Window/` Implements a sliding window variant of the AR model that estimates time-varying parameters by fitting the model to overlapping temporal segments, enabling analysis of parameter evolution and temporal stability.
## Short-term Simulation
**File path**: `Short_term_simulation/` Evaluates model performance on short-term (20-second) driving segments, providing robust validation through multiple temporal windows and assessing model stability across different driving scenarios.
## Long-term Simulation  
**File path**: `Long_term_simulation/` Simulates macroscopic traffic flow dynamics using ring-road scenarios over extended time periods (6000 timesteps), evaluating fundamental diagrams and emergent traffic phenomena at the system level.


# How to run 
We calibrate our data on Open ACC dataset (https://data.jrc.ec.europa.eu/dataset/9702c950-c80f-4d2f-982f-44d06ea0009f). Download the data on the website and open `Data_processing/`, file_path is where the raw data stored. Run this code and then the processed data is called "ar_idm_data". This data can be used for all four models (Basic IDM, Hierarchical IDM, AR Model, TV-AR Model). After calibration and validation, the trace gotten from each model is needed to run Short-term Simulation and Long-term Simulation.

# Prer









