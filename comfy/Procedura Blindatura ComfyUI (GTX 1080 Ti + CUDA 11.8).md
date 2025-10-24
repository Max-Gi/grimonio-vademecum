# 🛡️ Procedura Blindatura ComfyUI (GTX 1080 Ti + CUDA 11.8)

1. Apri il prompt dei comandi.

2. Vai nella cartella di ComfyUI:
   
   cd /d H:\ComfyUI

3. Attiva l’ambiente virtuale:

    call comfyenv\Scripts\activate.bat

4. Posizionati nella cartella checkpoints:

    cd checkpoints

5. Congela lo stato attuale dei pacchetti:

    pip freeze > requirements_locked.txt

6. Rinomina subito il file con la data del giorno:

    rename requirements_locked.txt requirements_locked_YYYY-MM-DD.txt

7. Archivia i file requirements_locked_YYYY-MM-DD.txt in H:\ComfyUI\checkpoints\.

8. Conserva anche i file .whl compatibili in H:\ComfyUI\checkpoints\wheels_locked\.

9. Per verificare che la GPU sia attiva, esegui:

    python -c "import torch; print(torch.cuda.is_available())"

    Se stampa True, la GPU è correttamente utilizzata.

10. Per ripristinare l’ambiente in futuro, usa:

    1. attivare l'ambiente:

        call H:\ComfyUI\comfyenv\Scripts\activate.bat

    2. Vai nella cartella dove hai il file congelato:

          cd H:\ComfyUI\checkpoints

    3. Lancia il comando di ripristino:

        pip install -r requirements_locked_2025-10-23.txt

    4. Verifica che la GPU sia attiva:

        python -c "import torch; print(torch.cuda.is_available())"


11. (Opzionale ma consigliato) Crea un file di log log_YYYY-MM-DD.txt con:

    Versioni chiave (torch, torchvision, torchaudio)

    Stato CUDA

    Una nota evocativa sul checkpoint (es. “Il portale GPU è stabile, il sigillo è compiuto”).

📄 Esempio di log_2025-10-23.md

    # 📜 Log del checkpoint – 23 Ottobre 2025

    ## Informazioni tecniche
    - Ambiente: `comfyenv`
    - GPU: NVIDIA GTX 1080 Ti
    - CUDA: 11.8
    - Torch: 2.4.1+cu118
    - TorchVision: 0.19.1+cu118
    - TorchAudio: 2.4.1+cu118
    - Numpy: 1.26.4
    - Python: 3.10

    ## Verifica GPU
    ```bash
    python -c "import torch; print(torch.cuda.is_available())"


📂 Mini Ripasso DOS

1. **cd [cartella]**
     - Cambia cartella.
    - Esempio: `cd ComfyUI`

2. **cd /d [unità:\cartella]**
    - Cambia cartella **e** unità in un colpo solo.
    - Esempio: `cd /d H:\ComfyUI`

3. **dir**
    - Elenca i file e le cartelle presenti nella directory corrente.

4. **cls**
    - Pulisce lo schermo del prompt dei comandi.

5. **rename [vecchio] [nuovo]**
    - Rinomina un file.
    - Esempio: `rename requirements_locked.txt requirements_locked_2025-10-23.txt`

6. **move [origine] [destinazione]**
    - Sposta file o cartelle.
    - Esempio: `move H:\checkpoints H:\ComfyUI\`

7. **copy [origine] [destinazione]**
    - Copia file da una posizione a un’altra.
    - Esempio: `copy requirements_locked_2025-10-23.txt H:\Backup\`

8. **del [file]**
    - Cancella un file.
    - Esempio: `del requirements_locked.txt`

9. **exit**
    - Chiude il prompt dei comandi.


