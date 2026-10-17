# Unit 37: BEHAVIOR-1K 2026 Challenge

Method: `BDDL subgoals+primitives`. Rollouts: 117 metrics JSON, 117 MP4 videos (one per rollout, hosted separately; link in the portal).

## Contents

- `metrics/`: one metrics JSON per rollout, byte-for-byte as written by the evaluator (`MANIFEST.sha256` lists the digests).
- `wrapper/eval_wrapper_rgbd_fullres.py`: the evaluation wrapper used (exposes only RGB, depth and proprioception to the policy).
- `robot_config/r1pro_official.yaml`: the robot config used.

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
- Robot config path: `robot_config/r1pro_official.yaml` (passed as `--robot-config OmniGibson/omnigibson/eval/r1pro.yaml`).
- `--instance-indices 0 1 2 3 4 5 6 7 8 9` are instance ids 301 to 310 in the output JSON; one rollout each, no reruns selected.

## Environment

OmniGibson / BEHAVIOR-1K v3.9.3-post1, headless.

## Policy serving

Docker image submission. Image: `ghcr.io/shengcheng123/unit37-behavior-2026:sub-0e8258a147`. The organizers run OmniGibson outside the container and connect through the WebSocket policy client; the model fits a single 24GB GPU.

## Per-rollout provenance

Each rollout below was produced by the Docker image / source commit listed (the image named under Policy serving is the final one; earlier rollouts came from earlier builds of the same policy).

| rollout | image | commit | batch |
|---|---|---|---|
| assembling_gift_baskets_302_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i1 |
| assembling_gift_baskets_305_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i4 |
| boxing_books_up_for_storage_305_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i4 |
| bringing_in_wood_301_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i0 |
| bringing_water_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i7 |
| chopping_wood_301_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i0 |
| chopping_wood_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| clean_a_keyboard_302_0 | p1g6-tree-run-at-commit | 0e8258a147 | sub14_clean_a_keyboard_302 |
| clean_a_keyboard_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i2 |
| clean_a_keyboard_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i4 |
| clean_a_keyboard_310_0 | p1g6-tree-run-at-commit | 0e8258a147 | sub14_clean_a_keyboard_310 |
| clean_up_broken_glass_304_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i3 |
| clean_up_broken_glass_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i4 |
| clean_up_broken_glass_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i7 |
| collecting_aluminum_cans_302_0 | 3070-tree-run-at-commit | 0e8258a147 | rent4q_i1 |
| collecting_aluminum_cans_304_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i3 |
| collecting_aluminum_cans_305_0 | 3070-tree-run-at-commit | 0e8258a147 | rent4q_i4 |
| collecting_aluminum_cans_306_0 | 3070-tree-run-at-commit | 0e8258a147 | rent4q_i5 |
| collecting_aluminum_cans_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i6 |
| collecting_aluminum_cans_309_0 | 3070-tree-run-at-commit | 0e8258a147 | rent4q_i8 |
| collecting_childrens_toys_309_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i8 |
| collecting_childrens_toys_310_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i9 |
| dispose_of_batteries_302_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i1 |
| dispose_of_batteries_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i7 |
| dispose_of_glass_302_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i1 |
| dispose_of_glass_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i2 |
| dispose_of_glass_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i4 |
| dispose_of_glass_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| dispose_of_glass_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i6 |
| dispose_of_glass_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i7 |
| halve_an_egg_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| halve_an_egg_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i6 |
| installing_a_fax_machine_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i4 |
| installing_a_modem_301_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i0 |
| installing_a_modem_304_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i3 |
| installing_a_modem_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i5 |
| installing_a_modem_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i6 |
| installing_a_modem_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i7 |
| installing_a_modem_310_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i9 |
| installing_a_scanner_301_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i0 |
| installing_a_scanner_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i2 |
| installing_a_scanner_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i4 |
| installing_a_scanner_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i6 |
| installing_a_scanner_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i7 |
| installing_smoke_detectors_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i2 |
| installing_smoke_detectors_304_0 | p1g6-tree-run-at-commit | 0e8258a147 | sub14_installing_smoke_detectors_304 |
| installing_smoke_detectors_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i4 |
| installing_smoke_detectors_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i5 |
| installing_smoke_detectors_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i7 |
| installing_smoke_detectors_310_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i9 |
| loading_the_car_302_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i1 |
| make_microwave_popcorn_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i7 |
| make_rose_centerpieces_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| moving_boxes_to_storage_301_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i0 |
| moving_boxes_to_storage_302_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i1 |
| moving_boxes_to_storage_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i2 |
| moving_boxes_to_storage_309_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| organizing_art_supplies_302_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i1 |
| picking_up_trash_302_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i1 |
| picking_up_trash_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| picking_up_trash_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i5 |
| picking_up_trash_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i7 |
| picking_up_trash_309_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| picking_up_trash_310_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i9 |
| polishing_shoes_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i5 |
| putting_away_Halloween_decorations_302_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i1 |
| putting_away_Halloween_decorations_304_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i3 |
| putting_away_Halloween_decorations_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i6 |
| putting_away_Halloween_decorations_309_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| putting_away_Halloween_decorations_310_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i9 |
| putting_away_toys_305_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i4 |
| putting_dirty_dishes_in_sink_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i4 |
| putting_shoes_on_rack_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i4 |
| putting_shoes_on_rack_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i6 |
| putting_shoes_on_rack_309_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| putting_shoes_on_rack_310_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i9 |
| re_shelving_library_books_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i5 |
| re_shelving_library_books_310_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i9 |
| rearrange_your_room_310_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i9 |
| set_up_a_coffee_station_in_your_kitchen_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| set_up_a_coffee_station_in_your_kitchen_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i5 |
| set_up_a_coffee_station_in_your_kitchen_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i6 |
| setting_mousetraps_301_0 | p1g6-tree-run-at-commit | 0e8258a147 | sub12_setting_mousetraps_301 |
| setting_mousetraps_302_0 | p1g6-tree-run-at-commit | 0e8258a147 | sub12_setting_mousetraps_302 |
| setting_mousetraps_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i2 |
| setting_mousetraps_304_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i3 |
| setting_mousetraps_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i5 |
| setting_mousetraps_309_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i8 |
| setting_mousetraps_310_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i9 |
| sorting_bottles_cans_and_paper_305_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i4 |
| spraying_for_bugs_301_0 | p1g6-tree-run-at-commit | 0e8258a147 | sub14_spraying_for_bugs_301 |
| spraying_for_bugs_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i7 |
| spraying_fruit_trees_301_0 | p1g6-tree-run-at-commit | 0e8258a147 | sub14_spraying_fruit_trees_301 |
| spraying_fruit_trees_304_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i3 |
| spraying_fruit_trees_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i5 |
| store_batteries_301_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i0 |
| store_batteries_304_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i3 |
| store_batteries_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i4 |
| store_honey_302_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i1 |
| store_honey_305_0 | rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i4 |
| store_honey_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i7 |
| tidying_bathroom_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i5 |
| tidying_bedroom_301_0 | p1g6-tree-run-at-commit | 0e8258a147 | sub12_tidying_bedroom_301 |
| tidying_bedroom_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| tidying_bedroom_304_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i3 |
| tidying_bedroom_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| tidying_bedroom_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i7 |
| tidying_living_room_306_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i5 |
| tidying_living_room_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i6 |
| turning_on_radio_301_0 | p1g6-tree-run-at-commit | 0e8258a147 | sub211h |
| turning_on_radio_303_0 | rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| turning_on_radio_304_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i3 |
| turning_on_radio_307_0 | rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i6 |
| turning_on_radio_308_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i7 |
| turning_on_radio_309_0 | rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| turning_on_radio_310_0 | rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i9 |
| turning_out_all_lights_before_sleep_310_0 | p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i9 |
