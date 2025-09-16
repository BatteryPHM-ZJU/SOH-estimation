# Battery cycling aging dataset

## Description

This dataset contains cycling charge and discharge data for 24 NCM-18650 lithium-ion batteries, covering the entire lifespan of the batteries until their State of Health (SOH) degrades to 80%. The nominal capacity of the batteries is 1250mAh. This dataset can be used for battery SOH estimation, Remaining Useful Life (RUL) prediction, State of Charge (SOC) estimation, and other related research.

## Data Source

This dataset is derived from experimental data collected for a research paper currently under review. The paper is titled "A Generalized MSET Framework with Integrated Weight Optimization for Accurate Lithium-ion Battery SOH Estimation" and is authored by Gaochao Wu, et al.  If you use this dataset, we kindly request that you acknowledge its origin and consider contacting the author (gaucho@zju.edu.cn) for updates on the paper's publication status.  Once the paper is published, we will update this information with the complete citation details.

**This release includes only the first 10 cycles of charge/discharge data for each battery.**  A full dataset is planned for public release if the related research finding is accepted for publication.

## Dataset Contents

### Process Information

*   **Charging Process:** Constant Current Constant Voltage (CC-CV Charge)
*   **Discharging Process:**
    *   8 Batteries: Constant Current Discharge (CC Discharge)
    *   8 Batteries: Dynamic Stress Test (DST)
    *   8 Batteries: Random Current Discharge (RC Discharge)
        *   The discharge current follows a discrete normal distribution.

### Environmental Information

Experiments were conducted in a 25-degree Celsius constant temperature chamber.

### Data Format

The dataset is stored in JSON format.

### Data Structure

Each JSON file contains the complete cycling data for one battery. The data structure is as follows:

```json
{
    "data": {
        "Charge_001": {
            "Cycle_ID": 1,
            "Type": "CC-CV Charge",
            "Summary_Info": {
                "Energy_Wh": 5.08225,
                "Q_Ah": 1.25394
            },
            "Record_Info": {
                "Current_A": [1.4996, 1.5001, 1.5001, ...],
                "Voltage_V": [2.9565, 3.0067, 3.0452, ...],
                "Q_Ah": [0.0, 0.0004, 0.0008, ...],
                "Temp_C": [25.8, 25.8, 25.8, ...]
            }
        },
        "Discharge_001": {
            "Cycle_ID": 1,
            "Type": "CC Discharge",
            "Summary_Info": {...}
            "Record_Info": {...}
        },
        // ... more cycle info
    }
}
```

## Contact

If you have any questions or suggestions, please contact gaucho@zju.edu.cn
