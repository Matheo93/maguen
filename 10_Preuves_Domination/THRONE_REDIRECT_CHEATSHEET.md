# 🎯 THRONE REDIRECT CHEATSHEET

## ✅ Configuration Actuelle
- **Page de redirection** : http://13.38.86.174 (votre belle page avec animations Matrix!)
- **Module configuré** : AdvancedExploit.ps1

## 🚀 Commandes Rapides

### Lancer THRONE avec redirection activée :
```bash
# Mode complet avec redirection
./throne_launch.sh -u http://target.com -a

# Ou directement avec throne.ps1
sudo pwsh ./throne.ps1 -Url http://target.com -Advanced -RedirectTraffic
```

### Ce qui se passe avec `-RedirectTraffic` :
1. 🔍 THRONE trouve des vulnérabilités
2. 🎣 Configure des techniques de redirection (DNS spoofing, ARP poisoning, etc.)
3. 🎯 Les visiteurs du site compromis sont redirigés vers http://13.38.86.174
4. 💥 Ils voient votre page d'alerte spectaculaire !

## 📁 Scripts de redirection créés
Après un scan, vérifiez :
```bash
ls -la throne_results_*/advanced_exploits/
```

Vous y trouverez :
- `dns_spoof.sh` - Script de DNS spoofing
- `arp_poison.sh` - Script d'ARP poisoning
- `setup_proxy.sh` - Configuration MITM proxy
- `phishing_site/` - Site de capture de credentials

## 🔧 Personnalisation
Pour changer la page de redirection :
```bash
# Éditez le fichier
sudo nano /home/ubuntu/throne_security_notice.html

# Redémarrez le serveur
sudo systemctl restart throne-web
```

## 🎨 Votre Page Actuelle
- **Effets** : Matrix rain, glitch text, animations
- **Score** : Affiche 90% de compromission
- **Vulnérabilités** : SQL Injection, XSS, Auth Bypass, Path Traversal
- **Message** : Alerte professionnelle de sécurité

---
💡 **Rappel** : La redirection ne fonctionne que si THRONE trouve et exploite des vulnérabilités sur la cible !