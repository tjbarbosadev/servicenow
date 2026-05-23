---
title: "SNAF - Módulo 1: ServiceNow — The Modernized Work Experience"
subtitle: "ServiceNow Administration Fundamentals (SNAF)"
author: "Notas de Estudo para Certificação"
date: "2026"
geometry: margin=2.5cm
fontsize: 11pt
toc: true
toc-depth: 3
header-includes:
  - \usepackage{fancyhdr}
  - \pagestyle{fancy}
  - \fancyhead[L]{SNAF — Módulo 1}
  - \fancyhead[R]{ServiceNow Administration Fundamentals}
  - \fancyfoot[C]{\thepage}
  - \usepackage{xcolor}
  - \definecolor{snblue}{HTML}{032D60}
  - \usepackage{tcolorbox}
  - \newtcolorbox{infobox}{colback=blue!5,colframe=snblue,title=Conceito-Chave}
  - \newtcolorbox{tipbox}{colback=green!5,colframe=green!50!black,title=Dica}
  - \newtcolorbox{warnbox}{colback=red!5,colframe=red!50!black,title=Atenção}
---

\newpage

# Visão Geral do Curso

O curso **ServiceNow Administration Fundamentals (SNAF)** ensina habilidades e conceitos fundamentais para gerenciar e configurar a plataforma ServiceNow. Ele é baseado no e-book (participant guide) como recurso principal.

## Estrutura do Curso

- **Vídeos** guiam o estudante pelo e-book
- **Labs práticos** em formato step-by-step para aplicar os conceitos na instância ServiceNow
- **Knowledge Checks** ao final de cada módulo para testar compreensão
- **Update Sets** disponíveis para cada lab (permitem ver o produto final do lab caso haja problemas)

## Pré-requisito

\begin{infobox}
O curso \textbf{Welcome to ServiceNow} (gratuito) é pré-requisito recomendado. Ele cobre navegação básica da plataforma, que não será revisitada em detalhe neste curso.
\end{infobox}

## Caminho de Certificação

```
Welcome to ServiceNow (gratuito)
        |
        v
ServiceNow Administration Fundamentals (SNAF)
        |
        v
Experiência prática na plataforma
        |
        v
Certified System Administrator (CSA) Exam
        |
        v
Cursos avançados de especialização
```

\newpage

# 1. ServiceNow: A Experiência de Trabalho Modernizada

## 1.1 O que é ServiceNow?

ServiceNow é uma **plataforma de aplicação baseada na nuvem** (cloud-based application platform) categorizada como **aPaaS** (Application Platform as a Service). Ela fornece todas as ferramentas e serviços necessários para construir, implantar e gerenciar aplicações.

### Características Principais

| Característica | Descrição |
|---|---|
| **Single System of Action** | Plataforma unificada onde workflows fluem entre tecnologia, operações, funcionários e clientes |
| **AI-Powered** | Inteligência artificial conectada a todos os cantos do negócio |
| **Unified Data Model** | Modelo de dados unificado que conecta AI agents, dados e workflows |
| **Workflow Data Fabric** | Conecta e unifica dados estruturados e não estruturados mantendo governança rigorosa |
| **367+ Integrações** | Integra-se com mais de 367 aplicações de negócios |
| **Compliance** | Suporte a indústrias altamente regulamentadas e requisitos de residência de dados |

### O que os administradores podem fazer

\begin{tipbox}
ServiceNow capacita administradores a trabalhar de forma mais inteligente, automatizando processos e simplificando operações.
\end{tipbox}

- **Automatizar Service Requests** — ex.: password resets usando Service Catalogs e Flows
- **Gerenciar Changes** — módulo de Change Management com aprovações automatizadas e análise de risco
- **Streamline Incidents** — logging e priorização com notificações automatizadas e SLAs
- **Knowledge Base** — resolver issues recorrentes rapidamente
- **Monitorar Performance** — dashboards e KPIs para identificar tendências
- **Simplificar Onboarding/Offboarding** — workflows automatizados com acesso seguro e compliance

## 1.2 Arquitetura da Plataforma

```
┌─────────────────────────────────────────────┐
│           DISPOSITIVOS CLIENTES             │
│   (Computadores, Tablets, Smartphones)      │
└──────────────────┬──────────────────────────┘
                   │ Requests
                   v
┌─────────────────────────────────────────────┐
│        SERVICENOW CLOUD PLATFORM            │
│  ┌───────────────────────────────────────┐  │
│  │         APPLICATION LAYER             │  │
│  │  ITSM | HRSD | CSM | SecOps | ...    │  │
│  └───────────────────┬───────────────────┘  │
│  ┌───────────────────┴───────────────────┐  │
│  │      PLATFORM LAYER (aPaaS)           │  │
│  │  Workflows | AI Agents | Automation   │  │
│  └───────────────────┬───────────────────┘  │
│  ┌───────────────────┴───────────────────┐  │
│  │     DATABASE (Tabelas / Records)      │  │
│  │  Incident | User | Group | HR Case    │  │
│  └───────────────────────────────────────┘  │
│  ┌───────────────────────────────────────┐  │
│  │     INFRASTRUCTURE LAYER              │  │
│  │  Data Centers | Compliance | Security │  │
│  └───────────────────────────────────────┘  │
└─────────────────────────────────────────────┘
```

### Conceito: Tudo é um Record dentro de uma Table

\begin{infobox}
\textbf{Tudo no ServiceNow é representado como um Record dentro de uma Table.} Quando o usuário faz uma request, ela é enviada ao servidor que processa e retorna os dados apropriados.
\end{infobox}

**Exemplos de tabelas:**

| Tabela | Aplicação | Compartilhada? |
|---|---|---|
| Incident | IT Service Management (ITSM) | Não |
| HR Case | HR Service Management | Não |
| User | Plataforma | Sim (cross-application) |
| Group | Plataforma | Sim (cross-application) |

## 1.3 Cenário do Curso: Cloud Dimensions

O curso utiliza a empresa fictícia **Cloud Dimensions** que está implementando ServiceNow para os departamentos de **IT** e **HR**.

### Cenário IT — Infinity Holographic Handheld Device

```
Cloud Dimensions (IT Dept)
        |
        v
Piloto do Infinity Holographic Handheld Device
(3D on-site repair instruction videos)
        |
        ├── Training Technology Team Leads
        │   └── Suporte técnico durante e após o piloto
        |
        └── Necessidades de tracking:
            ├── Identificar melhorias no treinamento
            ├── Construir FAQ na Knowledge Base
            ├── Criar Service Catalog Item para o device
            ├── Fornecer feedback ao fabricante
            └── Monitorar qualidade do suporte
```

### Cenário HR — HR Case Management

O departamento de HR está explorando as capacidades da aplicação **HR Case Management**, investigando o que é necessário para instalar e configurar a aplicação para atender suas necessidades.

\newpage

# 2. Acesso de Usuários e Personas

## 2.1 Role-Based Access Control (RBAC)

Uma das principais responsabilidades do System Administrator é configurar **acesso baseado em roles (roles)** dentro da plataforma. Roles determinam quais features, aplicações, funções e dados o usuário pode acessar.

### Hierarquia de Personas

```
┌──────────────────────────────────────────────────┐
│              SYSTEM ADMINISTRATOR                │
│                  (admin role)                    │
│  Acesso extensivo, mas com restrições em         │
│  HR e Security Operations                        │
├──────────────────────────────────────────────────┤
│         SPECIALIZED ADMINISTRATORS               │
│  Gerenciam funções/apps específicas              │
│  Acesso amplo, mas limitado à sua área           │
├──────────────────────────────────────────────────┤
│             PROCESS USERS                        │
│  Seguem workflows definidos                      │
│  Roles: ITIL, Approver User, etc.               │
├──────────────────────────────────────────────────┤
│              APPROVERS                           │
│  Apenas role approver_user                       │
│  Acesso limitado a tarefas de aprovação          │
├──────────────────────────────────────────────────┤
│             REQUESTERS                           │
│  Sem roles atribuídas                            │
│  Acesso via Service Catalog e Self-Service       │
└──────────────────────────────────────────────────┘
```

## 2.2 System Administrator (admin role)

| Capacidade | Permitido? |
|---|---|
| Acesso extensivo a features, funções e dados | Sim |
| Criar e modificar user roles | Sim |
| Impersonar outros usuários | Sim |
| Gerenciar a plataforma em alto nível | Sim |
| Acesso a HR functionalities | **Não** |
| Acesso a Security Operations | **Não** |
| Impersonar users com security_admin role | **Não** |
| Elevar privilégios durante impersonation | **Não** |

\begin{warnbox}
O role \texttt{admin} deve ser concedido com cautela devido aos seus amplos privilégios.
\end{warnbox}

## 2.3 Users, Groups e Roles

### Users

- Indivíduo com acesso à instância ServiceNow
- Identificado por um **User ID** único (credencial de login)
- Base do controle de acesso
- Roles e permissões baseados nas responsabilidades na organização

### Groups

- Coleções de users com propósito comum ou tarefas similares
- Permissões atribuídas coletivamente ao group
- Exemplos de uso: aprovar change requests, resolver incidents, receber email notifications, gerenciar o service catalog

```
┌── Grupo: Service Desk ──────────────┐
│                                     │
│  Role: itil                         │
│  Role: incident_manager             │
│                                     │
│  ┌─────────┐  ┌─────────┐          │
│  │ User A  │  │ User B  │  ...     │
│  └─────────┘  └─────────┘          │
│                                     │
│  Todos herdam as roles do grupo     │
└─────────────────────────────────────┘
```

### Importação de Users e Groups

- **External Corporate Directory** — importar de diretório existente (ex.: LDAP, Active Directory)
- **Manual** — criar diretamente na instância ServiceNow

## 2.4 Hierarquia de Roles (Role Inheritance)

Roles podem herdar permissões de outras roles, agrupando capacidades relacionadas.

```
        ┌──────────────────────┐
        │    catalog_admin     │
        └──────┬───────────────┘
               │ contains
        ┌──────┴───────────────┐
        │                      │
  ┌─────┴─────┐   ┌───────────┴───────┐
  │  catalog   │   │ user_criteria_admin│
  └────────────┘   └───────────────────┘

  Atribuir catalog_admin = herda permissões
  de catalog + user_criteria_admin
```

\begin{tipbox}
\textbf{Best Practice:} Atribua roles a \textbf{groups} em vez de a users individuais. Isso facilita a manutenção quando users mudam de posição ou responsabilidades. Basta adicionar/remover users do group.
\end{tipbox}

### Regra importante sobre remoção de roles

\begin{warnbox}
Roles atribuídas a um group \textbf{não podem ser removidas diretamente} do record de um user. Para revogar uma role, é necessário \textbf{remover o user do group} que possui a role.
\end{warnbox}

### Diferença: Role (ServiceNow) vs. Job Title (Empresa)

| Contexto | Significado |
|---|---|
| **Empresa** | Posição: Project Manager, Developer, etc. |
| **ServiceNow** | Define capacidades do user dentro da plataforma |

## 2.5 Self-Service Users

Users sem roles atribuídas que podem fazer login e realizar ações comuns:

- Visualizar dashboards
- Acessar o Service Catalog
- Ler Knowledge Articles
- Responder surveys

O acesso é determinado pelo que o System Administrator configurou como disponível sem restrições de role.

## 2.6 Impersonation

### O que é?

Ferramenta que permite ao admin **simular o acesso e interações de outro user** para testing e troubleshooting.

### Fluxo de Impersonation

```
Admin faz login
      |
      v
Seleciona "Impersonate User"
      |
      v
Escolhe o user-alvo
      |
      v
Visualiza a plataforma com as mesmas:
  - Applications
  - Modules
  - Data
do user impersonado
      |
      v
Testa e valida permissões/workflows
      |
      v
Retorna ao próprio perfil de admin
```

### Limitações da Impersonation

| Limitação | Detalhe |
|---|---|
| Roles app-specific (ex.: HR Admin, Security Incident Response Admin) | Não ganha acesso a features protegidas por esse role a menos que já tenha as permissões |
| Módulos fora do scope do user | Não pode visualizar |
| Alterar senha de users com roles admin app-specific | **Não permitido** |
| Impersonar users com admin role (para quem tem apenas impersonator role) | **Não permitido** |

### Role: Impersonator

\begin{infobox}
O role \texttt{impersonator} permite impersonar outros users para testing e visibilidade, mas \textbf{não permite impersonar users com o role admin}.
\end{infobox}

\newpage

# 3. Interfaces da Plataforma

## 3.1 Workspaces, Portals e Interfaces

A plataforma oferece múltiplas formas de interação, adaptadas a diferentes roles e departamentos:

| Método | Descrição | Público-Alvo |
|---|---|---|
| **Workspaces** | Interfaces configuráveis para gerenciar workflows | Agents, Admins |
| **Portals** | Portais centralizados para acesso a serviços | Employees, Customers |
| **Interfaces** | Experiências intuitivas para diferentes roles | Todos |

## 3.2 Service Operations Workspace (SOW)

Interface unificada para gerenciar múltiplos **ITSM workflows**. Hub central para o ciclo de vida de task records.

### Funcionalidades Principais

```
Service Operations Workspace
      |
      ├── Overview do dia
      │   ├── Assignments
      │   ├── Outages
      │   ├── Service Announcements
      │   └── Tasks
      |
      ├── Gerenciamento de Incidents
      │   ├── Criar incidents
      │   ├── Acessar incidents relacionados
      │   └── Interações recentes
      |
      ├── Priorização
      │   ├── SLAs (Service Level Agreements)
      │   ├── Priority levels
      │   └── Urgency
      |
      ├── Colaboração
      │   ├── On-call experts
      │   └── Comunicação direta com requesters
      |
      └── Task Records
          ├── Incidents
          ├── Requests
          └── Walk-ups
```

## 3.3 Employee Center

Portal centralizado para atender necessidades internas dos funcionários em múltiplos departamentos (HR, IT, Legal).

### Características

- Incluído como **aplicação padrão** para todos os clientes ServiceNow
- **One-stop shop** para acessar serviços e informações
- Opções configuráveis
- Páginas de portal customizáveis
- Workflows integrados
- Páginas curadas para tópicos populares

### Employee Center Pro

Disponível como:

- Standalone offering
- Parte dos pacotes HR Service Delivery: Professional ou Enterprise

\newpage

# 4. Labs Práticos do Módulo

## Lab 1: Granting Access e Impersonation

**Habilidades praticadas:**

1. Conceder acesso a uma aplicação (atribuir roles)
2. Impersonar outros users para validar permissões

## Lab 2: Explore the Modernized Work Experience

**Objetivo:** Familiarizar-se com a instância baseline, incluindo a aplicação ITSM e outras ferramentas fundamentais.

## Lab 3: Working with Incident Records

**Habilidades praticadas em três ambientes:**

1. **Core Platform Environment** — gerenciar incidents
2. **Workspace** — explorar interface streamlined
3. **Employee Center** — revisar incidents do ponto de vista do employee

```
Core Platform  ──>  Workspace  ──>  Employee Center
(criar/gerenciar)  (interface     (visão do
                    streamlined)   employee)

  Fluxo completo de um incident
  visto por diferentes ferramentas
```

\newpage

# 5. Knowledge Check — Módulo 1

## Pergunta 1: Quais são algumas formas de interagir com a plataforma ServiceNow?

**Resposta:**

- Workspaces
- Service Catalog
- Dashboards
- Lists
- Forms
- Knowledge Bases

Cada ferramenta é desenhada para ajudar a navegar e trabalhar eficientemente na plataforma.

## Pergunta 2: Quais são algumas features do Employee Center?

**Resposta:**

- Opções configuráveis
- Páginas de portal customizáveis
- Workflows integrados
- Páginas curadas para tópicos populares

\newpage

# 6. Resumo do Módulo 1

```
MÓDULO 1: MODERNIZED WORK EXPERIENCE
═══════════════════════════════════════

1. ServiceNow = Cloud-based aPaaS
   └── AI-powered, unified data model, 367+ integrations

2. Tudo é Record dentro de Table
   └── Incident Table (ITSM), HR Case Table (HRSD),
       User/Group Tables (shared)

3. Personas e Acesso
   ├── System Admin (admin) — acesso amplo com restrições
   ├── Specialized Admins — área específica
   ├── Process Users — ITIL, approver
   ├── Approvers — apenas aprovação
   └── Requesters/Self-Service — sem roles

4. Role Management
   ├── Role Inheritance (hierarquia)
   ├── Assign roles to GROUPS (best practice)
   └── Remoção: remover user do group

5. Impersonation
   ├── Simular acesso de outro user
   ├── Limitações de segurança
   └── Impersonator role ≠ admin access

6. Interfaces
   ├── Service Operations Workspace (agents)
   ├── Employee Center (employees)
   └── Core Platform (admins)
```

\begin{infobox}
\textbf{Próximo passo:} Módulo 2 — Explore the Power of the ServiceNow Platform
\end{infobox}
