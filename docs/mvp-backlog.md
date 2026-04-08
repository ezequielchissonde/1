# Backlog MVP - ASAMMPLAY

## Épico A - Plataforma Base

### A1. Autenticação
- [ ] Cadastro com email/senha
- [ ] Login com email/senha
- [ ] Login com Google
- [ ] Login com Apple
- [ ] Recuperação de senha
- [ ] Refresh token

### A2. Perfil
- [ ] Visualizar/editar perfil
- [ ] Preferências de notificação
- [ ] Exclusão de conta

## Épico B - Conteúdo e Comunidade

### B1. Comunidade
- [ ] Feed de posts
- [ ] Criação de post simples (texto + imagem)
- [ ] Comentários
- [ ] Curtidas

### B2. Busca
- [ ] Busca por posts
- [ ] Busca por links externos

## Épico C - Hub de Integrações

### C1. Links externos
- [ ] Cadastro por categoria (Loja, Redes Sociais, WordPress, Catálogos, Galeria)
- [ ] Abertura segura no app (WebView controlada) ou deep link
- [ ] Métricas básicas de clique

## Épico D - Notificações

### D1. Push
- [ ] Registro de device token
- [ ] Segmentação inicial por plataforma
- [ ] Envio de push manual via painel (fase web)

## Épico E - Offline-first

### E1. Cache e sync
- [ ] Cache local de feed, perfil e links
- [ ] Sincronização incremental
- [ ] Fila offline para ações pendentes

## Critérios de aceite do MVP

1. Usuário autentica por email/senha ou social login.
2. Usuário navega em feed e links externos com busca.
3. App funciona com leitura de dados recentes sem internet.
4. Push pode ser enviado para usuários autenticados.
5. Base técnica pronta para módulos avançados (agendamento, formulários, pagamentos etc.).
