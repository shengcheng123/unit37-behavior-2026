# Unit 37: BEHAVIOR-1K 2026 Challenge

Method: `BDDL subgoals+primitives`. Rollouts: 6 metrics JSON, 6 MP4 videos (one per rollout, hosted separately; link in the portal).

## Contents

- `metrics/`: one metrics JSON per rollout, byte-for-byte as written by the evaluator (`MANIFEST.sha256` lists the digests).
- `wrapper/eval_wrapper_rgbd_fullres.py`: the evaluation wrapper used (exposes only RGB, depth and proprioception to the policy).
- `robot_config/r1pro.yaml`: the robot config used.

## Exact evaluator command

```bash
python -m omnigibson.eval.eval \
  --task-name <TASK> --robot-config OmniGibson/omnigibson/eval/r1pro.yaml \
  --env-wrapper eval_wrapper_rgbd_fullres.RGBDFullResWrapper \
  --mode public_test --instance-indices 0 1 2 3 4 5 6 7 8 9 --num-rollouts 1 \
  --policy websocket --host <HOST> --port <PORT> \
  --output-dir <OUT> --write-video --headless
```

- Wrapper path: `wrapper/eval_wrapper_rgbd_fullres.py` (put its directory on `PYTHONPATH`).
- Robot config path: `robot_config/r1pro.yaml` (passed as `--robot-config OmniGibson/omnigibson/eval/r1pro.yaml`).
- `--instance-indices 0 1 2 3 4 5 6 7 8 9` are instance ids 301 to 310 in the output JSON; one rollout each, no reruns selected.

## Environment

OmniGibson / BEHAVIOR-1K v3.9.3-post1, headless.

## Policy serving

Docker image submission. Image: `ghcr.io/shengcheng123/unit37-behavior-2026:sub-6043644a55`. The organizers run OmniGibson outside the container and connect through the WebSocket policy client; the model fits a single 24GB GPU.

## Per-rollout provenance

Each rollout below was produced by the Docker image / source commit listed (the image named under Policy serving is the final one; earlier rollouts came from earlier builds of the same policy).

| rollout | image | commit | batch |
|---|---|---|---|
| clean_a_keyboard_310_0 | b1k-unit37-policy:sub-6043644a55 | 6043644a55 | sub11_clean_a_keyboard_310__closed_clean_a_keyboard |
| installing_smoke_detectors_303_0 | b1k-unit37-policy:sub-6043644a55 | 6043644a55 | sub11_installing_smoke_detectors_303__closed_installing_smoke_detectors |
| installing_smoke_detectors_304_0 | b1k-unit37-policy:sub-6043644a55 | 6043644a55 | sub11_installing_smoke_detectors_304__closed_installing_smoke_detectors |
| turning_on_radio_301_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| turning_on_radio_308_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| turning_on_radio_309_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
