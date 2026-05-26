# Criando-ia-simples
Criando ia simples com python usando chat-bot
from openai import OpenAI

API_KEY = ""

cliente = OpenAI(
    api_key=API_KEY,
    base_url="https://integrate.api.nvidia.com/v1"
)

resposta = cliente.chat.completions.create(
    model="meta/llama-3.1-8b-instruct",
    messages=[
        {
            "role": "system",
            "content": "Você é um especialista em Star Wars."
        },
        {
            "role": "user",
            "content": "Olá, o que é você?"
        }
    ]
)

print(resposta.choices[0].message.content)
