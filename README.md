# 🧠 Como Conversar com as LLMs Igual um Expert / How to Talk to LLMs Like an Expert
### Miniguia de Engenharia de Prompts / Prompt Engineering Mini-Guide

---

## 🌐 Idioma / Language
* [Português (BR)](#-versão-em-português)
* [English (US)](#-english-version)

---

## 🇧🇷 Versão em Português

### 📝 Contexto e Objetivos
Este repositório foi desenvolvido para o Desafio de Projeto da DIO, utilizando o **NotebookLM** como plataforma de aprendizagem ativa e curadoria de conhecimento.

O objetivo deste Caderno Temático é desmistificar a **Engenharia de Prompts**, transformando a interação com Grandes Modelos de Linguagem (LLMs) de uma abordagem de "tentativa e erro" para uma metodologia técnica e previsível. O material foca em como profissionais de tecnologia podem estruturar comandos eficazes para acelerar o aprendizado, debugar códigos e automatizar tarefas com precisão cirúrgica.

### 🔍 Curadoria de Fontes
Para municiar o NotebookLM com o que há de mais avançado e conceitual sobre o tema, foram selecionadas as seguintes fontes de referência técnica e acadêmica, além de materiais em vídeo:

1. **Prompt Engineering Guide (DAIR.AI):** O principal repositório de técnicas, artigos e guias práticos sobre o ecossistema de prompts. [https://www.promptingguide.ai/](https://www.promptingguide.ai/)
2. **OpenAI Prompt Engineering Guide:** Documentação oficial com as melhores práticas recomendadas para extrair o máximo de modelos GPT. [https://platform.openai.com/docs/guides/prompt-engineering](https://platform.openai.com/docs/guides/prompt-engineering)
3. **Anthropic Technical Cookbook:** Guia avançado da criadora do Claude focado em estruturação de XML, contexto e redução de alucinações. [https://docs.anthropic.com/en/docs/welcome](https://docs.anthropic.com/en/docs/welcome)
4. *Artigo Acadêmico:* "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models" (Wei et al., Google Research) — Artigo base sobre o método de raciocínio passo a passo.
5. **Material Complementar em Vídeo:** Playlist de estudos com conteúdos práticos aplicados. [Acessar Playlist no YouTube](https://www.youtube.com/playlist?list=PLnTte7--UAGg4g-8GrS6RtdN3VqwKdb0x)
6. **Engenharia de Prompt: O Guia Definitivo (Bruno Picinini):** Vídeo completo abordando desde os fundamentos até técnicas complexas (como Chain of Thought e estruturação XML) na prática. [Assistir no YouTube](https://www.youtube.com/watch?v=1VDcke66TRE)

### 🧠 Engenharia de Prompts e "Cicatrizes" (Troubleshooting)
Para entender a engenharia de prompts na prática, documentei a evolução de um comando feito no NotebookLM e as dificuldades encontradas ao longo do caminho.

#### ❌ Prompt Inicial (Amador)
> **User:** Me dá dicas para melhorar um código Python.
* **Resultado:** A IA gerou dicas extremamente genéricas (use nomes de variáveis claros, comente seu código, etc.). Um resultado raso e pouco utilitário para o dia a dia de um programador.

#### 🚀 Prompt Evoluído (Nível Expert)
> **User:** Atue como um Engenheiro de Software Sênior e Especialista em Clean Code. Analise o trecho de código Python abaixo aplicando os seguintes critérios: 
> 1. Identifique possíveis gargalos de performance (I/O blocking).
> 2. Proponha a refatoração utilizando a abordagem assíncrona com `async/await`.
> 3. Forneça o resultado final estruturado e explique o raciocínio por trás de cada alteração.
> 
> [Inserir Código Aqui]
* **Resultado:** A resposta mudou completamente de nível. A IA assumiu a persona solicitada, fez uma análise crítica da arquitetura do código e entregou a refatoração exata com as justificativas técnicas.

#### 🩹 Cicatrizes e Aprendizados (Troubleshooting)
* **O Problema (Alucinação/Perda de Contexto):** Ao pedir para o NotebookLM analisar um fluxo muito longo, ele começou a misturar variáveis e inventar funções que não existiam nas fontes.
* **A Solução:** Aplicação da técnica de **Delimitadores**. Passei a envelopar os códigos e textos de exemplo estritamente dentro de tags limpas (ex: `[CÓDIGO INÍCIO]` e `[CÓDIGO FIM]`). Além disso, adicionei a restrição: *"Se a resposta não puder ser fundamentada estritamente nas fontes fornecidas, responda que não possui dados suficientes"*. Isso zerou os desvios da IA.

### 🚀 Miniguia de Estudo (Entrega Final)

#### 📋 Resumo Estruturado: Pilares de um Prompt Perfeito
Para conversar com uma LLM como um expert, seu comando deve idealmente conter 4 elementos básicos:
1. **Papel/Persona:** Quem a IA deve fingir ser? (Ex: "Atue como um DBA especialista em PostgreSQL").
2. **Contexto/Dados de Entrada:** Os fatos, o código ou o texto que precisa ser analisado.
3. **Instrução/Tarefa Clara:** O que exatamente ela deve fazer (Use verbos de ação: *Refatore, Resuma, Classifique*).
4. **Formato de Saída esperado:** Como você quer o resultado (Em uma tabela Markdown, em formato JSON, em tópicos).

#### 📖 Glossário de Técnicas Avançadas
* **Zero-Shot Prompting:** Fazer uma requisição direta para a IA sem dar nenhum exemplo prévio de resposta esperada.
* **Few-Shot Prompting:** Fornecer um ou mais exemplos de estruturas de "Entrada -> Saída" antes de fazer a pergunta real, moldando o padrão de resposta do modelo.
* **Chain-of-Thought (Cadeia de Raciocínio):** Forçar a IA a pensar e detalhar o passo a passo lógico *antes* de entregar a resposta final. Reduz drasticamente erros de lógica.
* **Alucinação:** Fenômeno onde a LLM gera uma resposta que parece confiável e gramaticalmente correta, mas que é factual ou logicamente falsa.

#### 🔄 Prompts Reutilizáveis para o Dia a Dia
* **Para Estudo Ativo:** *"Explique o conceito de [Inserir Tema] para uma pessoa leiga, usando uma analogia do cotidiano. Em seguida, crie 3 perguntas de múltipla escolha para testar meu conhecimento sobre o que foi explicado."*
* **Para Revisão de Código:** *"Atue como um revisor de código focado em segurança. Vasculhe o seguinte script em busca de vulnerabilidades (como SQL Injection ou vazamento de credenciais) e liste os pontos críticos de forma prioritária."*

---

## 🇺🇸 English Version

### 📝 Context and Objectives
This repository was developed for the DIO Project Challenge, utilizing **NotebookLM** as a platform for active learning and knowledge curation.

The main goal of this Thematic Notebook is to demystify **Prompt Engineering**, shifting interactions with Large Language Models (LLMs) from a "trial-and-error" approach to a technical and predictable methodology. The material focuses on how tech professionals can structure highly effective commands to accelerate learning, debug code, and automate tasks with surgical precision.

### 🔍 Curation of Sources
To feed NotebookLM with the most advanced and conceptual knowledge on the subject, the following technical and academic reference sources were selected, alongside video materials:

1. **Prompt Engineering Guide (DAIR.AI):** The leading repository for techniques, research papers, and practical guides in the prompt ecosystem. [https://www.promptingguide.ai/](https://www.promptingguide.ai/)
2. **OpenAI Prompt Engineering Guide:** Official documentation with best practices recommended to extract the most out of GPT models. [https://platform.openai.com/docs/guides/prompt-engineering](https://platform.openai.com/docs/guides/prompt-engineering)
3. **Anthropic Technical Cookbook:** Advanced guide by the creators of Claude focusing on XML structuring, context windows, and reducing hallucinations. [https://docs.anthropic.com/en/docs/welcome](https://docs.anthropic.com/en/docs/welcome)
4. *Academic Paper:* "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models" (Wei et al., Google Research) — The foundational paper on step-by-step reasoning methods.
5. **Complementary Video Material:** Study playlist with applied practical content. [Access Playlist on YouTube](https://www.youtube.com/playlist?list=PLnTte7--UAGg4g-8GrS6RtdN3VqwKdb0x)
6. **Prompt Engineering: The Definitive Guide (Bruno Picinini):** Complete video teaching everything from fundamentals to complex structuring techniques (like Chain of Thought and XML formatting) in practice. [Watch on YouTube](https://www.youtube.com/watch?v=1VDcke66TRE)

### 🧠 Prompt Engineering and "Battle Scars" (Troubleshooting)
To understand prompt engineering in practice, this section documents the evolution of a command built within NotebookLM and the challenges faced along the way.

#### ❌ Initial Prompt (Amateur)
> **User:** Give me tips to improve a Python code.
* **Result:** The AI generated extremely generic tips (use clear variable names, comment your code, etc.). A shallow result with very little utility for a developer's daily workflow.

#### 🚀 Evolved Prompt (Expert Level)
> **User:** Act as a Senior Software Engineer and Clean Code Specialist. Analyze the Python code snippet below applying the following criteria: 
> 1. Identify potential performance bottlenecks (I/O blocking).
> 2. Propose a refactoring utilizing an asynchronous approach with `async/await`.
> 3. Provide the final structured result and explain the reasoning behind each modification.
> 
> [Insert Code Here]
* **Result:** The response completely changed levels. The AI assumed the requested persona, performed a critical analysis of the code's architecture, and delivered the exact refactoring alongside solid technical justifications.

#### 🩹 Battle Scars and Lessons Learned (Troubleshooting)
* **The Problem (Hallucination / Context Loss):** When asking NotebookLM to analyze an extensive logic flow, it began to mix up variables and invent functions that didn't exist in the provided sources.
* **The Solution:** Application of the **Delimiters** technique. I started wrapping code snippets and example texts strictly within clean tags (e.g., `[CODE START]` and `[CODE END]`). Additionally, I added the following constraint: *"If the answer cannot be strictly grounded in the provided sources, respond that you do not have enough data."* This completely eliminated AI deviations.

### 🚀 Study Mini-Guide (Final Delivery)

#### 📋 Structured Summary: Pillars of a Perfect Prompt
To talk to an LLM like an expert, your command should ideally contain 4 core elements:
1. **Role / Persona:** Who should the AI pretend to be? (e.g., "Act as a DBA specializing in PostgreSQL").
2. **Context / Input Data:** The facts, code, or text that needs to be analyzed.
3. **Clear Instruction / Task:** What exactly it needs to do (Use action verbs: *Refactor, Summarize, Classify*).
4. **Expected Output Format:** How you want the results displayed (In a Markdown table, in JSON format, or bullet points).

#### 📖 Glossary of Advanced Techniques
* **Zero-Shot Prompting:** Making a direct request to the AI without providing any prior examples of the expected response.
* **Few-Shot Prompting:** Providing one or more examples of "Input -> Output" structures before asking the actual question, shaping the model's response pattern.
* **Chain-of-Thought (CoT):** Forcing the AI to think and detail its logical step-by-step process *before* delivering the final answer. This drastically reduces logic errors.
* **Hallucination:** A phenomenon where an LLM generates a response that looks confident and grammatically correct but is factually or logically false.

#### 🔄 Reusable Prompts for Daily Work
* **For Active Learning:** *"Explain the concept of [Insert Topic] to a layperson using a daily life analogy. Then, create 3 multiple-choice questions to test my knowledge on what was explained."*
* **For Code Review:** *"Act as a security-focused code reviewer. Scan the following script looking for vulnerabilities (such as SQL Injection or credential leaks) and list the critical points by priority."*

---
🔬 *Projeto desenvolvido como parte do ecossistema de aprendizado da [DIO](https://www.dio.me/).*
