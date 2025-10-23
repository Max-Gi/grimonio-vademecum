# 🎭 Tabella Comparativa LoRA

Questa tabella raccoglie e confronta i LoRA che uso nei miei flussi ComfyUI.  
Ogni voce è annotata con stile, compatibilità, intensità consigliata e prompt trigger.  
È una mappa modulare per evocare stili, atmosfere e dettagli visivi.

| Nome LoRA         | Stile/Atmosfera     | Base Model Compatibile | Intensità Consigliata | Prompt Trigger         | Note Personali |
|-------------------|---------------------|-------------------------|------------------------|------------------------|----------------|
| Lightning XL      | Cinematico, realistico | SDXL                  | 0.6–0.8                | `cinematic`, `film still` | Ottimo con Juggernaut XL |
| RealFace Detailer | Ritratto, texture visiva | SDXL, SD 1.5         | 0.5–0.7                | `sharp face`, `real skin` | Migliora i volti in img2img |
| Anime Portraits   | Anime, stilizzato    | SD 1.5                 | 0.7–1.0                | `anime girl`, `cel shading` | Da testare con DreamShaper |
| Surreal Atmosphere| Onirico, astratto    | SDXL                   | 0.3–0.6                | `dreamscape`, `fog`       | In fase di esplorazione ✨ |

---

## 🧪 Note personali

- **Lightning XL**: perfetto per cinematici con Juggernaut XL, mantiene coerenza anche con pochi step.
- **RealFace Detailer**: utile in refining, soprattutto in flussi img2img con volti.
- **Anime Portraits**: risponde bene a prompt diretti, ma va dosato con CFG medio-alto.
- **Surreal Atmosphere**: da integrare quando sarai pronto a espandere la sezione texture e ambienti.

---

## 🔮 Prossimi test

- Combinazione Lightning + RealFace su SDXL
- Test img2img con Anime Portraits e DreamShaper
- Prompt atmosferici con Surreal Atmosphere

---

> _“Ogni LoRA è un catalizzatore. Ogni stile è una visione.”_
