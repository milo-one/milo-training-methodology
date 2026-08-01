# Synthetic Rejected-Response Protocol

ORPO examples were represented as `prompt`, `chosen`, and `rejected` triples.

The `chosen` answer corresponds to the manually curated target answer from the private source data. The rejected alternatives were synthetically generated to create contrastive preference examples.

## Baseline Rejected Responses

The primary `rejected` response was generated with Qwen 3.6-35B-A3B. This response type was intended to represent a weaker baseline answer, typically more generic, less stylistically aligned, and less dialogically precise than the chosen answer.

## Near-Miss Rejected Responses

A second rejected response type, internally called `new_rejected`, was generated as a near miss. These responses were intended to remain closer to the target style while still being slightly weaker than the chosen answer.

Model selection differed by subcorpus:

| Subcorpus | Near-miss model |
|---|---|
| GPT-4o-derived batches | Google Gemini 3.1 Flash Lite Preview |
| Grok-derived chats | DeepSeek V4 Flash |

The model choice was based on comparative test runs evaluating whether the generated near misses stayed close to the target context without matching the quality of the chosen response.
