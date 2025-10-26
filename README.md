# Individual Differences Database
Large-scale project examining individual differences in cognition and behavior across over a thousand participants. Includes automated pipelines for scoring psychological surveys (ADHD, OCD, anxiety, personality, etc.) and integrating survey data with behavioral task performance.


## Directory Structure

```individual_differences/
├── Survey_Scoring.ipynb            # Main notebook for survey scoring and data integration
└── README.md
```

### `Survey_Scoring.ipynb`

**Data Processing Workflow**  

***Setup and Imports***
- Mounts Google Drive and loads Qualtrics and Prolific exports for each session.
- Filters valid Prolific IDs (24-character alphanumeric).
- Generates hashed participant IDs for anonymity.

***Session Overview Scoring***
- Computes survey duration, start and end timestamps (UTC and localized).
- Uses timezonefinder and pytz to infer local time from geolocation.
- Outputs summary CSVs for each session (S1–S3).

***Survey Scoring Pipelines***

Automated scoring functions for all survey instruments, each saved as a dedicated CSV and tab in a master Excel file:
- ADHD, OCD, Anxiety, BIS, BFI, Grit, AQ, STAI, PSQI
- Maslach and Oldenburg Burnout Inventories
- Coping (BRCS), Alcohol (AUDIT/CUDIT), Social (UCLA, Gallup, Pastimes)
- Readiness, Flow, Imagery, Social Media Use, and others

***Each script:***
- Maps text responses → numeric values
- Handles reverse scoring where applicable
- Computes total, subscale, SD, and blank counts
- Appends question text as secondary column headers

***Export***

All scored outputs are saved both as individual CSVs and merged into an Excel workbook with multiple tabs for each instrument.

---

## Contact Information

For any questions regarding this project, please contact:

**Name:** Sarah Malykke  
**Email:** sarahmalykke@gwu.edu 
