# FORMATTER ET CORRIGER LES ERREURS AVEC ESLINT ET PRETTIER

Une première passe a été effectuée pour mettre en place [prettier](https://prettier.io/) afin que tous les dev formattent le code de la même façon, et ce, de manière automatique :

-   en configurant son IDE
-   en lançant une commande
-   en bloquant le merge si on a oublié

Voir comment la décision a été prise par Pix dans cet ADR [https://github.com/1024pix/pix/blob/dev/docs/adr/0036-formater-le-code.md
](https://github.com/1024pix/pix/blob/dev/docs/adr/0036-formater-le-code.md)

## Utilisation de Prettier

Configurer son IDE avec un plugin [vscode par exemple](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) et en activant la correction automatique lors de l'enregistrement.

-   Pour lancer eslint, utiliser la commande `npm run format`
-   Il est possible de les corriger, utiliser la commande `npm run format:fix`

Néammoins, il reste encore quelques améliorations à apporter au code, [eslint](https://eslint.org/) peut nous y aider.

## Configuration

Il est configuré de manière standard dans le fichier `.eslintrc.json` avec `eslint-config-next` qui intègre les paquets `eslint-plugin-react`, `eslint-plugin-react-hooks`, `@next/eslint-plugin-next` et sont donc installés par défaut.

Source : [configuration de eslint pour nextJs](https://nextjs.org/docs/app/building-your-application/configuring/eslint)

Pour corriger les problèmes petit à petit, le mieux est d'activer des règles via rules dans le fichier de configuration `.eslintrc.json` et leur attribuer un degré de criticité : `warn`, `error`, ou `off` pour les désactiver :

```json
{
    "rules": {
        "no-var": "warn",
        "no-console": "off",
        "no-duplicate-imports": "off"
    }
}
```

## Utilisation d'Eslint

-   Pour lancer eslint, utiliser la commande `npm run eslint`
-   Il est possible d'en corriger certaines automatiquement en ajoutant le suffixe `--fix`

## Intégration dans CI

Afin de ne pas introduire de code ne correspondant pas aux standards, le code est vérifié voir le [Dockerfile](.Dockerfile) :

```shell
RUN ["npm", "run", "test"]
RUN ["npm", "run", "format"]
RUN ["npm", "run", "lint"]
RUN ["npm", "run", "build"]
```

Si une erreur est detectée, la pull request ne pourra pas être validée et mergée sur la branche `main`.
