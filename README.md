# click-event-utility

Função utilitária que realiza um evento de click nas coordenadas `x` e `y` informadas.

```js
function clickOnElement(x, y) {
  const element = document.elementFromPoint(x, y);
  if (!element) return;

  const rect = element.getBoundingClientRect();
  const event = new MouseEvent("click", {
    view: window,
    bubbles: true,
    cancelable: true,
    clientX: rect.left + x,
    clientY: rect.top + y,
  });

  element.dispatchEvent(event);
}
```
