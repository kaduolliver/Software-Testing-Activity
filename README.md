# Software-Testing-Activity

Este projeto visa a criação de um sistema, organizado em etapas interdependentes que incluem análise de usuário e metodologia Scrum, criação de interface de usuário (UI), desenvolvimento da lógica do sistema, integração de APIs e implementação de banco de dados. A aplicação de testes de software em cada fase será fundamental para garantir a confiabilidade, usabilidade e desempenho da solução final.


Coisas relacionais:

-- Exemplo de Fluxo de Documentação --

Criar plano de teste → 2. Escrever casos de teste → 3. Executar testes e registrar defeitos → 4. Gerar relatório → 5. Atualizar matriz de rastreabilidade → 6. Revisar e arquivar.

-- Documento de Estratégia de Teste (Plano de Teste) --

Objetivo: Definir abordagem, recursos e cronograma.

Conteúdo:
Introdução: Objetivo do teste e escopo (módulos/funcionalidades incluídos e excluídos).
Objetivos de Teste: O que será validado (ex: requisitos específicos, desempenho).
Estratégia de Teste:
Tipos de teste (funcionais, não funcionais).
Níveis de teste (unitário, integração, sistema, aceitação).
Critérios de entrada/saída (ex: "Testes de sistema iniciam após aprovação dos testes de integração").
Recursos: Equipe, ambientes de teste, ferramentas (ex: Selenium para automação).
Cronograma: Datas e marcos (ex: "Testes de aceitação em 15/10").
Riscos e Mitigações: Ex: "Falta de dados de teste → Usar ferramenta de geração de dados fictícios".

@@@@@@@ Testes no Frontend @@@@@@@@

Objetivo: Validar a interação do usuário, interface gráfica (UI) e experiência do usuário (UX).
O que testar:

Funcionalidade da UI: Botões, formulários, navegação, menus e fluxos de telas.
Responsividade: Compatibilidade com diferentes dispositivos (mobile, desktop) e browsers (Chrome, Firefox).
Acessibilidade: Conformidade com padrões como WCAG (ex: contrastes de cores, leitores de tela).
Performance Cliente-Side: Carregamento de páginas, renderização de elementos, uso de memória.

Tipos de Teste:
Testes Manuais: Validação visual e de usabilidade.
Testes Automatizados:
E2E (End-to-End): Ferramentas como Cypress, Selenium ou Playwright para simular ações do usuário.
Testes de Componentes: Ferramentas como Jest + React Testing Library (para React) ou Vue Test Utils (para Vue).
Testes de Cross-Browser: Usando ferramentas como BrowserStack ou Sauce Labs.

Exemplo:
Testar se um formulário de cadastro exibe mensagens de erro claras quando campos obrigatórios estão vazios.

@@@@@@@ Testes no Backend @@@@@@@

Objetivo: Garantir que a lógica de negócio, APIs e processamento de dados funcionem corretamente.
O que testar:
APIs: Validação de endpoints (GET, POST, PUT, DELETE) e respostas (status codes, JSON Schema).
Regras de Negócio: Cálculos, validações de dados e fluxos complexos.
Integração Externa: Comunicação com serviços terceiros (ex: gateways de pagamento, APIs de autenticação).
Segurança: Autorização, autenticação, prevenção de ataques (SQL Injection, XSS).

Tipos de Teste:
Testes Unitários: Testar funções ou classes isoladas (ex: JUnit para Java, pytest para Python).
Testes de Integração: Verificar comunicação entre módulos ou microsserviços.
Testes de Contrato: Validar se APIs seguem especificações (ex: Pact, Postman).
Testes de Carga/Stress: Avaliar performance do servidor (ex: JMeter, Locust).

Exemplo:
Testar se uma API de cálculo de frete retorna o valor correto com base no CEP e peso do produto.

@@@@@@@ Testes no Banco de Dados (não é o foco, não precisa testar o SGBD) @@@@@@@

Objetivo: Garantir integridade, consistência e performance dos dados.
O que testar:
CRUD: Inserção, leitura, atualização e exclusão de dados.
Esquema do Banco: Validação de tabelas, colunas, chaves e constraints (ex: NOT NULL, UNIQUE).
Transações: Rollback em caso de falha, concorrência (ex: deadlocks).
Queries Complexas: Desempenho de consultas (ex: uso de índices).
Migrations: Verificar scripts de atualização do banco (ex: Flyway, Liquibase).

Tipos de Teste:
Testes Unitários para Queries: Usando frameworks como DBUnit.
Testes de Integração: Validar interação entre backend e banco.
Testes de Performance: Tempo de resposta de consultas sob carga (ex: pgBench para PostgreSQL).

Exemplo:
Testar se uma exclusão em cascata de um usuário remove todos os registros relacionados (pedidos, endereços).

@@@@@@@ (Ponto final) Testes Entre Camadas (Sistema Completo) @@@@@@@

Objetivo: Validar a integração entre frontend, backend e banco de dados.
Exemplos:
Fluxo Completo: Um usuário adiciona um produto ao carrinho (frontend) → a API processa a requisição (backend) → o banco atualiza o estoque.
Sincronização de Dados: Garantir que dados exibidos no frontend sejam consistentes com o banco de dados.
Ferramentas:
Testes E2E: Cypress, Playwright (simulam ações do usuário e validam resultados no banco).
Monitoramento: New Relic, Datadog (rastreiam transações entre camadas).
