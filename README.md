# Separador de Dados

Este projeto tem como objetivo separar arquivos de uma base de dados de empresas brasileiras para a prospecção comercial de uma empresa. Devido ao tamanho e peso do arquivo original, foi criado um script para dividir o arquivo em vários menores.

## Funcionalidades

- Leitura de um arquivo Excel contendo a base de dados.
- Seleção de colunas específicas para prospecção.
- Divisão do DataFrame em partes de 5.000 linhas.
- Salvamento das partes em arquivos Excel separados.
- Servidor Flask para download das partes geradas.

## Requisitos

- Python 3.x
- Pandas
- Flask
- python-dotenv

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

4. Crie um arquivo `.env` na raiz do projeto com base no arquivo `.env.example` e configure o caminho do arquivo Excel:

    ```bash
    cp .env.example .env
    ```

    Edite o arquivo `.env` para adicionar o caminho correto para o seu arquivo Excel:

    ```env
    EXCEL_FILE_PATH=seu_caminho
    ```

## Uso

### Script de Manipulação de Dados

1. Edite o caminho do arquivo no arquivo `.env`.

2. Execute o script:

    ```bash
    python script_manipulacao_dados.py
    ```

### Servidor Flask para Download de Arquivos

1. Edite o caminho do arquivo no arquivo `.env`.

2. Execute o servidor Flask:

    ```bash
    python server_flask.py
    ```

3. Acesse `http://127.0.0.1:5000/download/<num_parte>` para baixar a parte desejada do arquivo.

## Estrutura do Projeto

- `script_manipulacao_dados.py`: Script para manipulação de dados com Pandas.
- `server_flask.py`: Script para criar um servidor Flask para download dos arquivos.
- `.env.example`: Arquivo de exemplo contendo variáveis de ambiente.
- `.gitignore`: Arquivo para ignorar o arquivo `.env` real.
- `requirements.txt`: Arquivo com as dependências do projeto.

## Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
