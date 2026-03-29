# 💧 Arrosage Roquefort-les-Pins

> Gestion de l'arrosage automatique — Maison Jullien, Roquefort-les-Pins (06)
> Dernière mise à jour : 29 mars 2026

---

## 🔧 Système

| Composant | Détail |
|-----------|--------|
| **Contrôleur** | OpenSprinkler |
| **Nom** | Roquefort interieur |
| **IP locale** | 10.182.207.54 |
| **Intégration** | Home Assistant |
| **Taux d'arrosage** | 60% (ajustement météo auto) |
| **Météo** | 15.6°C, couvert (29/03/2026) |

### Entités Home Assistant
| Entity | Rôle |
|--------|------|
| `automation.gestion_arrosage_roquefort` | Rain delay auto si pluie élevée |
| `sensor.opensprinkler_rain_delay` | État du rain delay |
| `input_select.pluie_pour_arreter_arrosage` | Seuil de pluie (actuellement : 3mm) |

### Arrosage plantes intérieur (automations HA séparées)
| Automation | État |
|-----------|------|
| `automation.arrosage_plante_grasse_salon` | ✅ on |
| `automation.arrosage_petite_orchidee` | ✅ on |
| `automation.arrosage_agrumes_ko` | ✅ on |
| `automation.arrosage_plante_verte_salon` | ❌ off |

---

## 🌍 Zones d'arrosage (16 stations)

| # | Nom app | Réalité | État |
|---|---------|---------|------|
| S01 | Bord piscine | Bord piscine | ✅ |
| S02 | Pasteques | Pastèques | ✅ |
| S03 | Tour piscine et | Tour piscine | ✅ |
| S04 | Ko Bord garage | Bord garage | ❌ KO |
| S05 | Jardin du bas | Jardin du bas | ✅ |
| S06 | KoJets jardin du | Jets jardin du bas | ❌ KO |
| S07 | Rosiers et frais | Rosiers et fraisiers | ✅ |
| S08 | Tomates bord pis | Tomates bord piscine | ✅ |
| S09 | Tomates du fond | Tomates du fond | ⚙️ Vanne OK, tuyau pas connecté (dispo) |
| S10 | Agrumes | Agrumes | ✅ Testé 29/03 (1m17s) |
| S11 | KO Fraisiers sau | Fraisiers sauvages | ❌ FIL COUPÉ |
| S12 | Tomates mur vann | Tomates mur vannes | ✅ |
| S13 | Jets Jardin haut | Jets jardin haut | ✅ |
| S14 | jardin haut gou | Jardin haut goutte-à-goutte | ✅ |
| S15 | bord mur Entree | Bord mur entrée | ✅ |
| S16 | S16 | Non câblée | ⚙️ Disponible |

### ⚠️ Stations hors service
- **S04** — Ko Bord garage → KO
- **S06** — KoJets jardin du → KO
- **S11** — KO Fraisiers sau → fil coupé quelque part

### Vannes Zigbee (×3) — ⚠️ TOUTES HORS LIGNE
| Device | État | Possible usage |
|--------|------|---------------|
| `0x28dba7fffe6d4928` | unavailable | Vanne irrigation Zigbee |
| `0x28dba7fffe6d9f30` | unavailable | Vanne irrigation Zigbee |
| `0x28dba7fffe6daa1a` | unavailable | Vanne irrigation Zigbee |

→ Batteries mortes ou déconnectées du réseau Zigbee ?

---

## 🌱 Cartographie plantes ↔ zones

| Plante/Zone jardin | Stations |
|---------------------|----------|
| **Piscine** | S01 Bord piscine, S03 Tour piscine |
| **Pastèques** | S02 |
| **Jardin bas** | S05, S06 (jets) |
| **Rosiers / Fraisiers** | S07, S08 |
| **Tomates** | S09 (fond), S10 (bord piscine), S12 (mur vannes) |
| **Agrumes** | S11 |
| **Jardin haut** | S13 (jets), S14 (goutte-à-goutte ?) |
| **Entrée** | S15 |
| **Garage** | S04 (KO ?) |

---

## 📅 Programmes

> ⚠️ À compléter — les programmes sont dans l'interface OpenSprinkler (http://10.182.207.54)

**Programme Manuel** — Dernière exécution :
- Fraisiers sauvag (S08) : 1m07s le 29/03/2026 à 15:13

---

## 📡 Capteurs météo liés

| Capteur | Valeur (29/03) | Entity |
|---------|---------------|--------|
| Température | 18.2°C | `sensor.roquefort_temperature` |
| Humidité | 39.6% | `sensor.roquefort_humidite` |
| Précipitations | 0.0 mm | `sensor.roquefort_precipitation` |
| Chance de pluie | 0% | `sensor.roquefort_les_pins_rain_chance` |
| UV | 4 | `sensor.roquefort_les_pins_uv` |

---

## 📝 Notes

| Date | Action |
|------|--------|
| 29/03/2026 | Création fichier, inventaire 16 stations depuis OpenSprinkler |
| 29/03/2026 | Taux d'arrosage à 60% (ajustement météo auto) |
| 29/03/2026 | 3 vannes Zigbee hors ligne — à investiguer |
| 29/03/2026 | S08-S11 renommés dans l'app pour correspondre à la réalité. S10 Agrumes testé OK (1m17s). S11 renommé "KO Fraisiers sau" |

---

*Géré par Léa 🌙 — partagé avec Nicole*
