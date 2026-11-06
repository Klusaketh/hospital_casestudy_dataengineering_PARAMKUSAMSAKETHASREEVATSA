# Hospital Patient Care Analytics Pipeline

An end-to-end data engineering case study for a multi-specialty hospital. The pipeline integrates registration, appointment, lab, wearable, doctor-roster and consultation data, cleans it, checks scheduling against doctor shifts, builds an emergency review queue, and produces patient-level analytics and a dashboard.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

> Uses a synthetic dataset. The risk score is an academic demonstration, not a clinical tool.

## Pipeline

1. **Raw layer** - load 1,000 encounter rows (42 columns, 506 patients)
2. **Data quality checks** - required fields, missing IDs, duplicate encounters
3. **Clean layer** - remove 12 duplicate ingestion records (988 unique encounters), parse timestamps, calculate waiting time and delays
4. **Doctor scheduling** - verify every normal appointment falls inside the assigned doctor's shift
5. **Emergency review** - rank emergencies by triage level and flag cases with no matching working or on-call doctor
6. **Patient analytics** - per-patient visit counts and a transparent risk score with review flags
7. **Dashboard** - waiting time by department, delays, emergency load and doctor workload
8. **Validation** - automated checks that the cleaned data meets pipeline rules
9. **Curated outputs** - clean encounters, patient analytics, emergency queue and doctor workload saved as CSV

## Key Results

| Metric | Value |
|---|---|
| Normal appointments inside the doctor's shift | 843 / 843 |
| Emergency encounters | 145 |
| Matched to a working or on-call doctor | 136 |
| Escalations required | 9 |
| Average waiting time | 31.9 min |
| Average appointment delay | 23.7 min |
| High-risk patients flagged for review | 17 |

The notebook also covers monitoring, security and governance (data freshness, encryption, role-based access).

## Files

| File | Description |
|---|---|
| `PARAMKUSAM_SAKETHA_SREEVATSA_Hospital_Patient_Care_Analytics_Pipeline.ipynb` | Full pipeline notebook with outputs |
| `PARAMKUSAM_SAKETHA_SREEVATSA_Hospital_Patient_Care_Dataset.csv` | Synthetic encounter dataset |
| `PARAMKUSAM_SAKETHA_SREEVATSA_Hospital_Patient_Care_Analytics_Pipeline.docx` | Case study report |

## Run

```bash
pip install pandas numpy matplotlib jupyter
jupyter notebook PARAMKUSAM_SAKETHA_SREEVATSA_Hospital_Patient_Care_Analytics_Pipeline.ipynb
```

## Author

**Paramkusam Saketha Sreevatsa** - [GitHub](https://github.com/Klusaketh) · [LinkedIn](https://www.linkedin.com/in/paramkusamsakethasreevatsa)
