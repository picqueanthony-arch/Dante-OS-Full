# Pourquoi faire confiance à Dante OS

**[Français](#français) · [English](#english)**

## Français

Dante OS n'est pas open source. Voici pourquoi, ce que l'appli ne fait pas, et comment **vérifier toi-même** ce qu'elle fait, sans avoir à croire qui que ce soit sur parole.

### Pourquoi le code n'est pas publié

- Dante OS est le travail d'**une seule personne**, depuis un an. C'est **Dante Pro** (5,99 €, une seule fois) qui le fait vivre.
- Publier le code permettrait à n'importe qui de **republier des copies modifiées** sous un autre nom (avec de la pub, ou pire), et plus personne ne saurait laquelle est la vraie.
- L'appli touche au système quand tu actives le root : je préfère garder la main sur ce qui est distribué. Le Guide de l'appli le dit aussi, dans « Transparence totale ».

### Ce que Dante OS ne fait pas

- **Pas de publicité**, **pas d'outil de statistiques**, **pas de rapport de plantage**.
- **Pas de compte obligatoire.**
- Il ne demande **ni la localisation, ni les SMS, ni le journal d'appels**.
- **Aucune commande root sans ton accord.** Sans root, aucune n'est jamais lancée.
- Il ne modifie **pas les partitions système**, ne remplace aucun fichier d'Android et n'installe rien dans le système.
- La sauvegarde automatique d'Android est désactivée pour l'appli : tes réglages ne partent pas dans un cloud.

### Presque tout marche sans root

Le launcher, le dock, la Ruche, Dante FX, Dante Engine, Dante IA, Gateway, les actus, SSH, Fichiers, Maison… marchent **sans root**. Le root n'ouvre que le pare-feu, le filtre DNS, XRay, le processeur, la batterie et Dante Core.

### Ce qui part sur Internet

Seulement ce que tu utilises ou configures toi-même :

- **Tes sources** : les flux, API et serveurs que tu ajoutes reçoivent les requêtes que tu leur destines.
- **Dante IA** : le modèle se télécharge une fois depuis Hugging Face, quand tu le demandes. Ensuite il tourne **sur le téléphone** : tes conversations n'en sortent pas. Si tu laisses ses outils Internet allumés, une recherche part vers DuckDuckGo, Wikipédia ou Open-Meteo, sans aucun identifiant.
- **Filtre DNS** (root) : les listes publiques de blocage se téléchargent depuis leurs sites.
- **Magasin de thèmes** (facultatif) : regarder et installer ne demande aucun compte. Pour publier, noter ou signaler, tu te connectes avec Google.
- **Clé Dante Pro** : à l'activation, la clé et une **empreinte du téléphone** (jamais son identifiant Android) partent une fois au serveur Dante Pro (Supabase, en Europe), pour qu'une clé serve sur 3 téléphones au plus. Ensuite elle se vérifie **sans Internet**.
- **Dante Core** (root) : à ta demande, l'image Debian officielle (images.linuxcontainers.org, empreinte vérifiée), Kali (kali.download), VS Code (GitHub) et les paquets des dépôts officiels. Claude n'est utilisé qu'avec **ta propre clé** Anthropic, si tu la choisis.

Le détail complet est dans la [politique de confidentialité](https://picqueanthony-arch.github.io/dante-os-confidentialite/full.html).

### Vérifie toi-même

1. **Le fichier** : son empreinte SHA-256 doit être celle publiée avec chaque version (fichier `.sha256` dans [Releases](../../releases)). Pour la 5.0.0 :
   `9349e459f603bd8cface2972fd0a696c73f0215c180840c2a1c1cf3fec49fe74`
   ```
   sha256sum Dante-OS-5.0.0-Full.apk
   ```
2. **La signature** : toutes les versions sont signées avec le même certificat. Android refuse une mise à jour signée par quelqu'un d'autre.
   `78:FE:D6:BF:09:A3:EF:4D:CD:B7:C2:5F:F8:8E:E5:DA:EF:36:85:71:FA:AE:72:88:BE:C4:4C:4E:6C:1B:82:D7`
   ```
   apksigner verify --print-certs Dante-OS-5.0.0-Full.apk
   ```
3. **Les antivirus** : dépose l'APK sur [VirusTotal](https://www.virustotal.com), ou cherche son empreinte SHA-256.
4. **Les autorisations** : Réglages Android ▸ Applications ▸ Dante OS ▸ Autorisations. Le Guide de l'appli explique chacune, une par une.
5. **Le trafic** : un outil comme [PCAPdroid](https://github.com/emanuele-f/PCAPdroid) (sans root) montre chaque connexion de chaque appli.
6. **Les règles root** : avec le pare-feu ou le filtre DNS allumé, `iptables -S | grep DANTE` et `iptables -t nat -S | grep DANTE` montrent les seules chaînes que Dante pose (DANTE_FW, DANTE_DNS…). Elles sont retirées quand tu les coupes.
7. **Le Guide intégré** : la section « Transparence totale » liste ce que Dante lit, ce qu'il modifie et ce qu'il envoie.

### Une question ?

Viens la poser sur [Discord](https://discord.gg/XcstyCwGuP), ou écris à danteantpi@proton.me.

---

## English

Dante OS is not open source. Here is why, what the app does not do, and how to **check for yourself** what it does, without taking anyone's word for it.

### Why the code is not published

- Dante OS is the work of **one person**, over the past year. **Dante Pro** (€5.99, one-time) keeps it alive.
- Publishing the code would let anyone **re-publish modified copies** under another name (with ads, or worse), and nobody could tell which one is real.
- The app touches the system when you enable root: I prefer to stay in control of what gets distributed. The in-app Guide says so too, in "Total transparency".

### What Dante OS does not do

- **No ads**, **no analytics**, **no crash reports**.
- **No account required.**
- It does **not** ask for location, SMS or the call log.
- **No root command without your consent.** Without root, none is ever run.
- It does **not** modify system partitions, replaces no Android file and installs nothing into the system.
- Android's automatic backup is disabled for the app: your settings don't go to a cloud.

### Almost everything works without root

The launcher, the dock, the Hive, Dante FX, Dante Engine, Dante IA, Gateway, news, SSH, Files, Home… work **without root**. Root only opens the firewall, the DNS filter, XRay, CPU, battery and Dante Core.

### What goes to the Internet

Only what you use or set up yourself:

- **Your sources**: the feeds, APIs and servers you add receive the requests you send them.
- **Dante IA**: the model is downloaded once from Hugging Face, when you ask for it. Then it runs **on the phone**: your conversations never leave it. If you keep its Internet tools on, a search goes to DuckDuckGo, Wikipedia or Open-Meteo, without any identifier.
- **DNS filter** (root): public blocklists are downloaded from their sites.
- **Theme store** (optional): browsing and installing needs no account. To publish, rate or report, you sign in with Google.
- **Dante Pro key**: on activation, the key and a **fingerprint of the phone** (never its Android ID) are sent once to the Dante Pro server (Supabase, in Europe), so a key works on 3 phones at most. After that it is checked **offline**.
- **Dante Core** (root): on request, the official Debian image (images.linuxcontainers.org, checksum verified), Kali (kali.download), VS Code (GitHub) and packages from the official repositories. Claude is only used with **your own** Anthropic key, if you choose it.

Full details are in the [privacy policy](https://picqueanthony-arch.github.io/dante-os-confidentialite/full.html).

### Check for yourself

1. **The file**: its SHA-256 must match the one published with each version (`.sha256` file in [Releases](../../releases)). For 5.0.0:
   `9349e459f603bd8cface2972fd0a696c73f0215c180840c2a1c1cf3fec49fe74`
   ```
   sha256sum Dante-OS-5.0.0-Full.apk
   ```
2. **The signature**: every version is signed with the same certificate. Android refuses an update signed by someone else.
   `78:FE:D6:BF:09:A3:EF:4D:CD:B7:C2:5F:F8:8E:E5:DA:EF:36:85:71:FA:AE:72:88:BE:C4:4C:4E:6C:1B:82:D7`
   ```
   apksigner verify --print-certs Dante-OS-5.0.0-Full.apk
   ```
3. **Antivirus**: drop the APK on [VirusTotal](https://www.virustotal.com), or search its SHA-256.
4. **Permissions**: Android Settings ▸ Apps ▸ Dante OS ▸ Permissions. The in-app Guide explains each one.
5. **Traffic**: a tool like [PCAPdroid](https://github.com/emanuele-f/PCAPdroid) (no root) shows every connection of every app.
6. **Root rules**: with the firewall or DNS filter on, `iptables -S | grep DANTE` and `iptables -t nat -S | grep DANTE` show the only chains Dante adds (DANTE_FW, DANTE_DNS…). They are removed when you turn them off.
7. **The in-app Guide**: its "Total transparency" section lists what Dante reads, changes and sends.

### A question?

Ask it on [Discord](https://discord.gg/XcstyCwGuP), or write to danteantpi@proton.me.
