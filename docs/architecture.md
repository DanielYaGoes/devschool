# Arquitetura do DevSchool

Este documento descreve a arquitetura inicial do projeto DevSchool.

O objetivo é registrar como o sistema será organizado, quais decisões arquiteturais foram tomadas e como o projeto poderá evoluir ao longo do tempo.

---

## Visão Geral

O DevSchool será uma plataforma de estudos desenvolvida para praticar conceitos de Engenharia de Software.

O sistema começará como uma aplicação simples, mas será construído com organização suficiente para permitir evolução futura.

Inicialmente, o projeto será desenvolvido como um backend em Spring Boot, expondo uma API REST.

---

## Estilo Arquitetural

O projeto será desenvolvido como um **Monólito Modular**.

Isso significa que a aplicação será entregue como uma única aplicação, mas seu código será separado em módulos de negócio bem definidos.

Exemplo:

```text
devschool

auth
course
lesson
student
progress
notification
report