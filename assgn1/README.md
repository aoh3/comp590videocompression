Approach:

- One-pass lossless arithmetic compression of each pixel in frame order.
- Prediction: use prior-frame pixel value as context (temporal prediction).
- For each pixel, encode the difference from prediction (previous frame + local spatial predictor).
- Uses 256 independent adaptive `VectorCountSymbolModel<u8>` contexts.
- Updates counts for each difference symbol as data is processed.

How to run:

```bash
cd "c:\\Users\\aidan\\Documents\\School\\UNC\\2025-2026\\Sem 2\\COMP 590\\COMP590 A1 Compression Challenge\\comp590videocompression\\assgn1"
cargo run --release -- -count 8
```

The program expects `data/bourne.mp4` to exist (it is present in this repo).

Reported output (measured):

- `8 frames encoded, average size (bits): 3884074, compression ratio: 4.27`

Earlier sample output (reference):

- Frame sizes: 11892328, 4158001, 4226062, 5155903, 5885121, 5922883, 5907563, 5556315
- Average size: 6,088,026 bits/frame
- Compression ratio: 2.72


