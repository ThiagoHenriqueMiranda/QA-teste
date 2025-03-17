# QA-teste
Teste prático para Analista de Qualidade

**1º CENÁRIO**

**Plano de Testes para Integração com Marketplaces (Amazon, Mercado Livre, etc.)**

## 1. Documentação e Materiais de Apoio

### Identificação da Documentação:
- Documentação oficial das APIs dos marketplaces.
- Especificação técnica de integração.
- Requisitos do projeto e histórias do usuário.
- Diagramas de fluxo de dados.
- Casos de uso e critérios de acessibilidade.

### Análise da Documentação:
- Revisar endpoints das APIs para entender a comunicação entre o e-commerce e os marketplaces.
- Verificar restrições de taxas de requisições.
- identificar regras de negócio para sincronização de dados.
- Mapear os campos obrigatórios e formatos aceitos.

### Mapeamento dos Requisitos:
- Criar matrizes de rastreabilidade para garantir cobertura total dos testes.
- Mapear cada funcionalidade aos respectivos cenários de teste.
- Utilização de histórias de usuário para definir cenários reais.

### Utilização de Ferramentas:
- Jira ou TestRail para gerenciamento de requisitos e testes.
- Postman para testar APIs manualmente.
- Swagger para documentação da API.
- Trello para organizar tarefas.

## 2. Abrangência dos Testes

### Funcionalidades a Serem Testadas:
- **Sincronização de estoque** (envio e coleta de dados entre plataformas).
- **Cadastro e atualização de ofertas**.
- **Regras de aplicação de descontos**.
- **Processamento de pedidos** (importação, status de pagamento e atualização do pedido).
- **Sincronização de preços** (ajustes automáticos e promoções).

### Casos de Uso:
- **Cenários de Sucesso:**
  - Sincronização correta de produtos entre os marketplaces.
  - Preços e descontos sendo aplicados conforme a regra de negócio.
  - Estoque atualizado corretamente após uma compra.

- **Cenários de Falha:**
  - Falha na sincronização devido a dados inválidos.
  - Pedido realizado no marketplace, mas não importado corretamente.
  - Erro de timeout na API durante a transmissão de dados.

- **Cenários de Carga:**
  - Testes de alto volume de requisições para avaliar desempenho.
  - Verificação de comportamento sob carga simultânea de pedidos.

### Priorização dos Testes:
- Funcionalidades críticas que impactam diretamente nas vendas.
- Processos que envolvem transações financeiras.
- Testes de sincronização em tempo real.

## 3. Execução dos Testes

### Ambiente de Teste:
- Ambiente de **homologação** com dados simulados.
- Ambiente de **produção controlada** para testes finais.

### Dados de teste:
- Produtos fictícios** cadastrados com diferentes variações (cor, tamanho, peso, etc.).
- Pedidos simulados** para testar processamento.
- Cenários de estoque diferentes** (estoque alto, estoque baixo, produto esgotado).

### Ferramentas de Automação:
- Selênio** para testículos de ponta a ponta.
- Postman + Newman** para testes de API automatizadas.
- JMeter** para testes de carga e desempenho.
- Python (pytest)** para testes de backend.

### Registro de Resultados:
- Ferramenta de gestão de testes (TestRail, Zephyr).
- Logs detalhados em dashboards (Grafana, Kibana).
- Relatórios de execução e evidências documentadas.

---

**2º CENÁRIO**

**Plano de Testes para Integração com Bling**

## 1. Documentação e Materiais de Apoio

### Identificação da Documentação:
- Documentação oficial do Bling.
- Especificação técnica de integração.
- Requisitos do projeto.
- Diagramas de fluxo de dados entre Bling e o e-commerce.
- Casos de uso e critérios de acessibilidade.

### Mapeamento dos Requisitos:
- Criar matrizes de rastreabilidade para garantir cobertura total dos testes.
- Associar cada funcionalidade às regras de negócio e APIs utilizadas.
- identificar campos obrigatórios e formatos de dados aceitos.

### Utilização de Ferramentas:
- Jira ou TestRail para gerenciamento dos casos de teste.
- Postman para testes de manuais de API.
- Swagger para visualizar a documentação das APIs.
- Trello para organização de tarefas.

## 2. Abrangência dos Testes

### Funcionalidades a Serem Testadas:
- Sincronização de produtos** entre Bling e o e-commerce.
- Atualização de estoque** em tempo real.
- Processamento de pedidos** e envio de status.
- Geração de relatórios** e integração com dashboards.

### Priorização dos Testes:
- Funcionalidades críticas que impactam as operações diárias.
- Processos que envolvem transações financeiras e atualização de estoque.
- Testes de sincronização para evitar inconsistências.

## 3. Execução dos Testes

### Dados de teste:
- Produtos de teste** cadastrados com diferentes variações.
- Pedidos simulados** para verificar processamento.
- Cenários de estoque variados** para validar atualizações.

### Ferramentas de Automação:
- Selenium** para testes na interface do usuário.
- Postman + Newman** para testes de API automatizadas.
- JMeter** para testes de carga e desempenho.
- Python (pytest)** para validação de backend.

### Registro de Resultados:
- Ferramenta de gestão de testes (TestRail, Zephyr).
- Logs centralizados em dashboards (Grafana, Kibana).
- Relatórios documentados para rastreabilidade dos testes.

**3º CENÁRIO**

### Passo 1: **Entendimento do Fluxo de Anúncio**
Primeiro, é preciso entender como funciona o fluxo de estoque no sistema do cliente e como ele interage com o Mercado Livre. O que a documentação do Mercado Livre diz sobre o estado de "Pausado" e "Pausado (sem estoque)"? Isso é essencial para garantir que entendamos corretamente a mudança de status e quando ela deveria ocorrer.

### Passo 2: **Verificação de Logs e Histórico**
Você já foi informado de que não encontrou registros de envio de informações de estoque iguais a zero nos logs, ou que é um bom ponto de partida. A partir disso, recomendo-se:
- Verifique os logs da API do Magazord para analisar se há algum erro na atualização do estoque.
- Validar se o processo de envio de estoque do ERP para o Mercado Livre está configurado corretamente. Pode ser que a atualização não esteja enviando informações de "sem estoque" quando o estoque chegar a zero.

### Passo 3: **Verificar Integração ERP e Mercado Livre**
Considerando que você não tem acesso direto aos painéis, as possibilidades de erro podem ser:
- Falha de integração entre Magazord e Mercado Livre:** Se uma atualização de estoque não for realizada corretamente entre os sistemas, isso pode fazer com que o Mercado Livre não receba o sinal de que o item está esgotado.
- Erro de mapeamento de status no ERP:** O sistema Magazord pode ser configurado para marcar os itens como "Pausado" quando o estoque chega a zero, mas sem enviar o status "sem estoque" para o Mercado Livre.
- Problema de cache no Mercado Livre:** Pode ser que o sistema do Mercado Livre não esteja processando uma mudança de status imediatamente devido ao cache.

### Passo 4: **Testes de Comunicação**
- Manual de teste:** Se possível, tente simular a atualização de estoque diretamente no Magazord para ver como o sistema de estoque responde e o que é enviado para o Mercado Livre.
- Simular envio de estoque a zero:** Teste a integração para verificar se, ao enviar o estoque como zero para o Mercado Livre, o status de "Pausado (sem estoque)" é aplicado corretamente.

### Passo 5: **Revisão do Código ou API**
Se possível, verifique o código que envia as atualizações de estoque para o Mercado Livre. Pode haver algum erro de lógica na API ou falha de tratamento quando o estoque chega a zero.

### Passo 6: **Consulta à Documentação do Mercado Livre**
Por fim, consulte as documentos de integração do Mercado Livre para garantir que a atualização de status e estoque esteja sendo feita corretamente. O Mercado Livre pode ter regras específicas para quando um anúncio deve ser pausado ou marcado como "sem estoque", e seguir esses detalhes pode resolver o problema.


- Verifique se o Magazord está enviando o status correto ao Mercado Livre.
- Faça testes para simular a situação e veja se o problema persiste.
- Comunique-se com a equipe do cliente sobre a necessidade de revisar a configuração da integração e testar os fluxos manualmente.


**4º CENÁRIO**

1. **Nome Completo**  
   - Teste com nome válido:** Insira um nome completo real, com pelo menos um sobrenome.  
   - Teste com nome muito curto:** Insira um nome com menos de 3 caracteres e verifique se o sistema foi eliminado.  
   - Teste com caracteres especiais:** Insira caracteres inválidos (ex: "@,#,$,%,*") e verifique se o sistema aceita.  
   - Teste com números:** Insira os números no campo nome e valide se o sistema está bloqueado.

2. **E-mail**  
   - Teste com e-mail válido:** Insira um e-mail correto (ex: teste@email.com).  
   - Teste sem '@' ou domínio inválido:** Insira algo como "testemail.com" ou "teste@.com" e verifique a validação.  
   - Teste com espaço no meio:** Digite "teste @email.com" e verifique o comportamento.  

3. **Número de telefone**  
   - Teste com número válido:** Insira um número de telefone no formato correto (ex: (47) 98122-3451).  
   - Teste com letras:** Digite "abc123456" e verifique se o sistema foi eliminado.  
   - Teste com menos dígitos:** Insira "12345" e valide se o sistema não aceita.  
   - Teste com mais dígitos:** Insira um número exageradamente longo e valide a resposta do sistema.  

4. **Data de nascimento**  
   - Teste com dados válidos:** Inserir uma data de nascimento real, como "15/03/1990".  
   - Teste com formato inválido:** Digite "1990-03-15" e verifique se o sistema aceita.  
   - Teste com dados futuros:** Insira um dado no futuro (ex: "15/03/2030") e verifique se o sistema rejeitado.  
   - Teste com caracteres inválidos:** Insira "AB/CD/EFGH" e valide o comportamento.  

5. **Endereço (Rua, Cidade, Estado, CEP)**  
   - Teste com endereço completo e válido.
   - Teste com CEP inválido:** Digitar um CEP inexistente ou no formato errado.  
   - Teste com caracteres inválidos no campo cidade/estado:** Insira números ou caracteres especiais.  
