# Unit 37: BEHAVIOR-1K 2026 Challenge

Method: `BDDL subgoals+primitives`. Rollouts: 27 metrics JSON, 27 MP4 videos (one per rollout, hosted separately; link in the portal).

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

Docker image submission. Image: `ghcr.io/shengcheng123/unit37-behavior-2026:sub-0e8258a147`. The organizers run OmniGibson outside the container and connect through the WebSocket policy client; the model fits a single 24GB GPU.

## Per-rollout provenance

Each rollout below was produced by the Docker image / source commit listed (the image named under Policy serving is the final one; earlier rollouts came from earlier builds of the same policy).

| rollout | image | commit | batch |
|---|---|---|---|
| clean_a_keyboard_303_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| installing_a_modem_301_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| installing_a_modem_306_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| installing_a_modem_307_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| installing_a_modem_310_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| installing_a_scanner_307_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| installing_a_scanner_308_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| installing_smoke_detectors_303_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| installing_smoke_detectors_305_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| installing_smoke_detectors_306_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| picking_up_trash_302_0 | b1k-unit37-policy:sub-0e8258a147 | 0e8258a147 | sub12_picking_up_trash_302__closed_picking_up_trash |
| picking_up_trash_303_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| picking_up_trash_308_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| picking_up_trash_310_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| putting_shoes_on_rack_305_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| setting_mousetraps_301_0 | b1k-unit37-policy:sub-0e8258a147 | 0e8258a147 | sub12_setting_mousetraps_301__closed_setting_mousetraps |
| setting_mousetraps_309_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| store_honey_302_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| store_honey_305_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| store_honey_308_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| tidying_bedroom_301_0 | b1k-unit37-policy:sub-0e8258a147 | 0e8258a147 | sub12_tidying_bedroom_301__closed_tidying_bedroom |
| turning_on_radio_301_0 | b1k-unit37-policy:sub-0e8258a147 | 0e8258a147 | sub211h__closed_turning_on_radio |
| turning_on_radio_303_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| turning_on_radio_307_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| turning_on_radio_308_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| turning_on_radio_309_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
| turning_on_radio_310_0 | rented-GPU-run-at-commit | 0e8258a147 | rent3_results |
