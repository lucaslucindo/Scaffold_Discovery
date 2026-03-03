# Definição de Requisitos do Produto (PRD)

## Descrição do produto

**Problema:** Clínicas populares perdem receita com faltas de pacientes e sofrem com filas na recepção devido à triagem manual.

**Solução:** O MediFlow é uma plataforma web integrada ao WhatsApp que automatiza confirmações de agenda e realiza questionários de pré-triagem clínica de forma assíncrona.

Para as **Clínicas e Pacientes**, o sistema reduz o tempo de espera na recepção em até 70% e diminui a ociosidade médica ao liberar horários vagos automaticamente.

Nossos Diferenciais:
- Integração nativa com a API Oficial do WhatsApp.
- Pré-triagem configurável pelos próprios médicos.
- Dashboard de gestão de ociosidade em tempo real.

---

## Perfis de Usuário

### Recepcionista
- **Problemas:** Perde horas do dia enviando mensagens manuais para confirmar consultas.
- **Objetivos:** Ter a agenda atualizada automaticamente com status de "Confirmado", "Cancelado" ou "Pré-triado".
- **Dados demográficos:** Profissionais de 20 a 40 anos, ensino médio/técnico, alta familiaridade com sistemas web básicos.
- **Motivações:** Reduzir o estresse do balcão e focar no atendimento humanizado.
- **Frustrações:** O sistema atual da clínica não avisa quando o paciente cancela em cima da hora.

---

## Principais Funcionalidades

### RFN-01 Confirmação Automatizada via WhatsApp
- O sistema deve enviar uma mensagem de confirmação 24h antes da consulta com botões de ação ("Confirmar" ou "Cancelar").
- **Critérios de Aceitação:** A resposta do paciente deve alterar o status da consulta no dashboard em menos de 5 segundos. Se cancelado, o horário deve ficar disponível para encaixe.

### RFN-02 Link de Pré-triagem
- Após a confirmação, o paciente recebe um link web leve para preencher sintomas e histórico.
- **Critérios de Aceitação:** O formulário deve ser responsivo (mobile first) e salvar os dados diretamente no prontuário temporário do sistema.

---

## Requisitos Não Funcionais

### RNF-01 - Disponibilidade e Latência
O sistema deve estar disponível 99.9% do tempo comercial (07h às 19h) e carregar as telas do dashboard em menos de 2 segundos para não atrasar a recepção.

---

## Métricas de Sucesso
- Redução da taxa de no-show para menos de 10%.
- 80% dos pacientes confirmados preenchendo a pré-triagem online.

---

## Premissas e restrições
- A clínica deve ter conexão à internet estável.
- O paciente deve ter WhatsApp instalado no celular.

## Escopo
- **V1:** Confirmação via WhatsApp e Dashboard de visualização.
- **V2:** Módulo de pré-triagem digital e integração com prontuários externos.