---
id: preparar-software
title: Como preparar o software para emitir Notas Fiscais de Serviço (NFS-e)?
---

O procedimento descrito nesta FAQ só pode ser executado se o Emissor Fiscal já estiver homologado com a prefeitura.

<!-- Verificar questão da prefeitura-->
Para homologar o Emissor Fiscal com qualquer prefeitura é necessário um trabalho conjunto entre PARCEIRO e a Acronyn. Consulte a seção [Como homologar o software na prefeitura para emissão de NFS-e](https://clientes.acronyn.com/faq.aspx?numFaq=100629) e veja como as etapas necessárias para executar o processo de homologação.

Para prepara o software de forma a que seja possível emitir NFS-e é necessário efetuar algumas etapas iniciais de configuração.

**Importar tabelas de Serviços utilizados pela sua prefeitura**

Utilize os Wizards **Serviços** e **Serviços/CNAE** para importar o arquivo CSV com a tabela de serviços da sua prefeitura.

![Importar template](@site/static/img/nfs-e/importar-template.png)

Veja a seção [Como devem ser preparados arquivos CSV de configuração da emissão de NFS-e ( Nota de Serviço )?](https://clientes.acronyn.com/faq.aspx?numFaq=100302) para saber como obter as tabelas de serviços.

**Preencher os códigos CNAE**

Em **Configurações > Empresas > botão Ações > Editar** no campo **CNAE** preencha a lista de códigos CNAE da empresa. Separando com ; (ponto-virgula) cada um dos códigos CNAE.

![Código CNAE](@site/static/img/nfs-e/codigo-cnae.png)

**Ativar os Serviços**

Em **Produtos/Serviços > Servicos** e selecione a opção **Ativar serviços / CNAE**

![Ativar serviços / CNAE](@site/static/img/nfs-e/ativar-servicos-cnae.png)

Ao executar esta operação o Emissor vai ativar automaticamente todos os serviços que a empresa pode utilizar.

**Certificado Digital**

Em **Configurações > Empresas > botão Ações > Editar** no separador **Certificado Digital** confirme que já tem o certificado instalado.

Depois de executadas as etapas acima mencionadas o software está pronto para emitir NFS-e.

:::info
Se você utiliza múltiplos códigos CNAE e emite documentos fiscais distintos, pode ser necessário utilizar diferentes códigos CNAE para cada tipo de documento. Para mais informações, consulte a seção: [É possível associar diferentes códigos CNAE por tipo de documento?](https://clientes.acronyn.com/faq.aspx?numFaq=100866)
:::