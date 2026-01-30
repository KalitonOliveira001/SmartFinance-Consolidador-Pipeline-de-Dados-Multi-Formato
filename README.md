🚀 FinanceFlow Pro: Pipeline de Consolidação de Dados Multi-Formato
Descrição do Projeto
O FinanceFlow Pro é uma ferramenta de Engenharia de Dados desenvolvida para automatizar a ingestão e padronização de relatórios financeiros heterogêneos. Ele extrai dados de planilhas Excel, arquivos CSV e PDFs de múltiplas páginas, convertendo automaticamente os padrões monetários brasileiros (BRL) para o formato numérico internacional (USD), consolidando tudo em um único dataset auditável.

🛠️ Funcionalidades Técnicas
Ingestão Inteligente: Identifica e processa extensões .xlsx, .csv e .pdf em um único loop.

Extração Multi-Páginas (PDF): Utiliza a biblioteca pdfplumber para percorrer todas as páginas de um documento, garantindo que nenhum dado de extratos longos seja perdido.

Data Cleaning & Normalization: Função personalizada para tratar strings monetárias (limpeza de prefixos "R$", correção de separadores de milhar e decimal).

Mapeamento de Cabeçalhos: Traduz automaticamente nomes variados (ex: "Preço", "Stiker", "Operação") para as colunas oficiais exigidas pelo cliente.

Tratamento de Compliance: Adiciona metadados de origem (Coluna FONTE) para rastreabilidade de dados.

Excel Styling: Exporta os resultados utilizando openpyxl para aplicar formatação contábil americana (#,##0.00) diretamente nas células.

📋 Estrutura do Projeto
Plaintext
📂 FinanceFlow-Pro
├── 📂 DADOS_BRUTOS          # Pasta para upload dos arquivos originais
├── 📄 automacao_mestre.ipynb # Notebook Jupyter com o pipeline
├── 📄 Relatorio_Final.xlsx   # Output consolidado (gerado após execução)
└── 📄 README.md              # Documentação do projeto
🧠 Explicação do Pipeline
Ingestão: O script varre o diretório ./DADOS_BRUTOS.

Processamento: Cada arquivo é convertido em um DataFrame Pandas. No caso de PDFs, o script itera por cada página extraindo tabelas estruturadas.

Padronização: Aplicação da função limpar_valor() para garantir integridade matemática.

Consolidação: Uso do pd.concat() para unir milhares de registros de fontes distintas de forma eficiente em memória.
