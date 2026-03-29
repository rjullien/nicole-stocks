# 💧 Arrosage Roquefort-les-Pins

> Gestion de l'arrosage automatique — Maison Jullien, Roquefort-les-Pins (06)
> Dernière mise à jour : 29 mars 2026

---

## 🔧 Système

| Composant | Détail |
|-----------|--------|
| **Contrôleur** | OpenSprinkler |
| **Emplacement** | Fond du garage |
| **IP locale** | 10.182.207.54 |
| **Interface** | http://10.182.207.54 |
| **Intégration** | Home Assistant |
| **Taux d'arrosage** | 60% (ajustement météo auto) |

### Entités Home Assistant
| Entity | Rôle |
|--------|------|
| `automation.gestion_arrosage_roquefort` | Rain delay auto si pluie > 3mm |
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

## 🔧 Réseau de vannes — 4 zones physiques

| # | Zone | Emplacement | Stations |
|---|------|-------------|----------|
| 1 | **Local piscine** | Local technique piscine | S01→S07 — départ principal pour tout le jardin |
| 2 | **Cuisine d'été** | Cuisine d'été | S08, S09, S10, S11(KO), S12 — 5 vannes |
| 3 | **Jardin haut** | Jardin haut | S13 (jets), S14 (goutte-à-goutte) |
| 4 | **Devant maison** | Entrée | S15 |

> Le local piscine est le point de départ de l'ensemble du réseau.
> S16 = pas de fil, disponible au garage (près du contrôleur).

---

## 🌍 Les 16 stations

| # | Nom app | Ce que ça arrose | Zone vannes | État |
|---|---------|------------------|-------------|------|
| S01 | Bord piscine | Bord piscine | Local piscine | ✅ |
| S02 | Pasteques | Pastèques | Local piscine | ✅ |
| S03 | Tour piscine et | Tour piscine | Local piscine | ✅ |
| S04 | Ko Bord garage | Bord garage | Local piscine | ❌ KO |
| S05 | Jardin du bas | Jardin du bas | Local piscine | ✅ |
| S06 | KoJets jardin du | Jets jardin du bas | Local piscine | ❌ KO |
| S07 | Rosiers et frais | Rosiers et fraisiers | Local piscine | ✅ |
| S08 | Tomates bord pis | Tomates bord piscine | Cuisine d'été | ✅ |
| S09 | Tomates du fond | Tomates du fond | Cuisine d'été | ⚙️ Vanne OK, tuyau pas connecté (dispo) |
| S10 | Agrumes | Agrumes | Cuisine d'été | ✅ Testé 29/03 |
| S11 | KO Fraisiers sau | Fraisiers sauvages | Cuisine d'été | ❌ Fil coupé |
| S12 | Tomates mur vann | Tomates mur vannes | Cuisine d'été | ✅ |
| S13 | Jets Jardin haut | Haricots verts + pommes de terre (jets) | Jardin haut | ✅ Testé 29/03 |
| S14 | jardin haut gou | Oranger, kiwis du haut, framboisiers (goutte-à-goutte) | Jardin haut | ✅ Testé 29/03 |
| S15 | bord mur Entree | Cerisier, abricotier, kiwis | Devant maison | ✅ Testé 29/03 (kiwis OK, cerisier/abricotier à vérifier) |
| S16 | S16 | — | Garage | ⚙️ Non câblée, disponible |

### Résumé
- ✅ **10 actives** : S01, S02, S03, S05, S07, S08, S10, S12, S13, S14, S15
- ⚙️ **2 disponibles** : S09 (vanne OK), S16 (non câblée)
- ❌ **3 KO** : S04, S06, S11 (fil coupé)

### ⚠️ À vérifier en 2026
- **S15** : cerisier et abricotier — seuls les kiwis ont été testés
- **S11** : retrouver et réparer le fil coupé (fraisiers sauvages)

---

## 📡 Vannes Zigbee (×3) — TOUTES HORS LIGNE

| Device | État |
|--------|------|
| `0x28dba7fffe6d4928` | unavailable |
| `0x28dba7fffe6d9f30` | unavailable |
| `0x28dba7fffe6daa1a` | unavailable |

→ Batteries mortes ou déconnectées du réseau Zigbee ? À investiguer.

---

## 📡 Capteurs météo liés

| Capteur | Entity |
|---------|--------|
| Température | `sensor.roquefort_temperature` |
| Humidité | `sensor.roquefort_humidite` |
| Précipitations | `sensor.roquefort_precipitation` |
| Chance de pluie | `sensor.roquefort_les_pins_rain_chance` |

---

## 📝 Journal

| Date | Action |
|------|--------|
| 29/03/2026 | Création fichier — inventaire complet 16 stations depuis app OpenSprinkler |
| 29/03/2026 | Noms app corrigés : S08→Tomates bord pis, S10→Agrumes, S11→KO Fraisiers sau |
| 29/03/2026 | Tests manuels OK : S10 (agrumes), S13 (haricots/PDT), S14 (oranger/kiwis/framboisiers), S15 (kiwis) |
| 29/03/2026 | S11 fil coupé identifié — fraisiers sauvages plus d'arrosage auto |
| 29/03/2026 | S09 vanne OK mais tuyau pas connecté — sortie disponible |
| 29/03/2026 | 4 zones vannes documentées : local piscine, cuisine d'été, jardin haut, devant maison |
| 29/03/2026 | 3 vannes Zigbee hors ligne — à investiguer |
| 29/03/2026 | Taux d'arrosage à 60% (ajustement météo auto) |

---

*Géré par Léa 🌙 — partagé avec Nicole*
