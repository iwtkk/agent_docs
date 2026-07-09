"""
Tool: predict_marmoset_mask

Purpose:
    アノテ済みマーモセット画像に対し、GTの bbox（および可視 keypoint）を SAM3 の
    プロンプトとして与え、各画像1個体の2値マスクを生成・保存する。

Inputs:
    images:
        type: directory
        shape: [N, H, W, 3]
        dtype: uint8
        color_order: RGB

    annotation:
        type: file
        format: COCO json (bbox [x,y,w,h], keypoints [x,y,v] x 20)

    checkpoint:
        type: file
        format: PyTorch (base sam3.pt / facebook/sam3)

    bpe:
        type: file
        format: BPE vocab (.txt.gz)

Outputs:
    masks:
        type: directory
        shape: [N, H, W]
        dtype: uint8
        value_range: 0 or 255

    overlay:
        type: directory (optional)
        description: マスク+bbox 重畳の確認用PNG

Side effects:
    - outputs/marmoset_masks/ にPNGファイルを保存する
    - outputs/marmoset_overlay/ に確認用PNGを保存する（save_overlay=true 時）
    - outputs/logs/predict_marmoset_mask.log にログを書く

Registry:
    agent_docs/docs/tool_registry.yml#predict_marmoset_mask
"""
