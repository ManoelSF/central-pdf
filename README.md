# Central PDF

Programas para Windows para o dia a dia de um escritório com PDFs e documentos. Dois programas:

| Programa | Para quê | Arquivo |
|---|---|---|
| **Central PDF** | Menu com 10 ferramentas para PDF: editar páginas, juntar, preparar para protocolo, tarjar dados sensíveis, converter, buscar, renomear e enviar para as pastas. Digite o que quer fazer e ele indica a ferramenta. | `Central_PDF.zip` |
| **Renomear Docs** | Confere documentos (atestados, declarações…) um a um: o OCR sugere o nome da pessoa e o tipo, você confirma e ele renomeia e envia para as pastas. | `Renomear_Docs.zip` |

Instale um ou os dois. Dentro de qualquer um, em **Versão › Outros programas…**, dá para instalar o outro com um clique.

Funciona **100% offline**: nada é enviado para a internet (a internet só é usada na instalação das bibliotecas e, se você pedir, para buscar atualização aqui no GitHub).

> O antigo **Editor PDF** foi unificado ao Central: a mesma mesa de páginas está em **Editar PDF (visual)**. Quem usava o Editor deve baixar só o `Central_PDF.zip`.

## Baixar e instalar

1. Instale o **Python 3.10 ou superior** (<https://www.python.org/downloads/>) e marque **Add python.exe to PATH** na primeira tela do instalador.
2. Em **[Releases](../../releases/latest)** baixe `Central_PDF.zip` e/ou `Renomear_Docs.zip` e **descompacte** em qualquer pasta (não rode de dentro do ZIP).
3. Dê dois cliques em `Instalar_Dependencias.bat` (precisa de internet). Ele instala as bibliotecas e, no Central, pergunta se você quer instalar o Tesseract (OCR) que acompanha o pacote.
4. Para abrir: `Abrir Central PDF.bat` (ou `Abrir Renomear Docs.bat`). O instalador oferece criar um atalho na Área de Trabalho e no menu "Enviar para". Para ter "Abrir no Central PDF" no botão direito dos PDFs, rode `Instalar menu botao direito.bat`.

O Poppler já vem no pacote do Central. O Tesseract só é necessário para OCR (PDF escaneado: renomear pelo conteúdo, tarjar dados, deixar o PDF pesquisável).

## O que o Central PDF faz

**Editar e preparar**
- **Editar PDF (visual)** – veja as páginas e arraste: remova, gire (90° e 180°), reordene, duplique, insira ou substitua páginas de outro PDF, acrescente páginas em branco (inclusive "branca nos ímpares", para imprimir frente e verso), corte em partes, limite cada parte a X MB, comprima e escreva nas páginas (texto, carimbo, assinatura). O original nunca é alterado. Tem o painel recolhível **Ocultar dados** (valores em R$, nomes, CPF, NIT, RG, CNPJ, nascimento, telefone, e-mail e textos extras), que funciona em páginas giradas e escaneadas e remove o texto de verdade ao salvar.
- **Juntar PDFs** – em sequência (ordem natural: 1, 2, 3 … 10, 11) ou intercalando frente e verso.
- **Preparar para protocolo** – numerar folhas, reduzir/dividir por tamanho (limite do tribunal), OCR pesquisável, endireitar/girar, páginas por folha.
- **Tarjar dados sensíveis** – cobre ou apaga os dados acima em vários arquivos.
- **Automatizar em lote** – monte uma receita (sequência de passos), salve e aplique em todos os PDFs de uma pasta; tem modo *simular*.

**Converter**
- **Converter arquivos** – para PDF (imagens, Word, Excel) e de PDF (imagens, texto, Word, Excel).

**Nomes e pastas**
- **Buscar texto ou nome** – acha e extrai as páginas que contêm um nome ou texto (texto do PDF ou OCR).
- **Renomear arquivos** – pelo conteúdo (OCR + planilha), corrigir nomes, sufixos.
- **Listar nomes e códigos** – a partir dos nomes dos arquivos ou do conteúdo.
- **Enviar para as pastas** – você monta um **mapa de pastas** (pasta principal › subpastas › pasta de cada pessoa, com o padrão do nome: `{nome}`, `{codigo} - {nome}`…) ou importa de uma pasta que já existe. O programa descobre de quem é cada arquivo pelo nome e o envia para o lugar certo. É possível conferir antes, nunca sobrescreve e desfaz.

## Renomear Docs

Para quem recebe muitos documentos (atestados, declarações, certidões…) e precisa nomear cada um com **NOME - TIPO**:
- A pasta é opcional: você pode **arrastar** PDFs, fotos ou pastas para a janela.
- O OCR lê o documento e sugere o nome da pessoa: acha depois de rótulos como "Paciente:", "Nome:", "Pessoa:", "Name:" e frases como "Atesto que…". Funciona mesmo **sem planilha**, graças a uma lista de cerca de 64 mil nomes (Censos do IBGE) e sobrenomes comuns. Com uma planilha de nomes, ele corrige e confirma.
- O **tipo** (sufixo) pode ser escolhido por **regras**, por exemplo `atestado or medico`.
- Se a planilha tiver número de registro (RE, matrícula…), o campo aparece e pode entrar no nome do arquivo.
- Renomeia e envia só no fim, com numeral romano para repetidos (II, III), cópia opcional para uma pasta de rede e **desfazer**.

## Cadastro configurável

Para identificar pessoas (clientes, funcionários, processos…) o programa lê uma planilha sua (Excel ou CSV). Em **Formato do cadastro** você aponta qual coluna é o código (RE, CPF, nº do processo…), qual é o nome e, se quiser, a situação; também a linha do cabeçalho, a aba e o separador. Serve para qualquer planilha.

## Visual

Doze visuais (Neutro claro, Grafite, Escuro, Alto contraste, Azul clássico, Rosa suave, Lilás, Roxo, Noite roxa, Menta pastel, Pêssego e Céu pastel), em **Visual do programa**. Funciona com o zoom do Windows e tem zoom próprio de 75% a 150% (botões A－ A＋ ou Ctrl + / Ctrl − / Ctrl 0). O menu lateral pode ser ocultado (Ctrl+B) para liberar espaço.

## Atualização

Botão **Versão › Buscar atualização**: o programa consulta a última *Release* deste repositório e baixa só o que mudou. Suas configurações, logs e ferramentas (Tesseract/Poppler) não são tocados; os arquivos antigos ficam em `_backup_atualizacao`.

## Onde ficam as suas configurações

- Caminhos e escolhas gerais: `%APPDATA%\CentralPDF\caminhos.json`.
- Opções de cada ferramenta e logs: na própria pasta do programa (`.json` e `logs\`). São de cada pessoa e a atualização não as apaga.

## Requisitos

Windows, Python 3.10 ou superior. As bibliotecas (PyMuPDF, Pillow, pandas, openpyxl e outras, listadas em `requirements.txt` dentro de cada pacote) são instaladas pelo `Instalar_Dependencias.bat`. Os programas são Python puro (não precisam de compilação): o código vem dentro dos ZIPs. Converter Word/Excel ↔ PDF usa o Microsoft Office instalado no computador.

## Observações

- Dúvidas ou problemas: abra uma *issue* aqui no GitHub (não anexe documentos de clientes).
- Nenhum dado de documentos sai do computador; os logs ficam só na pasta do programa.
