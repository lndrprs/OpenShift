
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



</details>
</div>

----
