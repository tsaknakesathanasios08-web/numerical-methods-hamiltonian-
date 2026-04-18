# 📊 Numerical Methods for ODEs & Hamiltonian Systems

This repository contains Python implementations of a variety of numerical methods for solving:

* Ordinary Differential Equations (ODEs)
* Hamiltonian systems (e.g. the Kepler problem)

The project focuses on both **classical methods** and **structure-preserving (symplectic) integrators**, along with **convergence and error analysis**.

---

## 🚀 Features

* Clean and modular implementations of numerical schemes
* Support for both standard ODEs and Hamiltonian systems
* Includes **symplectic integrators** for long-time stability
* Built-in tools for:

  * Energy error analysis
  * Angular momentum conservation
  * Experimental Order of Convergence (EOC)

---

## 📦 Implemented Methods

### 🔹 Explicit Methods

* Explicit Euler

### 🔹 Implicit Methods

* Implicit Euler
* Implicit Midpoint Method

### 🔹 Symplectic Methods

* Symplectic Euler A
* Symplectic Euler B

### 🔹 Störmer–Verlet Methods

* Störmer–Verlet A
* Störmer–Verlet B

### 🔹 Runge–Kutta Type Methods

* Gauss–Legendre (4th order)
* Gauss–Legendre (6th order)

### 🔹 Lobatto Methods

* Lobatto IIIA–IIIB
* Lobatto IIIB–IIIA

---

## ⚙️ Requirements

```bash
pip install numpy scipy matplotlib
```

---

## 🧑‍💻 Usage

Each method follows a unified interface:

```python
tnodes, yvals = method(f, t0, T, y0, N)
```

### Parameters

* `f` : function defining the system
* `t0` : initial time
* `T` : final time
* `y0` : initial condition
* `N` : number of time steps

### Returns

* `tnodes` : time grid
* `yvals` : numerical solution

---

## 🧪 Example: Kepler Problem

```python
import numpy as np

def f_kepler(q, p):
    return p

def g_kepler(q, p):
    r = np.sqrt(q[0]**2 + q[1]**2)
    return -q / r**3
```

This example is useful for testing **energy conservation** and **long-term stability** of symplectic methods.

---

## 📈 Convergence Analysis

The repository includes tools to evaluate:

* Energy error
* Angular momentum error
* Experimental Order of Convergence (EOC)

### Example Output

```
EOC from N=1000 to N=2000: 1.000000
```

---

## 📁 Project Structure

```
.
├── explicit_euler.py
├── implicit_euler.py
├── symplectic_methods.py
├── verlet_methods.py
├── gauss_legendre.py
├── lobatto_methods.py
├── convergence_tests.py
└── README.md
```

---

## 📌 Notes

* Implicit methods use `scipy.optimize.fsolve` to solve nonlinear systems
* Symplectic integrators are ideal for **long-time simulations** of Hamiltonian systems
* Energy preservation is a key metric for evaluating performance

---

## 🎓 Use Cases

* Computational Physics
* Numerical Analysis courses
* Research experiments
* Method comparison studies

---

## 📜 License

This project is open-source and free to use for educational and research purposes.

---

## 👨‍💻 Author

Created as part of numerical analysis studies.

