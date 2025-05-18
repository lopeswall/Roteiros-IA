# ✨ Roteiros IA ✨

## 📝 Projeto de um assistente de viagens em python no Google Colab

A ideia é que este assistente auxilie os usuários a definir roteiros a partir do local e das datas sugeridas, levando-se em consideração o processamento de dados.

## ✨ Funcionalidades

* 🛠️ **Funcionalidade 1:** Coletar informações a respeito da viagem, como local, data de início da viagem, data de término e objetivo da viagem
* 🛠️ **Funcionalidade 2:** Agente buscador de roteiros diários, com base nas datas sugeridas.
* 🛠️ **Funcionalidade 3:** Formatação do roteiro em dias, separados por períodos (manhã, tarde e noite) com sugestão do que fazer e opções de transporte.


## 🚀 Tecnologias Utilizadas

* 🐍 Python: Uma linguagem de programação versátil.
* 📒 Google Colab
* 🗝️ Google API Key.
* ❇️ Google Gemini
* 🔗 Git / 🌎 GitHub


## 💻 O que é e como usar?

O documento "Assistente_de_viagens_Roteiros_IA.ipynb" é um notebook Jupyter que demonstra a criação de um assistente virtual de viagens utilizando inteligência artificial. Ele se concentra na geração de roteiros diários personalizados para viagens.

## A construção do assistente envolve os seguintes passos:

* Instalação de bibliotecas: Instalação das bibliotecas google-genai e google-adk.
* Configuração da API Key: Importação e configuração da chave da API do Google a partir dos Secrets do Colab para usar a biblioteca google.generativeai. É definido o modelo Gemini a ser utilizado (gemini-2.0-flash no exemplo).
* Importação de componentes e bibliotecas: Importação de componentes do ADK (Agent, Runner, InMemorySessionService, Google Search, built_in_code_execution) e outras bibliotecas úteis como types do google.genai, datetime, textwrap, IPython.display e requests.
* Definição de função auxiliar call_agent: Criação de uma função para enviar mensagens a um agente via Runner e obter a resposta final, incluindo tratamento de erro aprimorado com retentativas para erros de quota (status 429).
* Definição de função auxiliar to_markdown: Criação de uma função para formatar texto em Markdown para melhor exibição no Colab.
* Definição do Agente Buscador (agente_buscador): Implementação de um agente especializado em buscar e sugerir roteiros detalhados para um único dia específico de uma viagem, utilizando a ferramenta Google Search e evitando sugerir locais já mencionados em dias anteriores. O agente recebe informações sobre o destino, número de dias, data específica, tipo de viagem e uma lista de lugares já sugeridos, e retorna sugestões para o dia e uma lista dos locais sugeridos naquele dia.
* Coleta de informações da viagem: Interação com o usuário para coletar dados da viagem, como destino, datas de início e fim, número de viajantes e tipo de viagem.
* Processamento de datas e loop diário: Cálculo do número de dias da viagem com base nas datas fornecidas e inicialização de uma lista para armazenar todos os locais sugeridos na viagem. Um loop é então executado para cada dia da viagem. Dentro do loop:
    - A data do dia atual é formatada.
    - A função agente_buscador é chamada com as informações relevantes do dia e a lista total de lugares já sugeridos.
    - A resposta do agente é processada para extrair os locais sugeridos especificamente para aquele dia, que são adicionados à lista total de lugares sugeridos.
    - As sugestões do agente para o dia são exibidas formatadas em Markdown.
    - Uma pequena pausa é adicionada entre o processamento de cada dia para evitar problemas de quota na API.
* Conclusão: Ao final do loop, é exibida uma mensagem indicando a conclusão do processamento do roteiro diário e a lista final de locais únicos sugeridos na viagem.


Em resumo, o documento detalha a criação de um assistente de viagens inteligente em Python que, usando a API do Google GenAI e a ferramenta de busca, gera roteiros diários personalizados para uma viagem, mantendo um registro dos locais já sugeridos para variar as recomendações.
