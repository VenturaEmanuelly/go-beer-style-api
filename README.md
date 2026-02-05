# 🍺 BeerStyle API - Go (Golang)

API de alta performance desenvolvida para recomendar o estilo de cerveja ideal com base na temperatura informada, integrada ao **Spotify** para curadoria musical automatizada. O projeto foca em princípios de **Clean Architecture**, escalabilidade e **observabilidade nativa**.

---

### 🚀 Diferenciais Técnicos

* **Clean Architecture & SOLID**: Código estruturado para ser testável, desacoplado e independente de frameworks externos.
* **Observabilidade (OpenTelemetry)**: Implementação de métricas e rastreamento distribuído via **OpenTelemetry**, integrados ao **Prometheus** e **Grafana**.
* **Resiliência com RabbitMQ**: Uso de mensageria para garantir o processamento assíncrono e a resiliência do sistema em cenários de alta carga.
* **Integração com Spotify**: Consumo dinâmico da API do Spotify para enriquecimento da regra de negócio com playlists personalizadas.

---

### 🛠️ Como Executar

1. Clone o repositório.
2. Configure seu arquivo `.env` (baseado no `.env.template`).
3. Suba o ambiente com Docker:

```bash
docker compose up -d --build

```

### 🗄️ Carga Inicial do Banco (Seed)
Como o banco inicia vazio, popule os estilos de cerveja executando:

```bash
docker exec -it postgres_db psql -U user -d mydatabase -c "INSERT INTO beer_styles (style, min_temp, max_temp) VALUES ('Weissbier', -1, 3), ('Pilsens', -2, 4), ('Weizenbier', -4, 6), ('Red ale', -5, 5), ('India pale ale', -6, 7), ('IPA', -7, 10), ('Dunkel', -8, 2), ('Imperial Stouts', -10, 13), ('Brown ale', 0, 14);"

```

### 🛠️ Ecossistema e Acessos

Serviços e URL :

API Endpoint	http://localhost:8080/temperature?q=5	

Grafana     	http://localhost:3000	 | Credenciais : admin / admin

RabbitMQ    	http://localhost:15672 | Credenciais	guest / guest

Prometheus  	http://localhost:9090

### 🧪 Stack Tecnológica
Linguagem: Go (Golang) 🐹

Banco de Dados: PostgreSQL 🐘

Mensageria: RabbitMQ 🐰

Monitoramento: Prometheus & Grafana 📊

Containerização: Docker & Docker Compose 📦


### 📊 Monitoramento e Resiliência

#### Grafana (Métricas de Performance)
Acompanhamento em tempo real da latência e volume de requisições:
<img width="940" alt="Dashboard Grafana" src="https://github.com/user-attachments/assets/9dd0607f-f7b9-4997-affe-818fca9f6d3e" />


####  RabbitMQ (Gestão de Filas)
Garantia de que nenhuma mensagem seja perdida durante picos de acesso:
<img width="780" alt="RabbitMQ Dashboard" src="https://github.com/user-attachments/assets/f648c839-d670-4599-aade-26543f642fb0" />

---




