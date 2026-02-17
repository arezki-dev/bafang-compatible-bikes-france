# Dataset : 490 Velos Francais Compatibles Kits Bafang BBS02 / BBSHD

Base de donnees complete de la compatibilite entre les velos du marche francais
et les kits de conversion electrique Bafang (BBS02 750W et BBSHD 1000W).

Compile et maintenu par **[Volts-Bike.fr](https://www.volts-bike.fr)** - le guide complet de
conversion velo electrique DIY en France.

---

## Contenu

- **490 velos** references
- **21 marques** (Decathlon, Gitane, Lapierre, Trek, Specialized, Ghost...)
- Periodes : 2012-2026
- Format : CSV, separateur `;`, encodage UTF-8

## Colonnes

| Colonne | Description | Exemple |
|---|---|---|
| `Marque` | Fabricant | Rockrider |
| `Modele` | Modele exact | ST 540 |
| `Type` | VTT / Ville / Route / VTC | VTT |
| `Annee_Approx` | Fourchette d'annees | 2019-2022 |
| `Taille_Roue` | Pouces | 29 |
| `Boitier_Pedalier` | BSA ou PressFit | BSA |
| `Compatibilite_Moteur` | Verdict technique | OUI - Standard BSA |

## Statistiques

| Compatibilite | Nombre |
|---|---|
| Compatible directement | 447 |
| Compatible avec adaptateur | 0 |
| Non compatible | 0 |
| **Total** | **490** |

## Usage Python

```python
import pandas as pd

df = pd.read_csv('data/velos_france_compatibilite_bafang.csv', sep=';', encoding='utf-8')

# Tous les velos compatibles
compatibles = df[df['Compatibilite_Moteur'].str.startswith('OUI')]
print(f"{len(compatibles)} velos compatibles sur {len(df)}")

# Filtrer par marque
rockrider = df[df['Marque'] == 'Rockrider']

# Filtrer VTT avec boitier BSA
vtt_bsa = df[(df['Type'] == 'VTT') & (df['Boitier_Pedalier'] == 'BSA')]
```

## Guides d'installation

Pour chacun des 490 velos de ce dataset, un guide detaille est disponible :

- [Guide complet conversion velo electrique 2026](https://www.volts-bike.fr/guide-complet-conversion-velo-electrique-2026-tout-savoir/)
- [Tableau interactif compatibilite 490 velos](https://www.volts-bike.fr/compatibilite-bafang-490-velos-francais/)
- [Comparatif BBS02 750W vs BBSHD 1000W](https://www.volts-bike.fr/bafang-bbs02-750w-vs-bbshd-1000w-lequel-choisir-en-2026/)

## Licence

CC BY 4.0 - Libre d'utilisation avec attribution.
Source : [volts-bike.fr](https://www.volts-bike.fr)

---
*Derniere mise a jour : fevrier 2026*
