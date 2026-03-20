# Maxime Gagné — Architecte de Systèmes IA

> *"The real value will come from orchestrating agents to complete entire processes, with feedback from humans."*
> — McKinsey & Company, 2025 *(paraphrase condensée de The State of AI: Agents, innovation, and transformation)*

**On pourrait me reprocher mon manque d'expérience « classique ».**
Ce document montre que, sur les compétences clés identifiées par McKinsey, Gartner et les roadmaps IA 2026, mes systèmes implémentent déjà ce que les experts décrivent — pas en théorie, mais en code qui tourne.

---

### 〉Vision générale — Orchestration de Workflows Complets

> *"Les organisations qui capturent le plus de valeur avec l'IA redessinent des workflows entiers où agents et humains exécutent des processus multi-étapes."*
> — McKinsey, The State of AI, novembre 2025 *(paraphrase condensée)*

**Ma preuve — [SecondMind](https://github.com/Maxime-Gagne/SecondMind_portfolio_FR) :**
9 agents spécialisés qui coopèrent pour exécuter un processus complet, avec typage strict, validation systématique et audit automatique à chaque échange. Pas un chatbot isolé — un système qui orchestre un vrai workflow.

---

### 〉Compétence #1 — Prompt Engineering comme Architecture de Systèmes

> *"La valeur ne vient pas de prompts malins, mais de workflows d'agents déterministes et observables, capables de produire des résultats fiables en production."*
> — Roadmap IA 2026 *(synthèse de sources multiples)*

**Ma preuve — [SecondMind](https://github.com/Maxime-Gagne/SecondMind_portfolio_FR) :**
Le comportement du LLM n'est pas gouverné par des prompts flous, mais par des **contrats typés**.
Chaque agent reçoit des `Dataclasses` / `Pydantic models` en entrée et produit des `Dataclasses` validées en sortie.
L'`AgentAuditor` vérifie la conformité au **runtime** via analyse AST et bloque les réponses qui brisent le contrat.
Le prompt devient secondaire — l'architecture est gouvernée par le système de types, pas par de la « prompt magic ».

---

### 〉Compétence #2 — Validation des Sorties IA & Gouvernance

> *"La compétence clé est de construire des mécanismes de validation automatique et d'observabilité pour détecter les dérives avant qu'elles n'atteignent la production."*
> — Roadmap IA 2026 *(synthèse de sources multiples)*

**Ma preuve — [AgentAuditor](https://github.com/Maxime-Gagne/SecondMind_portfolio_FR/blob/main/Agentique/agent_Auditor/agent_Auditor.py) :**
Je n'ai pas misé sur la confiance implicite. J'ai construit l'**observabilité**.
`AgentAuditor` analyse statiquement le code au runtime (AST), détecte les dérives architecturales et bloque les échanges non conformes.
**Résultat réel documenté :** détection d'une fuite de données entre génération LLM et écriture mémoire — qui serait passée silencieusement dans un système naïf.

---

### 〉Compétence #3 — Orchestration Multi-Agents

> *"40% des applications d'entreprise intégreront des agents IA spécifiques d'ici 2026, avec une évolution vers des écosystèmes multi-agents orchestrant des workflows complexes."*
> — Gartner, 2025

**Ma preuve — [SecondMind](https://github.com/Maxime-Gagne/SecondMind_portfolio_FR) :**
9 agents spécialisés : orchestrateur, contexte, recherche, juge, parole, réflexion, mémoire, code, audit.
Chaque agent est un micro-service logique isolé.
La communication inter-agents se fait via **structures typées et validées** — aucun dictionnaire JSON non structuré ne circule dans le système.

---

### 〉Compétence #4 — Pensée Systémique Sous Contraintes

> *"Les architectes IA qui comptent sont ceux qui comprennent les trade-offs et les mesurent, au lieu de les supposer."*
> — McKinsey & roadmaps IA 2026 *(synthèse)*

**Ma preuve — [Optimisation KV Cache sur RTX 3090](https://github.com/Maxime-Gagne/SecondMind_portfolio_FR/blob/main/Docs/Plongee_au_coeur_de_la_Quantification_du_Cache_KV.pdf) :**
**Problème :** 130k tokens sur RTX 3090 (24 Go VRAM) — théoriquement impossible sans compromis.
**Solution :** quantification KV Cache Q4/Q8 avec benchmarks systématiques.
**Résultat mesuré :** réduction mémoire ~39% + gain de débit ~179%.
Le trade-off précision/performance a été **mesuré**, pas assumé.

---

### 〉Compétence #5 — Stack « Agent-First »

> *"Python typé, outputs structurés, observabilité par défaut — les prompts traités comme de l'infrastructure-as-code, pas comme du bricolage ad hoc."*
> — Roadmap IA 2026 *(synthèse de sources multiples)*

**Ma preuve — Stack [SecondMind](https://github.com/Maxime-Gagne/SecondMind_portfolio_FR) :**
Python avancé (métaclasses, AST, AOP) · Dataclasses & Pydantic · FAISS + SBERT · Llama.cpp · Logging cognitif par session.
Chaque décision technique répond à une contrainte d'**observabilité**, de **gouvernance** ou de **performance** — pas à une mode technologique.

---

### 〉Compétence #6 — Agilité par les Principes Premiers

> *"Les développeurs qui s'en sortent sont ceux qui savent réinterpréter les contraintes dans n'importe quelle stack — contextual synthesis plutôt que mémorisation de syntaxes."*
> — Roadmap IA 2026 *(synthèse de sources multiples)*

**Ma preuve — Polyvalence mesurée :**
- [Azure_Auditeur_Santé](https://github.com/Maxime-Gagne/Azure_Auditeur_Sante)  : audit de documents médicaux sur stack Azure inconnue — architecture livrée en **2 jours**
- [AI Workflow Discovery Agent](https://github.com/Maxime-Gagne/AI_Workflow_Discovery_Agent) : clustering NLP déterministe + pipeline 3 agents + génération DAG Airflow via Jinja2/AST — architecture livrée en **2 jours** sur stack inconnue

Je ne mémorise pas les syntaxes. Je comprends la **place de chaque outil dans l'architecture globale**.

---

### 〉Compétence #7 — Taste & Jugement Architectural

> *"Savoir quand une solution est simplement 'qui marche' versus 'la bonne solution' à long terme — c'est le jugement qui distingue l'architecte de l'exécutant."*
> — Analyses sur l'AI engineer, 2025-2026 *(synthèse)*

**Ma preuve — [MetaAgent, métaclasse commune](https://github.com/Maxime-Gagne/SecondMind_portfolio_FR/blob/main/metabase/META_agent.py) :**
Plutôt que de répéter l'initialisation du logger, de l'auditeur et de la mémoire dans chaque agent, j'ai conçu une **métaclasse** qui injecte ces dépendances automatiquement à l'instanciation.
Résultat : zéro boilerplate, cohérence garantie à l'échelle, base solide pour faire évoluer la stack sans effet domino.
Ce n'était pas nécessaire pour que « ça marche » — c'était nécessaire pour que ce soit **bien conçu**.

---

### 〉Compétence #8 — Vision Systémique & Éthique de l'IA

> *"Une IA optimise des objectifs — parfois en contradiction avec les intérêts humains — si on ne les explicite pas. La sur-confiance dans des systèmes opaques est le vrai risque."*
> — Chercheurs en agentic AI, 2025-2026 *(synthèse)*

**Ma preuve — Réflexion formulée 1 mois après avoir commencé l'IA :**
*« Le vrai danger n'est pas une IA malveillante, mais notre propre anthropomorphisme et notre confiance aveugle envers des systèmes qui optimisent des objectifs de manière indifférente aux valeurs humaines. »*
Même conclusion que des voix reconnues comme Hannah Fry — par raisonnement indépendant.
Cette vision oriente mes architectures : d'où l'importance de l'audit, des contrats et de l'observabilité.

---

## Portfolio

| Projet | Description | Stack | Délai |
|--------|-------------|-------|-------|
| [SecondMind](https://github.com/Maxime-Gagne/SecondMind_portfolio_FR) | Système cognitif multi-agents local, 130k tokens, gouvernance AST | Python, FAISS, SBERT, Llama.cpp | 6 mois R&D |
| [Azure_Auditeur_Santé](https://github.com/Maxime-Gagne/Azure_Auditeur_Sante) | Pipeline d'audit de documents médicaux, conformité, traçabilité | Azure, Streamlit, Python | 2 jours |
| [AI Workflow Discovery Agent](https://github.com/Maxime-Gagne/AI_Workflow_Discovery_Agent) | Clustering NLP + pipeline 3 agents + génération DAG Airflow | Gemini, HDBSCAN, Pydantic, Graphviz, Docker | 2 jours |
| PrixJuste *(en développement)* | App mobile de détection d'erreurs de prix en épicerie, OCR hybride | Flutter, FastAPI, Gemini, ML Kit | — |

---

## Contact

📧 maximegagne.ai@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/maxime-gagné-6b14541b9/)

---

*« Le développeur qui survivra à 2026 n'est pas celui qui code le mieux — c'est celui qui architecture le mieux, valide le mieux, et orchestre le mieux. »*
— Roadmap IA 2026
