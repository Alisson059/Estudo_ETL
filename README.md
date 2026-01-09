# 📊 Estudo_ETL – Pipeline ETL com Python e Gemini API

Este projeto implementa um **pipeline ETL (Extract, Transform, Load)** utilizando **Python**, **Pandas** e a **API Gemini (Google Generative AI)** para gerar **mensagens personalizadas de marketing bancário** a partir de dados estruturados em CSV.

O objetivo é demonstrar boas práticas de:
- Manipulação de dados
- Integração com API de IA generativa
- Organização de código
- Versionamento com Git/GitHub

---

## 🧱 Arquitetura do Pipeline ETL

### 🔹 Extract (Extração)
- Leitura de dados a partir de um arquivo CSV
- Extração de IDs e nomes dos usuários

### 🔹 Transform (Transformação)
- Consulta de dados por ID
- Conversão dos registros para JSON
- Geração de mensagens personalizadas usando a API Gemini
- Tratamento de erros e controle de requisições

### 🔹 Load (Carga)
- Inserção das mensagens geradas no DataFrame
- Exportação para um novo arquivo CSV
- Leitura posterior dos dados processados para validação

---

## 📁 Estrutura do Projeto
```
Estudo_ETL/
│
├── dados_analise_cartao.csv
├── dados_analise_cartao_mensagem.csv
├── etl_pipeline.py
├── README.md
└── .gitignore
```

---

## 🛠️ Tecnologias Utilizadas

- Python 3
- Pandas
- Google Gemini API (google-genai)
- Git e GitHub

---


## 🔐 Configuração da API Gemini

Por motivos de segurança, a chave da API **não é armazenada diretamente no código**.  
Ela é carregada através de uma **variável de ambiente**.

### Windows (PowerShell)
```powershell
setx GEMINI_API_KEY "SUA_CHAVE_AQUI"
```


### Linux / macOS
```bash
export GEMINI_API_KEY="SUA_CHAVE_AQUI"
```

---

### Uso no código
```python
import os
from google import genai

client = genai.Client(
    api_key=os.getenv("GEMINI_API_KEY")
)
```

---

## ▶️ Como Executar o Projeto
```
git clone https://github.com/Alisson059/Estudo_ETL.git
cd Estudo_ETL
pip install pandas google-genai
python Mensagem.py
```

---

### Exemplo de saída:
```
Ana: Investir é o melhor caminho para garantir segurança financeira no futuro.
Bruno: Começar a investir hoje ajuda a construir um amanhã mais tranquilo.
Carlos: Investimentos são essenciais para alcançar seus objetivos financeiros.
```

---

## 📌 Boas Práticas Aplicadas

- Estruturação clara do pipeline ETL
- Tratamento de exceções em chamadas de API
- Controle de limite de requisições com sleep
- Uso de variáveis de ambiente para segurança
- Código organizado e comentado
- Versionamento adequado com Git

---

## 👤 Autor

### Alisson Melo
- Estudante de Técnico em Informática
- Foco em Dados e Desenvolvimento

🔗 GitHub: https://github.com/Alisson059