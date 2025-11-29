## Обзор. Компонент Button (Кнопка)

### Оглавление

- [Назначение](#назначение)
- [Внешний вид](#внешний-вид)
- [Конфигурации](#конфигурации)
- [Код кнопки. Типовое применение в React](#код-кнопки-типовое-применение-в-react)
- [Паттерны использования](#паттерны)
- [Анти-паттерны использования](#анти-паттерны)

## Назначение

Компонент Button (кнопка) — отдельная кнопка для выполния действия одним нажатием. Кнопки должны обеспечивать интуитивно понятный и логичный интерфейс пользователя при размещении в модальных окнах, формах, карточках, панелях инструментов и других элементах.

## Внешний вид

Кнопки имеют форму прямоугольника с закругленными углами (за исключением [типа](./2-btn-types.md) `borderless`), текст и иконку или бейдж слева или справа от текста. Ширина кнопки определяется количеством текста и фиксированными отступами.<br>

Для подбора оптимальной кнопки и задания ей стиля предусмотрены:

- три [размера](/md/4-btn-sizes.md): `large`, `medium`, `small`;
- четыре [типа](/md/2-btn-types.md): `primary`, `secondary`, `tertiary`, `borderless`;
- шесть [состояний](/md/3-btn-states.md): `enabled`, `hover`, `active`, `disabled`, `pressed`, `loading`;
- иконка или бейдж слева или справа от текста (опция).

## Конфигурации

<details open>
  <summary>Отдельная кнопка</summary><br>
  <a target="_blank" rel="noopener noreferrer" href="../img/1-single-btn.png"><img src="../img/1-single-btn.png" alt="Отдельная кнопка" style="max-width: 650px;"></a>
</details>

<details>
  <summary>Кнопки по состояниям и типам</summary><br>
  <a target="_blank" rel="noopener noreferrer" href="../img/1-conf-types-states-btn.png"><img src="../img/1-conf-types-states-btn.png" alt="Кнопки по состояниям и типам" style="max-width: 650px;"></a>
</details>

<details>
  <summary>Кнопки с текстом и иконкой или бейджем </summary><br>
  <a target="_blank" rel="noopener noreferrer" href="../img/1-conf-icon-badge-btn.png"><img src="../img/1-conf-icon-badge-btn.png" alt="Кнопки с текстои и иконкой или бейджем" style="max-width: 650px;"></a>
</details>

## Код кнопки. Типовое применение в React

<details>
  <summary><b><em>Для разработчиков</em></b></summary><br>
  
  
  Кнопка создаётся тегом <b><</b><b>button></b> и после рендеринга по умолчанию получает глобальный атрибут `tabindex="0"`.

В особом случае при создании кнопки без текста с иконкой или бейджем рекомендуется задать атрибут `VisuallyHidden` с кратким описанием для ассистивных технологий — `Уточнить детали у дизайнера макета и разработчика`.

</details>

<details open>
  <summary>Типовое применение в React</summary><br>

```JSX
// Кнопка типа "primary" с обработкой состояния loading (загрузка)
<Button kind="primary" vertSize="40" loading loadingMessage="Проверяем данные">Продолжить</Button>

// Кнопка типа "secondary"
<Button kind="secondary">Отменить</Button>

// Кнопка типа "tertiary"
<Button kind="tertiary">QR-код</Button>

// Кнопка типа "borderless"
<Button kind="borderless">Подробнее</Button>
```

</details>

[Вверх](#оглавление)
<br>

## Паттерны

### 1. Кнопка для дискретного действия

:star: Избыточное количество кнопок может нарушать визуальное восприятие.

<details open>
  <summary>Кнопка для дискретного действия</summary><br>
  <a target="_blank" rel="noopener noreferrer" href="../img/1-conf-1-pattern-btn.png"><img src="../img/1-conf-1-pattern-btn.png" alt="Кнопка для дискретного действия" style="max-width: 650px;"></a>
</details>

[Анти-паттерн](#1-избыточное-количество-кнопок-интерфейса)

### 2. Текст одинаковой длины для кнопок переключения

:star: В кнопках переключения следует использовать текст одинаковой длины для обоих состояний.

<details>
  <summary>Текст одинаковой длины</summary><br>
  <a target="_blank" rel="noopener noreferrer" href="../img/1-conf-2-pattern-btn.png"><img src="../img/1-conf-2-pattern-btn.png" alt="Текст одинаковой длины для кнопок переключения" style="max-width: 650px;"></a>
</details>

[Анти-паттерн](#2-текст-разной-длины-для-кнопок-переключения)

[Вверх](#оглавление)<br>

## Анти-паттерны

### 1. Избыточное количество кнопок интерфейса

:star: Низкоприоритетные действия необходимо размещать в меню или в виде кнопок с иконкой без текста.

<details open>
  <summary>Избыточное количество кнопок интерфейса</summary><br>
  <a target="_blank" rel="noopener noreferrer" href="../img/1-conf-1-antipattern-btn.png"><img src="../img/1-conf-1-antipattern-btn.png" alt="Избыточное количество кнопок интерфейса" style="max-width: 650px;"></a>
</details>

[Паттерн](#1-кнопка-для-дискретного-действия)

### 2. Текст разной длины для кнопок переключения

:star: Длина текста в кнопке переключения не должна резко изменяться при смене состояния.

<details>
  <summary>Текст разной длины кнопок переключения</summary><br>
  <a target="_blank" rel="noopener noreferrer" href="../img/1-conf-2-antipattern-btn.png"><img src="../img/1-conf-2-antipattern-btn.png" alt="Текст разной длины кнопок переключения" style="max-width: 650px;"></a>
</details>

[Паттерн](#2-текст-одинаковой-длины-для-кнопок-переключения)

[Вверх](#оглавление) | [К содержанию](../README_Buttons.md)
