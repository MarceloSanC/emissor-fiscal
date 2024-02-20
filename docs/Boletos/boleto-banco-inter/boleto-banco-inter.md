---
id: boleto-banco-inter
title: Como gerar boletos para banco Inter
---

## Adicionar Pagamento/Desconto

Os boletos estão sempre associados a um qualquer documento de venda; Orçamento, Pedido, NF-e ou NFS-e. Quando um destes documentos for criado podem também ser criados boletos, de forma automática.

Em **Configurações > Pagamento/Desconto** selecione **Adicionar Pagamento/Desconto**.

![Adicionar Pagamento/Desconto](@site/static/img/boleto-inter-recorrente/adc-pagamento-desconto.png)

No separador **Prazos**, prazos e montantes percentuais dos boletos a gera. No **Meio de Pagamento**, selecione a opção **Boleto Bancário** e ative a opção **Retaguarda**.

No exemplo abaixo será gerada apenas um boleto com 100% do valor e prazo de 30 dias.

![Pagamento/Desconto](@site/static/img/boleto-inter-recorrente/pagamento-desconto.png)

No separador **Recebimentos** em **Banco** seleciona o **Banco Inter**.

![Selecionar Banco Inter](@site/static/img/boleto-inter-recorrente/banco-caixa.png)

A opção **NF-e** deve estar ativada, para que o software crie um novo **Recebimento** a cada nova **NF-e**.

Se pretende gerar boletos com outro tipo de documento, deve confirmar que a opção correspondente se encontra também ativada.

Em **Configurações > Bancos** localize o banco **INTER** e selecione **Ações > Editar**.

![Ações > Editar](@site/static/img/boleto-inter-recorrente/acoes-editar.png)

No separador **Notas** preencha utilizando formato XML os valores correspondentes a **BoletoInterClientId** e **BoletoInterClientSecret** obtidos do **Banco Inter**.

![Notas](@site/static/img/boleto-inter-recorrente/notas.png)

O **Limite de Pagamento (dias após vencimento)** permite estender o prazo permitido para o pagamento do boleto para além da data de vencimento apresentada no boleto. Se aqui definir o valor de 0 (zero dias), não será possível liquidar boletos após a data de vencimento.

Ainda no cadastro do banco selecione a opção **Importar Certificado** por forma a carregar o certificado e o arquivo com a chave obtidos no site **bancointer.com.br**.

![Importar certificado](@site/static/img/boleto-inter-recorrente/importar-certificado.png)

:::info
O **Código do Banco** para INTER no EmissorFiscal tem o valor no Emissor Fiscal o valor pré-definido de **077**, p.f. não modifique este valor.
As configurações e chaves aqui utilizadas são para o **Banco Inter**, estas diferem de Banco para Banco (Para mais detalhes consulte a FAQ **Como configurar os Bancos para pagamentos a cartão, Boleto ou PIX ?)**.
:::

Em **Limite de pagamento** especifique também o prazo de pagamento dos boletos.

No documento de venda o método de pagamento aqui configurado pode ser selecionado. No exemplo abaixo, uma NF-e de venda tem este **Pagamento/Desconto** selecionado.

![Adicionar NF-e de Venda](@site/static/img/boleto-inter-recorrente/adc-nfe-venda.png)

Depois de **Validar** a NF-e, em **Vendas > Recebimentos** poderá consultar os boletos gerados.

![Imprimir/Download Boleto](@site/static/img/boleto-inter-recorrente/imprimir-boleto.png)

Estes boletos podem ser enviados os cliente de forma manual por intervenção do usuário ou automática com o uso de Templates especificas para esse propósito.

Assim que o boleto for pago, o software atualizará automaticamente a **Situação** deste recebimento.

:::info
É de salientar que embora o boleto possa aparecer no Banco como pago a API do Banco pode retornar que esse boleto ainda não está pago, facto que revela que a API do banco não tem ligação direta a base de dados central do Banco e há apenas uma sincronização de informação que pode demorar algumas horas! Além disto, o Emissor Fiscal comunica com a API do banco a cada 60 minutos, fato que justifica também o tempo de resposta entre o que é apresentado pelo banco e o apresentado pelo software.
:::

Veja também como @@[É possível definir valores de juros e multa para Boletos](https://clientes.acronyn.com/faq.aspx?numFaq=100415)@@, e definir valores de juros/multa fazendo uso das chaves XML **BoletoMulta** e **BoletoJuros**

Veja também @@[Como colocar texto nas Instruções do Boletos](https://clientes.acronyn.com/faq.aspx?numFaq=100416)@@ e apresentar Instruções/Informações complementares nos boletos fazendo uso da chave XML **BoletoInstrucoes**

**Etapas para obter o certificado e chaves do Banco Inter**

Acesse a sua conta digital no Banco Inter e selecione **Conta Digital > Aplicações > Nova Aplicação**

Configure o **Nome da Aplicação** com **EmissorFiscal** e a **Descrição** com **EmissorFiscal**

Selecione **PROXIMO**

Em **Selecione o escopo da nova aplicação**, ative a opção de **Cobranças**, na qual estão inclusas as seguintes sub opções:

**Consulta de boletos e exportação para PDF**;
**Emissão e cancelamento de boletos**.

Selecione **CRIAR APLICACAO**

Digite a senha de confirmação recebida no seu celular

Selecione **BAIXAR CHAVES E CERTIFICADO**

Utilize os dois arquivos obtidos para configurar o certificado do Banco, como já foi explicado nesta FAQ.

Em **Suas aplicações**, selecione a opção **Ativo** para visualizar as aplicações ativas

Expanda a aplicação **EmissorFiscal** para visualizar e copiar as chaves **ClientId** e **ClientSecret** que necessita para configurar a chaves do banco, como explicado nesta FAQ.