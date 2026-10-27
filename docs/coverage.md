# Карта покрытия

Карта связывает темы интервью с практикой. Банк вопросов находится в `interview-bank.md`, а исходники — в `../projects` и `../algorithms`.

| Блок | Основная практика | Проверяемый результат |
|---|---|---|
| C# и runtime | `projects/TtlCache`, `projects/PerfLab` | память, GC, типы, аллокации, измерения |
| Async и concurrency | `projects/TtlCache`, `projects/AspNetLab` | гонки, атомарность, cancellation, backpressure |
| ASP.NET Core | `projects/AspNetLab` | pipeline, DI, ошибки, background workers |
| EF Core и SQL | `projects/EfCoreLab` | tracking, N+1, concurrency, индексы, планы запросов |
| SOLID и паттерны | `projects/SolidMap` | выбор паттерна по проблеме, компромиссы |
| DDD, Clean, CQRS | `projects/CleanLab` | границы, инварианты, зависимости, события |
| Микросервисы и брокеры | `projects/OrderFlow` | Outbox, Inbox, Saga, Kafka, идемпотентность |
| REST и gRPC | `projects/GrpcLab`, `projects/AspNetLab` | контракты, deadline, streaming, совместимость |
| Redis и кэширование | `projects/RedisLab`, `projects/TtlCache` | cache-aside, stampede, TTL, инвалидация |
| Docker, Kubernetes, CI/CD | `projects/K8sLab`, `.github/workflows/ci.yml` | Pod, Deployment, Service, probes, rollout |
| Тестирование | `projects/TestingLab` и тесты остальных проектов | unit, integration, Testcontainers, гонки |
| Производительность | `projects/PerfLab` | профилирование, BenchmarkDotNet, нагрузка |
| Наблюдаемость | `projects/ObservabilityLab`, `projects/OrderFlow` | logs, metrics, traces, propagation |
| System design | `projects/SystemDesign` | платёжный шлюз, webhooks, лента, уведомления |
| Behavioral | `projects/Behavioral` | STAR, решения, конфликты, инциденты |
| Алгоритмы и коллекции | `algorithms` | сложность, массивы, строки, списки, деревья |
| Security | банк + code review практических API | OAuth/OIDC, JWT, OWASP API, secrets, audit |
| Сети и Linux | банк + диагностика контейнеров | DNS, TCP/TLS, timeout, connection pool |
| Delivery и legacy | банк + CI + миграционные сценарии | совместимые изменения, rollback, feature flags |
| Applied AI для backend | `docs/applied-ai-track.md`, план `projects/AiAssistantLab` | LLM API, RAG, tool calling, evals, стоимость и AI security |

Тема считается закреплённой после двух самостоятельных ответов в разные дни и одного применения в коде, SQL или проектировании.

Applied AI учитывается отдельно от 19 обязательных блоков Senior .NET: он повышает рыночную широту, но отсутствие этого трека не маскирует пробелы в backend-основах.

