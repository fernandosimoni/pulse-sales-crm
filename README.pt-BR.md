# PulseSales — CRM e Vendas

Projeto de portfólio de Fernando Simoni. Aplicação de CRM em português com dados fictícios identificados, construída com assistência de IA.

## Funcionalidades

- Pipeline em seis etapas: Novo lead, Contato, Proposta, Negociação, Ganho e Perdido.
- Cadastro e edição de oportunidades: contato, empresa, e-mail, telefone, valor, responsável, próxima ação e observações.
- Visualização em cartões ou tabela, pesquisa e filtro por responsável.
- Importação CSV com seleção de colunas e exportação da carteira completa.
- Indicadores calculados sobre os registros: pipeline aberto, previsão ponderada, conversão e ticket médio.
- Interface responsiva, controles com rótulos e diálogos nativos.

## Cálculos

Pipeline: soma dos valores em etapas abertas. Previsão: soma do valor de cada negócio aberto multiplicado por 10%, 25%, 50% ou 75%, conforme a etapa. Conversão: ganhos / (ganhos + perdidos). Ticket médio: total ganho / quantidade de ganhos. Os filtros não alteram indicadores globais. Sem denominador, o indicador mostra “—”. Não há previsão baseada em IA; as probabilidades são premissas ilustrativas.

## CSV

Aceita vírgula, ponto e vírgula ou tabulação, UTF-8 e Windows-1252, até 5 MB e 10.000 linhas. Nome é obrigatório; colunas adicionais são opcionais. A importação substitui a carteira da sessão. Etapas desconhecidas viram Novo lead, valores ausentes ou inválidos viram zero, datas inválidas ficam vazias. Linhas sem nome são ignoradas e contadas. Colunas não mapeadas não são preservadas. Valores aceitam formato brasileiro e ponto decimal. Exportação UTF-8 com BOM, campos entre aspas e proteção contra fórmulas de planilha. Essa proteção pode prefixar apóstrofo em contatos que começam por + ou outros caracteres de fórmula.

## Privacidade e limites

Os dados ficam somente na memória desta página, sem envio a servidor ou armazenamento persistente. Exporte antes de fechar/recarregar e importe o arquivo ao retomar. Não é um CRM multiusuário nem há sincronização, histórico de alterações, notificações ou autenticação própria. A hospedagem pode restringir acesso ao proprietário. Dados reais não fazem parte do repositório ou da demonstração.

## Execução

HTML, CSS e JavaScript sem dependências externas. Sirva `dist/` com um servidor estático, por exemplo `python -m http.server 8000 --directory dist`, e abra http://localhost:8000.
