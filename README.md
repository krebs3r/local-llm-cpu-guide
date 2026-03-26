# CPU Platform Comparison – PCIe Lanes & LLM Multi-GPU

An interactive overview of **125+ AMD and Intel desktop CPUs** across all major platforms, with a focus on PCIe lane counts, multi-GPU configurations, and suitability for running **local Large Language Models (LLMs)**.

### Usage

Clone or download the repo and open `index.html` in any browser. Both files are required:

```
index.html   – app
cpus.js      – CPU data
```

No installation, no build step, no server needed.

Or use the live demo:

👉 **[krebs3r.github.io/local-llm-cpu-guide](https://krebs3r.github.io/local-llm-cpu-guide/)**

### Platforms Covered

| Platform | Manufacturer | PCIe Gen | CPU Lanes | Max GPU Config |
|----------|-------------|----------|-----------|----------------|
| LGA1200 | Intel | 3.0 / 4.0 | 16–20 | x8/x8 Dual |
| LGA1700 | Intel | 5.0 / 4.0 | 20 | x8/x8 Dual |
| LGA1851 | Intel | 5.0 | 20 | x8/x8 Dual |
| X299 | Intel HEDT | 3.0 | 28–48 | x16/x16/x16 Triple (48-lane) |
| AM4 | AMD | 3.0 / 4.0 | 24 | x8/x8 Dual |
| AM5 | AMD | 5.0 | 28 | x8/x8 Dual |
| X399 | AMD HEDT | 3.0 | 64 | x16/x16/x16 Triple |
| TRX40 | AMD HEDT | 4.0 | 72 | x16/x16/x16 Triple |
| TRX50 | AMD HEDT | 5.0 | 92 | x16/x16/x16 Triple |

### Features

- **Platform overview** with chipset-level dual/triple GPU configuration details
- **CPU list** with filterable platform, generation, and search
- **CPU comparison** – select up to 4 CPUs and compare specs side-by-side (cores, clock, TDP, PCIe, Cinebench, price, LLM rating), with best values highlighted
- **URL sharing** – comparison state is encoded in the URL, shareable via copy-link button
- **PNG export** – export the comparison table as a PNG image
- **Official product page links** – every CPU links directly to AMD product pages or Intel ARK
- **Launch MSRP & release date** for all 125 CPUs
- **LLM suitability rating** for every CPU (single GPU → triple GPU use cases)
- **Cinebench R23 & R24** single-core and multi-core scores for 120+ CPUs
- **iGPU info** for CPUs with integrated graphics (architecture, EU/CU count, clock, API support)
- **Estimated used market prices** (March 2026, German market) with color-coded price tiers
- **GE / low-TDP variants** included for energy-efficient builds
- **Touch-friendly design** – optimized for mobile and tablet
- **Glassmorphism UI** with dark mode and subtle background gradients
- **DE / EN** language toggle

### Why PCIe lanes matter for LLMs

Running large language models locally typically requires a dedicated GPU with significant VRAM. When running **multiple GPUs** to pool VRAM:

- **Single GPU**: PCIe lane count is irrelevant after model load. Even x4 lanes are fine for inference.
- **Dual GPU**: Minimum x8/x8 per GPU. Consumer platforms (AM4/AM5/LGA17xx) can do this on Z/X chipset boards.
- **Triple GPU**: Only possible on HEDT platforms (X399, TRX40, TRX50, X299 with 44+ lanes). Consumer platforms are structurally limited.

### Contributing

Pull requests are welcome! If you spot incorrect specs, missing CPUs, or outdated prices, feel free to open an issue or PR.

CPU data lives in `cpus.js` – easy to edit without touching the app logic.

**What to contribute:**
- Corrected or updated CPU specs / prices
- Missing CPU models (e.g. Xeon, Ryzen Pro, older generations)
- Additional platforms (e.g. TR5 / WRX90 Pro lineup)

### Tech

- `index.html` – React 18 + Tailwind CSS via CDN, no build step
- `cpus.js` – all CPU specs, benchmark scores, LLM ratings and launch data as plain JS

---

## License

MIT – do whatever you want, attribution appreciated.
