# Guide de mise en place sur GitHub

## Étapes à suivre sur GitHub.com

### 1. Créer le repository sur GitHub
1. Aller sur https://github.com
2. Cliquer sur le bouton "+" en haut à droite
3. Sélectionner "New repository"
4. Nom du repository : `AdventureWorks`
5. Description (optionnelle) : "Projet Power BI AdventureWorks"
6. Choisir "Public" ou "Private" selon vos besoins
7. **NE PAS** cocher "Initialize this repository with a README" (car on en a déjà un)
8. Cliquer sur "Create repository"

### 2. Connecter votre projet local à GitHub

Après avoir créé le repository sur GitHub, vous verrez des instructions. Utilisez celles-ci :

```bash
cd chemin/vers/AdventureWorks
git remote add origin https://github.com/VOTRE_USERNAME/AdventureWorks.git
git push -u origin main
```

**Note** : Remplacez `VOTRE_USERNAME` par votre nom d'utilisateur GitHub.

### 3. Configuration de Git (si ce n'est pas déjà fait)

Avant de pousser vers GitHub, configurez votre identité :

```bash
git config --global user.email "votre.email@exemple.com"
git config --global user.name "Votre Nom"
```

### 4. Authentification GitHub

Pour pousser vers GitHub, vous aurez besoin de vous authentifier :

**Option 1 : Personal Access Token (recommandé)**
1. Aller dans Settings > Developer settings > Personal access tokens
2. Générer un nouveau token avec les permissions "repo"
3. Utiliser ce token comme mot de passe lors du push

**Option 2 : SSH**
1. Générer une clé SSH : `ssh-keygen -t ed25519 -C "votre.email@exemple.com"`
2. Ajouter la clé publique dans GitHub Settings > SSH and GPG keys
3. Utiliser l'URL SSH : `git@github.com:VOTRE_USERNAME/AdventureWorks.git`

## Commandes Git utiles pour la suite

### Ajouter et committer vos fichiers Power BI
```bash
# Ajouter un fichier
git add Reports/MonFichier.pbix

# Ajouter tous les nouveaux fichiers
git add .

# Committer avec un message
git commit -m "Ajout du dashboard des ventes"

# Pousser vers GitHub
git push origin main
```

### Vérifier l'état du repository
```bash
git status
```

### Voir l'historique des commits
```bash
git log --oneline
```

## Bonnes pratiques

1. **Commits fréquents** : Committer régulièrement avec des messages clairs
2. **Messages descriptifs** : Ex: "Ajout visualisation des ventes par région"
3. **Fichiers .pbix** : Git peut gérer ces fichiers binaires, mais ils peuvent être volumineux
4. **Documentation** : Mettre à jour le README et la documentation au fur et à mesure

## Structure finale du projet

```
AdventureWorks/
├── .git/                    # Dossier Git (caché)
├── .gitignore              # Fichiers à ignorer
├── README.md               # Description du projet
├── Reports/                # Vos fichiers .pbix
│   └── README.md
├── Data/                   # Sources de données (souvent ignorées)
├── Documentation/          # Documentation du projet
│   └── README.md
└── Images/                 # Captures d'écran
```

## Besoin d'aide ?
- Documentation Git : https://git-scm.com/doc
- Documentation GitHub : https://docs.github.com
