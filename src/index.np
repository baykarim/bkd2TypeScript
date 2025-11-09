import * as fs from "fs";
import * as path from "path";

function lireCSV(filePath: string): any[] {
  const contenu = fs.readFileSync(filePath, "utf-8");
  const lignes = contenu.trim().split("\n");
  const [header, ...rows] = lignes;
  const colonnes = header.split(",");

  return rows.map((ligne) => {
    const valeurs = ligne.split(",");
    const obj: any = {};
    colonnes.forEach((col, i) => {
      obj[col.trim()] = isNaN(Number(valeurs[i]))
        ? valeurs[i].trim()
        : Number(valeurs[i]);
    });
    return obj;
  });
}

function calculerStats(donnees: any[], colonne: string) {
  const valeurs = donnees.map((d) => d[colonne]).filter((v) => typeof v === "number");
  const somme = valeurs.reduce((a, b) => a + b, 0);
  const moyenne = somme / valeurs.length;
  const min = Math.min(...valeurs);
  const max = Math.max(...valeurs);

  console.log(`📊 Nombre de lignes : ${donnees.length}`);
  console.log(`💰 Somme de '${colonne}' : ${somme}`);
  console.log(`📈 Moyenne : ${moyenne}`);
  console.log(`🔽 Min : ${min}`);
  console.log(`🔼 Max : ${max}`);
}

function main() {
  const fichier = path.resolve("data.csv");
  if (!fs.existsSync(fichier)) {
    console.error("❌ Fichier data.csv introuvable !");
    process.exit(1);
  }

  const donnees = lireCSV(fichier);
  calculerStats(donnees, "value");
}

main();
