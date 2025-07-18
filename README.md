# API de Clima para Viagens

Este repositório contém uma API de Clima para Viagens desenvolvida em Python com o framework FastAPI. A API fornece dados sobre o clima para diferentes cidades e países, e inclui uma interface de documentação interativa.

## Análise do Projeto

Este projeto é uma API web em Python que utiliza o framework **FastAPI**. A estrutura do projeto está bem organizada e segue as boas práticas de desenvolvimento.

*   **Framework Principal:** O projeto utiliza **FastAPI**, como indicado pela presença das bibliotecas `fastapi`, `uvicorn` e `pydantic` no ambiente virtual (`venv/`). Isso sugere uma API moderna, rápida e com documentação automática.
*   **Código Fonte:** O arquivo `main.py` contém a lógica central da sua API, com a definição dos endpoints (rotas).
*   **Testes:** A existência do arquivo `test_main.py` e da biblioteca `pytest` mostra que o projeto está preparado para testes automatizados, o que é uma excelente prática para garantir a qualidade do código.
*   **Dependências:** O arquivo `requirements.txt` define as bibliotecas Python necessárias para o projeto, facilitando a replicação do ambiente.
*   **Dados:** O arquivo `weather.json` provavelmente é usado como uma fonte de dados estática ou mock para a sua aplicação, talvez para simular respostas de uma API de clima.
*   **Documentação da API:** O projeto utiliza um arquivo `openapi.json` para descrever a API, que é usado para alimentar documentações interativas como Swagger UI e ReDoc.
*   **Ambiente de Desenvolvimento:** A presença de uma pasta `.devcontainer` e um `Dockerfile` indica que o projeto está configurado para rodar em um ambiente de contêiner (Dev Container), o que garante consistência e isolamento para o desenvolvimento.

## Como Executar o Projeto

Para executar este projeto, siga os passos abaixo:

1.  **Instale as dependências:**

    ```bash
    pip install -r requirements.txt
    ```

2.  **Inicie o servidor da API:**

    ```bash
    uvicorn main:app --reload
    ```

3.  **Acesse a documentação da API:**

    Abra o seu navegador e acesse a URL `http://127.0.0.1:8000/docs`. Você verá a documentação interativa da API (Swagger UI), onde poderá testar os endpoints disponíveis.

## 💪🏽 Exercício

A API atual não está expondo o endpoint `country/{country}`, que precisa ser implementado para listar as cidades. A rota deve permitir apenas requisições GET com uma resposta em JSON, fornecendo informações do histórico de temperaturas altas e baixas para o país, cidade e mês fornecidos.

Assim como em qualquer implementação, esta adição deve incluir pelo menos uma função de teste para funcionar com o executor de testes e o framework pytest.

### 🛠 Passo 1: Adicionar uma nova rota

No nosso primeiro exercício, vamos criar uma nova rota em nossa API. Vá para o arquivo `main.py` e, usando o chat inline com o comando `ctrl` + `i` (no Windows) ou `cmd` + `i` (no Mac), peça ao GitHub Copilot para ajudá-lo a criar uma nova API que mostre as cidades de um país.

`> Crie uma nova rota que exponha as cidades de um país.`

Este prompt deve fornecer algo semelhante a isto:

```python
# Crie uma nova rota que exponha as cidades de um país:
@app.get('/countries/{country}')
def cities(country: str):
    return list(data[country].keys())
```

Nota: Teste sua nova rota e refine seu prompt até que o resultado seja o desejado.

### 🔎 Passo 2: Criar um teste

Agora que você criou uma nova rota, vamos criar um teste com o Copilot Chat para esta rota que usa a Espanha como país. Lembre-se de selecionar seu código e pedir ao Copilot Chat para ajudá-lo com esta API específica que acabamos de criar.

`> /tests me ajude a criar um novo teste para esta rota que usa a Espanha como país.`

![Exemplo de imagem do Copilot Chat](./images/ideascopilot.png)

Depois que o Copilot o ajudar a criar seu teste, experimente-o. Se não estiver funcionando como esperado, sinta-se à vontade para compartilhar esses detalhes com o Copilot no chat. Por exemplo:

`> Este teste não está totalmente correto, não está incluindo cidades que não existem. Apenas Sevilha faz parte da API.`

Ele deve fornecer outra solução. Continue tentando até alcançar o resultado desejado.

### 🐍 Passo 3: Usar um agente para escrever o projeto

Durante esta etapa, usaremos um agente (workspace) para escrever a documentação do projeto sobre como executá-lo. No Chat do GitHub Copilot, tentaremos o seguinte prompt:

`> @workspace me ajude a usar um agente para escrever a documentação do projeto sobre como executá-lo.`

Finalmente, verifique se o novo endpoint está funcionando, acessando o endpoint `/docs` e confirmando que o endpoint aparece.

🚀 Parabéns, através do exercício, você não apenas usou o Copilot para gerar código, mas também o fez de uma maneira interativa e divertida! Você pode usar o GitHub Copilot para não apenas gerar código, mas também para escrever documentação, testar suas aplicações e muito mais.

# Notícias Legais

A Microsoft e quaisquer contribuidores concedem a você uma licença para a documentação da Microsoft e outros conteúdos neste repositório sob a [Licença Pública Internacional Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/legalcode), consulte o arquivo [LICENSE](LICENSE), e concedem a você uma licença para qualquer código no repositório sob a [Licença MIT](https://opensource.org/licenses/MIT), consulte o arquivo [LICENSE-CODE](LICENSE-CODE).

Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft mencionados na documentação podem ser marcas comerciais ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países. As licenças para este projeto não concedem a você direitos de uso de quaisquer nomes, logotipos ou marcas comerciais da Microsoft. As diretrizes gerais de marcas comerciais da Microsoft podem ser encontradas em http://go.microsoft.com/fwlink/?LinkID=254653.

As informações de privacidade podem ser encontradas em https://privacy.microsoft.com/en-us/

A Microsoft e quaisquer contribuidores reservam-se todos os outros direitos, seja sob seus respectivos direitos autorais, patentes ou marcas comerciais, seja por implicação, preclusão ou de outra forma.