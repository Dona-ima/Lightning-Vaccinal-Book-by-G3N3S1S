# ⚡ Lightning Vaccinal Book

## 👥 G3N3S1S Team

- **AGBALE Bellevie** – IU/UX Designer 
- **AGBOTON Ariane** – Web Developper – https://github.com/Dona-ima
- **AHOGNISSE Ariel** – Web et Mobile developper – https://github.com/arielcarmen
- **EDAYE DOKOUI Béni-Christ** – web Developper –
- **HOUEDANOU Gildas** – Computer Scientist –  

---

## 📄 Executive Summary

**Lightning Vaccinal Book** eIt is a digital vaccination record application that allows patients to store their vaccination proofs on a secure platform. It helps health centers certify vaccinations and enables inspectors to verify them quickly using QR codes.

Our solution combats fake vaccination booklets, facilitates vaccination tracking, and strengthens health security — especially in sensitive contexts such as travel or health inspections.

---

## ❗ Identified Problem

### 🔍 problem

In many countries, vaccination booklets are still **physical, fragile, and easily falsifiable**. This undermines data reliability, complicates verification processes, and poses a barrier to health security (e.g., COVID-19, yellow fever).

> In West Africa, 1 in 3 people is unable to present a complete or legible vaccination record.

### 👥 PTarget Audience

Our solution is designed for three types of users :
- **Patients** : to store their certificates without the risk of loss or damage.
- **Health Centers** : to issue **authentic and tamper-proof** vaccination proofs
- **Controllers** (hospitals, borders, schools): to quickly verify certificates.

Patients need a reliable way to keep their vaccination records without risk of loss or damage. Health centers, on their part, must be able to issue authentic and tamper-proof proof of administered vaccinations. Finally, inspectors (at borders, schools, or hospitals) require a simple and fast tool to verify the authenticity of vaccination records.

Today, the loss or deterioration of vaccination records is common, especially in West Africa, where approximately one in three people cannot present a complete or well-preserved booklet. This lack of traceability leads to difficulties accessing certain health, education, or mobility services. Additionally, the proliferation of fake certificates poses a serious threat to health security, particularly during epidemics such as COVID-19 or yellow fever.

It is therefore essential to provide a digital, portable, and secure solution that allows every individual to have a reliable and easily verifiable vaccination record. It is in this context that our application offers a concrete response, adapted to local realities, by strengthening trust between patients, health centers, and authorities.

---

## ✅ Our Solution

**The Lightning Vaccinal Book** project aims to develop a secure digital system for recording, storing, and verifying vaccination proofs. By leveraging the Lightning Network and cryptography, this system ensures the authenticity of vaccination certificates without relying on centralized infrastructure or traditional user account management.

Each individual has a secure identity based on a Lightning public key, guaranteeing confidentiality and the security of personal data. The project seeks to provide a lightweight, fast solution adapted to contexts with limited internet connectivity, especially in regions like Benin.

---

## 🧩 Key Features

### 🔐 Secure and Portable Vaccination Proof
After validation of their vaccination, the patient receives a certification that is added to their digital vaccination record. They can then generate a QR code from their record to present a tamper-proof and easily verifiable proof of vaccination.

### 📶 Fast and Offline Verification
Inspectors can verify the authenticity of a certificate without an internet connection, simply by scanning the QR code. The validity is confirmed locally using the cryptographic signature.

### 📅 Simple and Secure Appointment Booking
Le patient crée un compte et soumet une demande de rendez-vous en précisant :
- their **national identification number**
- the **desired type of vaccine**
- **a appointment**

On the day of the appointment, they confirm their identity using their national identification number shown on their **national ID card**.

---

## 🛠️ Technical Implementation

### 🏗️ General Architecture

#### 🧑‍💻 Patient Side
- Mobile Application
- Account creation on the platform
- Fonctions :
  - Appointment booking
  - Vaccination record consultationt
  - QR Code Generation for the Record
- **Local storage** (browser) or QR code image

#### 🏥 Health Center Side
- Secure Web Interface
- Fonctions :
  - Reception of appointment requests
  - Approval / Rejection / Modification
  - Vaccination Recording
  - Signing proofs with a **private key**

#### 🕵️ Controller Side
- Mobile ou Web Application
- Scan Patient QR Code
- Vérification :
  - Cryptographic Signature
  - Public key present in the whitelist
- **Works offline**

#### 🔗 Data exchange
- Secure messages (JSON) containing :
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

|      Composant      |      Technology         |
|---------------------|--------------------------|
|    **Frontend**     | HTML, CSS, JavaScript    |
|    **Backend**      | FastAPI                  |
|    **DataBase**     | Firestore                |
|  **UI/UX Design**   | Figma                    |
|  **APIs/Services**  | Lightning_pb2_grpc       |

---

## ⚙️ Ressoures

- Backend Server : https://github.com/arielcarmen/python-lnd-connect
- Frontend Server : 
- Mobile Apllication : https://github.com/arielcarmen/vaccination_book_app
- Mockups : https://www.figma.com/design/dGGxc8iEpWnEztIxOaZSHq/Book-Vaccinal-Lightning?node-id=85-3&p=f&t=GL4wf0vt7T49OIJp-0
- Application (generated) : https://drive.google.com/drive/folders/15nFxgE5UjH8U1zUEkUnznjrC2Ngqa1aq (Essayez v1 ou v2 en fonction de l'architecture de votre téléphone)


---

## 📌 Licence

MIT

---

## 🤝 Contribute

Contributions are welcome! If you have suggestions, please open an issue or submit a pull request.

---

## 📬 Contact

For any questions, please contact a team member **G3N3S1S**.

