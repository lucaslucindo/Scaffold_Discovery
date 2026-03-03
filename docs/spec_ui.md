# Especificação de UI

## Interfaces gráficas


### INT-01 - Dashboard da Recepção (Kanban de Consultas)
- **Tipo de contêiner:** Página Principal
- **Campos:** Cartões de pacientes com Nome, Horário, Status (Aguardando Confirmação, Confirmado, Cancelado, Triagem Concluída).
- **Botões:** "Novo Encaixe", "Reenviar WhatsApp".
- **Links:** "Ver Prontuário", "Configurações".
- **Considerações:** A tela deve ter auto-refresh a cada 30 segundos ou via WebSockets para refletir respostas instantâneas no WhatsApp.

### INT-02 - Formulário de Pré-Triagem (Mobile)
- **Tipo de contêiner:** Formulário (Pública)
- **Campos:** Queixa principal (texto longo), Histórico de alergias (checkboxes), Uso de medicação (texto).
- **Botões:** "Enviar Informações".
- **Considerações:** Interface com fontes grandes e alto contraste, otimizada para conexões 3G/4G, sem necessidade de login.

---

## Fluxo de Navegação
1. Recepcionista faz Login -> Redirecionado para INT-01 (Dashboard).
2. Paciente clica no link do WhatsApp -> Abre INT-02 (Pré-triagem).
3. Paciente clica em "Enviar" na INT-02 -> Recepcionista vê o status do card atualizar na INT-01.

---

## Diretrizes para IA
Ao gerar código de frontend, a IA deve utilizar o Tailwind CSS seguindo um padrão de cores focado em saúde (tons de azul e verde pastel) para transmitir tranquilidade e clareza.