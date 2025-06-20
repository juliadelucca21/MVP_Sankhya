```mermaid
graph TD
    A[Login do Operador no Coletor] --> B[Acessar Menu Principal]
    B --> C{Selecionar "Conferência"}
    C --> D[Bottom Sheet: Escolher "Conferência de Entrada"]
    D --> E[Stepper: Identificar Estágio do Processo]
    E --> F[Informar Doca de Recebimento (Obrigatório)]
    F --> G[Informar Dados do Produto]
    G --> H{Há mais itens para conferir?}
    H -- Sim --> I[Botão "Próximo Item"]
    I --> G
    H -- Não --> J[Botão "Enviar"]
    J --> K{Sistema Valida e Registra}
    K -- Sucesso --> L[Feedback: Envio Confirmado]
    K -- Erro --> M[Feedback: Erro de Preenchimento/Divergência]
    M --> G
