# 🤖 RAG Explorer : Mon premier pipeline de Retrieval-Augmented Generation

Bienvenue dans ce projet ! Ici, j'explore les bases du **RAG (Retrieval-Augmented Generation)**, une technique qui permet à une Intelligence Artificielle de répondre à des questions en s'appuyant sur des sources de données spécifiques et fiables (au lieu de se baser uniquement sur ses connaissances d'entraînement).

Ce projet est un "bac à sable" où j'ai implémenté de bout en bout la chaîne de traitement de l'information : de l'extraction de données sur le web à la génération de réponses précises via **Gemini**.

## 🚀 Ce que fait ce projet
Le but est simple : donner à l'IA un article de blog technique (ici, le célèbre article de Lilian Weng sur les agents IA) et lui permettre de répondre à des questions complexes sur son contenu sans "halluciner".

**Le workflow en 5 étapes :**
1.  **Extraction (Loading) :** Récupération du contenu HTML de l'article via `WebBaseLoader`.
2.  **Découpage (Splitting) :** Division du texte en petits morceaux (chunks) pour qu'ils soient digestes pour l'IA.
3.  **Vectorisation (Embedding) :** Transformation de ces textes en vecteurs mathématiques grâce au modèle de Google.
4.  **Stockage (Indexing) :** Sauvegarde dans une base de données vectorielle (**ChromaDB**) pour une recherche ultra-rapide.
5.  **Génération (RAG) :** Recherche des passages les plus pertinents et formulation d'une réponse par le modèle **Gemini 2.5 Flash**.

## 🛠️ Stack Technique
J'ai choisi des outils modernes et performants pour construire ce pipeline :
*   **Framework :** [LangChain](https://www.langchain.com/) (le standard pour les applications LLM).
*   **Modèles d'IA :** [Google Generative AI](https://ai.google.dev/) (Gemini pour les Embeddings et la Génération).
*   **Base de données :** [ChromaDB](https://www.trychroma.com/) (Vector Store open-source).
*   **Langage :** Python 🐍.

## 📈 Pourquoi ce projet ?
En tant que passionné d'IA, je voulais comprendre "sous le capot" comment les entreprises rendent les LLM plus fiables. Ce notebook m'a permis de manipuler des concepts clés :
- La gestion de la **fenêtre de contexte**.
- L'importance de la **qualité du découpage** du texte (chunking).
- Le fonctionnement des **bases de données vectorielles**.

## ⚙️ Installation
Si vous souhaitez tester le projet localement :

1. Clonez le repo :
   ```bash
   git clone https://github.com/dnelisee/rag-from-scratch.git
   ```
2. Installez les dépendances :
   ```bash
   pip install langchain langchain_community langchain_google_genai langchain-text-splitters chromadb bs4 
   ```
3. Configurez vos clés d'API (Google Cloud / AI Studio) le notebook.
4. Lancez le fichier `rag.ipynb` !

## 📝 Exemple de Résultat
Voici un exemple de question posée à l'IA via ce pipeline RAG :

**Question :** *"What is Task Decomposition?"*

**Réponse de l'IA :**
> "Task decomposition is a process that transforms big, complex tasks into multiple smaller, simpler, and more manageable steps. This can be achieved by instructing a model to \"think step by step\" (Chain of Thought) or by exploring multiple reasoning possibilities at each step, creating a tree structure (Tree of Thoughts).
>
> Task decomposition can be done in several ways:
> 1. By an LLM using simple prompts like \"Steps for XYZ.\" or \"What are the subgoals for achieving XYZ?\".
> 2. By using task-specific instructions, such as \"Write a story outline.\" for writing a novel.
> 3. With human inputs."

---
