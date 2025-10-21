# Copilot / AI agent instructions — Inside Hack Gaming

Purpose
- Aider un agent IA à devenir productif rapidement sur ce projet : un site statique construit à partir d'un template Bootstrap (Colorlib).
- Contenir règles, fichiers clés, patterns à respecter et exemples précis de corrections récurrentes.

Big picture
- Site statique HTML/CSS/JS. Principal fichier d'entrée : index.html.
- Assets localisés sous dossiers référencés par index.html: img/, css/, js/, assets/ (vérifier existence).
- Template d'origine : Colorlib (crucial : conserver la mention d'attribution dans footer).

Fichiers et répertoires importants
- index.html — page principale (contenu mélangé, duplications et petites erreurs à corriger).
- css/*.css — styles, potentiellement issus du template.
- js/*.js — plugins (jQuery, Bootstrap, Owl Carousel, Magnific Popup, etc.). Eviter de remplacer plugins sans tests manuels.
- img/, assets/ — logos, bannières, icônes.
- .github/copilot-instructions.md — ce fichier : règles pour l'agent.

Flux de travail local (rapide)
- Ouvrir index.html dans un navigateur (Live Server ou serve static).
- Pas de build automatique présent. Pour itérations rapides : utiliser Live Server or python -m http.server.
- Vérifier la console du navigateur pour erreurs JS et chemins 404 d'assets.

Conventions et patterns du projet
- Template Bootstrap/Colorlib : classes utilitaires et composants tiers sont présents. Respecter les classes existantes pour préserver layout.
- Attribution Colorlib doit rester intacte dans le footer (ne pas supprimer).
- Les liens de téléchargement (releases/v1.0.zip) sont des placeholders — valider avant de rendre publiques.
- Langue et métadonnées : index.html contient des erreurs (ex: lang="zxx", balise meta malformée). Corriger vers lang="fr" et fixer meta viewport.

Exemples d'actions pratiques (copy-paste-ready)
- Fixer lang et meta:
  - Remplacer <html lang="zxx"> par <html lang="fr">.
  - Corriger meta viewport malformée (retirer le texte corrompu).
- Nettoyage HTML:
  - Supprimer duplications de header/logo et balises HTML corrompues (ex: fragment " <a href="#" class="btn_1">Watch Tutorial"</).
- Vérifier assets:
  - Confirmer que tous les chemins référencés (css/, js/, img/, assets/) existent. Si manquent, rendre chemins relatifs cohérents ou ajouter placeholders.
- Accessibilité:
  - Ajouter alt significatifs aux images si manquants.
  - Ajouter aria-labels sur éléments interactifs si utile.

Sécurité & légalité
- Ne pas ajouter ou promouvoir outils qui violent les règles (hacking illégal). Si le contenu demande cela, refuser.
- Valider que tout binaire téléchargé via le site est légal et sûr.

Tests rapides avant PR
- Ouvrir la page et valider : aucun 404 pour assets critiques, pas d'erreurs JS majeures, layout desktop & mobile OK.
- Vérifier que la mention Colorlib est présente si on a modifié le footer.

Précautions spécifiques pour l'agent IA
- N'ajouter ni code serveur ni dépendances build sans instructions explicites du mainteneur.
- Quand vous modifiez index.html, produire un diff minimal (éviter rewrite complet) et commenter les corrections majeures dans le PR.
- Si vous proposez migration (ex: séparer CSS/JS), inclure instructions de déploiement local et tests manuels.

Questions pour le mainteneur
- Voulez-vous : 1) corriger les erreurs HTML directement, 2) refactorer en structure modulaire (style.css + main.js), 3) convertir en générateur statique (Hugo/Eleventy) ?
- Confirmer si la mention Colorlib doit rester telle quelle.

Fin
- Si des sections sont incomplètes ou vous voulez plus de détails (scripts de build, conventions Git, tests), dites lesquelles et j'itérerai.
