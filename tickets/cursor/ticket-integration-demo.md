# Ticket: Implémentation du module integration-demo

[Règles et méthodologie du projet](../../project-rules.md)

## Contexte Global
Le MVP Zéro a maintenant plusieurs modules clés terminés (a2a-core, langgraph, llm-tools, example-agent, a2a-langgraph). Il est temps de créer un module d'intégration qui démontre comment tous ces composants fonctionnent ensemble dans un système cohérent.

## Mission Spécifique
Créer un module `packages/integration-demo` qui:
1. Montre comment utiliser tous les modules ensemble
2. Fournit des scénarios de démonstration complets
3. Sert de référence pour les futurs développeurs

## Spécifications Techniques Détaillées

### Structure du module
Le module sera composé de plusieurs exemples de scénarios qui illustrent différents aspects du système:
- Scénario de base: utilisation d'un agent simple
- Scénario A2A: communication entre agents via A2A
- Scénario LangGraph: utilisation avancée de LangGraph pour orchestrer des agents
- Scénario complet: combinaison de tous les modules

### Structure des fichiers
```typescript
packages/integration-demo/
├── src/
│   ├── scenarios/
│   │   ├── basic-scenario.ts // Utilisation simple d'un agent
│   │   ├── a2a-scenario.ts // Communication A2A entre agents
│   │   ├── langgraph-scenario.ts // Orchestration avec LangGraph
│   │   ├── complete-scenario.ts // Utilisation complète
│   │   └── index.ts // Export des scénarios
│   ├── utils/
│   │   ├── logger.ts // Utilitaire de journalisation pour les démos
│   │   ├── setup.ts // Configuration des démos
│   │   └── index.ts // Export des utilitaires
│   ├── config/
│   │   ├── agent-config.ts // Configuration des agents
│   │   ├── llm-config.ts // Configuration des LLMs
│   │   └── index.ts // Export des configurations
│   ├── runners/
│   │   ├── cli-runner.ts // Exécution des scénarios via CLI
│   │   ├── web-runner.ts // Exécution des scénarios via serveur web
│   │   └── index.ts // Export des runners
│   └── index.ts // Point d'entrée principal
├── package.json
└── tsconfig.json
```

### Dépendances à utiliser
- `@multiagentsia/a2a-core`
- `@multiagentsia/langgraph`
- `@multiagentsia/llm-tools`
- `@multiagentsia/example-agent`
- `@multiagentsia/a2a-langgraph`

## Livrables Attendus
1. Le code source complet du module integration-demo
2. La structure des fichiers comme spécifiée
3. Des scénarios de démonstration fonctionnels et bien documentés
4. Un système de journalisation clair qui montre le flux d'exécution
5. Un README détaillé avec des instructions pour exécuter les démos

## Checklist à compléter
- [ ] Structure de fichiers créée
- [ ] Utilitaires de base implémentés (logger, setup)
- [ ] Configurations de base créées (agent, llm)
- [ ] Scénario de base implémenté
- [ ] Scénario A2A implémenté
- [ ] Scénario LangGraph implémenté
- [ ] Scénario complet implémenté
- [ ] CLI runner fonctionnel
- [ ] Web runner (simple) fonctionnel
- [ ] Documentation complète
- [ ] Exemples testés et vérifiés

## Règles Clés
- Assure-toi que les scénarios sont clairs et faciles à comprendre
- Utilise des commentaires détaillés pour expliquer le flux d'exécution
- Prévois une journalisation claire pour suivre les étapes d'exécution
- Les scénarios doivent fonctionner avec des mocks pour les tests, mais aussi avec des configurations réelles
- Le code doit servir d'exemple de meilleures pratiques pour l'utilisation de tous les modules

## Priorisation des tâches

Procède dans cet ordre pour maximiser l'efficacité du développement:

1. **D'abord les utilitaires et configurations**
   - Implémente le logger et les fonctions de setup
   - Crée les configurations de base pour agents et LLMs

2. **Puis les scénarios par ordre de complexité**
   - basic-scenario.ts: démontre l'utilisation d'un agent simple
   - a2a-scenario.ts: illustre la communication entre agents
   - langgraph-scenario.ts: montre l'orchestration avec LangGraph
   - complete-scenario.ts: intègre tous les modules

3. **Ensuite les runners**
   - cli-runner.ts: pour exécution en ligne de commande
   - web-runner.ts: pour exécution via interface web simple

4. **Finalisation**
   - Documentation complète dans README.md
   - Vérification que tout fonctionne ensemble