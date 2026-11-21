# Molise Connect

**Gestão de estoque e solicitações de EPIs integrada ao SAP Business One.**

O **Molise Connect** é um projeto acadêmico de extensão desenvolvido para a **Molise Serviços e Construções Ltda.**, com o objetivo de simplificar a comunicação entre os responsáveis pelas obras, o almoxarifado e a gestão. A solução propõe centralizar as solicitações de materiais, o acompanhamento dos pedidos e as movimentações do estoque em um único sistema, integrado ao **SAP Business One por API**.

> **Status do projeto:** em desenvolvimento. A etapa de levantamento do problema, definição dos requisitos e prototipação está documentada; as funcionalidades descritas abaixo representam o escopo planejado, não necessariamente recursos já implementados.

## O problema

Atualmente, as solicitações de **Equipamentos de Proteção Individual (EPIs)** e de itens de manutenção chegam ao almoxarifado por diferentes meios, como formulários em papel, impressões e mensagens de WhatsApp. Esse processo pode gerar:

- Pedidos incompletos ou com informações incorretas;
- Dificuldade para consultar a disponibilidade dos itens;
- Falta de visibilidade sobre o andamento das solicitações;
- Retrabalho no registro manual das movimentações no SAP;
- Divergências entre o estoque registrado e o estoque físico;
- Atrasos no atendimento às equipes em campo.

## A solução

O Molise Connect propõe um **fluxo digital único**, com duas interfaces complementares:

- **Aplicação web:** destinada principalmente ao almoxarifado e à gestão, para consulta e movimentação de estoque, processamento de pedidos, indicadores e relatórios.
- **Interface mobile:** destinada aos responsáveis pelos centros de custo, para consultar itens, criar solicitações e acompanhar seu andamento.

O sistema contará com um **banco de dados próprio** e integração via API com o SAP Business One. **A proposta não é substituir o SAP**, mas reduzir tarefas repetitivas e manter os registros sincronizados.

## Funcionalidades previstas

| Funcionalidade | Descrição |
| --- | --- |
| **Autenticação e perfis** | Acesso conforme o papel do usuário: responsável por centro de custo, almoxarife ou gestor. |
| **Consulta de estoque** | Busca por nome, código, categoria e situação, com visualização das quantidades disponíveis. |
| **Entradas e saídas** | Registro de movimentações e atualização do estoque. |
| **Solicitações digitais (C.I.)** | Criação de Comunicações Internas com centro de custo, responsável, data necessária e itens solicitados. |
| **Kits de solicitação** | Modelos editáveis para Admissão, Podador e Roçador. |
| **Fila de pendências** | Acompanhamento dos pedidos pelos status **Pendente**, **Separando**, **Separada** e **Lançada**. |
| **Integração com SAP** | Envio da baixa ao SAP após a separação e confirmação antes de marcar o pedido como lançado. |
| **Dashboard** | Visão de itens críticos ou parados, estoque por categoria, movimentações recentes e solicitações pendentes. |
| **Relatórios** | Consultas filtradas por período, item e centro de custo. |
| **Entregas e alertas** | Registro de entregas de fornecedores e notificações de estoque crítico ou solicitações paradas. |

As funcionalidades são priorizadas no planejamento do projeto; entregas e alertas estão entre os itens desejáveis para a versão prevista.

## Como funciona uma solicitação

1. O **responsável pelo centro de custo** consulta os itens e cria uma C.I. digital, preenchendo os campos obrigatórios.
2. A solicitação entra na **fila de pendências** do almoxarifado.
3. O **almoxarife** confere a solicitação e separa os materiais disponíveis.
4. Ao concluir a separação, o sistema **envia a baixa ao SAP por API**.
5. A C.I. recebe o status **Lançada** somente após a confirmação do SAP. Se a integração falhar, o envio permanece pendente para nova tentativa, sem perda de dados.
6. Os usuários podem acompanhar o status, e a gestão consulta indicadores e relatórios.

## Quem utiliza

- **Responsável por centro de custo:** solicita EPIs e materiais de manutenção e acompanha os pedidos de sua obra.
- **Almoxarife:** recebe e separa as C.I.s, consulta o estoque e registra movimentações.
- **Gestor:** acompanha o estoque, analisa indicadores e consulta relatórios para apoiar decisões.

## Benefícios esperados

- Redução de erros de preenchimento e de lançamentos duplicados;
- Mais agilidade no atendimento às equipes;
- Melhor visibilidade do estoque e das solicitações;
- Maior consistência entre o controle interno e os registros do SAP;
- Comunicação mais transparente entre os setores;
- Menor dependência de papéis, planilhas e mensagens dispersas.

## Diretrizes do projeto

O desenvolvimento foi planejado com **Scrum**, em entregas incrementais e validação com usuários da Molise. Entre os cuidados definidos estão interfaces acessíveis e simples de usar (com referência à **WCAG 2.2** e ao **eMAG**), proteção de dados conforme a **LGPD**, controle de acesso por perfil e comunicação segura.

**Escopo:** a solução se concentra no controle de EPIs e itens de manutenção, sem substituir o SAP ou incluir, nesta versão, operação offline, controle completo de máquinas e ferramentas ou um módulo de recursos humanos.

## Organização prevista do repositório

```text
.
├── README.md               # Visão geral do projeto
├── docs/                   # Documentação do projeto
│   ├── requisitos/         # Requisitos e Product Backlog
│   ├── modelagem/          # Diagramas do sistema
│   ├── prototipo/          # Telas e referência ao protótipo no Figma
│   └── testes/             # Plano e registros de testes
└── src/                    # Código-fonte, conforme o desenvolvimento avançar
```

> A estrutura acima é a **organização planejada** na documentação e pode ser ajustada conforme o repositório evoluir.

## Equipe

Projeto desenvolvido no contexto das atividades de **Engenharia de Software / Análise e Desenvolvimento de Sistemas do Instituto Federal de São Paulo (IFSP)**.

- **Vinicius Rodrigues:** gestão do projeto, back-end e integração com o SAP.
- **Ingrid Ferreira:** experiência do usuário e front-end web/mobile.
- **Lucas Carlos:** banco de dados, testes e documentação.

## Documentação

A documentação do projeto reúne o contexto e a viabilidade da proposta, o Business Model Canvas, os requisitos funcionais e não funcionais, as regras de negócio, os diagramas, os protótipos e o plano de testes. Para mais detalhes, consulte os materiais disponíveis na pasta `docs/` quando adicionados ao repositório.

---

**Molise Connect — conectando quem solicita, quem gerencia e quem precisa dos materiais.**
