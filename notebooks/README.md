# Finetuning Notebooks

## 02_finetuning.ipynb

This notebook replaces the original `train.sh` script with a modern approach using `transformers` and `peft` libraries directly. It's designed to run in Google Colab.

### What It Does

This notebook performs the **exact same training** as `train.sh` but uses modern libraries that work reliably in Colab:

**Original `train.sh` configuration:**
```bash
autotrain llm \
    --train \
    --model microsoft/Phi-3-small-8k-instruct \
    --use-peft \
    --learning-rate 2e-4 \
    --train_batch_size 4 \
    --num_train_epochs 3 \
    --trainer sft \
    --model_max_length 1024
```

**This notebook implements:**
- ✅ Same learning rate: `2e-4`
- ✅ Same batch size: `4`
- ✅ Same epochs: `3`
- ✅ Same max length: `1024`
- ✅ PEFT/LoRA with standard config (r=16, alpha=32)
- ✅ Seq2Seq training (SFT)

### Two Experiments

**Experiment A: Context-Only**
- Training data: `train_context_only.jsonl`
- Validation data: `dev_context_only.jsonl`
- Output model: `{your_username}/flan-t5-context-only`

**Experiment B: Explain-and-Answer**
- Training data: `train_exp_ans.jsonl`
- Validation data: `dev_exp_ans.jsonl`
- Output model: `{your_username}/flan-t5-explain-and-answer`

### How to Use

1. **Upload your data to Google Drive:**
   - Create folder: `/MyDrive/reproducing_project/`
   - Upload the `data/splits/` folder with all 6 JSONL files

2. **Open in Colab:**
   - Upload `02_finetuning.ipynb` to Colab
   - Or: File > Open notebook > Upload

3. **Adjust the path (cell 2):**
   ```python
   BASE_PATH = "/content/drive/MyDrive/reproducing_project"
   ```

4. **Set your HuggingFace username (cell 8):**
   ```python
   YOUR_HF_USERNAME = "your_actual_username"
   ```

5. **Run all cells:**
   - Runtime > Run all
   - Or run cells sequentially

6. **Monitor progress:**
   - Training progress shows in real-time
   - Time tracking is automatic
   - GPU hours calculated at the end

### Time Tracking for Reproducibility

The notebook automatically tracks:
- ⏱️ Start/end timestamps for each experiment
- ⏱️ Duration in hours and minutes
- 📊 Total GPU hours across both experiments
- 🔗 Links to published models

At the end, you'll see output like:
```
📝 LOG THIS IN REPRODUCIBILITY_LOG.md:
   - Experiment: Experiment A: Context-Only
   - Start: 2025-11-10 14:30:22
   - End: 2025-11-10 16:45:18
   - GPU Hours: 2.25
   - Model: your_username/flan-t5-context-only
```

Copy these details into your `REPRODUCIBILITY_LOG.md`!

### Differences from train.sh

| train.sh | This Notebook | Why Changed |
|----------|---------------|-------------|
| `autotrain-advanced` | `transformers` + `peft` | Autotrain is outdated and breaks in Colab |
| Phi-3 model | flan-t5-base | Match your experimental setup |
| Single run | Two experiments | Run both Context-Only and Explain-and-Answer |
| No time tracking | Automatic tracking | For reproducibility research |

### Troubleshooting

**"No module named 'transformers'"**
- Make sure cell 3 (pip install) runs successfully

**"Drive not mounted"**
- Run cell 2 to mount Google Drive
- Click the link and authorize

**"Cannot find data files"**
- Check that `BASE_PATH` is correct
- Verify files exist: `!ls {BASE_PATH}/data/splits/`

**Out of memory**
- Use a better GPU: Runtime > Change runtime type > T4 or A100
- Reduce batch size in the training function (change `per_device_train_batch_size=4` to `2`)

**Training is slow**
- This is normal! Each experiment takes 1-3 hours depending on GPU
- T4: ~2-3 hours per experiment
- A100: ~1 hour per experiment

### GPU Recommendations

- **Free Colab (T4):** Works but slow (~2-3 hrs per experiment)
- **Colab Pro (A100):** Recommended (~1 hr per experiment)
- **Local GPU:** Adjust paths and remove Colab-specific code

### Next Steps After Training

1. Update `REPRODUCIBILITY_LOG.md` with GPU hours and timestamps
2. Download or use the models from Hugging Face Hub
3. Run evaluation on test sets (`test_context_only.jsonl`, `test_exp_ans.jsonl`)
4. Document any issues or surprises in your log
