
# Hamiltonian Systems & Symplectic Integrators

Python implementations of numerical methods for solving **ordinary differential equations (ODEs)** and **Hamiltonian dynamical systems**, with emphasis on **structure-preserving (symplectic) integrators** and long-time stability.

---

## 📖 Overview

Hamiltonian systems arise naturally in physics and are governed by conservation laws such as **energy** and **angular momentum**. Standard numerical methods often fail to preserve these properties over long time intervals.

This project focuses on geometric numerical integration techniques that preserve the qualitative behavior of such systems.

Built on concepts from Hamiltonian Mechanics and Numerical Analysis.

---

## ⚙️ Implemented Methods

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

## 🧪 Example: Kepler Problem

We consider the classical two-body Kepler problem:

```python
def f_kepler(q, p):
    return p

def g_kepler(q, p):
    r = np.sqrt(q[0]**2 + q[1]**2)
    return -q / r**3
```

---

## 📊 Key Results

### Energy Behavior

![Image](https://images.openai.com/static-rsc-4/eQ_nOnadYPMEz5MFHTHdPnxhVyYUiLyGabyMxyBht9Ozr2tR3zR2DneYA3GuqI1Zr9AUr-EWyaO2x_bUXEmHLJ88WDF-NGWHnpb3ysxjqGgn3rYcezssDQSvSUa0ODkqboUEGStPW666md9KpURc_Aj6pZJEZeKPMo0qIm2Ge0n-mhVYCTM6vMwWuIDCA_Lt?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/hCB_DUnwqZOARFaeeefvcf5AXkhbsbOKBswoC4oCCD0CSJrVBmKobDWq2Kb-LVGk653EBVuYOBriYX_WYdDSJ84R9XguWgc6pcFZlXtnbRx7E0nMw5CDUKP1l1WCuRXxwfUq2VM3lxV1dzC4hukXwVxr1ukEzngvqLLm0ACSBfStiCJAXiBTzbLyELGmZUOr?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/aLUH1yI1_47gouBfYVjEeGsDLSrAi6O-OEnR4XRrPkbP7GGm8oxVNMIRGpo1Nj2o89SpkA4PNdDW-vaBMls-4qTB31EqqGQzBmHSTMizHb_eXojy1iXpvZHIpfHpZOSPyt97f12ColaJGlOVG_GX3T9xr1kT192m88mW2dcbnjP8wxE-nzWICgnUQVa7d2bm?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/4Kk9eUQJvW4mYXoUJaYyndKWojp381iagbsoneYt1thLYpoi18C3BoyhvIFrMe5Avk-tlqmXQOeXjqntkMPnDJTQJzwNlIi79H0rjTHgwfJimQE_oaSNbhyojqsKRsae8UlcIS0TCj_mE51YVj59bQpL9trfjcsgONiqX2J-V0eiCDfHGoSZJEvpdXY75vr0?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/O6kjE178kprV1C-tHmASXE7IYMVrny-AcM903NPOBe0Xt-HgqAzzRXPvZF2kYc8u_ARe5nLiPuW8k_U0DekB6EHH9Vsj9-0cIA0j9uAu6gQIFJpfW2JuK6kPlx_qv3xZi3LjvvBDM-p4Hbg-X5CDuUgCiEQfbqtTfXySJpSMFhaE80IhLE7ylF4cFuxZ9yTK?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/e44MXsk3huTaCe4Q24OSkqEjaD-iHkGwVlPHoXhBBEA673aoHs6COQm6-ODzLYWjCtFWA7Pt3DLi43om2BnKK5uYPou66QUaWsSOHAWMVAa-RQfpu54vn2JK2PHNlKKTCTz69PQLTxn343gW5HCuMbCFz0g8i_94Zw4flEODLCyF9xLwxhMIM2hVV_oObOP3?purpose=fullsize)

* Explicit Euler → energy **drifts** over time
* Implicit methods → artificial **damping**
* Symplectic methods → **bounded oscillations**

---

### Orbit Simulation

![Image](https://images.openai.com/static-rsc-4/eQ_nOnadYPMEz5MFHTHdPnxhVyYUiLyGabyMxyBht9Ozr2tR3zR2DneYA3GuqI1Zr9AUr-EWyaO2x_bUXEmHLJ88WDF-NGWHnpb3ysxjqGgn3rYcezssDQSvSUa0ODkqboUEGStPW666md9KpURc_Aj6pZJEZeKPMo0qIm2Ge0n-mhVYCTM6vMwWuIDCA_Lt?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/oqMXabZOi1hPU2ZLsc4Hugw9N5cJbb7kB1un6cpJu7jOjTRn7vqBPXIjT-lefzqf2u7NvP3XUSm57Yv_Xive2-Vso8OlpsmQNw9J3EwCzdkuI8hiFAyXXPkmO4OqiaxLlcRWZfmD16FtrJTQ00xnAqMIgm6QWftQMoYOchtAJ3jq0_P-6R27W5RvzQkNmb3D?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/aLUH1yI1_47gouBfYVjEeGsDLSrAi6O-OEnR4XRrPkbP7GGm8oxVNMIRGpo1Nj2o89SpkA4PNdDW-vaBMls-4qTB31EqqGQzBmHSTMizHb_eXojy1iXpvZHIpfHpZOSPyt97f12ColaJGlOVG_GX3T9xr1kT192m88mW2dcbnjP8wxE-nzWICgnUQVa7d2bm?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/U5VdqVJ4_4BToJRrvjKV5wznhYYqrVOQI6VDxEtdcjo1_E0iKg8RclTFSd-IsEoCrVGN16GGekIgbeBhtYSq11f8EZg_CGJ5I3Zc7yNeG-E2pT41jzOoLUk5blEoC4YMbj3T5gesWJuKgno88izfQMpJU0ui5cYi5MuW6gPjyy9TIpbpe_VWWjJr-U4DGwJE?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/O6kjE178kprV1C-tHmASXE7IYMVrny-AcM903NPOBe0Xt-HgqAzzRXPvZF2kYc8u_ARe5nLiPuW8k_U0DekB6EHH9Vsj9-0cIA0j9uAu6gQIFJpfW2JuK6kPlx_qv3xZi3LjvvBDM-p4Hbg-X5CDuUgCiEQfbqtTfXySJpSMFhaE80IhLE7ylF4cFuxZ9yTK?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/YqSCWMVXy1wnbDF8YinjJJmY11hW-4zauzfV7FVMBmaqatvFW1DUrypOjpDOvCNQjaU8GVazFUQqc9S-NH7cUl5k8SiP0RordTOxvTVHD3FWC2Sqdg9iZec2SB4PW9OMuv59eOtXOuCJZM6NuhtyLi5rKBTrFtQqmDOEoN_0gALrkD4L1Y18Dvz8E-ZxbioZ?purpose=fullsize)

* Symplectic integrators preserve orbital structure
* Non-symplectic methods distort trajectories

---

## 📈 Convergence Analysis

For each method, we compute:

* Energy error
* Angular momentum error
* Experimental Order of Convergence (EOC)

Example:

```
EOC from N=1000 to N=2000: 1.000000
```

---

## 🧠 Key Insights

* Standard methods approximate trajectories but distort invariants
* Symplectic methods preserve the **geometric structure**
* Energy is not exactly conserved, but remains **bounded and oscillatory**
* Long-time simulations are significantly more reliable with symplectic schemes

---

## 🚀 Usage

All methods follow the same interface:

```python
tnodes, yvals = method(f, t0, T, y0, N)
```

### Parameters:

* `f`: system function
* `t0`: initial time
* `T`: final time
* `y0`: initial condition
* `N`: number of time steps

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
├── docs/
│   ├── thesis.pdf
│   └── code_reference.pdf
└── README.md
```

---

## 📦 Requirements

```bash
pip install numpy scipy matplotlib
```

---

## 🔬 Mathematical Background

The dynamics are governed by Hamilton’s equations:

$$
\frac{dq}{dt} = \nabla_p H, \quad \frac{dp}{dt} = -\nabla_q H
$$

Symplectic integrators preserve the phase-space structure and are crucial for long-time integration.

---

## 🎯 Applications

* Computational physics
* Celestial mechanics
* Dynamical systems
* Numerical analysis research

---

## 📌 Notes

* Implicit methods are solved using `scipy.optimize.fsolve`
* Symplectic methods are preferred for long-time simulations
* Energy preservation is a key performance indicator

---

## 📜 License

This project is open-source and available for educational and research use.

---

## 👨‍💻 Author

Developed as part of a Master’s thesis on numerical methods for Hamiltonian systems.
