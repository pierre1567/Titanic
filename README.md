🛳️ Titanic Dashboard — Análise do Naufrágio de 1912
📊 Visão Geral

Este projeto apresenta uma análise exploratória e visual dos dados do Titanic, com foco em entender os fatores que influenciaram a sobrevivência dos passageiros durante o naufrágio ocorrido em 14 de abril de 1912.

A análise combina Python para tratamento e exploração dos dados e Power BI para visualização interativa.

🖼️ Capa do Projeto

<img width="735" height="418" alt="image" src="https://github.com/user-attachments/assets/6c55cd30-df11-480b-bec8-07c1c923449c" />


📈 Dashboard Interativo


<img width="722" height="411" alt="image" src="https://github.com/user-attachments/assets/c9c5ae14-a696-4904-9eb9-8120ac5ea474" />

O dashboard apresenta:

👨‍👩‍👧‍👦 Distribuição de passageiros por idade e sexo

💸 Taxas de sobrevivência por classe e tarifa

🚢 Comparativo entre sobreviventes e mortos por classe

🧮 Total de passageiros analisados: 1.309

🧠 Principais Insights

A classe social foi um dos principais fatores que determinaram a sobrevivência.

Passageiros da 1ª classe tiveram uma taxa de sobrevivência de 61,9%.

Passageiros da 3ª classe representaram a maioria a bordo (709 pessoas) e tiveram apenas 25,5% de sobrevivência.

Mulheres e crianças apresentaram maior probabilidade de sobreviver, confirmando o lema “mulheres e crianças primeiro”.

⚙️ Tecnologias Utilizadas
Área	Ferramenta
Linguagem de Programação	Python 3.11
Bibliotecas	Pandas, NumPy, Matplotlib, Seaborn
Visualização	Power BI
Controle de Versão	Git & GitHub
🧩 Estrutura do Projeto
📁 Titanic.Dataset     → Scripts Python e arquivos CSV
📁 Titanic.Report      → Relatórios, prints e dashboard Power BI
📄 README.md           → Documentação do projeto

🧮 Análise Técnica (Python)

A análise em Python foi usada para limpeza, transformação e exploração dos dados originais do Titanic (dataset disponível no Kaggle).

🔹 Importação e Leitura dos Dados
import pandas as pd

df = pd.read_csv("titanic.csv")
df.head()

🔹 Tratamento e Limpeza

Remoção de valores nulos e ajustes em colunas categóricas:

df['Age'].fillna(df['Age'].median(), inplace=True)
df['Embarked'].fillna(df['Embarked'].mode()[0], inplace=True)
df.drop(['Cabin'], axis=1, inplace=True)

🔹 Análise Exploratória

Distribuição de sobreviventes por classe:

import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(data=df, x='Pclass', hue='Survived')
plt.title('Sobreviventes por Classe')
plt.xlabel('Classe')
plt.ylabel('Quantidade')
plt.show()

🔹 Taxa de Sobrevivência por Sexo
df.groupby('Sex')['Survived'].mean() * 100


Resultado esperado:

Sexo	Taxa de Sobrevivência
Feminino	74%
Masculino	18%
🔹 Exportação dos Dados Tratados
df.to_csv("titanic_clean.csv", index=False)


Esse arquivo foi utilizado para gerar as visualizações no Power BI.

📊 Dashboard Power BI

Após o tratamento, os dados foram conectados ao Power BI, criando um painel interativo para demonstrar:

Taxas de sobrevivência por faixa etária

Relação entre classe, sexo e destino

Contagem geral e segmentada de passageiros

🚀 Como Reproduzir

Clone este repositório:

git clone https://github.com/pierre1567/Titanic.git


Entre na pasta:

cd Titanic


Execute o código Python (opcional):

python analise_titanic.py


Abra o arquivo .pbix no Power BI para explorar o dashboard.

✍️ Autor

Pierre
📊 Analista de Dados | Power BI | Python | SQL
🔗 GitHub

⭐ Conclusão

O projeto Titanic demonstra como a combinação entre análise de dados e visualização interativa pode revelar padrões importantes em eventos históricos.
Além de servir como estudo prático de Python e Power BI, reforça a importância da análise exploratória no entendimento de grandes volumes de informação.
