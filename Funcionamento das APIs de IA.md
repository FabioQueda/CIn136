# Desenvolvimento de um Projeto com AI Engineering

O desenvolvimento de projetos com em _AI Engineering_ envolve a integração de modelos de inteligência artificial em aplicações reais, garantindo escalabilidade, segurança e eficácia. Isso exige um planejamento estratégico do fluxo de dados, integração com APIs (tanto de dados quanto de modelos de IA), configuração adequada de variáveis de ambiente e implementação de boas práticas no consumo de modelos LLM (_Large Language Models_).

Uma das etapas mais críticas é a **definição clara do fluxo de informação e interação com a IA**, o que garante que todas as partes do sistema saibam como se comunicar, onde obter dados e como responder aos usuários finais.
# Processo
## 1. Determinar o fluxo 

Antes de qualquer implementação, é essencial entender como os dados irão fluir dentro da aplicação. Isso ajuda a responder perguntas como:

- Onde e como o usuário irá interagir com a aplicação?
- A IA precisa de dados externos (contextuais) para funcionar?
- Qual será o formato da entrada e da saída?
- A resposta da IA alimentará outras etapas do sistema?

**Exemplo de fluxo simples:**

```
Usuário -> Front-End -> Back-End -> API de Dados [opcional] -> LLM (IA) -> Resposta -> Usuário
```

Esse mapeamento pode variar de acordo com a complexidade do sistema. Dependendo do projeto, pode-se incluir etapas como pré-processamento de dados, armazenamento em banco de dados, etc.
## 2. API para fonte de dados [opcional]
- Caso o projeto necessite de dados externos para contexto da IA.
- Ex: API de dados financeiros, dados climáticos... 

1. Obter a API Key
2. Salvar a API Key como variável de ambiente e importá-la no código do Back-End.
	1. Pode-se utilizar um arquivo .env no projeto e inserir no .gitignore do projeto.
	2. **Lembre-se**: a API Key deve ser mantida em sigilo, apenas os membros da equipe devem ter acesso.

## 3. API da IA
- Determinar o provedor e modelo que serão usados no projeto.

1. Obter a API Key
2. Salvar a API Key como variável de ambiente e importá-la no código do Back-End.
	1. Pode-se utilizar um arquivo .env no projeto e inserir no .gitignore do projeto.
	2. **Lembre-se**: a API Key deve ser mantida em sigilo, apenas os membros da equipe devem ter acesso.

### Provedores:

#### OpenRouter (gratuito)
- Link: https://openrouter.ai
- Documentação: https://openrouter.ai/docs/quickstart
- O OpenRouter fornece uma API unificada que oferece acesso a centenas de modelos de IA por meio de um único endpoint, enquanto lida automaticamente com fallbacks. Por meio dele, é possível filtrar e utilizar os modelos que são disponibilizados gratuitamente pelos provedores de forma prática.
#### OpenAI (pago)
- Obter a API Key: platform.openai.com/login
- Documentação da OpenAI: https://platform.openai.com/docs/overview
- Boas práticas para Segurança de API Keys: https://help.openai.com/en/articles/5112595-best-practices-for-api-key-safety

> Acesse o arquivo [Recomendações de API de IA](/CIn136/Recomendações%20de%20API%20de%20IA.md) para mais informações sobre provedores e recomendações gerais de API.

# Como funcionam as requisições a API da IA?

Para interagir com um modelo de IA via API, é necessário entender como estruturar corretamente a requisição, o que envolve:
## Cada requisição precisa conter:
### 1. Modelo (LLM - Large Language Model)
- Um LLM é um algoritmo de aprendizado profundo treinado com grandes volumes de dados de linguagem natural. Esses modelos são capazes de gerar, completar e interpretar texto com alto nível de coerência.

**Referência**:
- [OpenAI: Introduction to LLMs](https://platform.openai.com/docs/introduction)
- [Hugging Face: What are LLMs?](https://huggingface.co/learn/nlp-course/chapter1/1)
### 2. Array de mensagens (messages)
- Estrutura baseada no padrão de _chat_:
    - `{ role: "system", content: "..." }` — Define o comportamento e o estilo da IA.
    - `{ role: "user", content: "..." }` — Entrada do usuário.
    - `{ role: "assistant", content: "..." }` — (Opcional) Resposta anterior, em caso de histórico.

**Referência**:
- [ChatML Format - OpenAI](https://platform.openai.com/docs/guides/gpt/chat-completions-api)
### 3. Outras configurações opcionais
- `temperature`: define a aleatoriedade da resposta (0 = determinístico, 1 = criativo).
- `max_tokens`: número máximo de tokens na resposta.
- `top_p`, `frequency_penalty`, `presence_penalty` (para controle fino de saída).

## A requisição será processada pela API e retornará:

```json
{
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "Aqui está sua resposta gerada..."
      }
    }
  ]
}
```

## Fazendo a requisição com o OpenRouter
### Passo 1: Criar uma Conta e Obter a Chave de API

1. **Acesse**: [https://openrouter.ai](https://openrouter.ai)
2. **Crie uma conta** utilizando seu e-mail ou conta do GitHub.
3. **Gere sua chave de API**:
    - Navegue até https://openrouter.ai/keys
    - Clique em "Create Key" e nomeie-a conforme sua preferência.
    - Copie a chave gerada e guarde-a em um local seguro.

### Passo 2: Fazer uma Requisição Simples

#### Python

Você pode interagir com a API do OpenRouter utilizando Python. Certifique-se de ter o pacote `requests` instalado:

``` bash
pip install requests
```

Em seguida, utilize o seguinte código:

``` python
import requests
import json

response = requests.post(
  url="https://openrouter.ai/api/v1/chat/completions",
  headers={
    "Authorization": "Bearer SUA_CHAVE_API",
  },
  data=json.dumps({
    "model": "meta-llama/llama-4-maverick:free",
    "messages": [
      {
        "role": "user",
        "content": "Explique a teoria da Relatividade de forma simples."
      }
    ]
  })
)

print(response.json())
```

#### JavaScript

Você pode interagir com a API do OpenRouter utilizando JavaScript. Abaixo está um exemplo básico usando `fetch`:

``` javascript
const apiKey = 'SUA_CHAVE_API'; // Substitua pela sua chave de API
const url = 'https://openrouter.ai/api/v1/chat/completions';

const headers = {
  'Authorization': `Bearer ${apiKey}`,
  'Content-Type': 'application/json'
};

const data = {
  model: 'meta-llama/llama-4-maverick:free',
  messages: [
    { role: 'user', content: 'Explique a teoria da relatividade de forma simples.' }
  ]
};

fetch(url, {
  method: 'POST',
  headers: headers,
  body: JSON.stringify(data)
})
  .then(response => response.json())
  .then(result => {
    console.log(result.choices[0].message.content);
  })
  .catch(error => {
    console.error('Erro:', error);
  });
```

#### Notas:
- Substitua `"SUA_CHAVE_API"` pela chave obtida no Passo 1.
- O modelo `"meta-llama/llama-4-maverick:free"` é um dos modelos gratuitos disponíveis. Você pode explorar outros modelos gratuitos na [lista de modelos do (OpenRouter)](https://openrouter.ai/models).

#### Dica: 
Alguns modelos gratuitos possuem limites diários de uso. Se atingir o limite de um modelo, você pode alternar para outro modelo gratuito disponível.
