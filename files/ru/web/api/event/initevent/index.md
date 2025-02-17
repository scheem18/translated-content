---
title: Event.initEvent()
slug: Web/API/Event/initEvent
translation_of: Web/API/Event/initEvent
---
{{ ApiRef("DOM") }}{{deprecated_header}}

The **`Event.initEvent()`** method is used to initialize the value of an {{ domxref("event") }} created using {{ domxref("Document.createEvent()") }}.

Events initialized in this way must have been created with the {{ domxref("Document.createEvent()") }} method. This method must be called to set the event before it is dispatched, using {{ domxref("EventTarget.dispatchEvent()") }}. Once dispatched, it doesn't do anything anymore.

> **Примечание:** **Не используйте этот метод, т.к. он устаревший. (deprecated)**
>
> Вместо него используйте такой специальный конструктор событий, как {{domxref("Event.Event", "Event()")}}. Страница [Creating and triggering events](/ru/docs/Web/Guide/Events/Creating_and_triggering_events) даст больше информации о возможностях использования.

## Синтаксис

```
event.initEvent(type, bubbles, cancelable);
```

- _`type`_
  - : {{domxref("DOMString")}}, определяющая тип события.
- _`bubbles`_
  - : Is a {{jsxref("Boolean")}} deciding whether the event should bubble up through the event chain or not. Once set, the read-only property {{ domxref("Event.bubbles") }} will give its value.
- _`cancelable`_
  - : Is a {{jsxref("Boolean")}} defining whether the event can be canceled. Once set, the read-only property {{ domxref("Event.cancelable") }} will give its value.

## Пример

```
// Create the event.
var event = document.createEvent('Event');

// Create a click event that bubbles up and
// cannot be canceled
event.initEvent('click', true, false);

// Listen for the event.
elem.addEventListener('click', function (e) {
  // e.target matches elem
}, false);

elem.dispatchEvent(event);
```

## Спецификация

| Спецификация                                                                                         | Статус                           | Комментарий                                                                                  |
| ---------------------------------------------------------------------------------------------------- | -------------------------------- | -------------------------------------------------------------------------------------------- |
| {{SpecName('DOM WHATWG', '#dom-event-initevent','Event.initEvent()')}}         | {{Spec2("DOM WHATWG")}} | Начиная с {{SpecName('DOM2 Events')}} - deprecated, заменено на event constructors. |
| {{SpecName('DOM2 Events','##Events-Event-initEvent','Event.initEvent()')}} | {{Spec2('DOM2 Events')}} | Начальное определение.                                                                       |

## Browser compatibility

{{Compat}}

## Смотрите также

- The constructor to use instead of this deprecated method: {{domxref("Event.Event", "Event()")}}. More specific constructors can be used too.
