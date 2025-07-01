# Agente Industrial Inteligente: Text-to-SQL com Smolagents

Este repositório apresenta uma solução para o desafio de construir um agente inteligente capaz de interpretar perguntas em linguagem natural e convertê-las em consultas SQL, atuando sobre um banco de dados de manutenção industrial. O projeto utiliza a biblioteca `smolagents` da Hugging Face, orquestrando Large Language Models (LLMs) para facilitar a interação.

## Abordagem

A solução é centrada em um `CodeAgent` que interage com um banco de dados SQLite. O coração do sistema é a capacidade do LLM de entender a estrutura do banco de dados e, a partir de uma pergunta em linguagem natural, gerar a consulta SQL correta.

### Diagrama de Arquitetura Simples

```mermaid
graph TD
    User[Usuário] -->|Pergunta em Linguagem Natural| Agente[Agente Industrial Inteligente]
    Agente -->|Consulta SQL Gerada| FerramentaSQL[Ferramenta SQL (executa consultas)]
    FerramentaSQL -->|Acessa e Consulta| BancoDeDados[Banco de Dados de Manutenção Industrial (SQLite)]
    BancoDeDados -->|Resultados da Consulta| FerramentaSQL
    FerramentaSQL -->|Resultados Processados| Agente
    Agente -->|Resposta em Linguagem Natural| User
