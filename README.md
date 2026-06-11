# Atividade: Primeiro Workflow de CI com GitHub Actions

Este repositório contém uma aplicação simples em Python com testes unitários automatizados utilizando `pytest`, integrada a um pipeline de Integração Contínua (CI).

## Evidência de Execução Bem-Sucedida

*Abaixo ficará o print ou link do status de sucesso do GitHub Actions:*
<img width="896" height="765" alt="Captura de tela 2026-06-11 173513" src="https://github.com/user-attachments/assets/cd878330-f2ab-42da-934c-74417b31de36" />


## Explicação dos Elementos do GitHub Actions

* **`on`**: Define os gatilhos (triggers) que disparam o workflow. No nosso arquivo, configuramos para que o pipeline seja executado automaticamente sempre que houver um evento de `push` ou `pull_request` nas branches principais.
* **`jobs`**: Representa um bloco de trabalho ou um conjunto de etapas (steps) que serão executadas. Um workflow pode ter um ou mais jobs rodando em paralelo ou de forma sequencial. No nosso caso, temos o job `testes`.
* **`runs-on`**: Especifica o sistema operacional do runner (o servidor virtual fornecido pelo GitHub) onde o job será executado. Configurando como `ubuntu-latest`, garantimos um ambiente Linux atualizado.
* **`steps`**: É a sequência de passos ou tarefas consecutivas que o job deve executar. Cada passo pode rodar um comando próprio ou usar uma Action pronta.
* **`uses`**: Indica a utilização de uma Action predefinida e reutilizável da comunidade ou do próprio GitHub. Por exemplo, `actions/checkout@v4` é usada para baixar o código do repositório para dentro do runner.
* **`run`**: Utilizado para executar comandos diretamente no terminal de linha de comando do runner. Nós usamos para atualizar o pip, instalar as dependências do `requirements.txt` e rodar o comando `pytest`.
