# Guía: documentar un repo para trabajar con IA

Receta práctica, independiente del stack, para dejar un repositorio listo para
que un agente de IA (Claude Code, Antigravity, Cursor, etc.) trabaje con poca
supervisión y sin romper las cosas que fallan en silencio.

> **Idea central:** la IA no recuerda nada entre sesiones. Lo que no está
> escrito en el repo, no existe. La documentación **es** el contexto del agente.

📖 **[Leer la guía completa](guia-documentacion-con-ia.md)**

Está sacada de cómo se armó una plataforma SaaS multi-tenant real (monorepo,
Clean Architecture, PostgreSQL con RLS, Next.js), pero aplica a cualquier
proyecto.

## Qué vas a encontrar

| Parte | Contenido |
| :--- | :--- |
| **I. Primeros pasos** | Estructura base del repo y el orden para arrancar. |
| **II. Cómo se arma el repo** | `AGENTS.md` / `CLAUDE.md`, monorepo, Clean Architecture y patrones, documentos de arquitectura, skills, migraciones y ADRs, `status.md`, Git y CI. |
| **III. Planear el MVP y las tareas** | Cómo armar el plan de alcance (P0/P1/P2) paso a paso con la IA y cómo convertirlo en tareas. |
| **IV. Trabajar con la IA** | Ciclo de trabajo, reparto humano/IA, prompts buenos vs. malos y troubleshooting. |
| **Apéndices** | Plantillas copiables, checklist de arranque, errores comunes y glosario. |

## La receta en 8 pasos

1. Crear el entorno reproducible (`CONTRIBUTING.md`).
2. Escribir `AGENTS.md` con stack, comandos y reglas que no se negocian.
3. Escribir el plan de alcance **antes** de pedirle código a la IA.
4. Documentar la arquitectura y una receta de "feature nueva" por área.
5. Instalar las skills del stack (`skills-lock.json`).
6. Configurar CI y el flujo de Git.
7. Crear `status.md` para registrar qué está hecho y cómo se verificó.
8. Trabajar con tareas chicas, una por sesión.

## Ideas clave

- **`AGENTS.md` es un contrato.** Solo entran reglas que, al romperlas, fallan
  en silencio, cada una con su consecuencia. `CLAUDE.md` solo contiene
  `@AGENTS.md`.
- **Monorepo + Clean Architecture** dan a la IA contexto completo, fronteras
  claras y recetas repetibles.
- **Las garantías críticas se hacen cumplir por máquina** (base de datos, tests,
  CI), no por memoria de la IA ni de las personas.
- **El alcance dice qué construir y qué no.** Se define con prioridades
  P0/P1/P2 y una lista explícita de ideas que quedan afuera.
- **Los ADRs registran el porqué** y las alternativas descartadas.
- **Verificar de verdad:** "compila" no es "funciona". Se exige evidencia.

## Para quién es

Equipos o personas que empiezan un proyecto con IA, o que quieren ordenar uno
existente para que los agentes dejen de inventar, duplicar o desviarse.

## Cómo usarla

1. Leé "Cómo leer esta guía" al inicio del documento.
2. Seguí el checklist del apéndice para configurar tu repo.
3. Copiá las plantillas (alcance, tarea, ADR, PR, `status.md`) y adaptalas.

---

Hecho por [@IvanRomeroMaurin](https://github.com/IvanRomeroMaurin).
