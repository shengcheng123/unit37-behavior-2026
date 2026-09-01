# Unit 37 — BEHAVIOR-1K 2026 Challenge

**This is a pipeline-validation submission, not a competitive entry.**
The rollout was produced with the evaluator's own built-in zero-action policy
(`--policy local`). No trained model was involved and the score is 0. We are
submitting it to validate the end-to-end submission path ahead of our real entry,
which will replace this one before the deadline.

## Contents
- `metrics/` — one official metrics JSON per rollout, exactly as written by the
  evaluator. Not modified in any way.
- `r1pro_eval.yaml` — the exact robot config passed via `--robot-config`.
- `bystander_patch.py` — recording-only shim (see below).

## Robot config
`r1pro_eval.yaml`, derived from the bundled `omnigibson/eval/r1pro.yaml`.

## Evaluation wrapper
Official `omnigibson.eval.wrappers.DefaultWrapper`, unchanged (the evaluator
default). Only RGB, depth and proprioception are exposed to the policy.

`bystander_patch.py` is a recording-only shim around `Evaluator.start_recording`,
`_write_video` and `stop_recording`; it saves an extra third-person MP4 next to
the official video. It does not touch observations, actions, scoring or episode
termination, and disables itself on error. It was DISABLED for this run
(`BYSTANDER_DISABLE=1`), so these results come from the stock evaluator path.

## Exact evaluator command used
```bash
python -m omnigibson.eval.eval \
  --task-name turning_on_radio \
  --robot-config /path/to/r1pro_eval.yaml \
  --mode public_test \
  --instance-indices 0 \
  --num-rollouts 1 \
  --output-dir <OUT> \
  --write-video \
  --policy local
```
Environment: OmniGibson 3.9.1 / BEHAVIOR-1K v3.9.1, Ubuntu, RTX 4000 Ada (12 GB),
NVIDIA driver 580.173.02.

## Policy serving
None yet. This entry has no servable endpoint: the rollout used the evaluator's
internal zero-action policy, so there is nothing for the organizers to connect to.
The policy server URL field is filled with a deliberately unresolvable
`.invalid` hostname to make that explicit. Our real entry will supply a Docker
image before the deadline.
