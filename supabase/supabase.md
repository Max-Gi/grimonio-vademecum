# 📜 Supabase — Il cerchio dei dati

Ogni tabella è un altare, ogni policy un sigillo di accesso.  
Qui si custodiscono gli eventi, pronti a manifestarsi nel frontend.

---

## 🔧 Setup rituale

1. **Creazione progetto**
   - Avviare da [app.supabase.com](https://app.supabase.com)
   - Annotare **Project URL** e **anon key**
   - 👉 Questi due valori sono le chiavi d’accesso al cerchio

2. **Configurazione ambiente**
   ```env
   VITE_SUPABASE_URL=https://<tuo-progetto>.supabase.co
   VITE_SUPABASE_ANON_KEY=<chiave_anon>

Riavviare npm run dev per caricare le variabili

👉 Senza queste variabili, il client non sa a quale altare rivolgersi

🏛️ **Creazione tabella eventi**

create table public.eventi (
  id uuid primary key default gen_random_uuid(), -- identificatore unico
  titolo text not null,                          -- titolo evento
  descrizione text,                              -- testo descrittivo
  data_inizio date,                              -- inizio evento
  data_fine date,                                -- fine evento
  data_testo text,                               -- data “editoriale” (es. “Primavera 2025”)
  luogo text,                                    -- luogo evento
  immagine_url text,                             -- link immagine
  link_esterno text,                             -- link a sito esterno
  created_at timestamp with time zone default now()
);

✨ Nota editoriale: ogni campo ha un peso semantico. data_testo serve a dare dignità a date non standard.

🔒 **Policy e sicurezza**

1. Abilitare RLS (Row Level Security)

    Sql: alter table public.eventi enable row level security;

2. Policy di lettura pubblica

    Sql: create policy "Allow public read access"
         on public.eventi
         for select
         to public
         busing (true);

👉 Tutti possono leggere gli eventi, nessuno deve loggarsi per vederli.     

3. **Variante avanzata**

    Sql: -- Lettura pubblica
            create policy "Allow public read access"
            on public.eventi
            for select
            to public
            using (true);

        -- Inserimento solo per utenti autenticati
            create policy "Allow insert for authenticated"
            on public.eventi
            for insert
            to authenticated
            with check (auth.uid() is not null);

👉 Così chiunque può leggere, ma solo utenti registrati possono inserire.

🧪 **Inserimento dati di prova**

    insert into public.eventi (titolo, descrizione, data_inizio, luogo, immagine_url, link_esterno)
    values
    ('Festival della Chitarra', 'Concerti e workshop con artisti internazionali', '2025-07-10', 'Teatro Comunale', 'https://...', 'https://festival-chitarra.it'),
    ('Marino Sotterranea', 'Visite guidate alle grotte storiche', '2025-08-20', 'Centro Storico', null, null);

🔍 **Debug rituale**

    Nel componente React:

    const { data, error } = await supabase
        .from('eventi')
        .select('*')
        .order('data_inizio', { ascending: true });

    console.table(data);
    console.log('Errore Supabase:', error);


    - [] → tabella vuota o progetto sbagliato

    - error → problema di policy o nome tabella

    - array di record → i tuoi eventi sono pronti a manifestarsi

🧹 **Pulizia e manutenzione**

    Svuotare la tabella:

        Sql: delete from public.eventi;


    ✨  Quando ha senso svuotare la tabella

        Reset di test: se hai popolato la tabella con dati fittizi o duplicati e vuoi ripartire da zero.

        Cambio di schema: se hai modificato i campi (es. aggiunto categoria) e i vecchi record non rispettano più la nuova struttura.

        Debug: se vuoi verificare che il frontend gestisca correttamente lo stato “nessun evento disponibile”.

    ⚠️ Quando NON farlo

        In produzione, dove i dati sono reali e preziosi.

        Se vuoi mantenere la cronologia degli eventi.

        Se i tuoi record sono già coerenti con lo schema e non ti danno problemi.

    🌱 Alternativa più “editoriale”

        Invece di cancellare tutto, puoi:

        Aggiornare i record con UPDATE per correggere valori.

        Eliminare solo i fittizi con DELETE ... WHERE titolo = 'Sagra dell'Uva'.

        Archiviare: aggiungere un campo stato (es. bozza, pubblicato, archiviato) e filtrare solo quelli pubblicati.

        Aggiungere un nuovo campo:

        Sql: alter table public.eventi add column categoria text;

👉 Ogni modifica è un sigillo inciso, non una correzione.

**Ultimo sigillo inciso: Secondo sigillo: il cerchio dei dati è stato tracciato**

---

**Step-by-step testing from root**

Questo è un percorso chiaro e ripetibile per testare lo script dalla root, poi archiviarlo nel Grimonio.


✨ Con questa struttura, la sezione Supabase del tuo grimonio è completa, annotata e coerente con lo stile rituale.  

    Setup → Tabella → Policy → Debug → Pulizia

**Preparazione dei file in root**

1. Copia script: carica in root test-ping_supabase.php (versione aggiornata con file_exists e logging).
2. Copia JSON: carica in root projects.json (la versione valida usata in produzione).
3. Permessi file: imposta 644 per entrambi, così PHP/Apache possono leggerli. Nella Root, però, non c'è un .htaccess,       ma permette di eseguire questi file di test.

**Esecuzione del test**

    Apri da browser: visita

    https://www.turladbrothers.com/test-ping_supabase.php

    Output atteso:

    A. Nessun errore a schermo (o messaggi di debug chiari se hai lasciato il check).

    B. Creazione cartelle log_ok e log_errors (solo se non esistono).

    C. Scrittura del file di log in una delle due cartelle.

    D. Notifica Telegram con esito e percorso del log.

**Chiusura e pulizia**

1. Rimuovi i file di test: elimina test-ping_supabase.php e projects.json dalla root.

2. Mantieni ordine: se non servono, elimina anche log_ok e log_errors in root (lo script le ricrea quando ti servono).

3. Ripristina sicurezza: rimuovi l’eccezione <Files "test-ping_supabase.php"> dal .htaccess root. NOn occorre.

4. Annota nel Grimonio: titolo, versione script, struttura projects.json, regole .htaccess usate, e il ciclo di verifica/esito.