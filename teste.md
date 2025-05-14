# Processamento NFS-e

A tela de **Processamento NFS-e** permite que o usuário preencha manualmente as informações necessárias para integrar uma Nota Fiscal de Serviço Eletrônica (NFS-e) ao sistema, mesmo quando não há um modelo de integração previamente configurado. Essa funcionalidade é especialmente útil para garantir que documentos fiscais sejam processados corretamente em situações mais específicas ou fora do padrão habitual.

![Processamento NFS-e](ProcesamentoNFSe.png)

---

## Funcionalidades da tela

- [Quando utilizar essa tela?](#quando-utilizar-essa-tela)
- [Campos da tela](#campos-da-tela)
- [Funcionamento](#funcionamento)
- [Parâmetros que influenciam a rotina](#parâmetros-que-influenciam-nessa-rotina)

---

## Quando utilizar essa tela?

Esta tela é utilizada para **gerenciar a integração de NFS-e**, permitindo configurar informações essenciais como Empresa, Tipo de Operação, Natureza, Parceiro, Serviço, entre outros campos relacionados à entrada de notas de serviço.

Além disso, possibilita a **consulta dos registros já processados**, facilitando a verificação das configurações aplicadas em cada integração e oferecendo maior controle e rastreabilidade do processo.

### Como os dados chegam nessa tela?

A origem dos dados apresentados na tela de vinculação manual é a **integração ASIS**, que realiza a captura automática das NFS-e diretamente da prefeitura ou do provedor do município.

Após a configuração dos tokens de autenticação e da integração NFS-e na plataforma **Kolossus (ASIS)**, as notas fiscais são recebidas e, quando o processo de integração automática não pode ser concluído (por ausência de modelo, dados inconsistentes ou regras específicas de negócio), os dados são direcionados para a tela de **Processamento NFSe**, onde ficam disponíveis para **vinculação manual**.

> Dessa forma, toda a configuração de integração, tais como: adicionar e editar Nota Modelo, antes obrigatória, será opcional.

---

## Campos da tela

Ao processar a nota, será possível preencher as informações das seguintes abas:

- **Informações da Nota**
- **Dados do Prestador**
- **Serviço Prestado**

Dentro delas, há campos que devem ser preenchidos manualmente, sendo alguns deles **obrigatórios** para que a integração seja concluída com sucesso.

### Campos obrigatórios

- Empresa  
- TOP (Tipo de Operação)  
- Tipo de Negociação  
- Parceiro  
- Serviço  

Esses campos são essenciais para o correto entendimento e processamento da nota fiscal pelo sistema.

### Campos opcionais

- Natureza  
- Centro de Resultado  
- Projeto  

Podem ser utilizados conforme a necessidade de classificação e controle interno da empresa.

[🔝 Voltar ao topo](#processamento-nfs-e)

---

## Funcionamento

O preenchimento manual permite **maior flexibilidade**, especialmente em casos onde não há modelos previamente cadastrados.

Se os dados da nota já tiverem sido vinculados anteriormente, como a empresa ou o tipo de serviço, o sistema reaproveita essas informações e permite que a integração ocorra **sem a necessidade de preenchê-los novamente**.

Se houver **alteração no tipo de serviço**, o sistema exigirá o preenchimento desse campo novamente.

Caso seja utilizado um modelo já cadastrado, os campos são preenchidos automaticamente, otimizando o tempo do usuário e garantindo **maior consistência nas integrações**.

> Se o tipo de serviço informado na nota for diferente daquele previsto em contrato, o sistema **emitirá um aviso**, mas permitirá a continuidade do processamento normalmente.

Após o preenchimento dos campos, siga para **Validar importação**. Feito isso, a nota que antes possuía status de **“Com divergência”** passa a ter status de **“Processada”**, sendo possível visualizá-la diretamente na **Central de Compras**, ao clicar no número na coluna **Nota Integrada**.

> ⚠️ Notas com status **"Não processada"** indicam que a requisição de integração não foi executada, geralmente por **duplicidade de dados** ou **inconsistências**.

---

## Informações importantes acerca desta rotina

- Esta tela permite **apenas visualizar** a integração de NFS-e. Não é possível editar ou processar manualmente.
- **Não será possível integrar** notas fiscais que contenham **itens com tipos de serviço diferentes** dentro do mesmo documento.

### Exemplos de uso:

- Primeira vinculação manual de uma nota fiscal, preenchendo todos os campos obrigatórios.
- Nota parcialmente vinculada anteriormente, com reaproveitamento automático dos dados.
- Utilização de **modelos previamente salvos**, com preenchimento automático.
- Tentativa de integrar uma nota já vinculada anteriormente: o sistema impedirá a duplicidade.
- Tipo de serviço divergente do contrato: o sistema alertará, mas permitirá continuar a integração.

[🔝 Voltar ao topo](#processamento-nfs-e)

---

## Parâmetros que influenciam nessa rotina

### `TPVSEMVALNATCUS`  
**Lista Tip.Mov. sem validação EXIGNATCFR/EXIGCRCFR**  
Define uma lista de Tipos de Movimento isentos da exigência dos parâmetros. Se o Tipo de Movimento estiver incluído, os campos **Natureza** e **Centro de Resultado** continuarão visíveis, mas **não serão obrigatórios**, mesmo se o sistema estiver configurado para exigi-los.

---

### `EXIGCRCFR`  
**Exigir CR na central/financeiro/rateio?**  
Define se o **Centro de Resultado (CR)** será obrigatório nas telas de integração ou rateio de documentos financeiros.

- **Ativado:** o sistema exigirá o preenchimento do CR.
- **Desativado:** o preenchimento do CR será opcional.

---

### `EXIGNATCFR`  
**Exigir natureza na central/financeiro/rateio?**  
Define se o campo **Natureza de Custo** será obrigatório.

- **Ativado:** o preenchimento da Natureza de Custo será obrigatório.
- **Desativado:** o preenchimento será opcional.

---
