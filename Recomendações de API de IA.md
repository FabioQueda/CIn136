Github models

[Como usar alguns modelos da OpenAI de graça (limites de uso baixo)](https://youtu.be/JCXl5_MMUfk?si=eGAYaecOj6pJO8WD)


OpenAI 

[Como usar a OpenAI API](https://youtu.be/Y9gOf4we3tk?si=IxZgW3T4hEzxYgUd)


A OpenAI oferece os modelos porém recomendamos o modelo GPT-4o-mini por ser mais barato.

Integração com Python

```
pip install openai
```

```
import openai

openai.api_key = "SUA_API_KEY"

response = openai.ChatCompletion.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "Olá, IA!"}]
)

print(response['choices'][0]['message']['content'])
```

Integração com Node.js

```
npm install openai
```

```
const OpenAI = require("openai");
const openai = new OpenAI({ apiKey: "SUA_API_KEY" });

const chat = await openai.chat.completions.create({
  model: "gpt-4o-mini",
  messages: [{ role: "user", content: "Olá, IA!" }],
});

console.log(chat.choices[0].message.content);
```

Prós:

    Modelo gpt-4o-mini é rápido, barato e poderoso

    Excelente qualidade nas respostas

    API com suporte oficial para Python, Node.js e outras linguagens

Contras:

    A API não possui plano gratuito (uso exige cartão de crédito)

Google Gemini

[Como usar](https://youtu.be/0qv_4x1K6hU?si=7ymCwGloHl0MGbJh)

O Gemini é o modelo de IA da Google, acessado via Google AI Studio ou Google Cloud Vertex AI. O modelo mais utilizado atualmente é o gemini-pro, indicado para tarefas de texto.

Integração com Python

```
pip install google-generativeai
```

```
import google.generativeai as genai

genai.configure(api_key="SUA_API_KEY")

model = genai.GenerativeModel("gemini-pro")
response = model.generate_content("Fale sobre integração de IA no backend")

print(response.text)
```

Integração com Node.js

```
npm install @google/generative-ai
```

```
const { GoogleGenerativeAI } = require("@google/generative-ai");

const genAI = new GoogleGenerativeAI("SUA_API_KEY");

const model = genAI.getGenerativeModel({ model: "gemini-pro" });
const result = await model.generateContent("Fale sobre integração de IA no backend");

console.log(result.response.text());
```

Prós:

    Fácil de usar para tarefas básicas como resumo de textos, geração de conteúdo e recomendação

    Biblioteca oficial com bom suporte em Python e Node.js

    Possui um plano gratuito que atende à maioria dos testes em sala de aula

Contras:

    Limites no uso gratuito
