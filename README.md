# Extração e Automação com Python — C&M Compliance

## Visão Geral do Projeto
### Objetivo: 
Utilizar Python para simular a extração e processamento de dados que poderiam ser utilizados para monitorar a "saúde" da informação de Compliance, e realizar uma análise exploratória.

### Descrição da Necessidade: 
A equipe de C&M busca garantir a integridade dos dados e a adoção de práticas analíticas. Frequentemente, isso implica interagir com APIs internas ou externas para obter informações relevantes.
---

## Fluxo da Solução

1. Gerar 100 alert IDs simulados (`range(1, 101)`).
2. Para cada ID, realizar requisição simulada a uma API.
3. Coletar dados retornados no formato JSON.
4. Desnormalizar os campos relevantes.
5. Exportar para um arquivo delimitado por vírgulas (`alerts_data.csv`).

---

## Bibliotecas Utilizadas

- `requests` — para simulação de chamadas à API.
- `csv` — para escrita dos dados em formato plano.
- `json` — para formatação e estrutura dos dados JSON.

---

## Principais Desafios e Estratégias

| Desafio                                  | Estratégia                                                                 |
|------------------------------------------|----------------------------------------------------------------------------|
| API fora do ar ou com falha              | Uso de `try-except` para capturar erros e retornar mensagens amigáveis    |
| Dados incompletos ou campos ausentes     | Utilização de `.get()` com valor padrão em cada campo                     |
| Variabilidade na estrutura do JSON       | Normalização por meio de lista de campos fixos                            |
| Limites de requisição (rate limiting)    | Em projetos reais, implementar atraso com `time.sleep()` ou batch         |
| Autenticação em APIs reais               | Adicionar cabeçalhos com token: `headers={"Authorization": "Bearer TOKEN"}` |

---

## Arquivos do Repositório

- `extract_compliance_data.ipynb` — script principal de coleta e tratamento dos dados
- `alerts_data.csv` — arquivo gerado com dados desnormalizados
- `README.md` — documentação da solução e estratégias adotadas

---

## Possíveis Melhorias Futuras

- Implementar autenticação OAuth2(protocolo de autorização que permite que aplicações acessem recursos protegidos em nome de um usuário, sem precisar expor sua senha diretamente) para APIs reais;
- Criar testes automatizados para garantir robustez;
- Adicionar análise exploratória e visualizações dos dados coletados;

---

> Desenvolvido por Fernanda Cardozo de Oliveira como desafio para o teste técnico do Meli.
