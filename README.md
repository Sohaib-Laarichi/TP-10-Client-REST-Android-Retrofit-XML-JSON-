# Client REST Android - Retrofit XML/JSON

Une application Android moderne qui démontre l'utilisation de Retrofit pour consommer des services REST avec support des formats XML et JSON.


## 🚀 Fonctionnalités

- **Support multi-format** : Basculement dynamique entre XML et JSON
- **CRUD complet** : Création, lecture, mise à jour et suppression de comptes
- **Interface moderne** : Design Material avec cartes, boutons flottants et animations
- **Architecture robuste** : Utilisation de Retrofit, RecyclerView et patterns Android modernes



La vidéo de démonstration montre :
- ✅ Basculement entre les formats JSON et XML
- ✅ Ajout d'un nouveau compte
- ✅ Modification d'un compte existant
- ✅ Suppression d'un compte avec confirmation
- ✅ Interface utilisateur Material Design en action
- ✅ Gestion des erreurs et feedback utilisateur

### Comment accéder à la vidéo
1. **Via le navigateur** : Ouvrez le fichier `public/t.mp4` dans votre navigateur
2. **Via l'explorateur** : Naviguez vers le dossier `public/` et double-cliquez sur `t.mp4`
3. **Via GitHub** : Si le projet est hébergé sur GitHub, cliquez sur le lien ci-dessus

*💡 **Astuce** : La vidéo démontre l'utilisation complète de l'application avec des exemples concrets*

## 🏗️ Architecture

### Structure du projet
```
app/
├── src/main/java/ma/projet/restclient/
│   ├── MainActivity.java              # Activité principale
│   ├── adapter/
│   │   └── CompteAdapter.java         # Adaptateur RecyclerView
│   ├── entities/
│   │   └── Compte.java                # Modèle de données
│   └── repository/
│       └── CompteRepository.java      # Couche d'accès aux données
├── src/main/res/
│   ├── layout/
│   │   ├── activity_main.xml          # Layout principal
│   │   ├── item_compte.xml            # Layout item de liste
│   │   └── dialog_add_compte.xml      # Dialog d'ajout/modification
│   └── values/
│       └── themes.xml                 # Thèmes Material Design
└── src/main/AndroidManifest.xml       # Configuration de l'application
```

### Technologies utilisées

- **Retrofit 2.9.0** - Client REST moderne
- **Gson** - Sérialisation/désérialisation JSON
- **SimpleXML** - Support du format XML
- **Material Components** - Interface utilisateur moderne
- **RecyclerView** - Affichage efficace des listes
- **FloatingActionButton** - Actions rapides

## 🛠️ Configuration

### Prérequis
- Android Studio Arctic Fox ou plus récent
- Android SDK 24 (API niveau 24) minimum
- Android SDK 33 (API niveau 33) pour la compilation
- Java 8 ou plus récent

### Installation

1. **Cloner le projet**
   ```bash
   git clone [URL_DU_REPO]
   cd ClientRESTAndroidRetrofitXMLJSON
   ```

2. **Ouvrir dans Android Studio**
   - Lancez Android Studio
   - Sélectionnez "Open an existing project"
   - Naviguez vers le dossier du projet

3. **Synchroniser les dépendances**
   ```bash
   ./gradlew build
   ```

4. **Configurer l'émulateur ou connecter un appareil**

5. **Lancer l'application**
   ```bash
   ./gradlew installDebug
   ```

## 🔧 Configuration du serveur REST

L'application est configurée pour se connecter à un serveur REST local. Assurez-vous que votre serveur backend est en cours d'exécution et accessible.

### Endpoints utilisés
- `GET /comptes` - Récupérer tous les comptes
- `POST /comptes` - Créer un nouveau compte
- `PUT /comptes/{id}` - Mettre à jour un compte existant
- `DELETE /comptes/{id}` - Supprimer un compte

### Format des données

#### Modèle Compte (JSON)
```json
{
  "id": 1,
  "solde": 1500.50,
  "type": "COURANT",
  "dateCreation": "2023-11-09"
}
```

#### Modèle Compte (XML)
```xml
<compte>
  <id>1</id>
  <solde>1500.50</solde>
  <type>COURANT</type>
  <dateCreation>2023-11-09</dateCreation>
</compte>
```

## 📋 Fonctionnalités détaillées

### 1. Sélection du format de données
- Boutons radio pour basculer entre JSON et XML
- Rechargement automatique des données lors du changement
- Interface intuitive avec cartes Material

### 2. Affichage des comptes
- Liste défilable avec RecyclerView
- Affichage des informations : ID, solde, type, date de création
- Boutons d'action : Modifier et Supprimer

### 3. Ajout de comptes
- Bouton flottant pour un accès rapide
- Dialog modal avec validation des données
- Champs : Solde (décimal) et Type (COURANT/EPARGNE)

### 4. Modification de comptes
- Dialog pré-rempli avec les données existantes
- Sauvegarde automatique après confirmation

### 5. Suppression de comptes
- Dialog de confirmation pour éviter les suppressions accidentelles
- Mise à jour immédiate de la liste

## 🎨 Interface utilisateur

L'application utilise Material Design 3 avec :

- **Thème** : `Theme.MaterialComponents.Light.NoActionBar`
- **Composants** :
  - MaterialCardView pour les conteneurs
  - MaterialRadioButton pour les sélections
  - TextInputLayout pour la saisie
  - FloatingActionButton pour les actions principales
  - RecyclerView pour les listes

### Palette de couleurs
- Arrière-plan principal : `#FAFAFA`
- Cartes : `#F5F5F5`
- Couleur primaire : Material Design par défaut
- Élévation des cartes : 0dp (design plat moderne)

## 🔍 Gestion des erreurs

L'application inclut une gestion robuste des erreurs :

- **Erreurs réseau** : Messages d'erreur informatifs
- **Validation des données** : Contrôles côté client
- **Timeouts** : Gestion des délais d'attente
- **Feedback utilisateur** : Toasts pour les actions réussies/échouées

## 🧪 Tests

### Tests unitaires
Les tests peuvent être exécutés avec :
```bash
./gradlew test
```

### Tests d'intégration
```bash
./gradlew connectedAndroidTest
```

## 📦 Dépendances

```gradle
dependencies {
    // Interface utilisateur
    implementation 'androidx.appcompat:appcompat:1.6.1'
    implementation 'com.google.android.material:material:1.5.0'
    implementation 'androidx.constraintlayout:constraintlayout:2.1.4'
    implementation 'androidx.recyclerview:recyclerview:1.3.0'
    
    // Retrofit et sérialisation
    implementation 'com.squareup.retrofit2:retrofit:2.9.0'
    implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
    implementation 'org.simpleframework:simple-xml:2.7.1'
    implementation 'com.squareup.retrofit2:converter-simplexml:2.9.0'
    implementation 'com.squareup.retrofit2:converter-jaxb:2.9.0'
    
    // Tests
    testImplementation 'junit:junit:4.13.2'
    androidTestImplementation 'androidx.test.ext:junit:1.1.5'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.5.1'
}
```

## 🚀 Déploiement

### Build de production
```bash
./gradlew assembleRelease
```

### Génération d'APK signé
1. Configurez le keystore dans `app/build.gradle`
2. Exécutez : `./gradlew assembleRelease`
3. L'APK sera généré dans `app/build/outputs/apk/release/`

## 🤝 Contribution

1. Fork le projet
2. Créez une branche feature (`git checkout -b feature/nouvelle-fonctionnalite`)
3. Committez vos changements (`git commit -am 'Ajout d'une nouvelle fonctionnalité'`)
4. Push vers la branche (`git push origin feature/nouvelle-fonctionnalite`)
5. Créez une Pull Request

## 📝 Changelog

### Version 1.0.0
- ✅ Interface utilisateur Material Design
- ✅ Support XML et JSON avec Retrofit
- ✅ CRUD complet pour les comptes
- ✅ Gestion des erreurs
- ✅ Architecture MVC
- ✅ RecyclerView avec adapter personnalisé

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

## 👥 Auteurs

- **Sohaib laarichi** - *Développement initial* - [VotreGitHub](https://github.com/votre-username)

## 🙏 Remerciements

- Équipe Android pour les outils de développement
- Square pour Retrofit
- Google pour Material Design Components
- La communauté open source pour les bibliothèques utilisées
  

---

## 📱 Captures d'écran et Démonstration

### 🎥 Vidéo de démonstration

https://github.com/user-attachments/assets/77e0e331-6836-49a3-99ab-918a7fe1d78d





**Note** : Cette application est un projet de démonstration pour illustrer l'utilisation de Retrofit avec XML et JSON dans le développement Android moderne.
