# Règles et Méthodologie du Projet KimaikoAgent

## Méthodologie de travail

### Principes généraux

1. **Communication par fichiers Markdown** - Toute la communication et documentation du projet se fait via des fichiers Markdown stockés dans ce repository.

2. **Factorisation du contenu** - Tout contenu réutilisable doit être factorisé et référencé plutôt que dupliqué.

3. **Mise à jour constante** - Le fichier de gestion de projet (`project-management.md`) doit être mis à jour après chaque action significative.

4. **Traçabilité complète** - Chaque ticket, chaque réponse et chaque décision doit être documentée et accessible.

### Workflow des tickets

1. **Création du ticket** - Le Chef de Projet (Claude-PM) crée un ticket de sprint dans un fichier Markdown à l'emplacement `/tickets/[dev-name]/ticket-[module-name].md`.

2. **Contenu du ticket** - Chaque ticket doit commencer par un lien vers ce document de règles et méthodologie, suivi des spécifications détaillées de la tâche à accomplir.

3. **Attribution du ticket** - Le ticket est attribué à l'un des développeurs IA (Cursor, C1, C2, C3).

4. **Traitement du ticket** - Le développeur IA traite le ticket et fournit sa réponse dans un fichier Markdown séparé à l'emplacement `/responses/[dev-name]/response-[module-name].md`.

5. **Validation du ticket** - Le Chef de Projet valide la réponse et met à jour le statut du ticket et le fichier de gestion de projet.

## Standards de codage

### Architecture

1. **Structure monorepo** - Le projet suit une structure monorepo avec packages individuels pour chaque module.

2. **Clean Architecture** - Tous les modules doivent suivre les principes de Clean Architecture avec une séparation claire des couches.

3. **Principes SOLID** - Le code doit adhérer aux principes SOLID de conception objet.

### Convention de code

1. **TypeScript** - Le projet utilise TypeScript pour tous les modules.

2. **Nommage** - Utiliser la convention camelCase pour les variables et méthodes, PascalCase pour les classes et interfaces.

3. **Documentation** - Toutes les classes, méthodes et interfaces publiques doivent être documentées avec JSDoc.

4. **Tests** - Chaque module doit inclure des tests unitaires et d'intégration appropriés.

### Structure des packages

```
packages/[module-name]/
├── src/
│   ├── types/       # Définitions des types et interfaces
│   ├── [domain-specific-folders]/
│   └── index.ts     # Point d'entrée et exports publics
├── tests/          # Tests unitaires et d'intégration
├── examples/       # Exemples d'utilisation
├── package.json
└── tsconfig.json
```

## Revue et validation

1. **Checklist de validation** - Chaque développeur doit fournir une checklist complétée avec sa réponse, indiquant les éléments implémentés.

2. **Critères de succès** - Le Chef de Projet doit vérifier que tous les critères de succès définis dans le ticket sont atteints.

3. **Tests** - La validation inclut la vérification que tous les tests passent et que la couverture de code est adéquate.

## Communication

1. **Questions et clarifications** - Si un développeur a besoin de clarifications, il doit créer un fichier de questions à l'emplacement `/questions/[dev-name]/questions-[module-name].md`.

2. **Réponses aux questions** - Les réponses aux questions sont fournies dans un fichier à l'emplacement `/answers/[dev-name]/answers-[module-name].md`.

3. **Mise à jour du statut** - Le statut de chaque module et ticket doit être reflété dans le fichier de gestion de projet.