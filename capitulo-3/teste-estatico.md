# Guia de Estudos: ISTQB - Certified Tester Foundation Level (CTFL)
**`Conteúdo resumido e utilizado nos meus estudos para o exame da certificação CTFL 4.0`**

---

# Teste Estático

## 3.1 Noções básicas de Teste Estático
Diferente do teste dinâmico, o teste estático baseia-se na análise de produtos de trabalho sem a necessidade de execução do código. Os produtos de trabalho são avaliados por meio de exame manual (como revisões) ou com o apoio de ferramentas (como análise estática). Seus objetivos incluem melhorar a qualidade, detectar defeitos, e avaliar características como legibilidade, integridade, correção, testabilidade e consistência, podendo ser aplicado tanto para verificação quanto para validação.

* **Abrangência:** Pode ser aplicado em requisitos, user stories, código-fonte, arquitetura, planos de teste e até cronogramas.
* **Foco:** Identifica diretamente o **defeito** (causa-raiz), enquanto o teste dinâmico foca na **falha** (comportamento visível).
* **Ferramentas:** Pode ser realizado manualmente (revisões) ou de forma automatizada (ferramentas de análise estática de código).

### 3.1.1 Produtos de trabalho examináveis por testes estáticos
Quase todos os produtos de trabalho podem ser examinados por meio de testes estáticos, desde que possam ser lidos e compreendidos (para revisões) ou tenham uma estrutura verificável, como uma sintaxe formal (para análise estática).
Exemplos incluem:

* Documentos de especificação de requisitos;
* Código-fonte;
* Planos de teste e casos de teste;
* Itens do backlog do produto e cartas de teste;
* Documentação do projeto, contratos e modelos.

### 3.1.2 Valor do teste estático
O teste estático aplica o princípio do teste antecipado (Shift-left), oferecendo diversos benefícios:

* **Detecção precoce e econômica:** Encontrar e corrigir defeitos antes da execução é mais barato e consome menos esforço.
* **Redução de prazos:** Diminui o retrabalho em fases posteriores do SDLC.
* **Identificação de defeitos invisíveis aos testes dinâmicos:** Como código inacessível ou padrões de projeto não implementados.
* **Melhoria da comunicação:** Cria um entendimento compartilhado entre os stakeholders, garantindo que os requisitos descrevem as necessidades reais.
* **Eficiência de código:** A análise estática encontra defeitos no código com mais eficiência que testes dinâmicos.

### 3.1.3 Diferenças entre testes estáticos e testes dinâmicos
Ambos se complementam, mas diferem em como encontram falhas e no que conseguem medir:

* **Como detectam:** Testes estáticos encontram defeitos diretamente. Testes dinâmicos causam falhas e, a partir delas, os defeitos são diagnosticados.
* **Objetivo:** Estático encontra defeitos (ex: inconsistências, erros de sintaxe); Dinâmico encontra falhas (ex: erro de cálculo em tempo de execução).
* **Características medidas:** Testes estáticos medem o que não depende da execução (ex: capacidade de manutenção, segurança); testes dinâmicos medem o que depende da execução (ex: eficiência de performance).
* Prevenção:** O teste estático é uma forma de prevenção de defeitos, enquanto o dinâmico é uma forma de detecção de falhas.

Defeitos típicos mais fáceis e/ou baratos de encontrar via teste estático:

* Defeitos nos requisitos (inconsistências, ambiguidades, contradições, omissões);
* Defeitos de projeto (estruturas ineficientes de banco de dados, modularização deficiente);
* Certas falhas de codificação (variáveis não declaradas, código duplicado ou inacessível);
* Desvios de padrões (ex: não seguir convenções de nomenclatura);
* Especificações incorretas de interface (número/tipo de parâmetros incompatíveis);
* Vulnerabilidades de segurança (ex: estouro de buffer);
* Lacunas ou imprecisões na cobertura da base de testes.

---

## 3.2 Processo de feedback e revisão
As revisões são a forma manual de teste estático. Elas variam em formalidade, mas todas visam avaliar um produto de trabalho em busca de anomalias.

### 3.2.1 Benefícios do feedback antecipado e frequente dos stakeholders
O feedback frequente ao longo do ciclo de vida evita mal-entendidos sobre os requisitos, garantindo que mudanças sejam compreendidas mais cedo. Isso impede o retrabalho dispendioso e permite que a equipe foque nos recursos de maior valor e impacto para o negócio.

### 3.2.2 Atividades do Processo de Revisão
Um processo de revisão formal segue uma sequência lógica de atividades:

1.  **Planejamento:** Definição do escopo, objetivo, produto a ser revisado, características de qualidade, critérios de saída, esforço e prazos.
2.  **Início da revisão:** Garantir que todos estejam preparados, possuam acesso ao material e compreendam suas funções.
3.  **Revisão individual:** Cada revisor avalia o documento isoladamente, identificando anomalias potenciais.
4.  **Comunicação e Análise de Problemas:** Discussão na reunião de revisão para analisar anomalias (que não são necessariamente defeitos), visando consolidar os achados e decidir o status de cada item.
5.  **Correção e relatório:** Criação de relatórios de defeitos, acompanhamento das correções, aceite do produto (quando os critérios de saída são atingidos) e comunicação dos resultados.

### 3.2.3 Funções e responsabilidades nas revisões

* **Autor:** Responsável por criar o produto de trabalho e realizar as correções.
* **Gerente:** Decide o que será revisado e aloca os recursos (equipe e tempo).
* **Moderador (Facilitador):** Responsável pela eficácia das reuniões e mediação de conflitos.
* **Relator:**  reúne as anomalias dos revisores e registra as informações da revisão, como decisões e novas anomalias encontradas durante a reunião de revisão.
* **Revisor:** Realiza a revisão técnica ou de negócios (pode ser alguém do projeto ou especialista).
* **Líder de Revisão:** Responsável geral pela organização e sucesso da revisão.

### 3.2.4 Tipos de Revisão
O mesmo produto pode passar por múltiplos tipos de revisão, dependendo da formalidade e necessidade do projeto:

* **Revisão Informal:** Não segue um processo documentado. Foco em rapidez e baixo custo. Objetivo: detectar anomalias.
* **Walkthrough (Passo a passo):** O autor conduz a sessão. Útil para explicar o funcionamento e buscar consenso.
* **Revisão Técnica:** Realizada por pares técnicos. Foca na conformidade técnica e tomada de decisão.
* **Inspeção:** O tipo mais formal. Usa checklists rigorosos, papéis definidos e métricas para encontrar defeitos.

**Regra Importante: O autor não pode ser líder nem relator na inspeção.**

### 3.2.5 Fatores de Sucesso para Revisões
* Definir objetivos claros e critérios de saída mensuráveis (nunca usar a revisão para avaliar os participantes);
* Escolher o tipo de revisão apropriado ao contexto, necessidades e produto de trabalho;
* Realizar revisões em pequenas partes para manter a concentração dos participantes;
* Fornecer feedback constante aos stakeholders e autores;
* Disponibilizar tempo suficiente para a preparação;
* Garantir o apoio e suporte da gerência;
* Integrar as revisões à cultura da organização para promover aprendizado contínuo.