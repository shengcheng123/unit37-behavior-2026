# Unit 37: BEHAVIOR-1K 2026 Challenge

Method: `BDDL subgoals+primitives`. Rollouts: 283 metrics JSON, 283 MP4 videos (one per rollout, hosted separately; link in the portal).

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
| assembling_gift_baskets_302_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i1 |
| assembling_gift_baskets_305_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i4 |
| attach_a_camera_to_a_tripod_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card22/gpu0/rent_i0 |
| attach_a_camera_to_a_tripod_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card26/gpu0/rent_i1 |
| attach_a_camera_to_a_tripod_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card25/gpu0/rent_i2 |
| attach_a_camera_to_a_tripod_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card29/gpu0/rent_i3 |
| attach_a_camera_to_a_tripod_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i7 |
| boxing_books_up_for_storage_305_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i4 |
| boxing_books_up_for_storage_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i6 |
| bringing_in_wood_301_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i0 |
| bringing_in_wood_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i3 |
| bringing_water_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i2 |
| bringing_water_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i5 |
| bringing_water_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i7 |
| chop_an_onion_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card209/gpu0/rent_i0 |
| chop_an_onion_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| chop_an_onion_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i3 |
| chop_an_onion_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i6 |
| chop_an_onion_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card265/gpu0/rent_i7 |
| chopping_wood_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i0 |
| chopping_wood_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card300/gpu0/rent_i2 |
| chopping_wood_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card45/gpu0/rent_i4 |
| chopping_wood_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| chopping_wood_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card45/gpu0/rent_i6 |
| chopping_wood_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card44/gpu0/rent_i7 |
| chopping_wood_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card46/gpu0/rent_i9 |
| clean_a_keyboard_302_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | sub14_clean_a_keyboard_302 |
| clean_a_keyboard_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i2 |
| clean_a_keyboard_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i4 |
| clean_a_keyboard_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i5 |
| clean_a_keyboard_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i7 |
| clean_a_keyboard_310_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | sub14_clean_a_keyboard_310 |
| clean_a_trumpet_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card300/gpu0/rent_i0 |
| clean_a_trumpet_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card106/gpu0/rent_i2 |
| clean_a_trumpet_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card57/gpu0/rent_i3 |
| clean_a_trumpet_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card297/gpu0/rent_i4 |
| clean_a_trumpet_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card50/gpu0/rent_i5 |
| clean_a_trumpet_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card36/gpu0/rent_i6 |
| clean_a_trumpet_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card298/gpu0/rent_i7 |
| clean_a_trumpet_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card296/gpu0/rent_i8 |
| clean_a_trumpet_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card219/gpu0/rent_i9 |
| clean_boxing_gloves_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card47/gpu0/rent_i2 |
| clean_boxing_gloves_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card13/gpu0/rent_i5 |
| clean_up_broken_glass_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i3 |
| clean_up_broken_glass_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i4 |
| clean_up_broken_glass_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i7 |
| clean_up_broken_glass_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i8 |
| cleaning_up_plates_and_food_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i7 |
| clearing_food_from_table_into_fridge_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i6 |
| collecting_aluminum_cans_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card277/gpu0/rent_i0 |
| collecting_aluminum_cans_302_0 | frozen<-3070-tree-run-at-commit | 0e8258a147 | rent4q_i1 |
| collecting_aluminum_cans_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i3 |
| collecting_aluminum_cans_305_0 | frozen<-3070-tree-run-at-commit | 0e8258a147 | rent4q_i4 |
| collecting_aluminum_cans_306_0 | frozen<-3070-tree-run-at-commit | 0e8258a147 | rent4q_i5 |
| collecting_aluminum_cans_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i6 |
| collecting_aluminum_cans_309_0 | frozen<-3070-tree-run-at-commit | 0e8258a147 | rent4q_i8 |
| collecting_childrens_toys_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i6 |
| collecting_childrens_toys_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i8 |
| collecting_childrens_toys_310_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i9 |
| composting_waste_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i3 |
| composting_waste_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card7/gpu0/rent_i5 |
| composting_waste_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card63/gpu0/rent_i6 |
| composting_waste_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i8 |
| cook_a_frozen_pie_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i9 |
| cook_broccolini_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card17/gpu0/rent_i3 |
| cook_broccolini_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card22/gpu0/rent_i6 |
| cook_broccolini_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card25/gpu0/rent_i8 |
| cook_broccolini_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card26/gpu0/rent_i9 |
| cook_hot_dogs_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i7 |
| dispose_of_batteries_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i1 |
| dispose_of_batteries_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i7 |
| dispose_of_batteries_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i8 |
| dispose_of_glass_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card248/gpu0/rent_i0 |
| dispose_of_glass_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i1 |
| dispose_of_glass_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i2 |
| dispose_of_glass_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i4 |
| dispose_of_glass_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| dispose_of_glass_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i6 |
| dispose_of_glass_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i7 |
| halve_an_egg_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card19/gpu0/rent_i2 |
| halve_an_egg_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| halve_an_egg_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i6 |
| halve_an_egg_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card291/gpu0/rent_i8 |
| halve_an_egg_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card292/gpu0/rent_i9 |
| hanging_pictures_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card13/gpu0/rent_i0 |
| hanging_pictures_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card76/gpu0/rent_i3 |
| hanging_pictures_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card9/gpu0/rent_i6 |
| hanging_pictures_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card100/gpu0/rent_i7 |
| hanging_pictures_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card100/gpu0/rent_i8 |
| hanging_pictures_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card65/gpu0/rent_i9 |
| hiding_Easter_eggs_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card39/gpu0/rent_i1 |
| hiding_Easter_eggs_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card37/gpu0/rent_i3 |
| hiding_Easter_eggs_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i5 |
| hiding_Easter_eggs_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| hiding_Easter_eggs_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card38/gpu0/rent_i9 |
| installing_a_fax_machine_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card254/gpu0/rent_i1 |
| installing_a_fax_machine_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card257/gpu0/rent_i3 |
| installing_a_fax_machine_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i4 |
| installing_a_fax_machine_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card22/gpu0/rent_i5 |
| installing_a_fax_machine_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card25/gpu0/rent_i6 |
| installing_a_fax_machine_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i7 |
| installing_a_fax_machine_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card18/gpu0/rent_i9 |
| installing_a_modem_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i0 |
| installing_a_modem_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card15/gpu0/rent_i2 |
| installing_a_modem_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i3 |
| installing_a_modem_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card15/gpu0/rent_i4 |
| installing_a_modem_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i5 |
| installing_a_modem_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i6 |
| installing_a_modem_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i7 |
| installing_a_modem_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card16/gpu0/rent_i8 |
| installing_a_modem_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i9 |
| installing_a_scanner_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i0 |
| installing_a_scanner_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i1 |
| installing_a_scanner_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i2 |
| installing_a_scanner_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i3 |
| installing_a_scanner_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i4 |
| installing_a_scanner_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i5 |
| installing_a_scanner_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i6 |
| installing_a_scanner_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i7 |
| installing_a_scanner_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| installing_a_scanner_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i9 |
| installing_smoke_detectors_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card13/gpu0/rent_i0 |
| installing_smoke_detectors_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card12/gpu0/rent_i1 |
| installing_smoke_detectors_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i2 |
| installing_smoke_detectors_304_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | sub14_installing_smoke_detectors_304 |
| installing_smoke_detectors_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i4 |
| installing_smoke_detectors_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i5 |
| installing_smoke_detectors_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i6 |
| installing_smoke_detectors_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i7 |
| installing_smoke_detectors_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i8 |
| installing_smoke_detectors_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i9 |
| loading_the_car_302_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i1 |
| make_cabinet_doors_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card109/gpu0/rent_i1 |
| make_cabinet_doors_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card259/gpu0/rent_i2 |
| make_cabinet_doors_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card21/gpu0/rent_i4 |
| make_cabinet_doors_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card261/gpu0/rent_i5 |
| make_cabinet_doors_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card262/gpu0/rent_i6 |
| make_cabinet_doors_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card18/gpu0/rent_i7 |
| make_cabinet_doors_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card266/gpu0/rent_i8 |
| make_cabinet_doors_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card286/gpu0/rent_i9 |
| make_gift_bags_for_baby_showers_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card52/gpu0/rent_i9 |
| make_microwave_popcorn_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card277/gpu0/rent_i5 |
| make_microwave_popcorn_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i7 |
| make_rose_centerpieces_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card32/gpu0/rent_i0 |
| make_rose_centerpieces_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card34/gpu0/rent_i2 |
| make_rose_centerpieces_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card36/gpu0/rent_i3 |
| make_rose_centerpieces_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| make_rose_centerpieces_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card32/gpu0/rent_i6 |
| make_rose_centerpieces_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card31/gpu0/rent_i8 |
| make_rose_centerpieces_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i9 |
| moving_boxes_to_storage_301_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i0 |
| moving_boxes_to_storage_302_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i1 |
| moving_boxes_to_storage_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i2 |
| moving_boxes_to_storage_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| organizing_art_supplies_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i1 |
| organizing_art_supplies_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card208/gpu0/rent_i6 |
| organizing_art_supplies_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card208/gpu0/rent_i8 |
| outfit_a_basic_toolbox_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card16/gpu0/rent_i6 |
| packing_meal_for_delivery_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card11/gpu0/rent_i5 |
| picking_up_trash_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card28/gpu0/rent_i0 |
| picking_up_trash_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i1 |
| picking_up_trash_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| picking_up_trash_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i3 |
| picking_up_trash_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card26/gpu0/rent_i4 |
| picking_up_trash_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i5 |
| picking_up_trash_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i6 |
| picking_up_trash_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i7 |
| picking_up_trash_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| picking_up_trash_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i9 |
| polishing_shoes_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i5 |
| put_together_a_basic_pruning_kit_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card17/gpu0/rent_i2 |
| putting_away_Halloween_decorations_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card43/gpu0/rent_i0 |
| putting_away_Halloween_decorations_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i1 |
| putting_away_Halloween_decorations_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card42/gpu0/rent_i2 |
| putting_away_Halloween_decorations_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i3 |
| putting_away_Halloween_decorations_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i5 |
| putting_away_Halloween_decorations_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i6 |
| putting_away_Halloween_decorations_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i7 |
| putting_away_Halloween_decorations_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| putting_away_Halloween_decorations_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i9 |
| putting_away_toys_305_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i4 |
| putting_dirty_dishes_in_sink_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i4 |
| putting_shoes_on_rack_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card40/gpu0/rent_i1 |
| putting_shoes_on_rack_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i3 |
| putting_shoes_on_rack_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i4 |
| putting_shoes_on_rack_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card41/gpu0/rent_i5 |
| putting_shoes_on_rack_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i6 |
| putting_shoes_on_rack_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card40/gpu0/rent_i7 |
| putting_shoes_on_rack_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| putting_shoes_on_rack_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i9 |
| re_shelving_library_books_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i5 |
| re_shelving_library_books_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i9 |
| rearrange_your_room_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card19/gpu0/rent_i1 |
| rearrange_your_room_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card18/gpu0/rent_i2 |
| rearrange_your_room_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card23/gpu0/rent_i3 |
| rearrange_your_room_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card24/gpu0/rent_i5 |
| rearrange_your_room_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i8 |
| rearrange_your_room_310_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i9 |
| scrubbing_bathroom_floor_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card12/gpu0/rent_i0 |
| scrubbing_bathroom_floor_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card8/gpu0/rent_i1 |
| scrubbing_bathroom_floor_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card90/gpu0/rent_i3 |
| scrubbing_bathroom_floor_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card65/gpu0/rent_i5 |
| scrubbing_bathroom_floor_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card15/gpu0/rent_i7 |
| set_up_a_coffee_station_in_your_kitchen_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| set_up_a_coffee_station_in_your_kitchen_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i5 |
| set_up_a_coffee_station_in_your_kitchen_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i6 |
| setting_mousetraps_301_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | sub12_setting_mousetraps_301 |
| setting_mousetraps_302_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | sub12_setting_mousetraps_302 |
| setting_mousetraps_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i2 |
| setting_mousetraps_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i3 |
| setting_mousetraps_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i5 |
| setting_mousetraps_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card30/gpu0/rent_i6 |
| setting_mousetraps_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i7 |
| setting_mousetraps_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i8 |
| setting_mousetraps_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i9 |
| sorting_books_on_shelf_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card50/gpu0/rent_i3 |
| sorting_bottles_cans_and_paper_305_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i4 |
| spraying_for_bugs_301_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | sub14_spraying_for_bugs_301 |
| spraying_for_bugs_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i7 |
| spraying_fruit_trees_301_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | sub14_spraying_fruit_trees_301 |
| spraying_fruit_trees_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card294/gpu0/rent_i2 |
| spraying_fruit_trees_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i3 |
| spraying_fruit_trees_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card293/gpu0/rent_i4 |
| spraying_fruit_trees_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i5 |
| spraying_fruit_trees_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i7 |
| spraying_fruit_trees_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card295/gpu0/rent_i8 |
| store_batteries_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i0 |
| store_batteries_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card84/gpu0/rent_i2 |
| store_batteries_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i3 |
| store_batteries_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i4 |
| store_batteries_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card95/gpu0/rent_i8 |
| store_batteries_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card66/gpu0/rent_i9 |
| store_honey_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i1 |
| store_honey_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card10/gpu0/rent_i2 |
| store_honey_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card11/gpu0/rent_i3 |
| store_honey_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i4 |
| store_honey_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| store_honey_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i6 |
| store_honey_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i7 |
| store_honey_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i8 |
| store_honey_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card10/gpu0/rent_i9 |
| store_produce_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i5 |
| sweeping_garage_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card57/gpu0/rent_i9 |
| tidying_bathroom_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i5 |
| tidying_bathroom_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i6 |
| tidying_bathroom_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i8 |
| tidying_bedroom_301_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | sub12_tidying_bedroom_301 |
| tidying_bedroom_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i1 |
| tidying_bedroom_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| tidying_bedroom_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i3 |
| tidying_bedroom_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i5 |
| tidying_bedroom_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i6 |
| tidying_bedroom_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i7 |
| tidying_living_room_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card295/gpu0/rent_i0 |
| tidying_living_room_302_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i1 |
| tidying_living_room_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card294/gpu0/rent_i2 |
| tidying_living_room_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i3 |
| tidying_living_room_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card296/gpu0/rent_i4 |
| tidying_living_room_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i5 |
| tidying_living_room_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card6/gpu0/rent_i6 |
| tidying_living_room_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card297/gpu0/rent_i8 |
| tidying_living_room_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card293/gpu0/rent_i9 |
| turning_on_radio_301_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | sub211h |
| turning_on_radio_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| turning_on_radio_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i3 |
| turning_on_radio_306_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card4/gpu0/rent_i5 |
| turning_on_radio_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card1/gpu0/rent_i6 |
| turning_on_radio_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i7 |
| turning_on_radio_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card5/gpu0/rent_i8 |
| turning_on_radio_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card2/gpu0/rent_i9 |
| turning_out_all_lights_before_sleep_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card3/gpu0/rent_i2 |
| turning_out_all_lights_before_sleep_310_0 | frozen<-p1g6-tree-run-at-commit | 0e8258a147 | rent4p_i9 |
| unloading_the_car_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card7/gpu0/rent_i6 |
| unloading_the_car_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card9/gpu0/rent_i9 |
| vacuuming_floors_301_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card19/gpu0/rent_i0 |
| vacuuming_floors_303_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card276/gpu0/rent_i2 |
| vacuuming_floors_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card79/gpu0/rent_i3 |
| vacuuming_floors_305_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card15/gpu0/rent_i4 |
| vacuuming_floors_307_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card79/gpu0/rent_i6 |
| vacuuming_floors_308_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card76/gpu0/rent_i7 |
| vacuuming_floors_309_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card21/gpu0/rent_i8 |
| vacuuming_floors_310_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card76/gpu0/rent_i9 |
| wash_a_baseball_cap_304_0 | frozen<-rented-GPU-run-at-commit | 0e8258a147 | card43/gpu0/rent_i3 |
