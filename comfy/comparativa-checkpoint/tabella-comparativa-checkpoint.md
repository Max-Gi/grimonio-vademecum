# 🧮 Tabella Comparativa Checkpoint

Questa sezione raccoglie e confronta i principali checkpoint utilizzati nei miei flussi ComfyUI.  
Ogni voce è annotata con stile, compatibilità LoRA, range CFG, sampler consigliato e compatibilità GPU.  
È una base modulare per test, rituali e prompt futuri.

---

| 🧠 Nome             | 🧬 Base Model | 🎨 Stile           | 🧿 LoRA Compatibili         | ⚙️ CFG Range | 🌀 Sampler Consigliato | 💾 Compatibilità GPU     |
|--------------------|--------------|--------------------|-----------------------------|-------------|------------------------|--------------------------|
| Juggernaut XL      | SDXL         | Cinematico         | Lightning, RealFace         | 4–7         | DPM++ 2M Karras        | ✅ Fluido su 1080 Ti     |
| DreamShaper v7     | SD 1.5       | Fantasy/Real       | Anime, Portraits            | 7–11        | Euler a                | ✅ Ottimo su 1080 Ti     |
| RealisticVision    | SD 1.5       | Fotorealistico     | FaceDetailer                | 5–9         | DPM++ SDE              | ✅ Ottimo su 1080 Ti     |
| Anything V5        | SD 1.5       | Anime/Illustrativo | Anime, Detailer             | 6–10        | Euler a                | ✅ Leggero e stabile     |
| MeinaMix V11       | SD 1.5       | Anime/Realistico   | Stylized, Portraits         | 7–10        | DPM++ 2M Karras        | ✅ Fluido su 1080 Ti     |
| Counterfeit V3.0   | SD 1.5       | Semi-realistico    | FaceDetailer, FX LoRA       | 6–9         | DPM++ SDE              | ✅ Nessun problema       |
| SDXL Lightning     | SDXL         | Cinematico/veloce  | RealFace, Turbo LoRA        | 3–6         | DPM++ 2M Karras        | ⚠️ OK con risoluzioni medie |

🧪 Note rituali

Anything V5: ottimo per stili anime, molto reattivo ai prompt dettagliati.

MeinaMix: eccellente per ritratti e blending tra anime e realismo.

Counterfeit: versatile per ambientazioni semi-realistiche, ottimo con LoRA FX.

SDXL Lightning: sorprendentemente leggero, ma da usare con risoluzioni moderate.

“Ogni checkpoint è una chiave. Ogni chiave apre una visione diversa.”