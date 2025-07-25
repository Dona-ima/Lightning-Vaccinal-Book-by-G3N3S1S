# ⚡ Lightning Vaccinal Book

## 👥 Équipe G3N3S1S

- **AGBALE Bellevie** – IU/UX Designer 
- **AGBOTON Ariane** – Développeur Backend – https://github.com/Dona-ima
- **AHOGNISSE Ariel** – Développeur Backend et mobile – https://github.com/arielcarmen
- **EDAYE DOKOUI Béni-Christ** – Développeur Frontend –
- **HOUEDANOU Gildas** – Ingénieur Informatique  

---

## 📄 Résumé Exécutif

**Lightning Vaccinal Book** est une application de carnet de vaccination numérique permettant aux patients de conserver leurs preuves de vaccination sur une plateforme sécurisée. Elle aide les centres de santé à certifier les vaccinations, et les contrôleurs à les vérifier rapidement à l’aide de QR codes.

Notre solution lutte contre les faux carnets, facilite le suivi vaccinal, et renforce la sécurité sanitaire, notamment dans des contextes sensibles comme les déplacements ou les contrôles de santé.

---

## ❗ Problématique Identifiée

### 🔍 Le problème

Dans de nombreux pays, les carnets de vaccination sont encore **physiques, fragiles et facilement falsifiables**. Cela nuit à la fiabilité des données, complique les contrôles, et représente un frein à la sécurité sanitaire (ex: COVID-19, fièvre jaune).

> En Afrique de l’Ouest, **1 personne sur 3** ne peut pas présenter un carnet complet ou lisible.

### 👥 Public cible

Notre solution s’adresse à trois types d’utilisateurs :
- **Les patients** : pour conserver leurs certificats sans risque de perte ou de dégradation.
- **Les centres de santé** : pour délivrer des preuves de vaccination **authentiques et infalsifiables**.
- **Les contrôleurs** (hôpitaux, frontières, écoles) : pour vérifier rapidement les certificats.

Les patients ont besoin d’un moyen fiable de conserver leur carnet de vaccination, sans risque de perte ou de dégradation. Les centres de santé, de leur côté, doivent pouvoir délivrer des preuves authentiques et infalsifiables des vaccinations administrées. Enfin, les contrôleurs (aux frontières, dans les écoles ou dans les hôpitaux) ont besoin d’un outil simple et rapide pour vérifier l’authenticité des carnets de vaccination.
Aujourd’hui, la perte ou la dégradation des carnets vaccinaux est fréquente, notamment en Afrique de l’Ouest où environ une personne sur trois ne peut présenter un carnet complet ou en bon état. Ce manque de traçabilité entraîne des difficultés d’accès à certains services de santé, d’éducation ou de mobilité. À cela s’ajoute la prolifération de faux certificats, qui constitue une menace grave pour la sécurité sanitaire, surtout en période d’épidémies comme le COVID-19 ou la fièvre jaune.
Il est donc essentiel de proposer une solution numérique, portable et sécurisée, qui permette à chaque individu de disposer d’un carnet vaccinal fiable et facilement vérifiable. C’est dans ce contexte que notre application apporte une réponse concrète, adaptée au terrain, en renforçant la confiance entre patients, centres et autorités.


---

## ✅ Solution Proposée

Le projet **Carnet Vaccinal Lightning** a pour objectif de développer un système numérique sécurisé permettant d’enregistrer, conserver et vérifier les preuves de vaccination. En s’appuyant sur le réseau Lightning et la cryptographie, ce système assure l’authenticité des certificats vaccinaux sans recourir à une infrastructure centralisée ni à la gestion classique de comptes utilisateur.
Chaque individu dispose d’une identité sécurisée basée sur une clé publique Lightning, garantissant la confidentialité et la sécurité des données personnelles. Le projet vise à fournir une solution légère, rapide et adaptée aux contextes où la connectivité internet est limitée, notamment dans des régions comme le Bénin.


---

## 🧩 Fonctionnalités clés

### 🔐 Preuve de vaccination sécurisée et portable
Après validation de sa vaccination, le patient reçoit une certification qui est ajoutée à son carnet vaccinal numérique. Il peut ensuite générer un QR code à partir de son carnet pour présenter une preuve de vaccination infalsifiable et facilement vérifiable.


### 📶 Vérification rapide et hors ligne
Les contrôleurs peuvent vérifier l’authenticité d’un certificat sans connexion internet, simplement en scannant le QR code. La validité est confirmée localement à partir de la signature cryptographique.


### 📅 Prise de rendez-vous simple et sécurisée
Le patient crée un compte et soumet une demande de rendez-vous en précisant :
- son **numéro d’identification national**
- le **type de vaccin souhaité**
- une **date préférée**

Le jour du rendez-vous, il confirme son identité avec son numéro d’identification national présent sur sa **carte nationale**.

---

## 🛠️ Mise en œuvre technique

### 🏗️ Architecture générale

#### 🧑‍💻 Côté Patient
- Application Mobile 
- Création de compte sur la plateforme
- Fonctions :
  - Prise de rendez-vous
  - Consultation du carnet
  - Génération de QR code du carnet
- Stockage **local** (navigateur) ou image QR

#### 🏥 Côté Centre de santé
- Interface web sécurisée
- Fonctions :
  - Réception des demandes de rendez-vous
  - Validation / Rejet / Modification
  - Enregistrement de vaccinations
  - Signature des preuves avec **clé privée**

#### 🕵️ Côté Contrôleur
- Application mobile ou web
- Scan QR code patient
- Vérification :
  - Signature cryptographique
  - Clé publique présente dans la liste blanche
- **Fonctionne hors ligne**

#### 🔗 Échange de données
- Messages sécurisés (JSON) contenant :
  ```json
  {
    "type": "vaccine_request",
    "N° d'identification": "1245505",
    "vaccine": "COVID-19",
    "preferred_date": "2025-07-12T09:00:00",
    "timestamp": 1721000000
  }
- Signature ECDSA (secp256k1)

---

## 🧪 Technologies utilisées

| Composant         | Technologie              |
|-------------------|--------------------------|
| **Frontend**      | HTML, CSS, JavaScript    |
| **Backend**       | FastAPI                  |
| **Base de données** | Firestore             |
| **Design UI/UX**  | Figma                    |
| **APIs/Services** | Lightning_pb2_grpc       |

---

## ⚙️ Ressoures

- Serveur backend : https://github.com/arielcarmen/python-lnd-connect
- Serveur frontend : 
- Application mobile : https://github.com/arielcarmen/vaccination_book_app
- Maquettes : https://www.figma.com/design/dGGxc8iEpWnEztIxOaZSHq/Book-Vaccinal-Lightning?node-id=85-3&p=f&t=GL4wf0vt7T49OIJp-0
- Application (generated) : https://drive.google.com/drive/folders/15nFxgE5UjH8U1zUEkUnznjrC2Ngqa1aq (Essayez v1 ou v2 en fonction de l'architecture de votre téléphone)


---

## 📌 Licence

MIT

---

## 🤝 Contribuer

Les contributions sont les bienvenues ! Si vous avez des suggestions, ouvrez une _issue_ ou soumettez une _pull request_.

---

## 📬 Contact

Pour toute question, contactez un membre de l’équipe **G3N3S1S**.

