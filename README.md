# UAV Assignment - Semester A3

This repository contains coursework for UAV design and analysis, organized into two main questions with airfoil analysis and conceptual vehicle sizing, the video uploaded in the google drive is to show everything was assembled that doesnt compel to say that thats my final results, here submitted ones in github are the final ones

## Project Structure

```
UAV-A3/
├── q1/                          # Question 1: Airfoil Analysis
│   ├── CLARKE-Y/                # Clarke-Y Airfoil Analysis
│   │   ├── CLARKEY.ipynb        # Jupyter notebook with analysis
│   │   ├── clarkey.xfl          # XFoil airfoil definition file
│   │   ├── clarky.dat           # Airfoil coordinate data file
│   │   ├── CLARK Y_T1-20_0 m_s-VLM1.txt   # Aerodynamic data (20 m/s)
│   │   ├── 2d_op.png            # 2D operating point plot
│   │   ├── 2d_polar.png         # 2D polar diagram (Cl vs Cd)
│   │   ├── 3d_op.png            # 3D operating point visualization
│   │   ├── 3d_polar.png         # 3D polar diagram
│   │   └── wing.png             # Wing geometry visualization
│   ├── EE334/                   # EE334 Airfoil Analysis
│   │   ├── EE334.ipynb          # Jupyter notebook with analysis
│   │   ├── ee334.xfl            # XFoil airfoil definition file
│   │   ├── E334.dat             # Airfoil coordinate data file
│   │   ├── EE334_T1-20_0 m_s-VLM1.txt     # Aerodynamic data (20 m/s)
│   │   ├── 2d_polar.png         # 2D polar diagram (Cl vs Cd)
│   │   ├── 2s_op.png            # 2D operating point plot
│   │   ├── 3d_op.png            # 3D operating point visualization
│   │   ├── 3d_polar.png         # 3D polar diagram
│   │   └── wing.png             # Wing geometry visualization
│   ├── MH60/                    # MH60 Airfoil Analysis
│   │   ├── MH60.ipynb           # Jupyter notebook with analysis
│   │   ├── MH60.xfl             # XFoil airfoil definition file
│   │   ├── mh60.dat             # Airfoil coordinate data file
│   │   ├── MH60_T1-20_0 m_s-VLM1.txt      # Aerodynamic data (20 m/s)
│   │   ├── 2d_op.png            # 2D operating point plot
│   │   ├── 2d_polar.png         # 2D polar diagram (Cl vs Cd)
│   │   ├── 3d_op.png            # 3D operating point visualization
│   │   ├── 3d_polar.png         # 3D polar diagram
│   │   └── wing.png             # Wing geometry visualization
│   └── NACA4415/                # NACA 4415 Airfoil Analysis
│       ├── NACA4415.ipynb       # Jupyter notebook with analysis
│       ├── NACA4415.xfl         # XFoil airfoil definition file
│       ├── NACA4115.dat         # Airfoil coordinate data file
│       ├── NACA4415_T1-20_0 m_s-VLM1.txt  # Aerodynamic data (20 m/s)
│       ├── 2d_op.png            # 2D operating point plot
│       ├── 2d_polar.png         # 2D polar diagram (Cl vs Cd)
│       ├── 3d_op.png            # 3D operating point visualization
│       ├── 3d_polar.png         # 3D polar diagram
│       └── wing.png             # Wing geometry visualization
└── q2/                          # Question 2: UAV Conceptual Sizing
    └── 1.ipynb                  # UAV design sizing analysis notebook
```

## Question 1: Airfoil Analysis (q1/)

This section analyzes four different airfoil profiles at a cruise speed of **20 m/s**. Each airfoil is compared based on:

### Airfoils Analyzed
- **CLARKE-Y**: A semi-symmetrical airfoil, popular for general aviation
- **EE334**: A high-performance airfoil suitable for efficiency-focused designs
- **MH60**: A medium-performance airfoil with good low-speed characteristics
- **NACA4415**: A cambered airfoil with moderate thickness, commonly used in UAV designs

### Files in Each Airfoil Folder

1. **Jupyter Notebook (.ipynb)**
   - Reads aerodynamic data from the corresponding .txt file
   - Calculates performance parameters:
     - Lift Coefficient (C_L)
     - Aerodynamic Efficiency (C_L/C_D)
     - Endurance Parameter (C_L^1.5/C_D)
     - Pitching Moment (C_M)
   - Generates 4-panel performance plots

2. **XFoil File (.xfl)**
   - XFoil airfoil format definition
   - Contains geometric profile coordinates
   - Used for aerodynamic simulations

3. **Airfoil Data File (.dat)**
   - Coordinate data file for the airfoil profile
   - Contains x/c (normalized chord position) and y/c (normalized height) coordinates
   - Used by aerodynamic analysis tools

4. **Aerodynamic Data (.txt)**
   - Raw performance data from VLM (Vortex Lattice Method) simulations
   - Contains angle of attack vs. aerodynamic coefficients
   - Naming convention: `[AIRFOIL]_T1-20_0 m_s-VLM1.txt`
   - Columns typically include:
     - α (Angle of Attack in degrees)
     - C_L (Lift Coefficient)
     - C_D (Drag Coefficient)
     - C_M (Pitching Moment Coefficient)

5. **Performance Visualizations (PNG Images)**
   - **2d_op.png**: 2D operating point plot showing aerodynamic coefficients across angle of attack range
   - **2d_polar.png**: 2D polar diagram displaying the relationship between lift and drag coefficients
   - **3d_op.png**: 3D operating point visualization for enhanced spatial representation
   - **3d_polar.png**: 3D polar diagram showing performance characteristics
   - **wing.png**: Wing geometry and planform visualization

## Question 2: UAV Conceptual Sizing (q2/)

This section contains a comprehensive UAV design sizing tool.

### Contents

**1.ipynb** - UAV Conceptual Sizer
- Implements the UAVConceptualSizer class
- Mission requirements definition:
  - Payload: 10 kg
  - Cruise speed: 25 m/s
  - Endurance: 5 hours
  - Operating altitude: 500 m
- Design calculations including:
  - Wing loading estimation
  - Aspect ratio optimization
  - Maximum lift coefficient analysis
  - Aerodynamic efficiency targets
  - Power requirements and propulsion selection
- Propulsion efficiency parameters:
  - Motor efficiency: 85%
  - Propeller efficiency: 80%
  - ESC (Electronic Speed Controller) efficiency: 95%

## How to Use

### Prerequisites
- Python 3.7+
- Required libraries:
  ```
  pandas
  matplotlib
  numpy
  ```

### Running Airfoil Analysis (Q1)

1. Navigate to any airfoil folder (e.g., `q1/NACA4415/`)
2. Open the corresponding Jupyter notebook (e.g., `NACA4415.ipynb`)
3. Run all cells to:
   - Load aerodynamic data
   - Calculate performance metrics
   - Display comparison plots

**Example Output:**
- Performance data table with α, C_L, C_L/C_D, C_L^1.5/C_D, C_M
- 2×2 subplot figure showing performance parameters vs. angle of attack

### Running UAV Sizing (Q2)

1. Open `q2/1.ipynb`
2. Execute the notebook to:
   - Initialize design parameters
   - Calculate required wing area, mass breakdown
   - Determine power and propulsion specifications
   - Generate design summary

## Data Interpretation

### Key Aerodynamic Coefficients
- **C_L (Lift Coefficient)**: Measures lift generation capability
- **C_D (Drag Coefficient)**: Measures aerodynamic drag
- **C_L/C_D**: Aerodynamic efficiency (higher is better for cruise)
- **C_L^1.5/C_D**: Endurance metric (indicates loiter performance)
- **C_M (Pitching Moment)**: Indicates longitudinal stability

### Design Criteria
- **Best Efficiency Airfoil**: Compare C_L/C_D values across all airfoils
- **Best Endurance Airfoil**: Compare C_L^1.5/C_D values (important for long-duration flight)
- **Stall Characteristics**: Observe behavior at high angles of attack

## Notes

- All aerodynamic data is computed at **20 m/s** airspeed
- XFoil format files can be imported into specialized aerodynamic analysis software
- The UAV sizing tool uses standard atmospheric models for altitude effects
- Performance calculations assume steady, level flight conditions

## Related Tools
- **XFoil**: For airfoil aerodynamic analysis
- **Jupyter Notebook**: For interactive analysis and visualization
- **Pandas & Matplotlib**: For data processing and plotting

