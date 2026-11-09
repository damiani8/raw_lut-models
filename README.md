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
