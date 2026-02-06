# SIRAH Protein Molecular Dynamics Simulation 🧬💻

This repository contains an **ongoing molecular dynamics (MD) simulation project of a protein using the SIRAH coarse-grained force field** with **GROMACS**.

The project is focused on **learning, implementing, and validating the SIRAH force field workflow** for protein simulations, including coarse-graining, solvation, ion addition, equilibration, and production MD.

> ⚠️ Status: **Ongoing / Learning Project**

---

## 🧠 Project Objective

- To understand and implement **protein MD simulations using the SIRAH force field**
- To learn the **coarse-graining workflow** for proteins
- To perform **energy minimization, equilibration, and production runs**
- To analyze system stability and behavior at the coarse-grained level

---

## 🔬 System Details

- **Protein:** 1CRN (Crambin)
- **Force Field:** SIRAH Coarse-Grained Force Field
- **Simulation Engine:** GROMACS
- **Solvent Model:** WT4 (SIRAH water model)

---

## 📁 Repository Contents

### 🔹 Input & Structure Files
- `1CRN.pqr`  
  → Prepared atomistic protein structure

- `1CRN_CG.pdb`  
  → Coarse-grained protein structure

- `protein.gro`  
  → CG protein converted to GROMACS format

---

### 🔹 Solvation & System Setup
- `WT4.gro`  
  → SIRAH water model

- `boxed.gro`  
  → Protein placed in simulation box

- `solvated.gro`  
  → Protein solvated with WT4 water

---

### 🔹 Topology & Restraints
- `topol.top`  
  → System topology file

- `posre.itp`  
  → Position restraints for protein

---

### 🔹 Simulation Parameters
- `ions.mdp`  
  → Parameters for ion addition

- `mdout.mdp`  
  → MD run parameters (equilibration / production)

---

## ⚙️ Simulation Workflow

1. **Protein preparation**
   - Atomistic structure preprocessing
   - Conversion to coarse-grained representation

2. **Topology generation**
   - SIRAH-compatible topology and restraints

3. **Box definition & solvation**
   - WT4 water model
   - Periodic boundary conditions

4. **Ion addition**
   - Charge neutralization

5. **Energy minimization**
6. **Equilibration**
7. **Production MD** *(in progress)*

---

## 🚀 How to Run (Example)

```bash
gmx grompp -f ions.mdp -c solvated.gro -p topol.top -o ions.tpr
gmx mdrun -deffnm ions
