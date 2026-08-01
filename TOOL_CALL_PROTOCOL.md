# Tool-Call Augmentation Protocol

Selected `chosen` responses were synthetically augmented with tool-call JSON objects.

Tool calls were not inserted into every eligible context. They were added only when the surrounding prompt and chosen answer made the call contextually plausible. This was intended to avoid training a reflexive tool-use pattern.

## Constraints

- Tool calls were appended to the end of the chosen text.
- Real line breaks were used before the JSON object.
- Each inserted tool call was validated with JSON parsing before writing.
- In ORPO examples, tool calls were inserted only into the `chosen` field.
- ORPO `rejected` fields were not modified.
- Final JSONL files were reparsed after writing.
- Row counts were checked to ensure no data loss.

## Aggregate Counts

| Measure | Count |
|---|---:|
| New tool-call injections | 222 |
| Final tool-call tails | 230 |
| SFT tool tails | 78 |
| ORPO chosen tool tails | 152 |

The difference between new injections and final tool tails reflects pre-existing valid tool tails in the input material.
