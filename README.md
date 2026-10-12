# African-Language Machine Translation Evaluation

An academic NLP project examining how corrected benchmark references affect translation scores and error interpretation. The notebook loads original and corrected FLORES references for Hausa, Sepedi, Xitsonga and isiZulu, and implements pretrained-model inference and multi-metric evaluation.

## What the project demonstrates

- Reference-data loading and comparison.
- Batch translation using NLLB-200 distilled 600M and M2M-100 418M.
- PyTorch and Hugging Face Transformers inference workflows.
- Evaluation with BLEU, ChrF, BERTScore and COMET.
- Sentence-level analysis to distinguish reference changes from model errors.

These models are used for inference; this project does not train a translation model from scratch.

## Evaluation scope

The saved notebook includes translation scores and correction-magnitude analysis. In that reference comparison, 225 of 1,012 isiZulu sentences differ between the original and corrected sets (22.23%). This measures changed references, not a translation error rate.

**Reproduction issue:** the M2M-100 mapping in the current notebook assigns `ns` to Sepedi and `ts` to Xitsonga. Confirm supported language codes against the selected tokenizer before interpreting comparisons; unsupported languages must be skipped explicitly. The saved M2M-100 score table does not provide complete coverage of all four languages. Blanket ranking conclusions are therefore omitted from this documentation.

## Run the notebook

Open [Machine_Translation_model_for_African_language_clean.ipynb](Machine_Translation_model_for_African_language_clean.ipynb) in Google Colab, select a GPU runtime and run cells in order after checking language support. Use the installation cells in the notebook for the actual evaluation dependencies; no `requirements.txt` is currently included.

Internet access is required to retrieve reference data and model weights. Some model or metric downloads may require accepting the provider’s access terms. Record package versions, model checkpoints and language mappings when reproducing results.

## Data source

Reference data is loaded from [dsfsi/flores-fix-4-africa](https://github.com/dsfsi/flores-fix-4-africa), associated with Abdulmumin et al. (2024), *Correcting FLORES Evaluation Dataset for Four African Languages*. Refer to that repository for data provenance and usage conditions.

## Files

- `Machine_Translation_model_for_African_language_clean.ipynb`: inference, evaluation and saved outputs.
- `README.md`: project overview and reproduction notes.

## Next steps

Validate language support, rerun supported comparisons with a documented environment, separate corpus-level scores from sentence-level diagnostics and publish a concise results table with explicit coverage. This documentation update did not rerun model inference.

**Author:** Merhawi Hailu · COS802 · University of Pretoria
