# 🎮 GUIDE DE CONTRÔLE THRONE

## 🎯 Script de Contrôle de Redirection

### Arrêter la redirection (rendre le site) :
```bash
./throne_redirect_control.sh stop
```
→ Le propriétaire peut accéder à son site normalement

### Redémarrer la redirection :
```bash
./throne_redirect_control.sh start
```
→ Les visiteurs sont redirigés vers votre page

### Vérifier l'état :
```bash
./throne_redirect_control.sh status
```

## 🔌 Auto-Shutdown Intelligent

### Lancer le monitoring (APRÈS que THRONE soit fini) :
```bash
# En arrière-plan avec nohup
nohup ./throne_smart_shutdown.sh > /dev/null 2>&1 &

# Ou dans un tmux séparé
tmux new -s shutdown -d ./throne_smart_shutdown.sh
```

### Comment ça marche :
- ✅ Vérifie toutes les 5 minutes si THRONE tourne
- ✅ Attend 15 minutes d'inactivité complète
- ✅ Sauvegarde automatique avant shutdown
- ✅ NE S'ÉTEINDRA PAS pendant un scan !

### Pour annuler le shutdown :
```bash
# Tuer le processus de monitoring
pkill -f throne_smart_shutdown.sh

# Ou si dans tmux
tmux kill-session -t shutdown
```

## ⚠️ IMPORTANT

**NE PAS lancer le smart shutdown maintenant !**
Vos scans THRONE sont en cours. Lancez-le seulement quand vous voyez que tout est terminé.

## 📊 Vérifier si THRONE tourne encore :
```bash
# Voir les sessions tmux
tmux ls

# Voir spécifiquement THRONE
tmux ls | grep throne
```

---

💡 **Conseil** : Attendez demain matin, vérifiez que THRONE a fini, PUIS lancez le smart shutdown pour économiser de l'argent AWS !