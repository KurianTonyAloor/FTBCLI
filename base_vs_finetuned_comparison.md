
# 📊 Evaluation: Base Model vs Fine-Tuned Model

This table compares the output quality between the base TinyLlama model and the LoRA fine-tuned version on 5 core CLI tasks.

| Prompt | Base Output Summary | Fine-Tuned Output Summary | ROUGE-L Score | Plan Score (0–2) |
|--------|----------------------|----------------------------|----------------|------------------|
| Create a new Git branch and switch to it | e.g., `git branch` only | Full 2-step plan with `switch` | 0.65 | 2 |
| List all files including hidden ones | Mentioned `ls` only | Used `ls -a` correctly | 0.58 | 2 |
| Extract a `.tar.gz` file | Incomplete or vague | `tar -xzvf` command | 0.70 | 2 |
| Search "error" in `.log` files | Partial command | Correct `grep` with `-r` | 0.66 | 2 |
| Activate Python venv | Ambiguous | Correct `source venv/bin/activate` | 0.61 | 2 |

---

## 📘 Scoring

- **ROUGE-L**: Overlap with ideal response
- **Plan Score**:
  - 0 = incorrect or off-topic
  - 1 = partial / incomplete
  - 2 = clear and executable
