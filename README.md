# RaccoonCSS

## Podstawowa struktura strony HTML:

```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>RacconCSS</title>
</head>
<body>
    <h1>Hello</h1>
    <p>This is my first page.</p>
</body>
</html>
```

## CSS

CSS (_Cascading Style Sheets_) to język służący do stylizowania i formatowania dokumentów HTML i XML (w tym SVG i XML). Pozwala on na określenie wyglądu elementów na stronie internetowej, takich jak kolory, czcionki, układ, marginesy, tła i inne aspekty wizualne.

### Główne cele CSS:
- Oddzielenie treści od wyglądu – CSS pozwala na rozdzielenie struktury dokumentu (HTML) od jego wyglądu (CSS), co ułatwia zarządzanie i utrzymanie stron.
- Lepsza organizacja i porządek – dzięki CSS można stosować te same style do wielu stron, co zapewnia spójność wyglądu witryny.
- Responsywność – CSS pozwala dostosować wygląd strony do różnych urządzeń (np. telefony, tablety, komputery).

### Podstawowe właściwości CSS:
- `color` – ustawia kolor tekstu.
- `background-color` – określa kolor tła elementu.
- `font-size` – definiuje rozmiar czcionki.
- `margin` – ustala marginesy wokół elementu.
- `padding` – ustawia odstęp wewnętrzny, czyli przestrzeń między zawartością a krawędzią elementu.
- `width` i `height` – określają szerokość i wysokość elementu.
- `border` – dodaje ramkę wokół elementu.

## Selektory:

Selektory w CSS to mechanizm, który pozwala na wybranie i stylizowanie określonych elementów HTML na stronie. Dzięki selektorom możesz wskazać, które elementy mają być poddane danym stylom, i określić, jakie właściwości mają zostać im przypisane.

### Rodzaje selektorów CSS:

1. **Selektor elementu** (typowy selektor) - wybiera wszystkie elementy określonego typu. Przykład:
```css
p {
    color: blue;
}
```

2. **Selektor klasy** - wybiera elementy, które mają określoną klasę. Klasy są oznaczane kropką `.`. Przykład:
```css
.button {
    color: blue;
}
```

3. **Selektor identyfikatora** (ID) - wybiera element o określonym identyfikatorze. Identyfikatory są oznaczane hashtagiem (`#`). Przykład:

```css
#header {
    background-color: lightgray;
}
```

4. **Selektor atrybutu** - wybiera elementy, które mają określony atrybut. Przykład:

```css
input[type="text"] {
    border: 2px solid blue;
}
```
