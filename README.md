# ASAMMPLAY Super App - Kickoff

Este repositório inicia a construção do MVP nativo (Android + iOS) e backend para a plataforma ASAMMPLAY.

## Objetivo deste primeiro commit

- Definir a arquitetura alvo (mobile + backend + offline-first).
- Definir backlog inicial do MVP por fases.
- Publicar uma especificação inicial da API (`OpenAPI`) para acelerar implementação.

## Stack proposta

- **Android:** Kotlin, Jetpack Compose, MVVM, Clean Architecture.
- **iOS:** Swift, SwiftUI, MVVM, Clean Architecture.
- **Backend:** NestJS (TypeScript), PostgreSQL, Redis, S3-compatible storage.
- **Admin Web (fase seguinte):** Next.js.

## Entregáveis já incluídos

1. Arquitetura de referência: `docs/architecture.md`
2. Backlog priorizado do MVP: `docs/mvp-backlog.md`
3. API inicial v1 (OpenAPI): `docs/api-v1.yaml`

## Próximo passo recomendado

Implementar o backend base com os seguintes módulos primeiro:

1. Autenticação (email/senha + OAuth Google/Apple)
2. Usuário/perfil
3. Conteúdo/comunidade básico
4. Notificações push (registro de device token)
5. Links externos com categorias (Loja, redes sociais, WordPress etc.)

Depois, conectar os apps Android/iOS com cache offline local.
