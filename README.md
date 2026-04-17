Projeto: Agente Inteligente para Controle de Semáforo de AGVs
1. Identificação do Grupo
Instituição: Fundação Salvador Arena (FTT)
Curso: Engenharia de Controle e Automação
Grupo: Grupo 05
Integrantes: * Rafael Bognar Soares da Silva
Bruno Eduardo
João Soares
William Balieiro
2. Área Problema Selecionada
Selecione a trilha tecnológica do projeto (marque com um [x]):

 Saúde 4.0: Robótica Assistiva (Controladores Inteligentes/Fuzzy)
 Smart Grid: Eficiência Energética e Descarbonização
 Agtech: Automação de Precisão e Visão Computacional
 Logística Autônoma: Coordenação de AGVs e Otimização de Rotas
3. Diagnóstico e Definição do Agente
Nesta seção, descrevemos o cenário de atuação e a modelagem do agente inteligente.

Contexto: Logística intra-industrial e Indústria 4.0. Controle de tráfego de Veículos Guiados Automaticamente (AGVs) em cruzamentos dentro de um armazém ou chão de fábrica.
Problema: Risco de colisões e ineficiência no fluxo quando múltiplos AGVs chegam simultaneamente a um cruzamento. Sistemas tradicionais baseados em regras fixas ou temporizadores falham em adaptar-se dinamicamente às condições do ambiente (distância, velocidade e prioridade da carga).
Impacto: A implementação do agente visa zerar colisões, reduzir drasticamente o tempo de espera dos veículos nos cruzamentos e otimizar o fluxo logístico global, aumentando a produtividade da planta.
Modelagem PEAS (Agente Inteligente)
Componente	Descrição
Performance (P)	Evitar colisões, garantir a passagem de um AGV por vez, reduzir tempo de espera e otimizar o fluxo logístico sem falhas.
Ambiente (E)	Cruzamento industrial de rotas de AGVs (simulado no Python/Colab).
Atuadores (A)	Semáforo do cruzamento (mudança de estados: Verde/Vermelho para permitir ou bloquear a passagem).
Sensores (S)	Leitura de distância do AGV ao cruzamento, velocidade de deslocamento e prioridade da carga (simulados por variáveis no código).
4. Arquitetura de Dados e IA
Definição das fontes de dados e da inteligência por trás da solução.

Origem dos Dados: Geração de dados simulados (cenários sintéticos) via script em Python para representar os diferentes estados do tráfego de AGVs no cruzamento.
Lógica de IA: Algoritmos de Otimização e Sistemas Especialistas/Heurística (com potencial uso de Lógica Fuzzy para tratar as variáveis contínuas de distância e velocidade na definição de prioridades).
Justificativa: Diferente de um temporizador rígido (que faria um AGV vazio parar em um cruzamento sem movimento), essa técnica de IA permite analisar os dados em tempo real e tomar decisões adaptativas, ponderando quem deve passar primeiro com base na urgência e segurança.
5. Plano de Tratamento de Dados (ETL)
O fluxo de processamento dos dados segue estas etapas:

Extração: Geração de cenários operacionais simulando a aproximação de 2 ou mais AGVs (velocidade, distância, peso, prioridade da carga).
Transformação: Normalização das grandezas (ex: converter distâncias para uma escala padrão) e tratamento de variáveis de prioridade para a tomada de decisão.
Carga: Disponibilização das matrizes de estado do cruzamento para o processamento do modelo de IA e do agente de controle.
6. Estrutura do Repositório
Organização simplificada para o Milestone 1:

/data: Arquivos de dados simulados (raw) e tratados (processed) de fluxo de AGVs.
/notebooks: Experimentos iniciais, modelagem PEAS e testes de lógica.
/scripts: Códigos Python (.py) contendo a lógica do agente inteligente simulando os sensores e atuadores.
requirements.txt: Lista de bibliotecas para rodar o projeto (Numpy, Pandas, NetworkX, etc).
README.md: Documentação atual do projeto.
7. Instruções para Execução
Para reproduzir o ambiente e testar o diagnóstico:

Clone este repositório.
Instale as dependências:
pip install -r requirements.txt
