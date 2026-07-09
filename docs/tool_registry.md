tools:
  - name: predict_fence_mask
    status: active
    owner_file: src/smartnest/pipelines/predict_fence_mask.py

    purpose: >
      入力画像列から金網マスクを推論し、各画像に対応するマスク画像を保存する。

    inputs:
      - name: input_images
        type: directory
        path_source: path_registry.data.experiment_images
        file_pattern: "*.png"
        shape: "[N, H, W, 3]"
        dtype: uint8
        color_order: RGB
        description: "実験ごとの入力画像列"

      - name: model_path
        type: file
        path_source: path_registry.models.fence_unet_best
        description: "学習済みU-Netモデル"

    outputs:
      - name: masks
        type: directory
        path_source: path_registry.outputs.fence_masks
        file_pattern: "*.png"
        shape: "[N, H, W]"
        dtype: uint8
        value_range: "0 or 255"
        description: "金網領域を255、それ以外を0とする2値マスク"

    command:
      example: >
        python -m smartnest.pipelines.predict_fence_mask
        --config configs/inference.yml

    notes:
      - "入力画像と出力マスクは同じ枚数であること。"
      - "画像サイズが大きい場合は内部でタイル分割する。"

    validation:
      - "出力枚数が入力枚数と一致する"
      - "マスクの値が0または255のみ"

