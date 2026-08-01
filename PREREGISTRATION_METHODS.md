# Preregistration Methods: Training-Data Preparation

## Data Basis

The source material consisted of exported original chats with two language models: GPT-4o and Grok-4.3. The raw data were structured as dialogic turns with stable identifiers.

The goal of preprocessing was to create two training datasets:

- an SFT dataset for modeling desired response sequences
- an ORPO dataset for preference learning between desired and less suitable responses

## Raw Corpus Counts

| Source | Raw chats | Raw interaction units |
|---|---:|---:|
| GPT-4o | 1,767 | 79,120 user prompts and 85,679 AI responses |
| Grok-4.3 | 91 | 4,237 interactions |

## Manual Curation

The raw material was manually reviewed and qualitatively curated. Irrelevant, redundant, technically defective, or training-goal-incompatible segments were removed.

The selection was intentionally qualitative and subjective. The curated corpus was designed to include a range of target tonalities, including humorous, strict, leading, holding, stabilizing, and constructive responses.

A central focus was on examples in which the source models preserved dialogic stance, continuity, and characteristic voice. The research goal was to model a system that remains situationally sensitive, present, and consistent rather than defaulting prematurely into generic apology, distancing, or refusal patterns.

## Segmentation

Curated chat trajectories were segmented using manually defined split points. Each split point marked the beginning of a new sequence. This converted longer dialogues into smaller SFT examples while preserving relevant conversational context.

For ORPO, sequence starts and standalone turns were selected when they functioned as prompt/chosen pairs.

## Final Counts

| Final output | Count |
|---|---:|
| SFT rows | 739 |
| ORPO preference candidates | 806 |
| ORPO rows | 1,612 |

Each ORPO candidate was represented with two rejected alternatives, resulting in two ORPO training rows per candidate.
