
# 🚀 Trabalhando com Machine Learning na Prática no Azure ML

### 📚 Descrição

Projeto consiste em criar um modelo de previsão dentro do ambiente cloud da azure, iremos trabalhar com um dataset sobre aluguel de bicicletas.

### 💻 Tecnologias

![Static Badge](https://img.shields.io/badge/Microsoft%20Azure-blue?logo=microsoftazure) ![Static Badge](https://img.shields.io/badge/Git-white?logo=git) ![Static Badge](https://img.shields.io/badge/GitHub-black?logo=github)

### 🚶‍♂️ Passo a Passo
- Dentro do ambiente ir na opção de **criar recurso** e pesquisar por **azure machine learning**;
- Uma vez selecionada a opção **criar** podemos nomear o grupo de recursos ou utilizar um que já existe;
- **Detalhes do worskspace**: Inserir nome (os demais campos irão preencher automaticamente);
- Selecionar opção **criar** e aguardar implantação;
- Após o processo, clicar em **Ir para o recurso**;
- Em visão geral, clicar na opção **iniciar o estúdio**;
- Na dock a esquerda, temos a opção **ML automatizado**;
- Clicar em **Novo trabalho de ML automatizado**;
- Seguindo a documentação, nome do trabalho **mslearn-bike-automl**;
- Nome do experimento **mslearn-bike-rental**;
- **Avançar**;
- Selecione o tipo de tarefa como **Regressão**;
- Selecione os Dados, clique em **Criar**;
- Nome ativo dos dados **bike-rentals** e tipo **Tabular**;
- Fonte dos dados **De arquivo da Web** e **Avançar**;
- URL da Web **https://aka.ms/bike-rentals** não selecione para ignorar validação dos dados e **Avançar**;
- Em **Cabeçalhos de Colunas** selecione "Somente o primeiro arquivo tem cabeçalhos" e **Avançar**;
- Deixe as opções de colunas marcadas e **Avançar** e **Criar**;
- **Coluna de Destino** selecione a opção "rentals (integer)"
- Configuração adicionais: 
    - Metrica primaria: Normalized root mean squared error
    - Desmarcar "Explicar o melhor modelo" e "Usar todos os modelos suportados"
    - Em Modelos permitidos selecione "RandomForest" e "LightGBM"
- Limites:
    - Máximo de avaliações: 3
    - Máximo de avaliações simultâneas: 3
    - Máximo de nós: 3
    - Limite de pontuação da métrica: 0.085
    - Tempo limite do experimento (minutos): 15
    - Tempo limite de iteração (minutos): 15
    - Enable early termination: Sim
- Validação e testar:
    - Tipo de validação: Divisão de validação de treinamento
    - Validação de percentual de dados: 10
    - Dados de teste: Nenhum 
- **Avançar**;
- Computação:
    - Selecione o tipo de computação: Sem servidor
    - Tipo de máquina virtual: CPU
    - Tipo de máquina virtual: Dedicada
    - Tamanho da máquina virtual: Standard_DS3_V2
    - Número de Instâncias: 1
    - **Enviar trabalho de treinamento** e Aguardar o processo terminar por completo;
    - Em nome do algoritmo selecione o melhor modelo;
- Para testar o modelo:
    - Na aba modelo temos a opção de **Implantar** selecione a opção "Serviço Web"
    - Implantar Modelo:
        - nome: prever-alugueis
        - Tipo de computação: Instância de Contêiner do Azure
        - Habilitar autenticação: sim
        - Aguardar que o status mude para "concluído"
        - Agora vá para a opção de "pontos de extremidade"
        - Na aba **Testar**
        - Use um arquivo nesse formato (altere os dados conforme necessidade):
        ```json
        {
            "Inputs": { 
                "data": [
                    {
                        "day": 26,
                        "mnth": 1,   
                        "year": 2024,
                        "season": 2,
                        "holiday": 0,
                        "weekday": 1,
                        "workingday": 1,
                        "weathersit": 2, 
                        "temp": 0.3, 
                        "atemp": 0.3,
                        "hum": 0.3,
                        "windspeed": 0.3 
                    }
                ]    
            },   
            "GlobalParameters": 1.0
        }
        ```
        - Saída:
        ```json
        {
            "Results": [
                357.34123867450256
            ]
        }
        ```
- Após testes não esqucer de apagar todos os recursos e grupo de recursos para evitar cobranças e alocação desnecessárias.

### 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://github.com/rafael-r-amancio) [![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rafael-ribeiro-amancio/)

### Referência

 - [Explore Automated Machine Learning in Azure Machine Learning](https://aka.ms/ai900-auto-ml)
 
 <details align="left">
  <summary></summary> 
 
  - Badges by <a href="https://shields.io/">shields.io</a><br>

</details>