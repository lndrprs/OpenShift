
<div align="Center"> 
<br>

<h4>
░█████╗░██████╗░███████╗███╗░░██╗░██████╗██╗░░██╗██╗███████╗████████╗
██╔══██╗██╔══██╗██╔════╝████╗░██║██╔════╝██║░░██║██║██╔════╝╚══██╔══╝
██║░░██║██████╔╝█████╗░░██╔██╗██║╚█████╗░███████║██║█████╗░░░░░██║░░░
██║░░██║██╔═══╝░██╔══╝░░██║╚████║░╚═══██╗██╔══██║██║██╔══╝░░░░░██║░░░
╚█████╔╝██║░░░░░███████╗██║░╚███║██████╔╝██║░░██║██║██║░░░░░░░░██║░░░
░╚════╝░╚═╝░░░░░╚══════╝╚═╝░░╚══╝╚═════╝░╚═╝░░╚═╝╚═╝╚═╝░░░░░░░░╚═╝░░░
</h4>
</div>

----

<details>
  <summary><b> 1. Tópicos </b></summary>
<div align="Left">  
<br>  

O1.1 - OpenShift
 > - Plataforma corporativa de contêineres desenvolvida pela Red Hat, construída sobre Kubernetes;
 > - Objetivos:
 >   - Padronização de deploy de aplicações;
 >   - Segurança por padrão;
 >   - Automação do ciclo de vida de aplicações e do cluster;
 >   - Experiência PaaS para desenvolvedores;
 >   - Governança e controle para times de operação. 

O1.2 - Diferenciais 
 > - Kubernetes "opinionado";
 > - Segurança restritiva por padrão;
 > - Operadores para Gerenciamento Automático;
 > - Integrações Nativas (CI/CD, Registry, Monitoring, Logging...)
 > - Suporte e Certificação Red Hat. 
 >
 > - Kubernetes é um Framework, OpenShift é uma plataforma completa. 

O1.3 - OpenShift como Plataforma (PaaS)
 > - Desenvolvedores focam em código;
 > - Operadores focam em políticas e governança;
 > - Plataforma cuida de deploy, scaling e segurança
 > - Características PaaS:
 >   - Build Automatizado;
 >   - Deploy Padronizado;
 >   - Escalabilidade Automática;
 >   - Observabilidade Integrada;
 >   - Controle de Acesso Centralizado. 

 O1.4 - Arquitetura Conceitual do OpenShift
 > - Infraestrutura: Bare Metal, VM, Cloud Pública ou Privada; 
 > - Plataforma: Kubernetes, CRI-O, etcd;
 > - Serviços OpenShift: Networking, Registry Interno, Monitoring, Logging e Operators;
 > - Aplicações: Pods, Services e Routes. 

 O1.5 - Secure by Default 
 > - Containers não rodam como Root;
 > - Uso restritivo de capacidades do Linux; 
 > - Isolamentro entre projetos;
 > - RBAC rigoroso;
 > - SCC (Security Context Constraints).

O1.6 - Projects vs Namespaces
 > - Baseado em namespaces do Kubernetes, o OpenShift tem o Project;
 > - Project = Namespace + Políticas;
 > - Inclui:
 >   - Quotas;
 >   - Limites de Recursos;
 >   - RBAC;
 >   - Isolamento de Rede. 
 > - Projetos facilitam a governança multi-time. 
 > 
 > - Namespace é o Isolamento Lógico no Kubernetes.

O1.7 - Componentes-Chave Introduzidos pelo OpenShift 
 > - ImageStreams: Controle lógico de imagens;
 > - BuildConfigs: Pipelines de Build;
 > - Routes: Exposição HTTP / HTTPS;
 > - Operators: Automação de Serviços Complexos;
 > - Cluster Operators: Gestão do Próprio Cluster. 

O1.8 - Modelo de Responsabilidades:
> | Setor | Responsabilidade |
> |-------|------------------|
> | Desenvolvedor | Código, Imagens, Deploy |
> | Plataforma | Segurança, Networking, Observabilidade |
> | Operações | Cluster, Upgrades, DR |

O1.9 - Visão Geral da Arquitetura
 > - Um cluster OpenShift é organizado em planos funcionais, com separação de responsabilidades:
 >   - Control Plane;
 >   - Data Plane;
 >   - Infra Plane;
 >   - Management Plane. 

O1.1O - Control Plane 
 > - Cérebro do Cluster. 
 > - Componentes Principais:
 >   - kube-apiserver
 >     - Ponto central de comunicação do Cluster;
 >     - Toda operação passa por ele (CLI, console, operadores);
 >     - Expõe a API Kubernetes;
 >     - Aplica autenticação, autorização (RBAC) e admission control. 
 >
 >   - etcd 
 >     - Banco de dados distribuído (key-value);
 >     - Extremamente sensível a latência e I/O. 
 >     - Armazena:
 >       - Estado desejado;
 >       - Configurações;
 >       - Segredos (Criptografados).
 > 
 >   - kube-scheduler
 >     - Decide em qual node um Pod será executado; 
 >     - Considera: 
 >       - Recursos Disponíveis;
 >       - Afinidade / anti-afinidade;
 >       - Taints e Tolerations;
 >       - Policies do Cluster. 
 >
 >   - kube-controller-manager
 >     - Garante que o estado atual convirja para o estado desejado. 
 >     - Controla:
 >       - Replicas;
 >       - Nodes;
 >       - Endpoints;
 >       - Jobs. 

O1.11 - Worker Nodes (Data Plane)
 > - Workers são responsáveis por executar workloads. 
 > - Componentes Principais:
 >   - kubelet
 >     - Agente do Kubernetes no Node; 
 >     - Garante que os Pods definidos rodem corretamente; 
 >     - Reporta status ao API Server. 
 >
 >   - CRI-O 
 >     - Runtime de containers do OpenShift;
 >     - Implementa o padrão OCI;
 >     - Mais enxuto e seguro que Docker. 
 >
 >   - kube-proxy / OVN
 >     - Gerencia regras de rede;
 >     - Comunicação enter Pods e Services. 
 >
 > - Responsabilidades dos Workers:
 >   - Execução de Pods;
 >   - Montagem de Volumes;
 >   - Coleta de Métricas;
 >   - Aplicação de Políticas de Rede. 

O1.12 - Infra Nodes (Camada de Plataforma)
 > - OpenShift permite Nós Dedicados para serviços de Infraestrutura:
 >   - Router (Ingress Controller);
 >   - Registry Interno; 
 >   - Monitoring (Prometheus, Alertmanager);
 >   - Logging (EFK / Loki).

O1.13 - Networking na Arquitetura 
 > - Networking é a parte central da arquitetura OpenShift:
 > - Características:
 >   - Rede flat (Todo Pod fala com todo Pod);
 >   - IP único por Pod;
 >   - DNS interno Nativo. 
 >
 > - Componentes:
 >   - OVN-Kubernetes (Padrão Atual);
 >   - Ingress Controllers;
 >   - Routes (Exposição HTTP / HTTPS). 
 >
 > - Fluxo: 
 >   - Usuário -> Route -> Router -> Service - Pod

O1.14 - Operadores e Automação
 > - OpenShift é gerenciado por Operators;
 > - Tipos:
 >   - Cluster Operators: Mantêm o Próprio Cluster;
 >   - Aplication Operators: Bancos de Dados, Middleware, etc. 
 >
 > - Funções:
 >   - Instalação;
 >   - Configuração;
 >   - Atualização;
 >   - Recuperação Automática. 
 >
 > - O cluster se auto-corrige via operadores. 

O1.15 - Cluster Version Operator (CVO)
 > - Componente Crítico da Arquitetura OpenShift 4.x:
 >   - Controla versões do Cluster;
 >   - Garante Upgrades Coordenados;
 >   - Atualiza Operadores de Forma Segura.  
 >
 > - Diferenciais:
 >   - Upgrades Declarativos;
 >   - Sem scripts manuais e complexos. 

O1.16 - Domínios de Falha (Failure Domains)
 > - Conceito Arquitetural Importante:
 >   - Node failure;
 >   - Zone Failure;
 >   - Control Plane Failure. 
 >
 > - OpenShift permite:
 >   - Spread de Pods;
 >   - Afinidade entre Zonas;
 >   - Tolerância a Falhas Planejada.     
 
O1.17 - Conceito de Objeto no OpenShift 
 > - Objeto é uma entidade declarativa armazenada no eetcd que descreve:
 >   - Estado Desejado;
 >   - Configuração;
 >   - Relacionamentos. 
 >
 > - Você declara o que quer -> O sistema tenta manter isso verdadeiro. 

O1.18 - Pod 
 > - Menor unidade implantável no OpenShift;
 > - Pode conter:
 >   - Um contêiner;
 >   - Múltiplos Contêineres fortemente acoplados. 
 >
 > - Características:
 >   - Compartilham:
 >     - IP;
 >     - Portas;
 >     - Volumes. 
 >   - Vida curta e descartável;
 >   - Não deve ser gerenciado diretamente em produção. 

O1.19 - ReplicaSet 
 > - Garante que N réplicas de um Pod existam;
 > - Substitui Pods mortos automaticamente;
 > - Não faz rollout controlado;
 > - Geralmente não é manipulado diretamente. 

O1.20 - Deployment 
 > - Camada acima do ReplicaSet;
 > - Gerenciamento de:
 >   - Versões;
 >   - Atualizações;
 >   - Rollbacks. 
 >
 > - Estratégias:
 >   - Rolling Update;
 >   - Recreate. 
 >
 > - Deployment -> ReplicatSet -> Pods 
 > - Deployment é a intenção de execução da aplicação. 
 >
 > - DeploymentConfig 
 >   - Permite gatilhos automáticos:
 >     - Image Change;
 >     - Config Change. 
 >   - Estratégias Blue-Green e Canary. 

O1.21 - Service 
 > - Fornece ENdpoint estável; 
 > - Abstrai IPs voláteis dos Pods.
 > - Tipos:
 >   - ClusterIP (Interno);
 >   - NodePort;
 >   - LoadBalancer. 

O1.22 - Route (Exposição Externa)
 > - Enquanto Kubernetes usa Ingress, Openshift usa Route;
 > - Expõe serviços HTTP /HTTPS;
 > - Terminação TLS;
 > - Políticas de Tráfego. 
 >
 > - Cliente -> Route -> Router -> Service -> Pod

O1.23 - ConfigMap  
 > - Variáveis de Ambiente;
 > - Arquivos de Configuração;
 > - Parâmetros Externos ao Container. 
 >
 > - Separação entre código e configuração. 

O1.24 - Secret 
 > - Armazena Senhas, Tokens e Certificados; 
 > - Codificados em Base64;
 > - Podem ser montados como volume, ou injetados como variáveis de ambiente;
 > - Possui controle via RBAC e criptografia em etcd. 

O1.25 - Labels e Selectos 
 > - Labels 
 >   - Metadados Chave-Valor;
 >   - Base de Seleção, Organização, Automação.
 >
 > - Selectors
 >   - Usados por Services, Deployments e NetworkPolicies

O1.26 - Volumes e Persistência
 > - Volumes
 >   - Acoplados ao Pod;
 >   - Definem onde os dados ficam. 
 >
 > - Persistência
 >   - PV (Infra);
 >   - PVC (Aplicação).
 > - Externa ao clico de vida do Pod. 

O1.27 - Autenticação
 > - Autenticação ocorre no kube-apiserver, por meio do subsistema OAuth do OpenShift.
 >
 > - Identidades e Usuários
 >   - Identity: Vínculo com o provedor externo;
 >   - User: Entidade interna do OpenShift;
 >   - Um usuário pode ter múltiplas identidades. 
 > 
 > - Provedores de Identidade (idP)
 >   - LDAP / Active Directory;
 >   - OAuth (GitHub, GitLab, Google);
 >   - OpenID Connect (OIDC);
 >   - HTPasswd - Ambientes Simples. 

O1.28 - Autorização 
 > - Baseada em RBAC (Role-Based Access Control)
 > - Elementos Principais:
 >   - Role / ClusterRole: Conjunto de Permissões;
 >   - RoleBinding / ClusterRoleBinding: Associação entre Permissão e Sujeito;
 >   - Subjects:
 >     - Users;
 >     - Groups;
 >     - ServiceAccounts. 

O1.29 - ServiceAccounts 
 > - Identidades Não Humanas;
 > - Usadas por Pods, Pipelines e Operators.
 >
 > - Cada Pod executa sob uma ServiceAccount, que define seu nível de acesso à API. 

O1.30 - CLI (oc) e Web Console
 > - oc CLI
 >   - Extensão do kubectl, com funcionalidades específicas do OpenShift; 
 >   - Capacidades: 
 >     - Gerenciamento de Recursos;
 >     - Login via OAuth;
 >     - Build e Deploy;
 >     - Debug e Troubleshooting;
 >     - Interação com Operadores. 
 >   - oc faz mais coisa que o Console.
 >
 > - Web Console
 >   - Interface Gráfica para Desenvolvedores, Operadores e Administradores. 
 >   - Funcionalidades:
 >     - Visualização de Workloads;
 >     - Logs e Métricas;
 >     - Topologia de Aplicações;
 >     - Deploy Guiado;
 >     - Gerenciamento de RBAC.
 >   - Reduz curva de aprendizado, em relação ao CLI.

O1.31 - Source-to-Image (S21)
 > - Modelo Tradicional do OpenShift.
 > - Processo:
 >   - Código é Fornecido;
 >   - Builder da Image (Java, Node, Python, etc);
 >   - Build Automatizado;
 >   - Imagem gerada e armazenada no registry interno. 

O1.32 - BuildConfig
 > - Objeto OpenShift Declarativo, que define:
 >   - Fonte do código;
 >   - Estratégia de Build;
 >   - Triggers;
 >   - Saída (ImageStream).

O1.33 - ImageStreams 
 > - Abstração lógica sobre Imagens;
 > - Permite Versionamento, Controle de Rollout e Triggers Automáticos.
 >
 > - Build -> ImageStream -> Deployment / DeploymentConfig -> Pods
 >
 > - Gatilhos Comuns:
 >   - Nova Imagem;
 >   - Alteração de Configuração;
 >   - Deploy Manual. 

O1.34 - Estratégias de Deploy
 > - Rolling Update;
 > - Recreate;
 > - Blue - Green;
 > - Canary.
 >
 > A escolha impacta Disponibilidade, Risco e Tempo de Rollback

O1.35 - Health Checks 
 > - Liveness Probe: Reinício;
 > - Readiness Probe: Tráfego;
 > - Startup Probe: Inicialização lenta. 
 

</details>
</div>

----
