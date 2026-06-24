+++
title = "Vibe coding: o fluxo que tem funcionado pra mim"
date = 2026-06-24
draft = false
tags = ["vibe-coding", "ia", "llm", "agentes"]
weight = 2
+++

Vibe coding virou termo pegajoso. Antes de opinar se é "o fim da programação" ou "modinha", deixo registrado o fluxo real que tem funcionado pra mim — com agentes de código tipo OpenCode e Claude Code.

## A premissa

Vibe coding não é "dar um prompt gigante e rezar". É **dirigir** o agente: definir o escopo, escrever os testes/arquitetura, revisar o que ele produz e manter o humano no controle das decisões.

## O ciclo que tem funcionado

1. **Especificar pequeno** — uma tarefa por vez, com contexto suficiente
2. **Deixar o agente propor** — deixo ele escrever o primeiro rascunho
3. **Revisar com olho crítico** — nunca aceitar cego; ler o diff
4. **Testar cedo** — rodar testes/compilar depois de cada passo
5. **Iterar** — corrigir o rumo com prompts curtos e específicos

## Onde funciona bem

- Projetos pequenos e bem delimitados
- Código boilerplate, refatoração mecânica
- Scripts e protótipos de uma tacada só
- Aprender uma linguagem/framework novo (o agente como tutor)

## Onde costuma falhar

- Sistemas grandes sem arquitetura clara
- Bugs que dependem de estado distribuído
- Requisitos vagos — o agente adivinha, e adivinhação não é engenharia
- Qualquer coisa que você mesmo não consegue avaliar se está certa

## O ponto

A LLM não substitui entender o que você está construindo. Ela **acelera** quem já sabe o que quer. Pra mim, vibe coding é isso: uma alavanca, não um piloto automático.

Próximos posts entram em exemplos concretos: projetos reais, prompts que funcionaram, e os que explodiram no meio.