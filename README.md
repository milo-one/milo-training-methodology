# MILO Training Methodology

This repository documents the methodology, preprocessing logic, validation approach, and preregistration-relevant decisions for the MILO private training-data preparation workflow.

**No training data are included in this repository.**

The underlying data consist of private human-AI chat histories and project-defining interaction patterns. For reasons of privacy, authorial confidentiality, and conceptual integrity, neither raw chats nor curated training examples are deposited here.

## Repository Scope

This repository provides:

- aggregate dataset statistics
- schema descriptions for SFT and ORPO outputs
- methodology notes for manual curation and segmentation
- documentation of synthetic rejected-response generation
- documentation of tool-call augmentation
- validation and data-availability statements for preregistration

This repository does not provide:

- raw chat exports
- curated chat excerpts
- final SFT or ORPO training files
- split-ID lists
- real prompt/chosen/rejected examples from the private corpus

## Related Repositories

- [`milo-one/core-analytics`](https://github.com/milo-one/core-analytics): computational language-processing and analysis pipeline
- [`milo-one/core-theory`](https://github.com/milo-one/core-theory): theoretical and preregistration context

## Current Final Aggregate Counts

| Output | Count |
|---|---:|
| SFT training rows | 739 |
| ORPO preference candidates | 806 |
| ORPO training rows | 1,612 |
| New tool-call injections | 222 |
| Final tool-call tails | 230 |

## AI-Assisted Documentation Note

Parts of the methodology text were drafted with AI assistance and then reviewed, revised, and approved by the author. The repository documents reproducibility-relevant decisions and aggregate statistics rather than every intermediate manual curation step.
