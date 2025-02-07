# MongoDB Checkpoint

## 📌 Objectif
Ce projet consiste à manipuler les opérations CRUD (Create, Read, Update, Delete) avec MongoDB en utilisant **MongoDB Atlas et MongoDB Shell**.

---

## 📂 Structure du projet
Le projet contient les fichiers suivants :
- `README.md` : Explication du projet et des commandes MongoDB.
- `commandes_mongodb.txt` : Liste des commandes exécutées.
- `Screenshots/` : Dossier contenant les captures d'écran des résultats.

---

## 📊 Opérations CRUD

### **1️⃣ Création de la base de données et de la collection**
```
use contact;

db.contactlist.insertMany([
    { nom: "Ben", prenom: "Moris", email: "ben@gmail.com", age: 26 },
    { nom: "Kefi", prenom: "Seif", email: "kefi@gmail.com", age: 15 },
    { nom: "Emilie", prenom: "brouge", email: "emilie.b@gmail.com", age: 40 },
    { nom: "Alex", prenom: "marron", age: 4 },
    { nom: "Denzel", prenom: "Washington", age: 3 }
]);
```

### **2️⃣ Lecture des données**
- Afficher tous les contacts :
  ```
  db.contactlist.find();
  ```
- Afficher un contact par ID :
  ```
  db.contactlist.findOne({ _id: ObjectId("<ID>") });
  ```
- Contacts ayant un âge > 18 :
  ```
  db.contactlist.find({ age: { $gt: 18 } });
  ```
- Contacts avec un âge > 18 et un nom contenant "ah" :
  ```
  db.contactlist.find({ age: { $gt: 18 }, nom: /ah/i });
  ```

### **3️⃣ Mise à jour des données**
- Modifier le prénom de "Kefi Seif" en "Kefi Anis" :
  ```
  db.contactlist.updateOne(
      { nom: "Kefi", prenom: "Seif" },
      { $set: { prenom: "Anis" } }
  );
  ```

### **4️⃣ Suppression des données**
- Supprimer les contacts ayant un âge < 5 ans :
  ```
  db.contactlist.deleteMany({ age: { $lt: 5 } });
  ```

---

## 📸 Captures d'écran
Toutes les opérations ont été documentées avec des captures d'écran disponibles dans le dossier `Screenshots/`.

---

## ✅ Conclusion
Ce projet permet de maîtriser les bases des opérations CRUD avec MongoDB. 🚀

