

numerical-methods-hamiltonian-
Repository navigation
Code
Issues
Pull requests
Python code and numerical experiments for simulating Hamiltonian dynamical systems using geometric and symplectic integrators. Includes implementations of classical and high‑order methods, along with detailed convergence studies for several benchmark problems.

 1 star
 0 forks
 0 watching
 1 Branch
 0 Tags
 Activity
Public repository
tsaknakesathanasios08-web/numerical-methods-hamiltonian-
Name	
tsaknakesathanasios08-web
tsaknakesathanasios08-web
3 days ago
README.md
3 days ago
numerical_results_in_hamiltonian_intinial_value_problems (5).pdf
5 days ago
python_codes (2).pdf
5 days ago
Repository files navigation
README
Numerical Methods for ODEs & Hamiltonian Systems
This repository contains Python implementations of various numerical methods for solving:

Ordinary Differential Equations (ODEs)
Hamiltonian systems (e.g. Kepler problem)
The focus is on both classical and structure-preserving (symplectic) methods, along with convergence and error analysis.

📦 Implemented Methods
🔹 Explicit Methods
Explicit Euler
🔹 Implicit Methods
Implicit Euler
Implicit Midpoint Method
🔹 Symplectic Methods
Symplectic Euler A
Symplectic Euler B
🔹 Störmer–Verlet Methods
Störmer–Verlet A
Störmer–Verlet B
🔹 Runge-Kutta Type Methods
Gauss–Legendre (4th order)
Gauss–Legendre (6th order)
🔹 Lobatto Methods
Lobatto IIIA–IIIB
Lobatto IIIB–IIIA
⚙️ Requirements
Make sure you have the following Python libraries installed:

pip install numpy scipy matplotlib
🚀 Usage
Each method is implemented as a Python function with the general structure:

tnodes, yvals = method(f, t0, T, y0, N)
Parameters:
f: function defining the system
t0: initial time
T: final time
y0: initial condition
N: number of time steps
Output:
tnodes: time grid
yvals: numerical solution
🧪 Example: Kepler Problem
The repository includes simulations of the Kepler problem, a classical Hamiltonian system:

def f_kepler(q, p):
    return p

def g_kepler(q, p):
    r = np.sqrt(q[0]**2 + q[1]**2)
    return -q / r**3
📊 Convergence Analysis
For each method, the following quantities are evaluated:

Energy error
Angular momentum error
Experimental Order of Convergence (EOC)
Example output:

EOC from N=1000 to N=2000: 1.000000
🎯 Key Features
Clean implementations of many classical numerical schemes

Focus on structure-preserving integrators

Includes error analysis and convergence tests

Suitable for:

Computational physics
Numerical analysis courses
Research experiments
📁 Structure
.
├── explicit_euler.py
├── implicit_euler.py
├── symplectic_methods.py
├── verlet_methods.py
├── gauss_legendre.py
├── lobatto_methods.py
├── convergence_tests.py
└── README.md
📌 Notes
Implicit methods use scipy.optimize.fsolve to solve nonlinear systems.
Symplectic methods are especially suitable for long-time integration of Hamiltonian systems.
Energy preservation is a key metric for evaluating performance.
📜 License
This project is open-source and free to use for educational and research purposes.

👨‍💻 Author
Created as part of numerical analysis studies
