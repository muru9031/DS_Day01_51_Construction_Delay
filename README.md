# 🏗️ DS_Day01_51: Construction — Why Are Projects Getting Delayed?

**Industry:** Construction and Infrastructure  
**Machine Learning Algorithm:** Random Forest Classifier  

---

## 📌 Project Overview
This project analyzes infrastructure project data (`Project_Size`, `Budget`, `Workforce`, `Material_Delivery`, `Weather`, `Contractor`, `Milestone`, `Planned_Progress`, `Actual_Progress`) to calculate progress gaps, identify operational bottlenecks across project stages, and predict project delays using a **Random Forest** machine learning model.

## 📂 Repository Files
* `DS_Day01_51_Construction_Delay.ipynb` — Complete Jupyter Notebook containing Data Cleaning, EDA, 4 Visualizations, and Random Forest Model Training & Evaluation.
* `construction_projects.csv` — Raw dataset used for analysis.
* `project_delay_visualizations.png` — Exported dashboard of the 4 key visualizations.

---

## 📊 4 Key Visualizations Included in the Notebook
1. **Delay Accumulation Across Project Milestones (Bar Chart):** Identifies which project stages accumulate the highest average progress gap.
2. **Impact of Material Delivery on Project Delay (Box Plot):** Shows the distribution of progress gaps across `On-Time`, `Slight Delay`, and `Severe Delay` material deliveries.
3. **Planned vs. Actual Progress by Project Category (Grouped Bar Chart):** Compares execution performance across Roads, Bridges, Commercial Buildings, Metro, and Water Infrastructure.
4. **Early Warning Indicators (Random Forest Feature Importance Plot):** Highlights the top operational variables predicting major project delays.

---

## 🔍 6 Key Insights
1. **Stage-Wise Delay Accumulation:** Delays peak heavily during the **3_Structural** and **4_MEP_Finishing** milestones, where the average progress gap is significantly higher than in the planning stage.
2. **Critical Impact of Material Delivery:** Projects facing **Severe Material Delays** suffer an average progress gap more than **3x higher** than projects with on-time delivery, making supply chain bottlenecks the #1 cause of delay.
3. **Weather Vulnerability:** Execution under **Stormy and Rainy** conditions causes sharp drops in actual completion rates, particularly during Foundation and Structural stages.
4. **Contractor Performance Disparity:** Projects managed by **Contractor_D and Contractor_C** consistently record larger progress gaps compared to Contractor_A.
5. **Project Category Comparison:** Heavy infrastructure categories (Bridges, Metro, Highways) show consistent gaps between Planned and Actual progress, requiring higher workforce buffers.
6. **Early Warning Indicators (Model Output):** Random Forest feature importance confirms that **Material Delivery Delays**, **Adverse Weather**, **Contractor Selection**, and **Workforce Count** are the strongest early warning indicators of project delay.

---

## 🤖 Random Forest Model Summary
* **Target Variable:** `Is_Delayed` (Binary classification: `1` if `Progress_Gap` exceeds 10%, else `0`)
* **Algorithm:** `RandomForestClassifier(n_estimators=150, max_depth=8, random_state=42)`
* **Evaluation Metrics:** Evaluated using Accuracy Score, Precision, Recall, F1-Score, and Confusion Matrix (detailed outputs available inside the `.ipynb` notebook).

---

## 🛠️ Practical Action Plan
1. **Supply Chain Buffering:** Enforce a mandatory 2-week buffer stock policy for critical structural and MEP materials, with automated vendor SLA alerts before Stage 3 (Structural).
2. **Stage-Gate Audits:** Conduct bi-weekly progress audits during the transition from Foundation to Structural milestones so delays are caught early.
3. **Contractor Tiering & SLA Penalties:** Assign high-budget infrastructure projects to top-performing contractors (Contractor_A & B) and introduce milestone-linked penalty clauses.
4. **Weather-Adaptive Scheduling:** Schedule indoor MEP/Finishing tasks and procurement during monsoon/stormy windows, reserving clear weather periods for excavation and structural work.
5. **Predictive Risk Dashboard:** Use the trained Random Forest model to flag high-risk projects early whenever material delays or workforce shortages occur.
