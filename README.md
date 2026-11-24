# CVtexeur

**CVtexeur** transforme un CV (Word, PDF, LibreOffice, RTF, HTML, Markdown ou texte) en PDF et en code LaTeX, dans le modèle de votre choix.

👉 **Utiliser CVtexeur en ligne : https://amanylili.github.io/cvtexeur/**

Tout se passe dans le navigateur : le CV n'est envoyé sur aucun serveur. Seul le bouton « Ouvrir dans Overleaf » transmet le code LaTeX à Overleaf, et uniquement si vous cliquez dessus.

## Comment ça marche

1. **Choisissez un modèle** parmi les quatre proposés.
2. **Déposez votre CV**, quel que soit son format (voir ci-dessous). CVtexeur repère le nom, le titre, les coordonnées, les rubriques, les postes et formations avec leurs dates, les listes à puces, les compétences et les langues.
3. **Vérifiez le contenu détecté.** Il s'affiche dans un format texte simple que vous pouvez corriger. Le code LaTeX se met à jour à chaque modification.
4. **Téléchargez le PDF** directement : un aperçu fidèle du modèle s'affiche, et le bouton « Télécharger le PDF » ouvre la fenêtre d'impression du navigateur (choisissez « Enregistrer au format PDF » et décochez « En-têtes et pieds de page »).
5. **Ou récupérez le LaTeX** : copiez-le, téléchargez le fichier `.tex` ou ouvrez-le directement dans Overleaf.

Le PDF direct est produit par le navigateur, à partir d'une reproduction HTML des modèles avec des polices équivalentes. Il est instantané et ne nécessite aucune installation. Pour le rendu typographique exact de LaTeX, compilez le code LaTeX (dans Overleaf, par exemple).

## Formats acceptés

| Format | Extensions |
|---|---|
| Word récent et ancien | `.docx`, `.doc` |
| PDF (avec du texte, pas un scan) | `.pdf` |
| LibreOffice / OpenOffice | `.odt` |
| Texte enrichi | `.rtf` |
| Page web, y compris un CV enregistré depuis Word en « page web » | `.html`, `.htm` |
| Markdown et texte brut | `.md`, `.txt` |

Le format est reconnu d'après le contenu du fichier, pas seulement d'après son extension. La lecture se fait entièrement dans le navigateur, sans bibliothèque externe : le PDF est décodé (polices, encodages, colonnes) pour retrouver l'ordre de lecture, les titres et les dates en marge.

## Les modèles

| Modèle | Style |
|---|---|
| **Classique** | Une colonne en Palatino, titres en petites capitales soulignés. Sobre et universel. |
| **ModernCV** | La classe LaTeX de référence pour les CV, avec ses variantes classic, banking, casual, oldstyle et fancy. |
| **Deux colonnes** | Barre latérale colorée pour le contact, les compétences, les langues et les centres d'intérêt. |
| **Chronologique** | Dates en marge gauche et police sans empattement, pour une lecture rapide du parcours. |

Options communes : couleur d'accent, taille du texte (10, 11 ou 12 pt), langue (français ou anglais), papier A4 ou US Letter, moteur pdfLaTeX ou XeLaTeX, icônes devant les coordonnées.

## Le format du contenu

```
NOM: Camille MARTIN
TITRE: Data scientist
CONTACT: camille@exemple.fr | 06 12 34 56 78 | Lyon | linkedin.com/in/camille

## Expérience professionnelle
* Data scientist senior | Énergies du Rhône | Lyon | Mars 2022 – aujourd'hui
- Conçu un modèle de prévision (erreur réduite de **18 %**)

## Langues
Anglais : courant (C1)
```

- `## Titre` : une rubrique
- `* Poste | Organisme | Lieu | Dates` : une entrée
- `- texte` : une puce
- `Intitulé : valeur` : une ligne de type compétence ou langue
- `**gras**` et `*italique*` : mise en forme dans le texte

## Compiler le LaTeX

Le plus simple est le bouton « Ouvrir dans Overleaf ». Pour compiler chez vous, il faut une distribution LaTeX complète (TeX Live ou MiKTeX). Les modèles utilisent uniquement des paquets standard : `moderncv`, `paracol`, `titlesec`, `enumitem`, `tabularx`, `xcolor`, `hyperref`, `marvosym`, `tikz`, `mathpazo`, `charter`, `helvet` et `babel`.

Choisissez **XeLaTeX** si votre CV contient des caractères hors de l'alphabet latin.

## Fichier d'exemple

Le dossier `exemple/` contient un CV fictif en plusieurs formats (`cv_exemple.docx`, `.pdf`, `.odt`, `.rtf`, `.html`, `.txt`) pour tester la conversion.

## Limites

- Un PDF **scanné** (une image de page) ne contient pas de texte : CVtexeur ne fait pas de reconnaissance de caractères. Un PDF protégé par mot de passe n'est pas lisible non plus.
- Les PDF sont les plus difficiles à analyser : vérifiez le contenu détecté, surtout pour les mises en page en colonnes. Le fichier Word d'origine, s'il existe, donne toujours le meilleur résultat.
- Les fichiers Apple Pages ne sont pas lus : exportez-les en Word ou en PDF.
- La structure est détectée automatiquement. Les mises en page très graphiques (zones de texte superposées, colonnes dessinées) peuvent demander quelques corrections dans le contenu détecté.
- Les photos et les images du document ne sont pas reprises. Le modèle ModernCV contient une ligne prête à décommenter pour ajouter une photo.
- Les émojis sont retirés, car LaTeX ne sait pas les afficher simplement.

## Licence

MIT
