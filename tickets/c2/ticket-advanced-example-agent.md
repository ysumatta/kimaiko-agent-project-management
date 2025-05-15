# Ticket: Développement de l'agent exemple avancé

[Règles et méthodologie du projet](../../project-rules.md)

## Contexte Global
Le MVP Zéro dispose maintenant de modules fondamentaux terminés (a2a-core, langgraph, llm-tools). Nous pouvons développer un agent exemple plus sophistiqué qui utilise toutes ces fonctionnalités.

## Mission Spécifique
Développer un agent exemple avancé dans le module `packages/advanced-example-agent` qui démontrera l'intégration complète de:
1. Agents LangGraph avec modèle BDI
2. Communication via le protocole A2A
3. Utilisation des LLMs via le module llm-tools

## Spécifications Techniques Détaillées

### Structure de l'agent
L'agent exemple sera un "Assistant Intelligent" qui peut:
- Analyser des requêtes utilisateur (via llm-tools)
- Planifier des étapes de réponse (via LangGraph BDI)
- Déléguer certaines tâches à d'autres agents (via A2A)
- Synthétiser une réponse finale

### Structure des fichiers
```typescript
packages/advanced-example-agent/
├── src/
│   ├── types/
│   │   ├── assistant.ts // Types pour l'assistant
│   │   ├── task.ts // Types pour les tâches
│   │   └── index.ts // Export des types
│   ├── nodes/
│   │   ├── analyze-node.ts // Nœud d'analyse des requêtes
│   │   ├── plan-node.ts // Nœud de planification
│   │   ├── delegate-node.ts // Nœud de délégation via A2A
│   │   ├── synthesis-node.ts // Nœud de synthèse
│   │   └── index.ts // Export des nœuds
│   ├── agent/
│   │   ├── assistant-agent.ts // Agent principal
│   │   ├── agent-card.ts // Carte d'agent A2A
│   │   └── index.ts // Export de l'agent
│   ├── server/
│   │   ├── a2a-server.ts // Serveur A2A pour l'agent
│   │   └── index.ts // Export du serveur
│   ├── demo/
│   │   ├── cli-demo.ts // Démo en ligne de commande
│   │   └── index.ts // Script principal de démo
│   └── index.ts // Point d'entrée principal
├── package.json
└── tsconfig.json
```

### Dépendances à utiliser
- `@multiagentsia/a2a-core`: Pour la communication A2A
- `@multiagentsia/langgraph`: Pour la structure de l'agent BDI
- `@multiagentsia/llm-tools`: Pour l'intégration des LLMs

### Fonctionnalités spécifiques
1. L'assistant utilisera une architecture BDI complète:
   - Beliefs: État de la conversation, compréhension de la requête
   - Desires: Objectifs dérivés de la requête utilisateur
   - Intentions: Plan d'action choisi
   - Plan: Séquence de nœuds à exécuter

2. L'agent pourra déléguer des tâches spécifiques via A2A:
   - Recherche d'information (simulée)
   - Génération de contenu créatif
   - Calculs ou transformations

3. L'agent utilisera les LLMs pour:
   - Comprendre les requêtes (analyze-node)
   - Planifier des réponses (plan-node)
   - Synthétiser le résultat final (synthesis-node)

## Livrables Attendus
1. Le code source complet du module advanced-example-agent
2. La structure des fichiers comme spécifiée
3. Une démo en ligne de commande fonctionnelle
4. Documentation dans le code et un README détaillé

## Checklist à compléter
- [ ] Structure de fichiers créée
- [ ] Types pour l'assistant et les tâches définis
- [ ] Nœuds LangGraph implémentés (analyse, planification, délégation, synthèse)
- [ ] Agent principal utilisant l'architecture BDI
- [ ] Intégration A2A pour la délégation de tâches
- [ ] Utilisation des LLMs via llm-tools
- [ ] Démo en ligne de commande
- [ ] Documentation complète
- [ ] Tests unitaires de base

## Règles Clés
- Respecte les principes SOLID et la Clean Architecture établie
- Utilise le mock LLM pour les tests et la démo
- Assure-toi que l'agent démontre clairement l'intégration des trois modules
- Prévois des messages de débogage clairs pour suivre le flux d'exécution