# Mettre en place l'accessibilité sur son projet

### Rappel sur la conformité requise

On parle souvent du RGAA par habitude, mais pour être exacte, ce n'est ni une norme ni une loi ni… : c'est une checklist pour mesurer. La loi française exige pleine conformité à la norme en vigueur, en l'occurence EN 301 549 V2.1.2 (ou WCAG 2.1 AA). Pour faciliter cela, deux référentiels existent (et c'est effectivement ce qu'il est intéressant de retenir) : **[RGAA](https://accessibilite.numerique.gouv.fr/methode/criteres-et-tests/) pour le Web** et **[RAAM](https://accessibilite.public.lu/fr/raam1/referentiel-technique.html) pour le mobile**. Pour en savoir plus : [Confluence](https://octo.atlassian.net/wiki/spaces/NR/pages/2670329943/) et [accessibilite.numerique.gouv.fr](https://accessibilite.numerique.gouv.fr/obligations/champ-application/#norme-de-reference-et-niveau-de-conformite) Édité


Il existe une formation pour s'approprier le Référentiel d'Évaluation de l'Accessibilité des Applications Mobiles (RAAM) : [https://formations.access42.net/formations/formation-audit-accessibilite-mobile/](https://formations.access42.net/formations/formation-audit-accessibilite-mobile/)

# Outils
Voice Over sur Firefox

**Ostendo** - l'Accessibilité des sites français
https://chrome.google.com/webstore/detail/ostendo-laccessibilit%C3%A9-de/hfbgfmeddkaplomgloehmhollecglldo?hl=fr
Voici un exemple d’exploitation des déclarations obligatoires d’accessibilité, orienté user : l’extension Ostendo ajoute une mention du niveau d’accessibilité directement dans les résultats de recherche (+ lien direct vers la déclaration détaillée), ce qui évite des clics inutiles (induisant donc une baisse d’audience des sites mauvais élèves).
(Romy)

# Dev tools
Afficher l'arbre https://developer.chrome.com/blog/full-accessibility-tree/

# Sources

[Vue d’ensemble des standards d’accessibilité du W3C](https://www.w3.org/WAI/standards-guidelines/fr)
[Ressources autours du numériques responsable](https://github.com/cecilefreyd/numerique_inclusif_ressources/tree/844b1ba354ac275bdb8b27c94e928b1d2acb721c)

# Formations
- https://access42.net/


# Tester l'accessibilité

- extension tanaguru Chrome et Firefox
- W3C validation pour les pages non privées
- extension Wave

Voici quelques tips pour aider à tester l’accessibilité pour les devs, POs, designer :  

-   Vérifier les contrastes (ex outil : [https://chrome.google.com/webstore/detail/wcag-color-contrast-check/plnahcmalebffmaghcpcmpaciebdhgdf?hl=fr](https://chrome.google.com/webstore/detail/wcag-color-contrast-check/plnahcmalebffmaghcpcmpaciebdhgdf?hl=fr))
-   S’aider de [10 easy checks](https://www.w3.org/WAI/test-evaluate/preliminary/) sur W3C (structure de base, hiérarchie des titres, alternatives, zoom texte, navigation au clavier…)
-   Lancer[Wave](https://wave.webaim.org/) et vérifier qu’il n’y a pas d’erreur
-   Tester sur 2 navigateurs
-   Tester avec un lecteur d’écran type VoiceOver, NVDA, JAWS

(Thanks Clarisse / Pix)

[10 choses faciles à vérifier pour un site plus accessible](https://doc.incubateur.net/design/ressources-design/kit-accessibilite/accessibilite/10-choses-faciles-a-verifier-pour-un-site-plus-accessible)
[Easy Checks – A First Review of Web Accessibility](https://www.w3.org/WAI/test-evaluate/preliminary/) / W3 ORG




- [Notice d’accessibilité fonctionnelle et graphique](https://www.accede-web.com/notices/fonctionnelle-graphique/)
- [Designer un web  **accessible et inclusif**](https://design-accessible.fr/)
