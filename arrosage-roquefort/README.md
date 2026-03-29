# 💧 Arrosage Roquefort-les-Pins

> Gestion de l'arrosage automatique — Maison Jullien, Roquefort-les-Pins (06)
> Dernière mise à jour : 29 mars 2026

---

## 🔧 Système

| Composant | Détail |
|-----------|--------|
| **Contrôleur** | OpenSprinkler |
| **IP locale** | 10.182.207.54 |
| **Intégration** | Home Assistant |

### Entités Home Assistant
| Entity | Rôle |
|--------|------|
| `automation.gestion_arrosage_roquefort` | Rain delay auto si pluie élevée |
| `sensor.opensprinkler_rain_delay` | État du rain delay |
| `input_select.pluie_pour_arreter_arrosage` | Seuil de pluie (actuellement : 3mm) |

### Capteurs météo liés
| Capteur | Entity |
|---------|--------|
| Température | `sensor.roquefort_temperature` |
| Humidité | `sensor.roquefort_humidite` |
| Précipitations | `sensor.roquefort_precipitation` |
| Chance de pluie | `sensor.roquefort_les_pins_rain_chance` |

---

## 🌍 Zones d'arrosage

> ⚠️ À compléter avec les zones réelles configurées dans OpenSprinkler

| Zone | Description | Plantes | Durée | Fréquence |
|------|-------------|---------|-------|-----------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |
| 7 | | | | |
| 8 | | | | |

---

## 📅 Programmes par saison

### 🌞 Été (juin → septembre)
| Zone | Jours | Heure | Durée |
|------|-------|-------|-------|
| | | | |

### 🌸 Mi-saison (avril → mai, octobre)
| Zone | Jours | Heure | Durée |
|------|-------|-------|-------|
| | | | |

### ❄️ Hiver (novembre → mars)
- Arrosage réduit ou coupé

---

## 📝 Notes

| Date | Action |
|------|--------|
| 29/03/2026 | Création du fichier — à compléter avec config OpenSprinkler |

---

*Géré par Léa 🌙 — partagé avec Nicole*
