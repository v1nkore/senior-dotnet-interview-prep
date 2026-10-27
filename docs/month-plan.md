# Обязательный план на один месяц: Senior .NET + Applied AI

Период: 30 календарных дней с 27 октября 2026. Объём: 24 учебных дня по 4 часа, 4 дня восстановления и 2 резервных дня для реальных интервью, болезни или отставания. Всего — 96 обязательных учебных часов.

Цель месяца — пройти и проверить всю карту, закрыть главные пробелы, собрать работающий AI-вертикальный срез и начать реальные собеседования. Месяц не гарантирует одинаково глубокое владение всеми 20 блоками: закреплённой считается только тема, подтверждённая повторным ответом и практикой.

## Ежедневный режим — 4 часа

| Время | Работа |
|---:|---|
| 60 минут | Слепое интервью: core + минимум один AI-вопрос со второго дня |
| 75 минут | Главный core-блок дня: теория, код, SQL или диагностика |
| 75 минут | `AiAssistantLab` или интеграционная практика текущей недели |
| 30 минут | Повтор 1/3/7, фиксация `S/Q/H/N`, ошибки и план следующего дня |

Распределение 96 часов: 24 часа интервью, 34 часа core .NET, 28 часов Applied AI, 10 часов повторов, метрик и итоговой проверки. AI является обязательной частью общей программы, а не факультативом.

## Неделя 1 — фундамент приложения и LLM

### Core

- C# runtime: equality, hashing, изменяемые ключи, boxing, GC и аллокации;
- async/concurrency: cancellation, locks, `TaskCompletionSource`, race conditions;
- ASP.NET Core: DI lifetimes, pipeline, `HttpClientFactory`, background workers;
- EF Core/SQL: запросы, индексы, планы, concurrency и keyset pagination;
- HTTP/gRPC: контракты, deadline, streaming и совместимость.

### AI

- вероятностная природа LLM, tokens и context window;
- роли инструкций, prompt templates и версии промптов;
- выбор модели по качеству, latency, стоимости и данным;
- provider abstraction в .NET;
- structured output по JSON Schema и валидация.

### Результат недели

`AiAssistantLab` принимает запрос, вызывает модель через абстракцию, возвращает проверенный типизированный ответ и фиксирует модель, prompt version, latency и token usage. В конце — смешанное часовое интервью и первый пересчёт метрик.

## Неделя 2 — архитектура, надёжность и RAG

### Core

- SOLID и выбор паттерна по проблеме;
- Clean Architecture, DDD, CQRS и границы транзакций;
- Outbox/Inbox, Saga, retry, Circuit Breaker и неопределённый внешний side effect;
- RabbitMQ/Kafka: маршрутизация, ordering, consumer groups и backpressure;
- Redis и тестирование: cache-aside, stampede, Testcontainers и race-тесты.

### AI

- ingestion и повторная индексация документов;
- chunking, overlap, embeddings и metadata;
- PostgreSQL + `pgvector`;
- full-text, vector и hybrid retrieval;
- reranking, citations, freshness и ACL до retrieval.

### Результат недели

Работает вертикальный срез `ingestion → retrieval → structured answer with citations`. Тест доказывает, что пользователь не получает чужие документы. В конце — system design RAG-сервиса и повтор слабых тем первой недели.

## Неделя 3 — эксплуатация и агенты

### Core

- Docker и Kubernetes: image/container, probes, resources, Pending, storage, StatefulSet, NetworkPolicy и autoscaling;
- CI/CD: единый артефакт, миграции, blue-green/canary, rollback и блокировка деплоев;
- производительность: GC, allocation profiling, pools, contention и connection pool;
- observability: logs, metrics, traces, SLI/SLO и диагностика;
- security, сети и Linux: JWT/OIDC, CSRF/XSS, webhook security, DNS/TCP/TLS и контейнерная диагностика.

### AI

- tool calling и валидация схемы инструмента;
- workflow против автономного агента;
- состояние, память, лимит шагов и восстановление;
- timeout, retry и idempotency tool call;
- MCP и границы его ответственности;
- least privilege и human approval для опасных действий.

### Результат недели

В `AiAssistantLab` есть read-only tool и изменяющее состояние действие с подтверждением, идемпотентностью и audit trail. Ошибка или повтор доставки не создаёт второй side effect. В конце — сценарий сбоя агента и смешанное интервью.

## Неделя 4 — качество, безопасность и собеседования

### Core

- алгоритмы и коллекции в timed-режиме;
- два полных system-design сценария;
- behavioral: минимум четыре STAR-истории;
- delivery/legacy: feature flags, strangler, совместимость контрактов;
- целевые повторы всех ответов `H/N` и нестабильных `Q`.

### AI

- golden dataset и baseline;
- retrieval-метрики, groundedness и task success;
- детерминированные проверки и ограничения LLM-as-judge;
- eval-регрессии в CI;
- traces, token/cost/latency budgets, caching и fallback;
- prompt injection, indirect injection, data exfiltration, PII и audit;
- проверка кода, созданного coding agent.

### Результат недели

`AiAssistantLab` имеет eval-набор, CI-порог регрессии, traces и тесты безопасности. Проводятся два полных интервью по 60 минут и финальное двухчасовое: код/SQL, backend design и AI system design.

## Контрольные точки

| День | Что проверяем |
|---:|---|
| 1 | Диагностика Applied AI и фиксация исходного уровня |
| 6 | LLM API + structured output, обновление метрик |
| 12 | RAG vertical slice и проверка ACL |
| 18 | Tool calling/MCP, идемпотентность и human approval |
| 24 | Evals, tracing, AI security и готовность проекта |
| 30 | Итоговое смешанное интервью и новый процент готовности |

## Обязательные артефакты к концу месяца

- работающий `AiAssistantLab` с инструкцией запуска;
- минимум 20 eval-примеров, включая граничные и вредоносные;
- два timed-решения алгоритмических задач;
- две SQL-задачи и один конкурентный integration-тест;
- два system-design разбора, один из них — AI-система;
- четыре готовые STAR-истории;
- журнал ежедневных `S/Q/H/N`, повторов и изменений готовности;
- начатые реальные отклики и собеседования, не дожидаясь завершения месяца.

## Правило при отставании

Не удаляем обязательный блок и не компенсируем пропуск чтением без практики. Сначала используем два резервных дня, затем сокращаем объём дополнительной реализации внутри проекта, сохраняя проверяемый вертикальный срез, интервью и критерии безопасности.
