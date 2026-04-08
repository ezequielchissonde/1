# Arquitetura v1 - ASAMMPLAY Super App

## 1) Visão geral

A solução será composta por:

- App Android nativo (Kotlin + Jetpack Compose)
- App iOS nativo (Swift + SwiftUI)
- Backend API central (NestJS + PostgreSQL + Redis)
- Painel Admin Web (próxima fase) para gestão de módulos/conteúdo

Objetivo principal do MVP: autenticação, comunidade básica, notificações push, busca, catálogo de links externos e suporte offline para dados essenciais.

## 2) Princípios técnicos

1. **Offline-first:** leituras priorizam cache local; sincronização incremental com backend.
2. **Modularidade:** cada domínio funcional (Auth, Community, Booking, Coupons...) como módulo desacoplado.
3. **Segurança por padrão:** JWT curto + refresh token rotativo, criptografia de dados sensíveis, trilha de auditoria.
4. **Escalabilidade:** filas e cache para operações assíncronas (push, campanhas, importações).

## 3) Arquitetura mobile

### 3.1 Camadas

- **Presentation:** telas, componentes, ViewModels.
- **Domain:** casos de uso e regras de negócio.
- **Data:** repositórios, integrações API, cache local, mapeamento DTO <-> entidade.

### 3.2 Persistência local

- Android: Room
- iOS: SwiftData (ou Core Data se necessário)

### 3.3 Estratégia de sincronização

- Tabelas com `updatedAt` e `syncVersion`.
- Endpoint de `delta sync` por módulo.
- Fila local para comandos offline (ex.: envio de formulário sem internet).
- Política de conflito padrão: *last write wins* (inicial) com auditoria.

## 4) Arquitetura backend

### 4.1 Serviços/módulos iniciais

- `auth`: login email/senha, refresh token, OAuth Google/Apple.
- `users`: perfil e preferências.
- `community`: posts básicos e comentários iniciais.
- `links`: links externos categorizados (loja, redes sociais, WordPress, catálogos etc.).
- `notifications`: registro de dispositivo e disparo push.
- `search`: busca textual por conteúdos e links.

### 4.2 Infra

- PostgreSQL para dados transacionais.
- Redis para cache, rate limit e filas leves.
- Storage S3-compatible para mídia.
- Observabilidade mínima: logs estruturados + métricas + tracing básico.

## 5) Segurança e LGPD

- Senhas com Argon2/Bcrypt.
- Tokens JWT com expiração curta e refresh rotativo.
- Criptografia de dados sensíveis localmente no dispositivo.
- Consentimento explícito para notificações e coleta de dados.
- Endpoint para exportação/exclusão de dados do usuário.

## 6) Roadmap técnico (alto nível)

### Fase 1 (MVP)

- Auth completo
- Perfil
- Comunidade básica
- Push
- Busca
- Links externos
- Cache offline essencial

### Fase 2

- Formulários dinâmicos
- Agendamentos (TWIM)
- QRCode
- Cupons + fidelidade
- Doações + gateways de pagamento

### Fase 3

- Sorteios
- Quiz
- Lembrete de aniversários
- Gestão de senhas (definir escopo exato)
- Ferramentas utilitárias (calculadora etc.)
