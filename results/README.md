# Recorded results and artifact provenance

These artifacts come from the saved outputs of the user-provided, executed **`Retinal_Vessel_Segmentation_UNet_.ipynb`**. The canonical repository copy is [the executed notebook](../notebook/retinal_vessel_segmentation_unet.ipynb), preserved byte for byte. Training and inference were not rerun for this repository update.

- Source notebook SHA-256: `8b40a47bf09df47f7caa7a5ee9298075f85c3ff97ecaddeb14a51f1c940d1119`.
- Recorded run ID: `20261022T234750_550523Z` (UTC run-directory identifier).
- Recorded split: **16 training / 4 validation / 20 official test images**.
- Selected checkpoint: **epoch 15 of 15**, using validation Global Dice at fixed threshold 0.50.
- Validation-selected threshold: **0.50**.
- Validation Global Dice / Global IoU: **0.7330 / 0.5785** when rounded to four decimal places.
- Official test status: **20 predictions generated; no manual vessel ground truth and no test Dice/IoU**.

## Figure extraction

PNG files were decoded directly from the notebook's saved `image/png` outputs. Their bytes were not redrawn, recomputed, resized, or enhanced. They are the embedded notebook renderings, not the separate higher-DPI files named in its `fig.savefig` calls. Cell and output indices below are zero-based.

| Committed figure | Notebook cell / output | Scope |
|---|---|---|
| [Input pairs](input_pairs.png) | 4 / 1 | Fundus/manual-mask pairing preview |
| [Training and validation loss](training_validation_loss.png) | 16 / 0 | Recorded 15-epoch loss curves |
| [Validation Dice and IoU](validation_dice_iou.png) | 16 / 1 | Validation metrics at fixed threshold 0.50 |
| [Validation predictions](sample_predictions/sample_predictions.png) | 16 / 2 | All four validation images, with vessel ground truth and error overlays |
| [Test predictions](test_predictions.png) | 17 / 0 | Fixed test IDs 01–04, prediction-only preview; no error scores |

Figure dimensions, byte sizes, SHA-256 hashes, and extraction locations are recorded in [recorded_run_summary.json](recorded_run_summary.json).

## Tables and text

| File | Source and precision |
|---|---|
| [training_log.txt](training_log.txt) | Exact saved stdout from the 15-epoch training cell (cell 12); epoch metrics were printed to four decimal places |
| [validation_metrics.csv](validation_metrics.csv) | Saved validation table from cell 14; six decimal places as displayed by pandas |
| [validation_threshold_results.csv](validation_threshold_results.csv) | Saved validation threshold table from cell 14; six displayed decimal places |
| [test_metrics.csv](test_metrics.csv) | Saved unavailable-metric table from cell 18; values are empty and status is `unavailable_no_vessel_ground_truth` |
| [split_ids.csv](split_ids.csv) | Image IDs and split membership printed in cell 2; no source images or masks included |
| [recorded_run_summary.json](recorded_run_summary.json) | Repository-side transcription of verified notebook outputs and configuration, with provenance |

These CSV/JSON exports are explicitly derived from the saved notebook. They are **not copies of the original full-precision runtime CSV/JSON files**, which were not supplied. Undefined values remain empty CSV fields or JSON `null` and must not be treated as scores. Validation Global Dice pools pixel counts over all four resized images; Mean image Dice instead averages image-level Dice values.

## Artifacts listed by the notebook but not supplied separately

The notebook's final cell lists temporary Colab files, including a trained `.pth` checkpoint, full-precision metrics/history files, individual masks for all 20 test images, and a submission ZIP. Those file listings and `/content/...` links do not embed the files themselves. This update includes only the supplied executed notebook, the five embedded figures, and the documented table/text transcriptions above. It does not claim to provide the checkpoint, original runtime files, 20 individual test masks, an official-server submission, or an independent test score.

The original dataset, credentials, large model files, and run archives are excluded. `.gitignore` covers common dataset/checkpoint/run locations, archives, and credential filenames to help prevent accidental future uploads.
