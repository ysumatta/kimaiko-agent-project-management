# Ticket: Développement de tests d'intégration complets

[Règles et méthodologie du projet](../../project-rules.md)

## Contexte Global
Le MVP Zéro dispose maintenant de 6 modules terminés et fonctionnels. Pour assurer la qualité et la stabilité de l'ensemble, nous avons besoin d'une suite de tests d'intégration qui valide que tous ces modules fonctionnent correctement ensemble.

## Mission Spécifique
Créer un module `packages/integration-tests` qui:
1. Teste les intégrations entre tous les modules existants
2. Vérifie les scénarios d'utilisation principaux
3. Établit une base de référence pour la qualité du MVP Zéro

## Spécifications Techniques Détaillées

### Structure des tests
Les tests d'intégration seront organisés par scénarios, chacun testant une combinaison spécifique de modules:
- Tests a2a-core + langgraph: communication entre agents LangGraph via A2A
- Tests langgraph + llm-tools: utilisation des LLMs dans le contexte de LangGraph
- Tests a2a-langgraph: fonctionnalités d'adaptation A2A pour LangGraph
- Tests state-persistence + langgraph: persistance de l'état des agents LangGraph
- Tests example-agent: intégration complète de tous les modules

### Structure des fichiers
```typescript
packages/integration-tests/
├── src/
│   ├── scenarios/
│   │   ├── a2a-langgraph.test.ts // Tests d'intégration A2A + LangGraph
│   │   ├── langgraph-llm.test.ts // Tests d'intégration LangGraph + LLM
│   │   ├── state-persistence.test.ts // Tests de persistance d'état
│   │   ├── example-agent.test.ts // Tests de l'agent exemple
│   │   └── full-integration.test.ts // Tests d'intégration complète
│   ├── utils/
│   │   ├── test-helpers.ts // Utilitaires pour les tests
│   │   ├── mocks.ts // Mocks pour les tests
│   │   └── fixtures.ts // Fixtures pour les tests
│   ├── setup/
│   │   ├── jest-setup.ts // Configuration de Jest
│   │   └── test-env.ts // Configuration de l'environnement de test
│   └── index.ts // Point d'entrée pour les utilitaires
├── jest.config.js // Configuration Jest
├── package.json
└── tsconfig.json
```

### Approche de test recommandée
- Utiliser Jest comme framework de test
- Structurer les tests avec des "describe" et "it" clairs
- Utiliser des mocks pour les composants externes (LLMs, etc.)
- Inclure des assertions complètes sur le comportement attendu
- Documenter les scénarios de test avec des commentaires détaillés

## Livrables Attendus
1. Le code source complet du module integration-tests
2. La structure des fichiers comme spécifiée
3. Des tests d'intégration fonctionnels pour tous les scénarios
4. Un README décrivant comment exécuter les tests
5. Configuration CI pour l'exécution automatique des tests

## Checklist à compléter
- [ ] Structure de fichiers créée
- [ ] Configuration Jest mise en place
- [ ] Utilitaires de test implémentés
- [ ] Tests d'intégration A2A + LangGraph
- [ ] Tests d'intégration LangGraph + LLM
- [ ] Tests de persistance d'état
- [ ] Tests de l'agent exemple
- [ ] Tests d'intégration complète
- [ ] Documentation des tests
- [ ] Configuration CI

## Règles Clés
- Les tests doivent être clairs, lisibles et bien documentés
- Chaque test doit se concentrer sur un aspect spécifique de l'intégration
- Utiliser des assertions précises pour valider le comportement
- Prévoir des mocks pour les composants externes
- Les tests doivent être déterministes et indépendants