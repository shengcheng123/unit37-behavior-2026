# Unit 37: BEHAVIOR-1K 2026 Challenge

Method: `BDDL subgoals+primitives`. Rollouts: 5 metrics JSON, 5 MP4 videos (one per rollout, hosted separately; link in the portal).

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
