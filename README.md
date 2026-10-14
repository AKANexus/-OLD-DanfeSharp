# DanfeSharp

**Fork histórico — sem manutenção ativa nesta conta.** Este repositório preserva uma versão da biblioteca DanfeSharp para consulta. O estado deste fork não descreve a manutenção dos projetos de origem.

## Sobre a biblioteca

Biblioteca em C# para geração de DANFE em PDF a partir de dados de NF-e. O código organiza a composição do documento em blocos, elementos gráficos e modelos de apresentação.

A árvore também contém classes para DANFE de NFC-e, QR codes e documentos de eventos, incluindo carta de correção. Há um projeto de testes separado, cuja execução não foi realizada nesta revisão.

## Tecnologias e organização

A biblioteca tem como alvo .NET Standard 2.0 e utiliza PdfClown.NetStandard 0.2.0-beta e QRCoder 1.3.5. O projeto principal fica em `DanfeSharp/`, com blocos de impressão em `Blocos/`, modelos em `Modelo/` e testes em `DanfeSharp.Test/`.

## Exemplo básico

O exemplo abaixo preserva o fluxo apresentado na documentação anterior: carregar um XML, gerar o documento e salvar o PDF. O arquivo `nfe.xml` representa uma entrada fornecida pelo consumidor da biblioteca.

```csharp
using DanfeSharp;
using DanfeSharp.Modelo;

var modelo = DanfeViewModelCreator.CriarDeArquivoXml("nfe.xml");
using (var danfe = new Danfe(modelo))
{
    danfe.Gerar();
    danfe.Salvar("danfe.pdf");
}
```

## Origem e licença

Este repositório é um fork de [nfe/DanfeSharp](https://github.com/nfe/DanfeSharp), cuja origem na rede de forks é [SilverCard/DanfeSharp](https://github.com/SilverCard/DanfeSharp). A licença MIT incluída no repositório credita **Ricardo Brito, 2017**; consulte [LICENSE.txt](LICENSE.txt) para os termos completos.

A descrição das funcionalidades não atribui a autoria integral da biblioteca ao mantenedor deste fork. Os avisos de licença e créditos originais foram preservados.

## Estado da versão preservada

A revisão foi documental, sem build, execução dos testes ou validação dos PDFs produzidos. A presença do código não comprova adequação dos leiautes a exigências fiscais atuais, nem suporte a todos os documentos de entrada.
