# Design Phase

- Which data can be locally processed / stored? (no privacy leak for the user)

- Which data must be processed / stored remotely? (possible data leak)

  - how can the following steps possibly help:

    - encryption

    - anonymisation

    - pseudonymisation

    - organisational steps

      - -> data minimisation steps (SDM)

      ​

  ### Dataflow and other components (backend and frontend)(Datenflüsse und andere Komponenten)

- Data recieving problematically? (Datenabruf problematisch? (Metadata & PKR))

- Data sending problematically? (Datenversand problematisch?)

- Data processing problematically? (Datenverarbeitung problematisch?)

- Interaction with 3rd parties? (Interaktion mit dritten? (z.B. beim Bezalvorgang)) 

  - No? (z.B. bei Bezahlvorgang (Barzahlung = unproblematisch))
  - Yes? (z.B. beim Bezahlvorgang (paypal / Kreditinstitut etc.))
    - back to point -> "how can the following steps possibly help?"

### Interveneabality enforcement (Intervenierbarkeit sicherstellen)

- which extend functionality is necessary? (Welche zusätzliche Funktionalität wird benötigt?)
  - Contact person (Ansprechpartner)
- availability (Verfügbarkeit (sowohl SDM als auch technisch))