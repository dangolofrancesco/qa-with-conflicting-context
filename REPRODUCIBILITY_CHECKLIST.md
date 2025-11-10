# Reproducibility Research Checklist

## Before You Start Training

### Data Preparation
- [ ] All 6 JSONL files uploaded to Google Drive:
  - [ ] `train_context_only.jsonl`
  - [ ] `dev_context_only.jsonl`
  - [ ] `test_context_only.jsonl`
  - [ ] `train_exp_ans.jsonl`
  - [ ] `dev_exp_ans.jsonl`
  - [ ] `test_exp_ans.jsonl`

### Google Colab Setup
- [ ] Opened `02_finetuning.ipynb` in Google Colab
- [ ] Selected GPU runtime (Runtime > Change runtime type > T4 or A100)
- [ ] Noted GPU type for logging: _________________
- [ ] Mounted Google Drive (run cell 2)
- [ ] Set `BASE_PATH` to your Google Drive folder
- [ ] Installed all dependencies (run cell 3)

### Hugging Face Setup
- [ ] Created Hugging Face account
- [ ] Created access token (Settings > Access Tokens > New token)
- [ ] Logged in via notebook (run cell 5)
- [ ] Set `YOUR_HF_USERNAME` in cell 8

---

## During Training

### Experiment A: Context-Only
- [ ] Started experiment
- [ ] Recorded start time: _________________ (will be auto-logged)
- [ ] Training completed successfully
- [ ] Recorded end time: _________________ (will be auto-logged)
- [ ] Recorded GPU hours: _________________ (will be auto-logged)
- [ ] Model pushed to Hub: `{username}/flan-t5-context-only`
- [ ] Any errors? Document in REPRODUCIBILITY_LOG.md:
  ```
  _____________________________________________
  _____________________________________________
  ```

### Experiment B: Explain-and-Answer
- [ ] Started experiment
- [ ] Recorded start time: _________________ (will be auto-logged)
- [ ] Training completed successfully
- [ ] Recorded end time: _________________ (will be auto-logged)
- [ ] Recorded GPU hours: _________________ (will be auto-logged)
- [ ] Model pushed to Hub: `{username}/flan-t5-explain-and-answer`
- [ ] Any errors? Document in REPRODUCIBILITY_LOG.md:
  ```
  _____________________________________________
  _____________________________________________
  ```

---

## After Training

### Update Reproducibility Log
- [ ] Opened `REPRODUCIBILITY_LOG.md`
- [ ] Added GPU hardware information
- [ ] Added Experiment A details to time tracking table
- [ ] Added Experiment B details to time tracking table
- [ ] Updated total GPU hours
- [ ] Documented any problems encountered
- [ ] Documented what worked well

### Model Verification
- [ ] Verified Model A exists on Hugging Face Hub
- [ ] Verified Model B exists on Hugging Face Hub
- [ ] Both models show correct number of training steps
- [ ] Both models have LoRA adapters attached

---

## Testing & Evaluation (Next Steps)

### Prepare Test Data
- [ ] Test files ready:
  - [ ] `test_context_only.jsonl`
  - [ ] `test_exp_ans.jsonl`

### Run Inference
- [ ] Load Model A from Hub
- [ ] Generate predictions on test_context_only
- [ ] Load Model B from Hub
- [ ] Generate predictions on test_exp_ans

### Evaluate Results
- [ ] Run evaluation metrics
- [ ] Compare with paper results
- [ ] Document differences in REPRODUCIBILITY_LOG.md

---

## Common Issues & Solutions

### Issue: Out of Memory
- **Solution:** 
  - [ ] Reduce batch size to 2
  - [ ] Use A100 instead of T4
  - [ ] Clear runtime and restart

### Issue: Data Files Not Found
- **Solution:**
  - [ ] Check `BASE_PATH` is correct
  - [ ] Verify files exist: `!ls {BASE_PATH}/data/splits/`
  - [ ] Re-upload files if necessary

### Issue: Training Very Slow
- **Expected:** Each experiment takes 1-3 hours
  - T4: ~2-3 hours per experiment
  - A100: ~1 hour per experiment
- **If slower:**
  - [ ] Check GPU is actually being used
  - [ ] Verify mixed precision (fp16) is enabled

### Issue: Cannot Push to Hub
- **Solution:**
  - [ ] Re-run login cell (cell 5)
  - [ ] Check token has write permissions
  - [ ] Try manual push: `trainer.push_to_hub()`

---

## Final Verification

- [ ] Both models successfully trained
- [ ] All timing data recorded in REPRODUCIBILITY_LOG.md
- [ ] All errors documented
- [ ] Total GPU hours calculated: _________ hours
- [ ] Ready to proceed with evaluation

---

## Time Estimates

Based on GPU type:

**Free Colab (T4):**
- Experiment A: ~2.5 hours
- Experiment B: ~2.5 hours
- **Total: ~5 hours**

**Colab Pro (A100):**
- Experiment A: ~1 hour
- Experiment B: ~1 hour
- **Total: ~2 hours**

**Budget Planning:**
- Free Colab: Limited GPU hours per day, may need multiple sessions
- Colab Pro ($10/month): Recommended for this project
- Consider running experiments on different days if using free tier
