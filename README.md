# stark-soil-intelligence
Abstract: ML pipeline screening Materials Project for novel gate dielectric candidates optimized for ultra-low-power agricultural sensors. Identifies rare earth trifluorides (DyF3, YF3) with 3x higher dielectric constant than SiO2 and superior humidity stability. Foundation for the Stark Soil Node analog intelligence system.

# Rare Earth Materials Discovery Pipeline 🧪💻

This repository contains an automated discovery pipeline for next-generation **low-power semiconductors** and **gate dielectrics**. By leveraging the Materials Project API and Machine Learning, this tool accelerates the search for materials suitable for sensitive environments, such as agricultural soil sensors.

## 🌟 Research Objective
The goal is to identify materials that are not only electronically superior (specific band gaps) but also **environmentally robust** (non-toxic and moisture-resistant) and **economically viable** (Earth-abundant).

## 🚀 Key Features

### 1. Multi-Dimensional Screening
The pipeline filters through thousands of compounds based on:
*   **Electronic Properties:** Targeted band gap ranges for semiconductors (0.5–2.5 eV) and dielectrics (>4.0 eV).
*   **Stability Metrics:** Filters for low "Energy Above Hull" (≤ 0.05 eV/atom) to ensure the materials can actually be synthesized.
*   **Environmental Safety:** A custom blacklist automatically removes compounds containing toxic elements like Lead (Pb), Arsenic (As), and Thallium (Tl).

### 2. Custom Figure of Merit (FOM) Logic
Materials are ranked by a weighted scoring algorithm:
*   **Performance:** Proximity to the ideal band gap for the specific application.
*   **Thermodynamics:** Magnitude of formation energy (chemical "toughness").
*   **Abundance:** Integration of Earth-abundance scores to prioritize sustainable materials.

### 3. Machine Learning Novelty Detection
Using **Scikit-Learn’s One-Class Support Vector Machine (SVM)**, the script builds a baseline of the chemical "norm" from 4,000+ materials. It then flags candidates that are statistically unusual, helping researchers find "outlier" materials that traditional search methods might miss.

### 4. Humidity Stability Analysis
A specialized module for agricultural applications. It compares the formation energy of **Fluorides** against **Hydroxides** to predict which materials will resist degradation when exposed to moisture or humidity.

---

## 🛠️ Technical Stack
*   **Data Source:** [Materials Project API (MP-API)](https://materialsproject.org/)
*   **Language:** Python 3.10+
*   **Data Science:** `Pandas`, `NumPy`
*   **Machine Learning:** `Scikit-Learn` (StandardScaler, OneClassSVM)
*   **Environment:** `python-dotenv` for secure API key management

---

## 📁 Repository Structure
*   `Materials Project 2 Main Text.py`: The primary analysis engine.
*   `.env`: Secure storage for API credentials (ignored by Git).
*   `.gitignore`: Prevents sensitive keys and local data exports from being uploaded.
*   **Data Exports:** 
    *   `semiconductor_candidates.csv`
    *   `dielectric_candidates.csv`
    *   `novel_dielectric_candidates.csv`

---

## 📈 Current Results
As of the latest run, the pipeline identifies **Rare Earth Trifluorides** (such as DyF3 and TbF3) as premier candidates for gate dielectrics due to their massive band gaps (≈ 7.7 eV) and high resistance to hydration.

---

## ⚖️ License
This project is open-source. Please credit the Materials Project for data sourcing.
