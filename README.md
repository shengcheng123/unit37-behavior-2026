# Unit 37 — BEHAVIOR-1K 2026 Challenge

Method: `zero-action flow test`  ·  rollouts: 1  ·  release: `v0-skilltest`

## Contents
- `metrics/` — one official metrics JSON per rollout, exactly as written by the
  evaluator. Not modified in any way.
- `r1pro_eval.yaml` — the exact robot config passed via `--robot-config`.
- `bystander_patch.py` — recording-only shim around `Evaluator.start_recording`,
  `_write_video` and `stop_recording`; saves an extra third-person MP4. It does not
  touch observations, actions, scoring or termination, and disables itself on error.

## Evaluation wrapper
Official `omnigibson.eval.wrappers.DefaultWrapper`, unchanged. Only RGB, depth and
proprioception are exposed to the policy.

## Exact evaluator command
```bash
python -m omnigibson.eval.eval \
  --task-name <TASK> --robot-config <PATH>/r1pro_eval.yaml \
  --mode public_test --host <HOST> --port <PORT> \
  --instance-indices 0 1 2 3 4 5 6 7 8 9 --num-rollouts 1 \
  --output-dir <OUT> --write-video
```
Environment: OmniGibson 3.9.1 / BEHAVIOR-1K v3.9.1, RTX 4000 Ada (12 GB),
NVIDIA driver 580.173.02.

## Policy serving
None yet. The policy server URL field carries a deliberately unresolvable
`.invalid` hostname to make that explicit; please do not attempt to connect.
