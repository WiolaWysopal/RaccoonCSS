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

## Model pudełkowy: 
### 1. Co to jest model pudełkowy?
Model pudełkowy (_Box Model_) w CSS określa sposób, w jaki przeglądarki interpretują i rozmieszczają elementy na stronie. Każdy element HTML traktowany jest jak prostokątne pudełko składające się z kilku warstw.

### 2. Składniki modelu pudełkowego
Każde pudełko składa się z następujących części:

1. **Content (Zawartość)** – miejsce, w którym znajduje się treść elementu (tekst, obraz, inne elementy).
2. **Padding (Wypełnienie)** – przestrzeń między zawartością a obramowaniem.
3. **Border (Obramowanie)** – linia otaczająca element, oddzielająca go od innych.
4. **Margin (Margines)** – przestrzeń wokół obramowania, oddzielająca elementy od siebie.

### Wizualizacja:

```ascii
            Margin
+-------------------------------+
|           Border              |
|  +------------------------+   |
|  |        Padding         |   |
|  |  +------------------+  |   |
|  |  |                  |  |   |
|  |  |     Content      |  |   |
|  |  |                  |  |   |
|  |  +------------------+  |   |
|  |                        |   |
|  +------------------------+   |
|                               |
+-------------------------------+
```

### Pozycjonowanie:

1. `static` (domyślne pozycjonowanie):
- Jest to domyślne ustawienie dla wszystkich elementów HTML.
- Elementy są umieszczane w dokumencie według normalnego przepływu strony.
- Nie można zmieniać ich położenia za pomocą `top`, `bottom`, `left`, `right`.

Przykład:
```css
div {
    position: static; /* domyślnie */
}
```

2. `relative` (pozycjonowanie względne):
- Element pozostaje w normalnym układzie dokumentu.
- Można go przesuwać względem jego pierwotnej pozycji za pomocą `top`, `bottom`, `left`, `right`.
- Przestrzeń, którą element zajmował, pozostaje pusta.

Przykład:

```css
div {
    position: relative;
    top: 20px; /* Przesunięcie o 20px w dół */
    left: 10px; /* Przesunięcie o 10px w prawo */
}
```

3. `absolute` (pozycjonowanie absolutne):
- Element jest usuwany z normalnego układu dokumentu.
- Pozycjonuje się go względem najbliższego nadrzędnego elementu z `position`: `relative` lub `absolute` (jeśli takiego nie ma, to względem `body`).
- Można używać `top`, `bottom`, `left`, `right` do dokładnego określenia położenia.

Przykład:

```css
/* W tym przykładzie `child` jest umieszczony 50px od góry i 100px od lewej krawędzi `.container` (bo `.container` ma `position: relative`). */
.container {
    position: relative;
}

.child {
    position: absolute;
    top: 50px;
    left: 100px;
}
```

4. `fixed` (pozycjonowanie stałe):
- Element jest usuwany z normalnego układu dokumentu.
- Jest pozycjonowany względem widocznego obszaru przeglądarki (`viewport`).
- Pozostaje w tej samej pozycji nawet podczas przewijania strony.

Przykład:

```css
/* Przydatne do tworzenia pasków nawigacyjnych lub przycisków zawsze widocznych na ekranie. */
.fixed-header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: navy;
    color: white;
    padding: 10px;
}
```

5. `sticky` (pozycjonowanie "przyklejone"):
- Element działa jak relative, dopóki użytkownik nie przewinie strony do określonej pozycji, gdzie staje się `fixed`.
- Wymaga określenia `top`, `bottom`, `left` lub `right` do określenia momentu "przyklejenia".

```css
.sticky-nav {
    position: sticky;
    top: 0;
    background-color: lightblue;
    padding: 10px;
}
```

## `Flexbox` oraz `Grid`:

`Flexbox` (_Flexible Box Layout_) i Grid to dwa modele układu w CSS, które pomagają w tworzeniu elastycznych i złożonych layoutów.

### 1. Flexbox:

- Cel: Flexbox ułatwia tworzenie jednokierunkowych układów (w poziomie lub w pionie).
- Jak działa: Flexbox działa na kontenerach, w których umieszczamy elementy dzieci (tzw. `flex items`). Umożliwia ich rozmieszczenie, wyrównanie oraz dynamiczną zmianę rozmiaru w zależności od dostępnej przestrzeni.
- Przykład zastosowania: Układy na stronie, w których elementy są ustawione w jednej linii (np. nagłówki, przyciski w menu).

### 2. Grid:

- Cel: 
    - Grid jest bardziej zaawansowanym systemem, który pozwala na tworzenie dwuwymiarowych układów (zarówno w poziomie, jak i w pionie).
- Jak działa: 
    - Dzieli stronę na siatkę (kolumny i wiersze) i pozwala na precyzyjne rozmieszczenie elementów w tych komórkach. Można określić, które elementy zajmują określoną liczbę kolumn lub wierszy.
- Przykład zastosowania: 
    - Układy stron z wieloma sekcjami, np. layouty dla galerii zdjęć, dashboardów.

### Pojęcia:

1. `justify-content` (Flexbox):
   - Określa rozmieszczenie elementów wzdłuż głównej osi (domyślnie poziomej).
   - Działa w Flexboxie (kontener z `display: flex`).
   - Wartości:
        - `flex-start`: Wyrównanie do początku kontenera.
        - `flex-end`: Wyrównanie do końca kontenera.
        - `center`: Wyśrodkowanie elementów.
        - `space-between`: Równomierne rozmieszczenie z przestrzenią między elementami.
        - `space-around`: Równomierne rozmieszczenie z przestrzenią wokół elementów.
        - `space-evenly`: Równomierne rozmieszczenie z równą przestrzenią wokół elementów.

2. `align-items` (Flexbox i Grid):
   - Określa wyrównanie elementów wzdłuż osi poprzecznej (domyślnie pionowej).
   - Działa zarówno w Flexboxie, jak i w Gridzie.
   - Wartości:
        - `flex-start`: Wyrównanie do góry (Flexbox) / do początku wiersza (Grid).
        - `flex-end`: Wyrównanie do dołu (Flexbox) / do końca wiersza (Grid).
        - `center`: Wyśrodkowanie wzdłuż osi poprzecznej.
        - `baseline`: Wyrównanie do linii bazowej tekstu.
        - `stretch`: Rozciągnięcie elementów, aby wypełniły dostępne miejsce.

3. `grid-template-columns` (Grid):
   - Określa strukturę kolumn w siatce Grid.
   - Definiuje liczbę kolumn oraz ich szerokość.
   - Przykład: 
     `grid-template-columns: 1fr 2fr 1fr;`
        - Trzy kolumny, pierwsza i trzecia mają szerokość 1 fr, a środkowa 2 fr.

4. `grid-template-rows` (Grid):
   - Określa strukturę wierszy w siatce Grid.
   - Definiuje liczbę wierszy oraz ich wysokość.
   - Przykład: 
    `grid-template-rows: 100px auto 200px;`
        - Trzy wiersze: pierwszy ma wysokość 100px, drugi automatyczną wysokość, trzeci ma 200px.

## Pseudoklasy i pseudoelementy:

- `:hover` – stosuje styl do elementu, gdy użytkownik najedzie na niego kursorem.
- `:active` – stosuje styl do elementu w momencie jego aktywacji, np. podczas kliknięcia.
- `:focus` – stosuje styl do elementu, gdy znajduje się on w stanie aktywnego fokusu, np. po kliknięciu lub nawigacji klawiaturą.
- `::before` – dodaje generowany element przed zawartością wybranego elementu.
- `::after` – dodaje generowany element po zawartości wybranego elementu.

## Animacje i przejścia

- `Animation` – pozwala tworzyć bardziej złożone animacje CSS poprzez definiowanie klatek kluczowych w `@keyframes`.
- `Transition` – umożliwia płynne przejście między dwiema wartościami właściwości CSS po wystąpieniu zdarzenia, np. `:hover`.

## Responsive Design i Media Queries:

- `Media queries` to technika w CSS, która pozwala na stosowanie różnych stylów w zależności od cech urządzenia, takich jak szerokość ekranu czy jego orientacja.
- `Responsive design` to podejście do projektowania stron internetowych, które zapewnia ich optymalne wyświetlanie na różnych urządzeniach i rozdzielczościach ekranów.
- `Breakpoints` to określone punkty w kodzie CSS, które definiują zmiany w układzie strony przy określonych szerokościach ekranu, aby dostosować jej wygląd do różnych urządzeń.

## Zmienne CSS:

Zmienne CSS (_variables CSS_) to mechanizm umożliwiający przechowywanie wartości, które można wielokrotnie wykorzystywać w arkuszu stylów. Zmienna jest zdefiniowana za pomocą `--` na początku nazwy (np. `--primary-color: #ff5733;`), a następnie używana w innych regułach CSS za pomocą funkcji `var()`, np. `color: var(--primary-color);`. Dzięki temu łatwiej zarządzać i zmieniać wartości w całym projekcie.

### `:root`:

`:root` to pseudo-klasa CSS, która odnosi się do najwyższego elementu w drzewie DOM, którym jest element `<html>` w dokumencie HTML. Jest to miejsce, gdzie zwykle definiuje się globalne zmienne CSS, ponieważ zmienne zdefiniowane w `:root` mają zakres na cały dokument, co pozwala na ich użycie w różnych częściach strony. Definiowanie zmiennych w `:root` zapewnia spójność i łatwość w zarządzaniu stylami na całej stronie.