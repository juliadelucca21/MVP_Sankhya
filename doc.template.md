# 📑 Sumário - Template de Documentação de Tela ERP

- [📄 Nome da Tela](#-nome-da-tela)
- [🔸 Módulo](#-módulo)
- [🔸 Versão](#-versão)
- [🔸 Descrição da Funcionalidade](#-descrição-da-funcionalidade)
- [🔸 Caminho de Acesso](#-caminho-de-acesso)
- [🔸 Pré-requisitos](#-pré-requisitos)
- [🧩 Estrutura da Tela](#-estrutura-da-tela)
- [👣 Jornada Passo a Passo](#-jornada-passo-a-passo)
- [⚠️ Pontos de Atenção](#️-pontos-de-atenção)
- [💡 Dicas de Usabilidade](#-dicas-de-usabilidade)
- [📘 Casos de Uso](#-casos-de-uso)
- [❓ Perguntas Frequentes (FAQ)](#-perguntas-frequentes-faq)
- [🔎 Artigos Relacionados](#-artigos-relacionados)
- [🧠 Palavras-chave para o Assistente](#-palavras-chave-para-o-assistente)


# 📄 Documentação de Tela - ERP

## 🔹 Nome da Tela  
**[Nome exato da tela no sistema]**

## 🔸 Módulo  
**[Nome do módulo funcional — ex: Vendas, Financeiro, Compras]**

## 🔸 Versão  
**[Versão mínima do sistema necessária para a funcionalidade]**

## 🔸 Descrição da Funcionalidade  
> Esta tela permite o **cadastro, edição e consulta de pedidos de venda**, controlando o ciclo de vendas do início ao faturamento.

## 🔸 Caminho de Acesso  
**Menu Principal > Submenu > Nome da Tela**

## 🔸 Pré-requisitos

- **Permissões Necessárias**:  
  - Acesso ao menu `Menu/Submenu`  
  - Permissões: inclusão, edição ou exclusão

- **Parâmetros Essenciais**:  
  - `USAESTOQUE=Sim`: para controle de estoque  
  - `HABILITAPEDVENDA=Sim`: para habilitar uso da tela

- **Configurações Relacionadas**:  
  - Cadastro de clientes ativos  
  - Tabela de preços configurada

---

## 🧩 Estrutura da Tela

### 🔸 Campos

| Nome do Campo | Tipo     | Obrigatório? | Descrição                     | Validações                    | Exemplo             |
|---------------|----------|--------------|-------------------------------|-------------------------------|---------------------|
| Cliente       | Pesquisa | Sim          | Cliente vinculado ao pedido  | Cliente deve estar ativo      | Comercial XPTO Ltda |
| Data Emissão  | Data     | Sim          | Data de criação do pedido    | Não pode ser futura           | 27/05/2025          |

### 🔸 Botões / Ações

| Botão   | Ação             | Comportamento Esperado       | Observações                         |
|---------|------------------|------------------------------|-------------------------------------|
| Novo    | Iniciar registro | Limpa os campos para edição | Sempre disponível                   |
| Salvar  | Gravar dados     | Mensagem de sucesso/erro     | Requer preenchimento obrigatório    |
| Excluir | Remover registro | Solicita confirmação         | Ação permanente e sem reversão      |

---

## 👣 Jornada Passo a Passo

1. Acesse via **Menu > Submenu > Tela**
2. Clique em **“Novo”**
3. Preencha os campos obrigatórios:
   - Cliente
   - Data Emissão
   - Produtos
4. Clique em **“Salvar”**
5. Para editar: selecione e clique em **“Editar”**
6. Para excluir: selecione e clique em **“Excluir”**
7. Utilize os filtros para buscar registros específicos

---

## ⚠️ Pontos de Atenção

- O sistema **não permite salvar** sem cliente ou produtos
- Pedidos podem ser **bloqueados por crédito**
- A exclusão é definitiva e **não reversível**
- Estoque deve estar disponível para reserva

---

## 💡 Dicas de Usabilidade

- Use **F2** para busca avançada
- Use **TAB** para navegação rápida
- **Duplicar** disponível via botão (se habilitado)
- Campos obrigatórios têm asterisco (*)

---

## 📘 Casos de Uso

### ✔ Cadastro de Pedido de Venda Padrão
> Um vendedor registra uma venda para "Loja Sol Nascente" preenchendo os dados e salvando o pedido.

### ✔ Edição de Pedido
> O cliente pediu troca de item. O usuário edita o pedido e substitui o produto.

### ❌ Tentativa com Cliente Inativo
> O sistema exibe “Cliente inativo” ao tentar salvar.

---

## ❓ Perguntas Frequentes (FAQ)

**1. Por que o botão “Salvar” está desabilitado?**  
Campos obrigatórios não preenchidos ou inválidos.

**2. Posso editar um pedido já faturado?**  
Não. Ele será somente leitura.

**3. Como excluir um pedido com itens?**  
Selecione e clique em “Excluir”. Confirmação necessária.

**4. O que significa “Produto sem saldo”?**  
Não há estoque suficiente para o item selecionado.

---

## 🔎 Artigos Relacionados

- [Cadastro de Clientes](#)
- [Tabela de Preços - Guia](#)
- [Parâmetro `USAESTOQUE`](#)
- [Regras de Crédito](#)
- [Relatório de Pedidos por Cliente](#)

---

## 🧠 Palavras-chave para o Assistente

> pedido de venda, cadastrar pedido, salvar pedido, editar pedido, excluir pedido, cliente inativo, erro ao salvar, produto sem estoque, configurar tabela de preço, restrição de crédito, tela de pedidos
