# 🧮 Tabella Comparativa Checkpoint

Questa tabella raccoglie e confronta i principali checkpoint utilizzati nei miei flussi ComfyUI.  
Ogni voce è annotata con stile, compatibilità LoRA, range CFG e sampler consigliato.  
È una base modulare per test, rituali e prompt futuri.

| Nome           | Base Model | Stile         | LoRA Compatibili         | CFG Range | Sampler Consigliato |
|----------------|------------|---------------|--------------------------|-----------|----------------------|
| Juggernaut XL  | SDXL       | Cinematico    | Lightning, RealFace      | 4–7       | DPM++ 2M Karras      |
| DreamShaper v7 | SD 1.5     | Fantasy/Real  | Anime, Portraits         | 7–11      | Euler a              |
| RealisticVision| SD 1.5     | Fotorealistico| FaceDetailer             | 5–9       | DPM++ SDE            |

---

## 🧪 Note personali

- **Juggernaut XL**: ottimo per cinematici con pochi step, molto compatibile con LoRA Lightning.
- **DreamShaper v7**: versatile, risponde bene a prompt lunghi e stili misti.
- **RealisticVision**: eccellente per volti e texture, da testare con FaceDetailer e upscaler.

---

## 🔮 Prossimi test

- Confronto tra LoRA Lightning e RealFace su Juggernaut XL
- Test img2img con RealisticVision e CFG variabile
- Prompt negativi su DreamShaper per refining

---

> _“Ogni checkpoint è un artefatto. Ogni test è un rituale.”_
