# Ticket: Développement du module d'intégration UI

[Règles et méthodologie du projet](../../project-rules.md)

## Contexte Global
Maintenant que les composants fondamentaux du MVP Zéro sont terminés, nous avons besoin d'un module d'intégration UI simple qui permettra d'interagir facilement avec nos agents depuis différentes interfaces.

## Mission Spécifique
Créer un module `packages/ui-integration` qui fournira:
1. Une API REST simple pour interagir avec les agents
2. Une interface en ligne de commande (CLI) pour les tests
3. Un adaptateur WebSocket pour les interfaces en temps réel

## Spécifications Techniques Détaillées

### Composants à implémenter
- `RESTAdapter`: Adaptateur pour exposer les agents via une API REST
- `CLIAdapter`: Interface en ligne de commande pour tester les agents
- `WebSocketAdapter`: Adaptateur pour communication en temps réel

### Structure des fichiers
```typescript
packages/ui-integration/
├── src/
│   ├── types/
│   │   ├── adapter.ts // Types d'adaptateurs
│   │   ├── message.ts // Types de messages
│   │   └── index.ts // Export des types
│   ├── adapters/
│   │   ├── rest-adapter.ts // Adaptateur REST
│   │   ├── cli-adapter.ts // Adaptateur CLI
│   │   ├── websocket-adapter.ts // Adaptateur WebSocket
│   │   └── index.ts // Export des adaptateurs
│   ├── server/
│   │   ├── express-server.ts // Serveur Express pour REST
│   │   ├── socket-server.ts // Serveur WebSocket
│   │   └── index.ts // Export des serveurs
│   ├── cli/
│   │   ├── commands.ts // Commandes CLI
│   │   ├── prompt.ts // Gestionnaire de prompt
│   │   └── index.ts // Point d'entrée CLI
│   ├── demo/
│   │   ├── rest-demo.ts // Démo de l'API REST
│   │   ├── cli-demo.ts // Démo CLI
│   │   ├── websocket-demo.ts // Démo WebSocket
│   │   └── index.ts // Script de démo principal
│   └── index.ts // Point d'entrée principal
├── package.json
└── tsconfig.json
```

### Dépendances à utiliser
- `express` pour l'API REST
- `ws` ou `socket.io` pour WebSocket
- `commander` et `inquirer` pour CLI
- `@multiagentsia/a2a-core` pour la communication avec les agents
- `@multiagentsia/example-agent` pour les démos

## Livrables Attendus
1. Le code source complet du module ui-integration
2. La structure des fichiers comme spécifiée
3. Démos fonctionnelles pour REST, CLI et WebSocket
4. Documentation dans le code et un README détaillé

## Checklist à compléter
- [ ] Structure de fichiers créée
- [ ] Types d'adaptateurs définis
- [ ] Adaptateur REST implémenté
- [ ] Adaptateur CLI implémenté
- [ ] Adaptateur WebSocket implémenté
- [ ] Serveur Express pour API REST
- [ ] Serveur WebSocket
- [ ] Interface CLI complète
- [ ] Démos fonctionnelles
- [ ] Documentation complète
- [ ] Tests unitaires de base

## Règles Clés
- Assure-toi que les adaptateurs sont génériques et peuvent fonctionner avec n'importe quel agent
- L'API REST doit suivre les meilleures pratiques RESTful
- La CLI doit être intuitive et fournir une aide claire
- Le WebSocket doit gérer les connexions/déconnexions proprement
- Toutes les interfaces doivent permettre d'interagir de manière cohérente avec les agents