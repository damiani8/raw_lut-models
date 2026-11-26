# raw_lut models

Model files that RAW LUT Commander downloads on first use. They are too large for the app's own repository.

## enhance-1

Real-ESRGAN x2plus and x4plus by Xintao Wang et al. ([xinntao/Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN)), exported to ONNX
(NCHW float 0 to 1 in and out, any height and width; even sides for x2) by the app's `scripts/convert_enhance_models.py --real`.
The weights are unchanged and remain under Real-ESRGAN's BSD 3-Clause licence (`LICENSE`).

| File | SHA-256 |
|---|---|
| `realesrgan_x2plus.onnx` | `d5fb208e5cf835f37c75b375434eedf82541f63d640d9400fc5446b21443ab4d` |
| `realesrgan_x4plus.onnx` | `62cfa9ab1f763c7837eaafede22f739d59b89dae128b6fae0da0cd2248c20f6e` |

## masks-1

The Subject and Sky masks of Local adjustments (the app's `server/ai_masks.py` and `server/mask_models.py`). Both take 1 x 3 x N x N float,
sRGB-encoded and normalised with ImageNet's mean and deviation, and give 1 x 1 x N x N.

- `subject_birefnet_lite_fp16.onnx`: BiRefNet-lite by Zheng Peng et al. ([ZhengPeng7/BiRefNet](https://github.com/ZhengPeng7/BiRefNet)), the
  half-precision ONNX export of [onnx-community/BiRefNet_lite-ONNX](https://huggingface.co/onnx-community/BiRefNet_lite-ONNX) as it is; N = 1024,
  logits out. MIT licence (`LICENSE-BiRefNet`).
- `sky_u2net_fp16.onnx`: the sky U^2-Net by xiongzhu666 ([Sky-Segmentation-and-Post-processing](https://github.com/xiongzhu666/Sky-Segmentation-and-Post-processing)),
  from [JianyuanWang/skyseg](https://huggingface.co/JianyuanWang/skyseg), converted to half precision with `onnxconverter-common`
  (`convert_float_to_float16(..., keep_io_types=True)`); N = 320, 0 to 1 out. MIT licence (`LICENSE-sky-segmentation`).

| File | SHA-256 |
|---|---|
| `subject_birefnet_lite_fp16.onnx` | `d39b897ceb16ae654c1731f3dba0cf9b368d9cae74b5a57459b455cc8bfec402` |
| `sky_u2net_fp16.onnx` | `74d87f4a69378a610a6be662f859c38cfbdfdd75ff74bbfc54842965ed6fc9f7` |
