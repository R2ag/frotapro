# 🚛 FrotaPro

> Plataforma SaaS Enterprise para Gestão Inteligente de Transportes e Frotas.

O **FrotaPro** é um sistema SaaS multi-tenant desenvolvido para transportadoras e empresas com frota própria, permitindo controle completo de:

- 🚚 Viagens
- 👨‍✈️ Motoristas
- 🚛 Veículos
- ⛽ Abastecimentos
- 💰 Despesas e Receitas
- 📊 Indicadores financeiros
- 📈 Analytics operacional

Construído com arquitetura escalável e preparada para ambientes enterprise.

---

# 🏗️ Arquitetura

O projeto segue:

- ✅ DDD (Domain-Driven Design)
- ✅ Clean Architecture
- ✅ Monólito Modular (Microservices Ready)
- ✅ Multi-Tenant (Shared Database + Tenant ID)
- ✅ Cloud Ready
- ✅ Observabilidade integrada

---

# 🧱 Stack Tecnológica

## 🔹 Backend

- Java 21
- Spring Boot 4.0.2
- Spring Security + JWT
- Spring Data JPA
- PostgreSQL
- Flyway
- Redis
- Hibernate Envers
- OpenAPI (Swagger)
- Micrometer + Prometheus

## 🔹 Frontend

- Angular
- TypeScript
- Angular Material
- Chart.js / ngx-charts

## 🔹 Infraestrutura

- Docker
- Docker Compose
- MinIO (Storage)
- Preparado para Kubernetes
---

# 🔐 Multi-Tenancy

O FrotaPro utiliza o modelo:

**Single Database + Shared Schema + Tenant ID**

Cada registro possui:

```sql
empresa_id UUID NOT NULL
```

O tenant é resolvido via JWT e aplicado automaticamente nos filtros Hibernate.

---

# 📂 Estrutura do Projeto (Backend)
```
br.com.rlag.frotapro
│
├── application
│   ├── usecase
│   ├── dto
│   └── mapper
│
├── domain
│   ├── model
│   ├── repository
│   ├── service
│   └── exception
│
├── infrastructure
│   ├── persistence
│   ├── security
│   ├── config
│   ├── storage
│   └── messaging
│
└── interfaces
    └── rest

```

# 📊 Módulos do Sistema

## 🔹 IAM (Identidade e Acesso)

- Empresas
- Usuários
- Perfis
- Permissões
- Planos e Assinaturas

## 🔹 Operações

- Viagens
- Motoristas
- Veículos
- Clientes

## 🔹 Financeiro

- Despesas
- Adiantamentos
- Receitas
- Relatórios

## 🔹 Combustível

- Abastecimento
- ARLA
- Custo por KM
- Consumo médio

## 🔹 Analytics

- Dashboard operacional
- Indicadores de lucro
- Ranking de motoristas
- Performance da frota

---

# 🚀 Como Executar Localmente

## 1️⃣ Subir infraestrutura
```
docker-compose up -d
```

Isso iniciará:

- PostgreSQL
- Redis
- MinIO

## 2️⃣ Rodar a aplicação

```
./mvnw spring-boot:run
```

ou

```
mvn clean install
java -jar target/frotapro.jar
```

## 3️⃣ Acessar documentação

Swagger:
```
http://localhost:8080/swagger-ui.html
```

Actuator:
```
http://localhost:8080/actuator
```
---

# 🔎 Observabilidade

- Métricas: /actuator/prometheus
- Logs estruturados
- Correlation ID por requisição
- Preparado para Grafana

---

# 🔄 Roadmap

## MVP

- Autenticação
- CRUD básico
- Dashboard inicial

## Fase 2

- Upload de comprovantes
- Relatórios avançados
- Controle de consumo

## Fase 3

- Microserviços
- API Gateway
- Event-driven architecture
- Billing automático

---

# 🔐 Segurança

- JWT com empresa_id
- RBAC (Role Based Access Control)
- Auditoria com Envers
- Rate limiting com Redis

---

# 📌 Diferenciais

- Cálculo automático de lucro por viagem
- Custo por KM em tempo real
- Visão 360° da frota
- Arquitetura enterprise desde o início

---

# 🏢 Licença

Proprietary Software – FrotaPro

---

# 🏢 Sobre a FrotaPro

FrotaPro é um produto desenvolvido e mantido por RLAG.

© 2026 FrotaPro. Todos os direitos reservados.


--- 
