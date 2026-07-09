"""
Tool: predict_fence_mask

Purpose:
    入力画像列から金網マスクを推論し、各画像に対応する2値マスクを保存する。

Inputs:
    input_images:
        type: directory
        shape: [N, H, W, 3]
        dtype: uint8
        color_order: RGB

    model_path:
        type: file
        format: PyTorch state_dict

Outputs:
    masks:
        type: directory
        shape: [N, H, W]
        dtype: uint8
        value_range: 0 or 255

Side effects:
    - outputs/masks/ にPNGファイルを保存する
    - logs/predict_fence_mask.log にログを書く

Registry:
    docs/agent/tool_registry.yml#predict_fence_mask
"""
