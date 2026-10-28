# Метрики подготовки

Обновлено: 28 октября 2026.

Это рабочая оценка по ответам в диалоге, практическим задачам и учебным проектам. Она показывает состояние подготовки, а не вероятность оффера. Категории: `S` — самостоятельно; `Q` — верно после уточнения формулировки; `H` — с существенной подсказкой; `N` — тема пока не разобрана.

## Сводка

| Показатель | Текущее значение |
|---|---:|
| Позиция во времени | 10-й календарный день из 30 |
| Завершённые учебные сессии | 8 из 24 |
| Остаток после 28 октября | 20 календарных дней |
| Блоков в полной обязательной карте | 20 |
| Блоков затронуто полностью или частично | 13 из 20 (65%) |
| Размеченных ответов за 23–28 октября | 106 |
| `S` — самостоятельно | 41 (38,7%) |
| `Q` — после уточнения | 39 (36,8%) |
| `H` — с подсказкой | 25 (23,6%) |
| `N` — пока не разобрано | 1 (0,9%) |
| Самостоятельно или после небольшого уточнения (`S + Q`) | 80 (75,5%) |
| Готовность по исходной core .NET-карте | около 45% |
| Готовность по расширенной цели .NET + AI | требует первого AI-диагностического интервью |
| Applied AI | обязательный блок, ещё не оценён |

По количеству охвата темп выше линейного: за треть запланированных учебных сессий затронуто 65% карты. По качеству есть риск: доля самостоятельных ответов снизилась до 39%, потому что 27–28 октября целенаправленно проверялись новые runtime- и async-детали. Это не откат, но до повтора они не считаются закреплёнными. За 27–28 октября точно зафиксировано около 4 часов 2 минут голосовой подготовки: 2 часа 7 минут 27 октября и 1 час 55 минут 28 октября. По более ранним дням часы остаются неполными.

Новые контрольные точки: 27 октября — 10 (`S1/Q5/H4`), 28 октября — 14 (`S4/Q5/H5`). Всего добавлено 24 оценённых ответа.

Последний показатель — экспертная оценка покрытия и устойчивости знаний. Он не складывается напрямую из числа вопросов: тема считается закреплённой только после повторного самостоятельного ответа в другой день и применения в коде, SQL или проектировании.

## Состояние блоков

| Блок | Текущий уровень | Что уже получается | Что повторить |
|---|---|---|---|
| C# / runtime | средний | value/reference semantics, equality/hashing, поколения GC, LINQ deferred execution | roots/finalization, closures, `Span`/`Memory`, variance без подсказки |
| Async / concurrency | средний+ | `Task.WhenAll`, `Interlocked`, `SemaphoreSlim`, bounded parallelism, I/O против CPU | `ConfigureAwait`, `AsyncLocal`, `ValueTask`, `volatile`, `ConcurrentDictionary`, race-тесты |
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
| Redis | базовый | TTL, lease, распределённый семафор и token bucket после разбора | primitives, Lua без подсказки, invalidation, cache stampede |
| Алгоритмы | требует проверки | есть репозиторий задач | провести timed-задачи и оценить сложность |
| Behavioral | не оценено | — | подготовить и проверить STAR-истории |
| Сети / Linux | не оценено системно | отдельные знания по HTTP, DNS и пулам | отдельный диагностический блок |
| Delivery / legacy | базовый–средний | expand-contract, rollback, безопасный релиз | feature flags, strangler, совместимость контрактов |
| Applied AI | не оценено | общая backend-база применима | LLM API, RAG, agents/MCP, evals, AI security |

## История срезов

| Дата | Количественный срез | Что изменилось |
|---|---|---|
| 4 октября | 5 из 17 разделов; 3 из 14 проектов | Исходный чек-лист до текущего цикла. |
| 19 октября | Учебный день 1 | Начат 30-дневный цикл; первый baseline по надёжной обработке платежа. |
| 22 октября | Первый структурированный качественный срез | Зафиксированы SQL/EF Core, reliability, observability и начало Kubernetes. |
| 26 октября | 6 сессий; 82 ответа: `S36/Q29/H16/N1` | Kubernetes расширен до NetworkPolicy; добавлены CI/CD, testing, performance, gRPC, system design, security и ASP.NET Core/C#. |
| 27 октября | 7 сессий; 92 ответа: `S37/Q34/H20/N1` | Разобраны equality/hashing, GC, resources, closures, buffers, variance, events и async; Applied AI добавлен как обязательный финальный блок. |
| 28 октября | 8 сессий; 106 ответов: `S41/Q39/H25/N1`; 13 из 20 блоков | Углублены `ConfigureAwait`, `AsyncLocal`, `Task.WhenAll`, `ValueTask`, `Task.Run`, ограничение параллелизма, Redis semaphore, `Interlocked` и `volatile`. |

## Ближайшие повторы

### Через 1 день

- `ConfigureAwait(false)`: UI против ASP.NET Core и роль `SynchronizationContext`.
- `AsyncLocal`: один статический контейнер и разные значения в `ExecutionContext`.
- `ValueTask`: условие выгоды и правило однократного `await`.
- `volatile`: видимость/порядок против атомарности.
- Redis: локальный и распределённый concurrency limit, семафор против token bucket.
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

Продолжить с вопроса о `ConcurrentDictionary.GetOrAdd` и побочных эффектах value factory, затем завершить C# concurrency и перейти к SOLID/Clean Architecture/CQRS. После этого — Redis, алгоритмы и behavioral, затем первое строго таймированное смешанное интервью.

Работать по обязательному [месячному плану](month-plan.md). Сначала завершить 18 учебных дней технической части; AI-диагностику и `AiAssistantLab` начать на 19-й учебный день. После диагностики зафиксировать отдельный baseline Applied AI и общую готовность к расширенной цели.

