# gita-docs
Documentação de software de gerenciamento para orquestrador kubernetes

# Documentação do GITA

Este docuemtno servirá como base para criar a documentação de usuário do GITA

## O que é o GITA?

GITA é um gerenciador de Kubernetes, baseado em boas práticas. Com ele, você consegue ver quais melhorias podem ser feitas nas suas cargas de trabalho (workloads).
Ele também acompanha os eventos do cluster, bem como alertas e incidentes.

## Como é organizado?

Existem duas entidades no GITA, que são: Organização e Cluster. Uma Organização é um conjunto de um ou mais clusters. E um Cluster é um cluster Kubernetes.

Este é um exemplo de visão de Organização:  ![ visão do dashboard de um Cluster](./imagens/img_01.png)

Este é um exemplo de visão de dashboard de um Cluster:

![alt text](image.png)

|Dashboard
|
|Timeline
|
|Health
|____
|   |Cluster Events
|   |
|   |Alerts
|   |____
|   |    |Open
|   |    |
|   |    |Closed
|   |
|   |Incidents
|   |____
|   |    |Open
|   |    |
|   |    |Closed

## Dashboard

A visão geral do sistema, com métricas e status consolidados.
O dashboard do Gita é a principal interface de monitoramento, consolidando informações essenciais em um único local. Ele permite uma visão ampla e detalhada da infraestrutura Kubernetes, destacando:

### Métricas Consolidadas

- **Incidentes, Alertas e Problemas:** Exibe contadores e indicadores visuais (ex.: ícones, cores) para eventos críticos.
- **Status dos Clusters:** Mostra quais clusters estão ativos, offline ou enfrentando problemas.
- **Dados de Desempenho:** Inclui informações como utilização de CPU, memória e nós.

### Exemplo de Uso

- **Identificação Rápida de Problemas:**
        Um cluster exibe "Offline" e alertas elevados → permite priorizar ações corretivas.
- **Comparação de Ambientes:**
        Compare métricas entre ambientes, como "Produção" e "Desenvolvimento".

### Orientação

- **Personalize a Visualização:**
        Use filtros para visualizar clusters ou métricas específicas.
- **Tome Decisões Baseadas em Dados:**
        Priorize ações com base nos problemas mais críticos exibidos no painel.
- **Acesse Detalhes:**
        Clique em métricas ou alertas para expandir detalhes e acessar logs ou recomendações.

O dashboard potencializa equipes técnicas a monitorar, reagir e otimizar a infraestrutura de forma eficiente.

## Timeline

Histórico de eventos e ações realizadas no cluster.
A Timeline do Gita apresenta o histórico completo de eventos e ações realizados nos clusters Kubernetes, permitindo monitorar e auditar a infraestrutura com precisão.

### Funcionalidade

- **Registro Cronológico:** Exibe ações como criação de pods, alterações de configurações, incidentes e alertas.
- **Segmentação por Clusters:** Permite filtrar eventos específicos de um cluster ou organização.
- **Detalhamento de Eventos:** Mostra o usuário responsável, timestamp e descrição da ação realizada.

### Aplicações

- **Auditoria:**
        Identifique quem aplicou uma alteração que causou um problema no cluster.
        Verifique ações que ocorreram antes de um incidente.
- **Orquestração Eficiente:**
        Use o histórico para rastrear deploys bem-sucedidos e criar fluxos mais eficientes.
        Compare eventos entre clusters para ajustar configurações de maneira uniforme.

### Usos

- **Filtro por Intervalos de Tempo:**
    Localize rapidamente eventos críticos ou ações recentes.
- **Correlacione Eventos e Métricas:**
    Use a Timeline junto ao dashboard para entender o impacto de ações realizadas.
- **Documente Rotinas:**
    Utilize o histórico como base para registrar procedimentos de sucesso e evitar repetições de erros.

   A Timeline auxilia equipes na identificação de causas de problemas, na orquestração eficiente de clusters e na manutenção de uma infraestrutura bem documentada e rastreável.

## Health

    As informações sobre a saúde do sistema e dos clusters monitorados incluem verificações detalhadas do estado do sistema, abrangendo eventos, alertas e incidentes. Essas verificações avaliam a integridade dos clusters e das cargas de trabalho (workloads), classificando os dados em categorias específicas para facilitar o monitoramento e a análise.

### Cluster Events

    Exibe todos os eventos ocorridos no cluster em tempo real ou histórico.
    Exemplo de Uso: Monitorar mudanças, falhas ou ações administrativas dentro dos clusters.

### Submenus de Health

- **Cluster Events**: Os eventos de um cluster Kubernetes são notificações automáticas geradas pelo sistema Kubernetes para descrever algo que aconteceu ou está acontecendo no cluster. Eles são uma forma de monitorar o comportamento dos recursos e ações dentro do cluster, ajudando os administradores e operadores a diagnosticar problemas e entender o que está acontecendo.
- **Alerts**: São gerados em situações que merecem atenção, mas não está impactando (ainda) o cluster, Por exemplo: Uso de disco acima de 90%. Existem regras pré-definidas de alertas no Gita. Acesse <https://doc.gita.cloud/docs/category/alert> para ver maiores detalhes.
- **Open**: Alertas em aberto. Mostra alertas ativos que requerem atenção.
        **Exemplo de Uso:** Identificar problemas críticos e agir para mitigá-los.
- **Closed**: Alertas resolvidos. Lista alertas que não exigem mais atenção.
        **Exemplo de Uso:** Analisar problemas previamente resolvidos para prevenir futuras ocorrências.
- **Incidents**: Indicam indisponibilidade ou problemas críticos no cluster kubernetes. Exemplo: Um workload indisponível. Exemplos de regras de incidentes podem ser vistas em <https://doc.gita.cloud/docs/category/incident>
- **Open**: Incidentes em aberto. Exibe incidentes em andamento com detalhes, como gravidade e impacto.
        **Exemplo de Uso:** Priorizar esforços para solucionar falhas atuais.
- **Closed**: Incidentes resolvidos. Armazena incidentes resolvidos ou encerrados.
        **Exemplo de Uso:** Fornece um histórico para auditoria e análise de causa raiz.

|Misconfigurations
|____
|   |Segurity
|   |
|   |Alerts
|   |____
|   |    |Open
|   |    |
|   |    |Closed
|   |
|   |Problem
|   |____
|   |    |Open
|   |    |
|   |    |Closed

## Estrutura do Menu - Misconfigurations

## Misconfigurations

O monitoramento e gerenciamento de configurações incorretas ou vulneráveis identifica problemas que comprometem a segurança, estabilidade e desempenho do cluster. Essas falhas, como configurações inadequadas ou inseguras, podem surgir de erros humanos, desconhecimento ou negligência na configuração de recursos e políticas. A identificação e resolução dessas questões são fundamentais para evitar vulnerabilidades, garantir a confiabilidade do cluster e preservar o desempenho das aplicações.

### Submenus de Misconfigurations

- **Security**: A funcionalidade identifica falhas e vulnerabilidades relacionadas à segurança do cluster, destacando configurações incorretas que podem expor o ambiente a riscos. Exemplos incluem cargas de trabalho com recursos excessivos ou privilégios desnecessários. Essas configurações são analisadas para garantir conformidade com regras de segurança, minimizando vulnerabilidades e protegendo a infraestrutura.
        **Exemplo de Uso:**Revisar configurações inseguras, como permissões excessivas ou falhas no controle de acesso.
- **Conformidade**: São configurações incorretas nos recursos Falta de Limites de Recursos (Resource Limits): Pods sem limites de CPU e memória podem consumir todos os recursos disponíveis do Node. Outro exemplo comum é Deployments Sem Readiness ou Liveness Probes: Aplicações que falham não são reiniciadas ou removidas adequadamente. Exemplos de regras: <https://doc.gita.cloud/docs/category/problem>
- **Alerts**:
- **Open:** Alertas de segurança em aberto. Lista alertas relacionados a problemas de configuração que ainda precisam ser corrigidos.
        **Exemplo de Uso:** Priorizar a resolução de configurações críticas pendentes.
- **Closed**: Alertas resolvidos ou fechados.
- **Problem**:
- **Open**: Problemas detectados em aberto. Apresenta problemas de configuração ativos no cluster, como recursos mal configurados.
        **Exemplo de Uso:** Investigar problemas e aplicar ajustes para garantir a estabilidade.
- **Closed**: Problemas resolvidos. Exibe alertas já resolvidos ou fechados.
        **Exemplo de Uso:** Analisar problemas previamente corrigidos para melhorar políticas de configuração.

### Orientação Geral

- **Revisão Constante:** Monitore a seção Security para identificar riscos de configuração.
- **Ação Imediata em Alertas:** Resolva alertas abertos antes de escalar para incidentes.
- **Análise Preventiva:** Use dados de problemas fechados para prevenir erros futuros.

Essa seção promove um ambiente Kubernetes mais seguro e resiliente.

|Inventory
|____
|   |Nodes
|   |
|   |Namespace
|   |
|   |Workload
|   |____
|   |    |Pods
|   |    |
|   |    |Pods Status
|   |    |
|   |    |Deployment
|   |    |
|   |    |Replicaset
|   |    |
|   |    |Statefulset
|   |    |
|   |    |Daemonset
|   |    |
|   |    |Cronjob
|   |    |
|   |    |Job
|   |
|   |Service Discovery
|   |____
|   |    |Ingress
|   |    |
|   |    |Service
|   |
|   |Storage
|   |____
|   |    |PV
|   |    |
|   |    |PVC
|   |    |
|   |    |Storage Classes
|   |    |
|   |    |ConfigMaps
|   |    |
|   |    |Secrets

## Estrutura do Menu - Inventory

## Inventory

Gerenciamento e visualização detalhada dos recursos do cluster. fornece uma visão detalhada O gerenciamento e visualização detalhada dos recursos do cluster fornecem uma visão organizada e categorizada de elementos como Workloads, Storage e Services no Kubernetes. No inventário, é possível editar objetos em formato YAML, acessar consoles e consultar logs dos pods. Essa estrutura facilita a administração da infraestrutura e garante um monitoramento eficiente dos recursos do cluster.de todos os recursos gerenciados no cluster Kubernetes. Ela é organizada em categorias que facilitam a administração e monitoramento da infraestrutura.

### Submenus de Inventory

- **Nodes**: Lista e status dos nós do cluster. Com informações detalhadas sobre seu status e capacidade.
      - **Exemplo de Uso:** Identificar nós sobrecarregados ou com problemas de conectividade.
- **Namespace**: Visualização dos namespaces configurados. Apresenta os namespaces do cluster, separando os recursos em ambientes lógicos.
  - **Exemplo de Uso:** Verificar isolamento e organização de workloads.
- **Workload**:
  - **Pods**: Detalhes dos pods em execução no cluster.
  - **Pods Status**: Monitora os estados dos pods (Running, Pending, Failed, etc.).
  - **Deployment**: Gerencia implantações, garantindo a disponibilidade de aplicações além da configuração e status dos deployments.
  - **Replicaset**: Informações sobre os replicasets, Assegura o número desejado de réplicas de pods.
  - **Statefulset**: Monitoramento de statefulsets.
  - **Daemonset**: Configuração e gerencia aplicações estateful de daemonsets.
  - **Cronjob**: Gerenciamento de cronjobs. Implanta pods em todos os nós.
  - **Job**: Execução e status de jobs. Automatiza tarefas programadas e jobs únicos.
- **Service Discovery**:
  - **Ingress**: Configurações de entrada. Controla o acesso externo às aplicações no cluster.
Service, Gerencia a comunicação entre os componentes do cluster.
  - **Service**: Lista de serviços configurados.
- **Storage**:
  - **PV**: Volumes persistentes.
  - **PVC**: Reclamações de volume persistente.
  - **Storage Classes**: Classes de armazenamento configuradas.
  - **ConfigMaps**: Mapas de configuração.
  - **Secrets**: Informações secretas armazenadas no cluster.

    Monitore o Status dos Recursos: Use as seções Nodes e Pods para identificar gargalos.
    Automatize e Organize: Utilize Cronjobs e Namespaces para simplificar a administração.
    Gerencie Dados com Segurança: Configure Secrets e PVCs para proteger e persistir dados críticos.

Essa seção permite controle total sobre os recursos do cluster, garantindo eficiência e organização.

|Configuration
|____
|    |Rules
|    |
|    |Installation
|    |
|    |Users
|    |
|    |Notifications
|    |
|    |Settings

## Estrutura do Menu - Configuration

## Configuration

Menu dedicado à configuração e personalização da aplicação. concentra todas as opções para personalizar e gerenciar o funcionamento da aplicação, garantindo que ela se adapte às necessidades do ambiente e dos usuários.

### Submenus de Configuration

- **Rules**: Configuração de regras específicas para monitoramento e alertas. Define ações automáticas, como limites de alerta ou políticas de segurança.
        **Exemplo de Uso:** Configurar alertas para níveis críticos de uso de CPU.
- **Installation**: Procedimentos para instalação e integração do sistema, etapas de instalação e integração com clusters Kubernetes.
        **Exemplo de Uso:** Configurar tokens de autenticação para conectar novos clusters ao sistema.
- **Users**: Gerenciamento de contas de usuários e permissões, Gerencia contas de usuários, suas permissões e roles.
        **Exemplo de Uso:** Adicionar um administrador ou definir permissões específicas para operadores.
- **Notifications**: Configuração de notificações e canais de alerta, por e-mail, Slack ou outras plataformas para incidentes ou alertas.
        **Exemplo de Uso:** Enviar alertas em tempo real para equipes de resposta.
- **Settings**: Ajustes gerais e personalizações da aplicação, reúne configurações gerais do sistema, como idioma, fuso horário, e preferências de exibição.
        **Exemplo de Uso:** Alterar o intervalo de atualização do dashboard.

    Automatize Monitoramento: Use Rules para configurar políticas que simplifiquem o gerenciamento.
    Notifique as Equipes Corretas: Ajuste Notifications para alertar as pessoas certas no momento certo.
    Controle de Acesso: Configure Users para garantir segurança e organização.

Essa seção oferece controle total sobre o comportamento e a administração da aplicação.

## Aplicação de Monitoração de Clusters Kubernetes

## Introdução

### Visão Geral

Gita é uma **plataforma de monitoração projetada para gerenciar e visualizar o status de clusters Kubernetes**. Com um dashboard centralizado, o usuário pode acessar rapidamente informações críticas sobre **incidentes, segurança, problemas, alertas nós ativos**.

## Funcionalidades Principais

- **Dashboard de Status**: Exibe métricas como incidentes, problemas de segurança, alertas e uso de nós em tempo real.
- **Adição de Clusters**: Permite a inclusão de clusters para monitoramento.
- **Indicadores de Desempenho**: Cada seção mostra percentuais e contagens detalhadas para análise rápida.

## Benefícios

- **Monitoramento Centralizado**: Facilita a administração de múltiplos clusters em uma interface amigável.
- **Tomada de Decisões Baseada em Dados**: Fornece insights em tempo real que ajudam na rápida identificação de problemas.

## Configuração inicial

### Cadastro

**Campos obrigatórios:**

- **Nome:** Nome completo do usuário.
- **E-mail:** Endereço eletrônico único para identificação.
- **Senha:** Definição de senha segura.
- **Confirmação de Senha:** Repetição da senha para validação.

### Dados de Pagamento

- **Telefone com DDD:** Número de contato incluindo o código de área.
- **Enderço:** logradouro, rua, casa.
- **UF (Estado):** Unidade Federativa de residência.
- **Cidade:** Localização do usuário.
- **CPF:** Cadastro de Pessoa Física para identificação.
- **CEP:** Código postal da residência.

### Login

- **E-mail:** Credencial de acesso.
- **Senha:** Código de autenticação.

## Interface do Usuário

A interface possui uma navegação intuitiva com painéis individuais para cada métrica de monitoramento, garantindo uma visão abrangente e detalhada das operações de clusters.

## Elementos e Funcionalidades

### Create Organization

Permite a criação de novas organizações para gerenciar clusters específicos, segmentando dados de diferentes ambientes.

### Como Adicionar um Cluster

- **Acesse o Dashboard**: Entre na aplicação com suas credenciais.
- **Selecione "Add Cluster"**: Clique no botão amarelo para iniciar o processo.
- **Preencha as Informações do Cluster**: Adicione os detalhes específicos do cluster a ser monitorado.
- **Conclua o Cadastro**: Salve e visualize o novo cluster no painel.

### Lista de Clusters (e.g., Gita Prod Old, gita-dev)

- Cada item representa um cluster Kubernetes monitorado.
- Status do Cluster: Indicadores como versão (e.g., v1.31.0, v1.28.0) e o estado operacional (e.g., "Online").
- Métricas Numéricas:

**Incidentes** (Vermelho): Número de incidentes críticos.
**Problemas de Segurança** (Amarelo): Relatórios de vulnerabilidades.
**Outras métricas**: Estatísticas adicionais para problemas e alertas.

- **Botão "Add Cluster"**: Funcionalidade para inserir novos clusters ao painel.
- **Configurações** (ícone de engrenagem): Opções para personalização

## Elementos da Tela

### Menu de Navegação e Pesquisa

Permite ao usuário buscar clusters ou organizações específicas, facilitando o gerenciamento.

### Seção "Create Organization"

Opção para criar uma nova organização, expandindo a estrutura gerenciada dentro da aplicação.

### Ambientes Listados ("Gita Prod Old", "gita-dev")

Exibe diferentes ambientes de
