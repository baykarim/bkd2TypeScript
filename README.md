# bkd2TypeScript

## Description

Ce projet TypeScript simple permet de lire des fichiers CSV et de calculer des statistiques sur une colonne spécifiée.  
Exemple : somme, moyenne, min, max, médiane, écart-type.  

### Exemple CSV

name	value
Alice	10
Bob	15
Charlie	20

### Exemple de résultats calculés

📊 Nombre de lignes 	: 3  
💰 Somme de 'value' 	: 45  
📈 Moyenne 		: 15  
🔽 Min 			: 10  
🔼 Max 			: 20

Un workflow GitHub Actions est inclus pour compiler automatiquement le projet TypeScript.

---

## Installation

Cloner le dépôt :

```bash
git clone https://github.com/baykarim/bkd2TypeScript.git
cd bkd2TypeScript
npm install
npm run build
npm run start -- --file data.csv --col value
