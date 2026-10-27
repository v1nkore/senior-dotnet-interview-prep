# Метрики подготовки

Обновлено: 27 октября 2026.

Это рабочая оценка по ответам в диалоге, практическим задачам и учебным проектам. Она показывает состояние подготовки, а не вероятность оффера. Категории: `S` — самостоятельно; `Q` — верно после уточнения формулировки; `H` — с существенной подсказкой; `N` — тема пока не разобрана.

## Сводка

| Показатель | Текущее значение |
|---|---:|
| Позиция во времени | 9-й календарный день из 30 |
| Завершённые учебные сессии | 6 из 24; сессия 27 октября — текущая |
| Остаток после 27 октября | 21 календарный день |
| Блоков в полной обязательной карте | 20 |
| Блоков затронуто полностью или частично | 13 из 20 (65%) |
| Ретроспективно размеченных ответов за 23–26 октября | 82 |
| `S` — самостоятельно | 36 (44%) |
| `Q` — после уточнения | 29 (35%) |
| `H` — с подсказкой | 16 (20%) |
| `N` — пока не разобрано | 1 (1%) |
| Самостоятельно или после небольшого уточнения (`S + Q`) | 65 (79%) |
| Готовность по исходной core .NET-карте | около 45% |
| Готовность по расширенной цели .NET + AI | требует первого AI-диагностического интервью |
| Applied AI | обязательный блок, ещё не оценён |

По количеству охвата темп выше линейного: за первую четверть учебных сессий затронуто 65% карты. По качеству темп ближе к плановому, но с риском: самостоятельно дано меньше половины ответов, а пройденные темы ещё нужно подтвердить повтором и практикой. Точные часы занятий ранее не фиксировались, поэтому выполнение нормы 4 часа в день пока нельзя подтвердить.

Последний показатель — экспертная оценка покрытия и устойчивости знаний. Он не складывается напрямую из числа вопросов: тема считается закреплённой только после повторного самостоятельного ответа в другой день и применения в коде, SQL или проектировании.

## Состояние блоков

| Блок | Текущий уровень | Что уже получается | Что повторить |
|---|---|---|---|
| C# / runtime | средний | value/reference semantics, record equality, LINQ deferred execution | boxing, изменяемые ключи Dictionary, GC internals |
| Async / concurrency | средний | cancellation, lock и I/O, условное удаление, базовая синхронизация тестов | TaskCompletionSource без подсказки, детерминированные race-тесты |
| ASP.NET Core / DI | средний+ | lifetimes, HttpClientFactory, middleware order, exception handling | scope в BackgroundService, service-provider anti-pattern |
| EF Core / SQL | средний+ | агрегации, N+1, AsNoTracking, ExecuteUpdate, оконные функции после разбора | LEFT JOIN и место фильтров, индексы, планы, keyset pagination |
| Надёжность / брокеры | средний+ | идемпотентность, Outbox/Inbox, retry, Saga, redelivery | неопределённость внешнего side effect, Kafka/RabbitMQ routing |
| Kubernetes | базовый–средний | Pod, Deployment, Service, probes, ресурсы, Ingress, базовая диагностика | Pending, PVC/StatefulSet, ResourceQuota, NetworkPolicy, autoscaling |
| CI/CD / delivery | средний | единый артефакт, rollback, blue-green, совместимые миграции | конкурентные деплои, секреты, самостоятельное сравнение стратегий |
| Тестирование | средний | unit/integration, реальная PostgreSQL, структура конкурентного теста | Testcontainers, test doubles, размещение контрольной точки гонки |
| Производительность | средний | поиск bottleneck, lock contention, connection pool, большие выборки | GC-метрики, allocation profiling, keyset pagination |
| gRPC | средний+ | выбор gRPC, Protobuf compatibility, cancellation, deadline | streaming/backpressure и диагностика |
| System design | средний | очередь, Outbox, workers, ordering, backpressure, status API | distributed rate limiting, exactly-once внешнего вызова |
| Security | базовый–средний | object-level authorization, webhook flow, различие cookie/header | HMAC/replay, antiforgery, secrets encryption |
| Observability | средний | trace/span, context propagation, базовая локализация задержек | самостоятельный выбор метрик и алертов |
| SOLID / Clean / CQRS | требует проверки | есть проектная база | провести отдельное интервью и code review |
| Redis | требует проверки | TTL/cache stampede частично разобраны на своём кэше | Redis primitives, invalidation, distributed cache |
| Алгоритмы | требует проверки | есть репозиторий задач | провести timed-задачи и оценить сложность |
| Behavioral | не оценено | — | подготовить и проверить STAR-истории |
| Сети / Linux | не оценено системно | отдельные знания по HTTP, DNS и пулам | отдельный диагностический блок |
| Delivery / legacy | базовый–средний | expand-contract, rollback, безопасный релиз | feature flags, strangler, совместимость контрактов |
| Applied AI | не оценено | общая backend-база применима | LLM API, RAG, agents/MCP, evals, AI security |

## Что изменилось после 22 октября

- Kubernetes пройден от probes до NetworkPolicy, включая ресурсы, Ingress, PVC, StatefulSet, Job/CronJob и autoscaling.
- Разобран полный CI/CD-поток, blue-green и совместимая миграция схемы.
- Пройдены unit/integration testing, Testcontainers и детерминированный тест гонки через управляемый барьер.
- Разобраны performance-сценарии: contention, GC/аллокации, большие выборки, keyset pagination и connection pool.
- Пройдены основы gRPC, system design сервиса уведомлений и базовый API security.
- Начат блок C# / ASP.NET Core: DI lifetimes, HttpClientFactory, middleware, LINQ, boxing и equality.

## Ближайшие повторы

### Через 1 день

- Kubernetes: Pending, PVC против emptyDir, StatefulSet, ResourceQuota и NetworkPolicy.
- Конкурентный integration-тест: где ставить барьер и что проверять в PostgreSQL.
- Внешний вызов после успешной отправки и падение до фиксации результата.
- CSRF, antiforgery, подпись webhook и защита от replay.
- Boxing и изменяемый ключ Dictionary.

### Через 3 дня

- Blue-green против rolling/canary и expand-contract для базы.
- Keyset pagination и диагностика connection pool.
- Protobuf reserved fields, deadline и cancellation.
- DI scopes в singleton/background worker.

### Через 7 дней

- Полное смешанное интервью на 60 минут без подсказок.
- Одна задача на код или SQL.
- Один system-design сценарий.
- Повторная разметка `S/Q/H/N` и обновление процента готовности.

## Следующий шаг

Продолжить с вопроса про изменяемый ключ `Dictionary`, затем пройти SOLID/Clean Architecture/CQRS, Redis, алгоритмы и behavioral. После этого провести первое строго таймированное смешанное интервью, которое станет базовой контрольной точкой.

Работать по обязательному [месячному плану](month-plan.md). Сначала завершить 18 учебных дней технической части, начиная с изменяемого ключа `Dictionary`; AI-диагностику и `AiAssistantLab` начать на 19-й учебный день. После диагностики зафиксировать отдельный baseline Applied AI и общую готовность к расширенной цели.

