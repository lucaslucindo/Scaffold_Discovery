# Especificação Técnica

## 1. Visão Geral Técnica
Este documento orienta os desenvolvedores e engenheiros de infraestrutura na construção da versão V1 e V2 do MediFlow.

---

## 2. Arquitetura de Referência

Adotaremos uma arquitetura baseada em microsserviços para separar o motor de mensageria (WhatsApp) do core de gestão de agendas. 
- **Frontend:** Single Page Application (SPA).
- **Backend:** API RESTful.
- **Comunicação:** Webhooks para eventos do WhatsApp.
- **Deployment:** Containers Docker orquestrados em provedor cloud (AWS ou GCP).

---

## 3. Stack Tecnológica Recomendada
- **Frontend:** React.js (v18+) com Tailwind CSS.
- **Backend:** Node.js (v20+) com NestJS.
- **Persistência:** PostgreSQL (v15+) para dados relacionais e Redis para controle de filas de mensagens.
- **ORM:** Prisma.
- **Integrações:** WhatsApp Cloud API (Meta).

---

### 4. Segurança
- **Mecanismo de autenticação:** JWT (JSON Web Tokens).
- **Algoritmo:** RS256.
- **Tokens:** Access Token com expiração de 15 minutos e Refresh Token em cookie HTTP-Only.
- Criptografia TLS 1.3 em trânsito.

---

### 5. Auditoria
Todas as mudanças de status de agendamento (criado, confirmado, cancelado) devem ser registradas em uma tabela de log (`audit_logs`) com o ID do usuário (ou sistema) e o timestamp.

---

## 6. APIs
- **Endpoint principal:** `https://api.mediflow.com/v1`
- **Padrão:** RESTful utilizando nouns plurais (ex: `/patients`, `/appointments`).
- **Webhooks:** Endpoint não autenticado por usuário, mas validado via assinatura HMAC do provedor (Meta).

---

## 7. Tenancy
- **Estratégia:** Single-database, logical isolation (isolamento lógico via coluna `tenant_id` em todas as tabelas transacionais).

---

## 8. Diretrizes para Desenvolvimento Assistido por IA
Modelos de IA atuando como copilotos devem sempre verificar a variável `tenant_id` em consultas ao banco de dados e priorizar a criação de componentes React reutilizáveis no frontend.

---

## 9. Evolução Futura
Preparação para integração HL7/FHIR visando interoperabilidade com sistemas hospitalares maiores.