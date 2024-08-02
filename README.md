# Separador de Dados de Empresas

Este projeto tem como objetivo separar arquivos de uma base de dados de empresas brasileiras para a prospecção comercial. Devido ao tamanho e peso do arquivo original, foi criado um script para dividir o arquivo em vários menores.

## Estrutura do Projeto

- `MA2V - Base_Metropole.ipynb`: Script para manipulação da base de dados das empresas na capital da Bahia.
- `MA2V - Base_Interior.ipynb`: Script para manipulação da base de dados das empresas no interior da Bahia.
- `MA2V - Base_SP.ipynb.ipynb`: Script para manipulação da base de dados das empresas de São Paulo

## Funcionalidades

- Leitura de um arquivo Excel contendo a base de dados.
- Seleção de colunas específicas para prospecção.
- Divisão do DataFrame em partes de X linhas.
- Salvamento das partes em arquivos Excel separados.
- Servidor Flask para download das partes geradas.

## Requisitos

- Python 3.x
- Pandas
- Flask

## Instalação

1. Clone o repositório:

    ```bash
    git clone https://github.com/seu-usuario/separador-de-dados.git
    cd separador-de-dados
    ```

2. Crie um ambiente virtual:

    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows, use `venv\Scripts\activate`
    ```

3. Instale as dependências:

    ```bash
    pip install -r requirements.txt
    ```

## Uso

### Script de Manipulação de Dados

1. Abra e execute o Jupyter Notebook `MA2V - Base_Metropole.ipynb` para manipular a base de dados das empresas na capital.
2. Abra e execute o Jupyter Notebook `MA2V - Base_Interior.ipynb` para manipular a base de dados das empresas no interior.

### Servidor Flask para Download de Arquivos

1. Execute o servidor Flask contido no notebook após a manipulação dos dados:

    ```python
    from flask import Flask, send_file
    import pandas as pd

    app = Flask(__name__)

    @app.route('/download/<int:num_parte>')
    def download_file(num_parte):
        nome_arquivo = f'parte_{num_parte}.xlsx'
        return send_file(nome_arquivo, as_attachment=True)

    if __name__ == '__main__':
        app.run()
    ```

2. Acesse `http://127.0.0.1:5000/download/<num_parte>` para baixar a parte desejada do arquivo.
