# Project brief - Blog IT & Automatisation

**Document de cadrage - version de travail du 24 octobre 2026**  
**Langue de l’équipe et de la documentation : français**  
**Équipe : 8 personnes, Product Owner compris**

## 1. Vision du produit

Créer un blog pratique consacré à l’informatique et à l’automatisation. Les visiteurs peuvent lire des guides publiés ; les contributeurs peuvent créer un compte et publier leurs propres guides.

## 2. Utilisateurs et responsabilités

- **Visiteur** : consulte la liste des guides publiés et ouvre un guide pour le lire.
- **Contributeur** : crée un compte, se connecte, rédige et publie un guide.
- **Product Owner (1 personne)** : porte l’objectif du produit, définit et ordonne le backlog, clarifie les besoins et vérifie les critères d’acceptation avec l’équipe.
- **Équipe de réalisation (7 personnes)** : s’organise pour découper et réaliser le travail ; elle choisit les solutions techniques, développe, teste, relit et documente le code. Les responsabilités peuvent être partagées ou tourner.

Le Product Owner donne la direction et les priorités ; il ne distribue pas les tâches de réalisation à la place de l’équipe.

## 3. MVP - première version utile

Le MVP comprend le parcours suivant :

1. Le visiteur voit la liste des guides publiés.
2. Le visiteur ouvre un guide et lit son titre et son contenu.
3. Une personne peut créer un compte contributeur et se connecter.
4. Le contributeur rédige puis publie un guide ; le guide publié devient consultable par les visiteurs.

### Critères d’acceptation initiaux

- La liste publique ne présente que des guides publiés.
- Chaque guide publié possède une page de lecture accessible au visiteur.
- Un contributeur connecté peut publier un guide contenant au minimum un titre et un contenu.
- L’auteur ne peut pas agir sur le compte d’un autre utilisateur.
- Le contenu publié est enregistré dans une base de données et reste disponible après le redémarrage ou le redéploiement du service.
- Les mots de passe sont stockés sous forme de hachage ; les secrets de configuration ne sont pas ajoutés au dépôt Git.

Les critères seront précisés et découpés en user stories dans Azure Boards avant leur réalisation.

## 4. Périmètre futur

Ces fonctions ne sont pas nécessaires au premier MVP et pourront être priorisées plus tard : recherche avancée, filtres et catégories, commentaires, likes, téléversement d’images, newsletter, modération avancée, multilingue, Kubernetes et Ansible.

La langue de l’application destinée aux visiteurs reste à décider. Elle est distincte de la langue de travail de l’équipe, qui est le français.

## 5. Architecture et outils envisagés

- **Application web et API** : Python, FastAPI et Jinja2.
- **Hébergement de démonstration** : un Render Web Service héberge l’application et son API.
- **Données persistantes** : PostgreSQL est envisagé pour les données publiées ; Azure Database for PostgreSQL reste à valider avec l’offre Azure for Students et les coûts affichés avant la création de la ressource.
- **Développement local** : une base locale peut servir aux essais ; elle ne doit pas être considérée comme stockage durable sur le service gratuit Render.
- **Code** : dépôt GitHub ; branches courtes, commits compréhensibles et pull requests vers `main`.
- **Planification** : Azure Boards, avec epics, user stories, tâches, bugs et priorités.
- **CI** : pipeline automatisée de tests et contrôles avant fusion ; l’implémentation technique est à planifier.

Aucune ressource payante ni conversion vers Pay-As-You-Go ne sera activée sans accord préalable du Product Owner. Avant de déployer la base Azure, l’équipe vérifiera l’éligibilité, le crédit étudiant, la limite de dépenses et les alertes de coûts.

## 6. Méthode de travail

L’équipe suit le cycle représenté dans [`process/agile-workflow-fr.pdf`](process/agile-workflow-fr.pdf) : objectif, MVP, user stories et critères, backlog priorisé, UML, petit incrément, tâches, développement et tests, CI, démonstration, retours, amélioration.

Le backlog détaillé est maintenu dans Azure Boards. Le travail peut être visualisé avec les colonnes **À faire → En cours → Revue → Terminé**, en limitant le nombre de tâches commencées en même temps.

### UML

Un diagramme de cas d’utilisation accompagne le cadrage du produit. Les autres diagrammes utiles (composants, données, séquence) sont ajoutés au fil des décisions et mis à jour lorsque le périmètre ou la conception évolue. Le diagramme initial est dans [`uml/use-case-diagram.puml`](uml/use-case-diagram.puml), avec son export SVG.

## 7. Hors décision / à confirmer

- Langue initiale du site destiné aux visiteurs.
- Choix et disponibilité de la base PostgreSQL Azure pour l’offre étudiante.
- Critères exacts de rédaction et contenu des guides.
- Rythme des itérations et date de démonstration.
- Gestion éventuelle de signalements ou de modération après le MVP.

Ces points sont clarifiés dans le backlog ou dans un document de décision avant d’affecter le périmètre du MVP.
