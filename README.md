# neo-design-patterns-hw-08

## 📚 Домашнє завдання — Патерн Спостерігач (Observer)

Цей проєкт демонструє використання патерну **Спостерігач (Observer)** у генераторі документа для відслідковування процесу рендерингу окремих елементів.

---

## 📐 Структура

- `RenderEventPublisher.ts` — статичний клас-посередник, який розсилає події всім підписникам.
- `interfaces/RenderEventSubscriber.ts` — інтерфейс підписника.
- `interfaces/RenderContext.ts` — тип об'єкта події, який передається підписникам.
- `subscribers/` — каталог з реалізацією підписників:
  - `RenderLoggerSubscriber.ts`
  - `SummaryCollector.ts`
  - `PerformanceSubscriber.ts`

---

## 🧩 Як реалізовано Observer

Кожен елемент документа (`Section`, `Paragraph`, `List`) після рендерингу створює об'єкт `RenderContext` і викликає:

```ts
RenderEventPublisher.notify(context);
```
