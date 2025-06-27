# ✈️ Aircraft Safety Analysis: Injury Rates by Plane Type

This repository contains a data analysis project focused on understanding serious/fatal injury patterns across different airplane types using cleaned aviation accident data.

---

## 🧹 Data Cleaning & Preprocessing Summary

This section outlines the cleaning and filtering steps taken to ensure the dataset aligns with the client's expectations and is prepared for analysis.

### Aircraft Selection Criteria

1. **Professional Aircraft Only**  
   Filtered the `"Amateur Built"` column to retain only professionally manufactured aircraft.

2. **Modern Aircraft Focus**  
   Removed all aircraft manufactured prior to 1983 to focus the analysis on more recent aviation standards and technology.

3. **Make & Model Integrity**  
   Inspected both `'Make'` and `'Model'` fields, removing any records with missing or blank values to ensure grouping accuracy.

4. **Injury Records Validation**  
   Confirmed that serious and fatal injury fields (`'Total.Fatal.Injuries'`, `'Total.Serious.Injuries'`) contain only valid, positive values when applicable.

5. **Incident Type Filtering**  
   The client is only interested in **accidents**, so all **incidents** were removed from the dataset.  
   Additional validation columns were created to cross-check consistency:
   - `TOTAL_Passengers = Fatal + Serious + Minor + Uninjured`
   - `TOTAL_bad_Injuries = Fatal + Serious`

---

### Injury & Damage Classification

6. **Injury Severity Cleaning**  
   Rows with unavailable or blank values in `'Injury Severity'` were dropped, as these entries had no useful injury information (typically zero or missing values in the injury columns).

7. **Aircraft Damage Standardization**  
   - Blanks in `'Aircraft.damage'` were replaced with `"Unknown"`.  
   - Records marked as `"Unknown"` were retained **only** if they also included serious/fatal injuries. Otherwise, they were removed to avoid ambiguity in injury severity analysis.

---

### Domain-Specific Filtering

8. **Aircraft Category**  
   Only records classified as **"Airplane"** were retained to match the client's scope of interest.

9. **FAR Description Cleanup**  
   The `'FAR Description'` column was cleaned to remove records that were irrelevant to commercial or passenger aviation. Specifically, we excluded:
   - Part 137 agricultural operations (e.g., crop dusters, aerial spraying)
   - Military/ARMF classifications
   - Drones (Part 107)
   - Non-U.S. non-commercial operations
   - Explicitly unknown or ambiguous designations  
   These records do not align with the client's goal of analyzing commercial/passenger airplane safety patterns and were therefore excluded from the analysis.

10. **Injury Rate per Passenger**  
    A new column was calculated to measure the **rate of serious/fatal injuries per passenger**.  
    Records with zero passengers were excluded from the rate calculation but retained in the dataset to support aircraft damage analysis.

11. **Additional Fields Reviewed**  
    Several columns were cleaned and inspected for modeling and visualization purposes, including:
    - `Engine.Type`
    - `Weather.Condition`
    - `Number.of.Engines`
    - `Purpose.of.flight`
    - `Broad.phase.of.flight`

---

## 📊 Analysis Summary

1. **Passenger Size Classification**  
   A binary size label was created to classify aircraft into:
   - `Small` — fewer than 20 passengers
   - `Large` — 20 or more passengers

2. **Key Findings**
   - The rate of fatal/serious injuries in small planes is nearly **twice** that of large planes.
   - 13 large airplane makes had a **0% fatal/serious injury rate** across all recorded accidents.
   - Among large aircraft, the **top 10 makes with non-zero injury rates** are all significantly **below the overall average**.
   - Flights under **IMC (Instrument Meteorological Conditions)** have **nearly 3 times** the fatal/serious injury rate compared to **VMC (Visual Meteorological Conditions)**.
   - Aircraft with **4 engines** and **2 engines** show **higher average injury rates**, while surprisingly, **3-engine aircraft** exhibit a **notably lower** rate of fatal/serious injuries.

---

## 📁 Files

- `airplane_safety_analysis.ipynb`: Main Jupyter notebook with all visualizations and analysis
- `data/`: Contains cleaned and raw CSV files used for modeling
- `README.md`: Project overview and methodology

---

## 👤 Author

Alejandro Silva  
Flatiron School – Data Science Bootcamp  
2025