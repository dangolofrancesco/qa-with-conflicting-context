# Reproducibility Log

**Project:** QA with Conflicting Context  
**Researcher:** Francesco Dangolo & Romain Salvi 
**Start Date:** November 7, 2025  
**Repository:** dangolofrancesco/qa-with-conflicting-context

---

## Executive Summary
This log tracks all attempts to reproduce the results from the original project, including hardware specifications, time investments, successes, and challenges encountered.

---

## Hardware Configuration

### GPU Information
- **GPU Model:** _[e.g., Google Colab T4, NVIDIA A100, RTX 3090, etc.]_
- **GPU Memory:** _[e.g., 16GB, 40GB, etc.]_
- **Number of GPUs:** _[e.g., 1, 2, 4, etc.]_
- **CPU:** _[e.g., Intel Xeon, AMD EPYC, etc.]_
- **RAM:** _[e.g., 32GB, 64GB, etc.]_
- **Storage:** _[e.g., 500GB SSD, etc.]_
- **Platform:** _[e.g., Local Machine, Google Colab, AWS, Azure, etc.]_

---

## Time Tracking

### Total GPU Hours
| Date | Experiment/Task | GPU Hours | Notes |
|------|----------------|-----------|-------|
| _YYYY-MM-DD_ | _Description_ | _X.X hrs_ | _Additional notes_ |
| | | | |
| | | | |
| **TOTAL** | | **0.0 hrs** | |

### Wall-Clock Time (Total Human Time Invested)
- **Setup & Environment:** _X hours_
- **Data Preparation:** _X hours_
- **Training Experiments:** _X hours_
- **Evaluation:** _X hours_
- **Debugging:** _X hours_
- **Documentation:** _X hours_
- **TOTAL:** _X hours_

---

## Experiments Log

### Experiment 1: [Name/Description]
- **Date Started:** _YYYY-MM-DD HH:MM_
- **Date Completed:** _YYYY-MM-DD HH:MM_
- **Duration (Wall-Clock):** _X hours Y minutes_
- **GPU Hours:** _X.X hours_
- **Objective:** _What were you trying to reproduce/achieve?_
- **Configuration:**
  - Model: _[e.g., Phi-3, etc.]_
  - Dataset: _[e.g., ConflictQA, etc.]_
  - Hyperparameters:
    - Learning rate: _X_
    - Batch size: _X_
    - Epochs: _X_
    - Other parameters: _..._
- **Command/Script Used:**
  ```bash
  # Copy the exact command here
  ```
- **Results:**
  - Metrics: _[e.g., Accuracy: X%, F1: X%, etc.]_
  - Expected vs. Actual: _Compare to paper results_
- **Status:** ✅ Success / ⚠️ Partial / ❌ Failed
- **Notes:** _Any observations_

---

### Experiment 2: [Name/Description]
- **Date Started:** _YYYY-MM-DD HH:MM_
- **Date Completed:** _YYYY-MM-DD HH:MM_
- **Duration (Wall-Clock):** _X hours Y minutes_
- **GPU Hours:** _X.X hours_
- **Objective:** _What were you trying to reproduce/achieve?_
- **Configuration:**
  - _Details..._
- **Command/Script Used:**
  ```bash
  # Command here
  ```
- **Results:**
  - _Results here_
- **Status:** ✅ Success / ⚠️ Partial / ❌ Failed
- **Notes:** _Any observations_

---

## Problems Encountered

### Issue 1: [Brief Description]
- **Date:** _YYYY-MM-DD_
- **Severity:** 🔴 Critical / 🟡 Moderate / 🟢 Minor
- **Component:** _[e.g., Data Loading, Training Script, Evaluation, Environment Setup]_
- **Description:** 
  _Detailed description of what went wrong_
- **Error Message/Symptoms:**
  ```
  Paste error messages or describe symptoms here
  ```
- **Time Lost:** _X hours_
- **Solution/Workaround:**
  _How you fixed it or worked around it_
- **Root Cause:**
  _What was actually wrong?_
- **Preventable?** Yes / No
  _Could this have been avoided with better documentation?_

---

### Issue 2: [Brief Description]
- **Date:** _YYYY-MM-DD_
- **Severity:** 🔴 Critical / 🟡 Moderate / 🟢 Minor
- **Component:** _[Component name]_
- **Description:** 
  _Details_
- **Error Message/Symptoms:**
  ```
  Errors here
  ```
- **Time Lost:** _X hours_
- **Solution/Workaround:**
  _Solution here_
- **Root Cause:**
  _Root cause_
- **Preventable?** Yes / No

---

## What Worked Well ✅

### Success 1: [Brief Description]
- **Date:** _YYYY-MM-DD_
- **Component:** _[e.g., Data Loading, Evaluation Script, etc.]_
- **Description:**
  _What worked smoothly and why you think it worked well_
- **Time Saved:** _Estimate how much time this saved vs. if it had been broken_
- **Documentation Quality:** ⭐⭐⭐⭐⭐ (1-5 stars)
- **Notes:**
  _Any additional observations_

---

### Success 2: [Brief Description]
- **Date:** _YYYY-MM-DD_
- **Component:** _[Component name]_
- **Description:**
  _Details_
- **Time Saved:** _Estimate_
- **Documentation Quality:** ⭐⭐⭐⭐⭐
- **Notes:**
  _Observations_

---

## Environment Setup

### Initial Setup
- **Date:** _YYYY-MM-DD_
- **Python Version:** _[e.g., 3.10.12]_
- **CUDA Version:** _[e.g., 12.1]_
- **PyTorch Version:** _[e.g., 2.1.0]_
- **Installation Steps:**
  ```bash
  # Record exact steps taken
  pip install -r requirements.txt
  # Any additional steps...
  ```
- **Issues Encountered:** _Any problems during setup?_
- **Time to Complete:** _X minutes/hours_

### Package Versions
```
# Output of: pip freeze > installed_packages.txt
# Or key packages:
torch==X.X.X
transformers==X.X.X
# etc.
```

---

## Data Preparation

### Dataset: ConflictQA
- **Date Processed:** _YYYY-MM-DD_
- **Source:** _Path or URL_
- **Size:** _Number of examples_
- **Preprocessing Required:** Yes / No
  - _If yes, describe steps_
- **Issues:** _Any problems?_
- **Time Required:** _X minutes/hours_

### Dataset: AmbigNQ
- **Date Processed:** _YYYY-MM-DD_
- **Source:** _Path or URL_
- **Size:** _Number of examples_
- **Preprocessing Required:** Yes / No
- **Issues:** _Any problems?_
- **Time Required:** _X minutes/hours_

---

## Code Quality Assessment

### Scripts Evaluated
| Script | Works Out-of-Box? | Documentation | Code Quality | Notes |
|--------|-------------------|---------------|--------------|-------|
| `train.sh` | ✅ / ⚠️ / ❌ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | _Comments_ |
| `generate_phi3_conflictqa_test.py` | ✅ / ⚠️ / ❌ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | _Comments_ |
| `evaluate_conflictqa.py` | ✅ / ⚠️ / ❌ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | _Comments_ |
| _Other scripts..._ | | | | |

---

## Reproducibility Checklist

- [ ] Environment successfully set up
- [ ] All dependencies installed
- [ ] Data downloaded and prepared
- [ ] Training scripts run successfully
- [ ] Evaluation scripts run successfully
- [ ] Results match paper (within reasonable margin)
- [ ] Documentation sufficient for reproduction
- [ ] All experiments logged with GPU hours
- [ ] Issues documented
- [ ] Successes documented

---

## Comparison with Original Paper

### Reported Results vs. Reproduced Results
| Metric | Paper Value | Reproduced Value | Difference | Notes |
|--------|-------------|------------------|------------|-------|
| _Metric 1_ | _X%_ | _Y%_ | _±Z%_ | _Comments_ |
| _Metric 2_ | _X%_ | _Y%_ | _±Z%_ | _Comments_ |
| _etc._ | | | | |

---

## Recommendations for Future Reproducibility

### What Should Be Improved
1. _Recommendation 1_
2. _Recommendation 2_
3. _etc._

### What Was Done Well
1. _Positive point 1_
2. _Positive point 2_
3. _etc._

---

## Daily Log (Optional - For Detailed Tracking)

### YYYY-MM-DD
- **Time:** HH:MM - HH:MM (_X hours_)
- **GPU Hours:** _X.X hours_
- **Activities:**
  - _Activity 1_
  - _Activity 2_
- **Blockers:**
  - _Any issues that stopped progress_
- **Achievements:**
  - _What got done_

---

## Additional Notes

_Use this section for any other observations, insights, or context that doesn't fit elsewhere._

---

## Quick Reference Commands

### Start Training
```bash
cd src/finetuning
./train.sh
```

### Generate Predictions
```bash
cd src/generation
python generate_phi3_conflictqa_test.py
```

### Run Evaluation
```bash
cd src/evaluation
python evaluate_conflictqa.py
```

### Monitor GPU Usage
```bash
# For NVIDIA GPUs
watch -n 1 nvidia-smi

# Or for detailed monitoring
nvtop
```

---

**Last Updated:** _YYYY-MM-DD HH:MM_
