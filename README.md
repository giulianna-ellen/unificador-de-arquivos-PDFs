# unificador-de-arquivos-PDFs

Este é um script Python simples que unifica todos os arquivos PDF localizados em uma pasta específica em um único documento.

## Funcionalidades

* Lê todos os arquivos PDF de uma pasta chamada `arquivos`.
* Organiza os PDFs em ordem alfabética antes de unificá-los.
* Combina todos os PDFs em um único arquivo chamado `PDF Final.pdf`.

## Como Usar

1.  **Pré-requisitos:**
    * Certifique-se de ter o Python instalado.
    * Instale a biblioteca `PyPDF2` com o seguinte comando:
        ```bash
        pip install PyPDF2
        ```

2.  **Estrutura do Projeto:**
    * Crie uma pasta chamada `arquivos` no mesmo diretório onde o script `projeto1.py` está salvo.
    * Coloque todos os arquivos PDF que você deseja unificar dentro da pasta `arquivos`.

    Sua estrutura de diretórios deve ficar assim:
    ```
    .
    ├── arquivos/
    │   ├── documento1.pdf
    │   ├── documento2.pdf
    │   └── relatorio.pdf
    └── projeto1.py
    ```

3.  **Execução:**
    * Abra o terminal ou prompt de comando.
    * Navegue até o diretório do projeto.
    * Execute o script com o comando:
        ```bash
        python projeto1.py
        ```

Após a execução, um novo arquivo chamado `PDF Final.pdf` será criado no diretório principal, contendo todos os PDFs da pasta `arquivos` combinados.

## Código

O código-fonte do projeto está disponível neste repositório. Ele utiliza as bibliotecas `PyPDF2` para manipulação de PDF e `os` para interagir com o sistema de arquivos.

```python
import PyPDF2 
import os    

merger = PyPDF2.PdfMerger()
 
lista_arquivos = os.listdir("arquivos") 
lista_arquivos.sort() 
print(lista_arquivos) 

for arquivos in lista_arquivos: 
    if ".pdf" in arquivos: 
        merger.append(f"arquivos/{arquivos}") 
merger.write("PDF Final.pdf")        
print("PDFs unificados com sucesso! O arquivo 'PDF Final.pdf' foi criado.")
merger.write("PDF Final.pdf")
print("PDFs unificados com sucesso! O arquivo 'PDF Final.pdf' foi criado.")
