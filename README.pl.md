**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  PHP <img src="./assets/php.svg" width="40" height="40" alt="PHP logo"/>
</h1>

<h2>Najpopularniejsze pytania i odpowiedzi na rozmowie kwalifikacyjnej z PHP</h2>

<details>
<summary>1. Czym jest PHP i jakie problemy rozwiązuje we współczesnym backendzie?</summary>

#### PHP

PHP to serwerowy język programowania zaprojektowany głównie do tworzenia aplikacji webowych. We współczesnym backendzie PHP rozwiązuje kilka praktycznych problemów:

1. **Szybkie tworzenie backendu HTTP:** PHP ułatwia szybkie budowanie API, aplikacji webowych i stron renderowanych po stronie serwera.

2. **Obsługa żądań i logiki biznesowej:** Przetwarza przychodzące żądania HTTP, waliduje dane, wykonuje reguły biznesowe i zwraca odpowiedzi.

3. **Integracja z bazami danych:** PHP ma dojrzały ekosystem narzędzi do pracy z bazami (MySQL, PostgreSQL, SQLite) przez PDO i ORM-y.

4. **Sesje i uwierzytelnianie:** Wspiera sesje użytkownika, systemy logowania, obsługę cookies i kontrolę dostępu.

5. **Ekosystem dla aplikacji produkcyjnych:** Frameworki takie jak Laravel i Symfony dostarczają routing, dependency injection, kolejki, eventy i infrastrukturę testową.

6. **Przetwarzanie w tle:** PHP może wykonywać zadania asynchroniczne przez kolejki (maile, raporty, powiadomienia, importy) poza przepływem request-response.

7. **Skalowalność w realnych systemach:** Dzięki OPcache, warstwom cache (Redis), kontenerom i skalowaniu poziomemu PHP napędza systemy o dużym obciążeniu.

8. **Integracje z usługami zewnętrznymi:** PHP jest szeroko używany do integracji z bramkami płatności, brokerami wiadomości, API firm trzecich i usługami chmurowymi.

Krótko mówiąc, PHP obsługuje pełny cykl backendowy: przyjmowanie żądań, przetwarzanie danych, pracę ze storage i dostarczanie bezpiecznych, utrzymywalnych usług webowych.

</details>

<details>
<summary>2. Jakie są kluczowe różnice między PHP a JavaScript (runtime, model wykonania)?</summary>

#### PHP

PHP i JavaScript są szeroko używane w tworzeniu aplikacji webowych, ale istotnie różnią się modelem runtime, przepływem wykonania i typowym zachowaniem backendowym.

1. **Główne środowisko uruchomieniowe:**
   PHP działa na serwerze (PHP-FPM, CLI, Swoole/RoadRunner), podczas gdy JavaScript działa w przeglądarce oraz na serwerze przez Node.js/Deno/Bun.

2. **Model wykonania (klasyczny):**
   Tradycyjny PHP działa w modelu request-per-process/request-per-worker: każde żądanie HTTP startuje, wykonuje się i kończy z izolowanym stanem.
   JavaScript (Node.js) zwykle działa jako proces długowieczny ze współdzielonym stanem w pamięci.

3. **Model współbieżności:**
   Współbieżność w PHP zazwyczaj osiąga się przez wiele workerów/procesów obsługujących żądania równolegle.
   Serwerowe runtime JavaScript używają event loop z async I/O i operacjami nieblokującymi w pojedynczym procesie (plus skalowanie przez worker threads/procesy, gdy potrzeba).

4. **Cykl życia stanu:**
   W klasycznym PHP stan in-memory nie jest trwały między żądaniami, więc trwały stan zwykle żyje w Redis/DB/cache.
   W Node.js pamięć procesu może trwać między żądaniami, co bywa wygodne, ale wymaga ostrożnego zarządzania stanem.

5. **Typowa rola webowa:**
   PHP jest tradycyjnie backend-first (SSR, API, logika biznesowa).
   JavaScript z natury jest full-stack: język UI na frontendzie plus opcja backendowa.

6. **Fokus ekosystemu:**
   Ekosystem PHP akcentuje frameworki backendowe (Laravel, Symfony), szablonowanie serwerowe i backendy enterprise.
   Ekosystem JavaScript silnie akcentuje frameworki frontendowe oraz uniwersalne/full-stack tooling.

7. **Profil operacyjny:**
   PHP często wdraża się za Nginx/Apache z pulami PHP-FPM.
   Backendy JavaScript zwykle działają jako długowieczne procesy aplikacyjne za reverse proxy.

W praktyce PHP częściej wybiera się dla przewidywalnej izolacji żądań i dojrzałych frameworków backendowych, a JavaScript gdy zespoły chcą jednego języka na frontend i backend oraz serwerowego developmentu async-by-default.

</details>

<details>
<summary>3. Jakie są najważniejsze funkcje wprowadzone w PHP 8.x (8.1–8.5)?</summary>

#### PHP

PHP 8.1–8.5 wprowadził duże usprawnienia języka i runtime. Najważniejsze elementy według wersji:

1. **PHP 8.1 (wydanie: 25 listopada 2021):**
   Enums, readonly properties, fibers, first-class callable syntax, intersection types oraz typ zwracany `never`.

2. **PHP 8.2 (wydanie: 8 grudnia 2022):**
   Readonly classes, typy DNF, samodzielne typy `null`/`false`/`true`, nowe rozszerzenie `Random` oraz deprecacja dynamic properties.

3. **PHP 8.3 (wydanie: 23 listopada 2023):**
   Typed class constants, atrybut `#[\Override]`, dynamiczne pobieranie stałej klasy (`Class::{$name}`) oraz usprawnienia readonly/klonowania.

4. **PHP 8.4 (wydanie: 21 listopada 2024):**
   Property hooks, asymetryczna widoczność (`public private(set)`), atrybut `#[\Deprecated]`, zaktualizowane API DOM oraz wsparcie dla lazy objects.

5. **PHP 8.5 (wydanie: 20 listopada 2025):**
   Operator pipe (`|>`), rozszerzenie URI, aktualizacje clone-with przez `clone(...)`, `#[\NoDiscard]`, closures w constant expressions oraz dodatkowe ulepszenia API/runtime.

#### Dlaczego to ma znaczenie

- **Lepsze bezpieczeństwo typów:** silniejsze typowanie, bezpieczniejsze kontrakty, mniej niespodzianek w runtime.
- **Czystsze modelowanie domeny:** enums, konstrukcje readonly i nowoczesna semantyka właściwości.
- **Bardziej ekspresyjny kod:** operator pipe, atrybuty i ulepszone wsparcie callable.
- **Wydajność i utrzymywalność:** ciągła ewolucja silnika, narzędzi i biblioteki standardowej.

Krótko: PHP 8.x znacząco zmodernizował język i ułatwił budowanie oraz utrzymanie nowoczesnej architektury backendowej.

</details>

<details>
<summary>4. Czym są enums, attributes i readonly properties w PHP?</summary>

#### PHP

Enums, attributes i readonly properties to nowoczesne funkcje języka PHP, które poprawiają poprawność, czytelność i utrzymywalność kodu.

1. **Enums**

- Enumy definiują stały zestaw dozwolonych wartości jako rzeczywisty typ.
- Zapobiegają nieprawidłowym stanom string/int i ułatwiają bezpieczne modelowanie domeny.
- PHP wspiera:
  backed enums (`enum Status: string { ... }`) i unit enums (`enum Role { ... }`).

```php
enum OrderStatus: string
{
    case Draft = 'draft';
    case Paid = 'paid';
    case Shipped = 'shipped';
}
```

2. **Attributes**

- Atrybuty to natywne metadane (`#[...]`) dołączane do klas, metod, właściwości, parametrów i innych elementów.
- Zastępują wiele zastosowań adnotacji docblock, dostarczając ustrukturyzowane, maszynowo czytelne metadane.
- Typowe zastosowania: routing, walidacja, dependency injection, reguły serializacji, znaczniki deprecacji.

```php
#[Deprecated(reason: 'Use NewService instead')]
class LegacyService {}
```

3. **Readonly properties**

- Właściwość `readonly` może zostać zapisana tylko raz (zwykle w konstruktorze).
- Po inicjalizacji modyfikacja jest zabroniona.
- Jest to przydatne dla niemutowalnych DTO, value objects i bezpieczniejszego projektowania obiektów.

```php
final class UserDto
{
    public function __construct(
        public readonly int $id,
        public readonly string $email,
    ) {}
}
```

#### Dlaczego razem są ważne

- **Enums** chronią dozwolone stany.
- **Attributes** dostarczają jawne metadane dla frameworków i narzędzi.
- **Readonly properties** wymuszają niemutowalność krytycznych danych.

Razem te funkcje zmniejszają liczbę błędów, czynią API bardziej przejrzystymi i poprawiają jakość analizy statycznej w nowoczesnych kodowych bazach PHP.

</details>

<details>
<summary>5. Czym jest ścisłe typowanie (strict typing) w PHP i dlaczego jest ważne?</summary>

#### PHP

Ścisłe typowanie w PHP włącza się per plik przez:

```php
declare(strict_types=1);
```

Gdy ścisłe typowanie jest włączone, deklaracje typów skalarnych są egzekwowane bardziej rygorystycznie dla argumentów funkcji i wartości zwracanych.

1. **Bez ścisłego typowania (`strict_types=0`, domyślnie):**
   PHP może dokonywać konwersji wartości skalarnych (np. `'10'` na `10`), gdy to możliwe.

2. **Ze ścisłym typowaniem (`strict_types=1`):**
   PHP rzuca `TypeError` zamiast cicho konwertować niezgodne wartości skalarne.

```php
declare(strict_types=1);

function add(int $a, int $b): int
{
    return $a + $b;
}

add('2', 3); // TypeError w trybie strict
```

#### Dlaczego to jest ważne

- **Wczesne wykrywanie błędów:** niezgodności typów kończą się błędem od razu.
- **Bezpieczniejszy refaktoring:** czytelniejsze kontrakty zmniejszają ukryte regresje.
- **Bardziej przewidywalne zachowanie:** mniej „magii” niejawnych konwersji.
- **Lepsza analiza statyczna:** narzędzia jak PHPStan/Psalm działają skuteczniej.
- **Czystsze granice API:** sygnatury funkcji są traktowane jak ścisłe kontrakty.

#### Praktyczna rekomendacja

Używaj `declare(strict_types=1);` we wszystkich nowych plikach PHP i łącz to z jawnymi type hints, DTO/value objects oraz analizą statyczną, aby uzyskać niezawodność klasy production.

</details>

<details>
<summary>6. Czym są typy unii i przecięcia?</summary>

#### PHP

Typy unii i przecięcia w PHP to narzędzia do wyrażania bardziej rygorystycznych i jawnych kontraktów typów.

1. **Typy unii (`A|B`)**

- Wartość może być **jednym z kilku dozwolonych typów**.
- Przydatne, gdy argument lub wartość zwracana mogą legalnie się różnić.

```php
function formatId(int|string $id): string
{
    return (string) $id;
}
```

2. **Typy przecięcia (`A&B`)**

- Wartość musi spełniać **wszystkie wymienione typy jednocześnie**.
- Często używane z interfejsami, aby wymagać wielu możliwości naraz.

```php
interface Cacheable {}
interface Jsonable { public function toJson(): string; }

function store(Cacheable&Jsonable $entity): void
{
    // $entity musi implementować oba interfejsy
}
```

3. **Kluczowa różnica**

- `A|B` oznacza **albo A, albo B**.
- `A&B` oznacza **A i B jednocześnie**.

4. **Dlaczego są ważne**

- Lepsze kontrakty API i samodokumentujący się kod.
- Mniej błędów runtime wynikających z nieprawidłowego kształtu obiektów/wartości.
- Silniejsza analiza statyczna i bezpieczniejszy refaktoring.

5. **Praktyczne wskazówki**

- Używaj typów unii dla elastycznych granic wejścia.
- Używaj typów przecięcia dla projektowania opartego na możliwościach (szczególnie z interfejsami).
- Gdy to możliwe, preferuj typy konkretne zamiast `mixed`.

</details>

<details>
<summary>7. Czym jest operator nullsafe i kiedy go używać?</summary>

#### PHP

Operator nullsafe w PHP to `?->`. Umożliwia bezpieczny dostęp do metod/właściwości obiektów, które mogą być `null`.

1. **Co robi**

- Jeśli lewa strona jest obiektem, dostęp przebiega normalnie.
- Jeśli lewa strona to `null`, ewaluacja zatrzymuje się i zwraca `null` zamiast rzucać błąd.

```php
$country = $user?->getProfile()?->getAddress()?->country;
```

2. **Dlaczego jest przydatny**

- Eliminuje rozbudowane zagnieżdżone sprawdzanie nulli.
- Zmniejsza boilerplate w łańcuchach opcjonalnych obiektów.
- Lepiej komunikuje intencję, gdy wartości są legalnie nullable.

3. **Typowe przypadki użycia**

- Struktury API/DTO z opcjonalnymi zagnieżdżonymi polami.
- Relacje ORM, które mogą nie istnieć.
- Obiekty kontekstu requestu, gdzie część danych jest opcjonalna.

4. **Odpowiednik bez nullsafe (bardziej rozwlekły)**

```php
$country = null;
if ($user !== null) {
    $profile = $user->getProfile();
    if ($profile !== null) {
        $address = $profile->getAddress();
        if ($address !== null) {
            $country = $address->country;
        }
    }
}
```

5. **Ważne uwagi**

- `?->` działa tylko dla dostępu do obiektów (metody/właściwości), nie dla indeksów tablic.
- Działa z short-circuit od lewej do prawej.
- Jeśli łańcuch rozwiąże się do `null`, końcowy wynik to `null`.

Używaj operatora nullsafe, gdy `null` jest oczekiwanym stanem i chcesz zwięzłego, bezpiecznego przechodzenia po grafie obiektów.

</details>

<details>
<summary>8. Czym są property hooks (PHP 8.4+)?</summary>

#### PHP

Property hooks (wprowadzone w PHP 8.4) pozwalają podpiąć logikę bezpośrednio do operacji odczytu/zapisu właściwości za pomocą hooków `get` i `set`.

1. **Jaki problem rozwiązują**

- Redukują boilerplate getterów/setterów.
- Trzymają walidację/transformację blisko definicji właściwości.
- Umożliwiają właściwości obliczane (wirtualne) z czytelniejszą składnią.

2. **Podstawowa idea**

```php
class User
{
    public string $name {
        set => trim($value);
    }
}
```

Każde przypisanie do `$user->name` przechodzi przez hook `set`.

3. **Przykład właściwości obliczanej**

```php
class Person
{
    public function __construct(
        public string $firstName,
        public string $lastName,
    ) {}

    public string $fullName {
        get => $this->firstName . ' ' . $this->lastName;
    }
}
```

`$fullName` jest wyprowadzane z innych pól i nie wymaga ręcznych metod getter.

4. **Przykład walidacji/transformacji**

```php
class Product
{
    public float $price {
        set {
            if ($value < 0) {
                throw new InvalidArgumentException('Price cannot be negative');
            }
            $this->price = round($value, 2);
        }
    }
}
```

5. **Kiedy używać**

- Encje domenowe ze ścisłymi niezmiennikami.
- Obiekty DTO/value-like wymagające kontrolowanych zapisów.
- Przypadki, gdzie klasyczne metody get/set były głównie boilerplate’em.

Property hooks czynią modele obiektowe bardziej ekspresyjnymi i redukują powtarzalny kod akcesorów, zachowując silną walidację i enkapsulację.

</details>

<details>
<summary>9. Czym jest operator pipe (PHP 8.5) i kiedy jest przydatny?</summary>

#### PHP

Operator pipe w PHP 8.5 to `|>`. Przekazuje wynik wyrażenia po lewej stronie do callable po prawej, umożliwiając czytelne transformacje danych od lewej do prawej.

1. **Główna idea**

Zamiast głęboko zagnieżdżonych wywołań możesz zbudować liniowy pipeline przetwarzania.

```php
$result = " Hello World "
    |> trim(...)
    |> strtolower(...)
    |> (fn(string $s) => str_replace(' ', '-', $s));
```

2. **Dlaczego jest przydatny**

- Poprawia czytelność wieloetapowych transformacji.
- Ogranicza liczbę zmiennych tymczasowych.
- Unika wywołań funkcji zagnieżdżonych „od środka”.
- Ułatwia refaktoryzację łańcuchów transformacji.

3. **Przed vs po**

Bez pipe:

```php
$slug = strtolower(str_replace(' ', '-', trim($title)));
```

Z pipe:

```php
$slug = $title
    |> trim(...)
    |> (fn(string $s) => str_replace(' ', '-', $s))
    |> strtolower(...);
```

4. **Dobre przypadki użycia**

- Pipeline normalizacji stringów/danych.
- Przepływy mapowania/transformacji DTO.
- Funkcyjny styl przetwarzania danych w serwisach.

5. **Praktyczna uwaga**

Używaj operatora pipe do czytelnych, sekwencyjnych transformacji. Przy złożonej logice z rozgałęzieniami zwykłe zmienne pośrednie nadal mogą być łatwiejsze do zrozumienia.

</details>

<details>
<summary>10. Czym są superglobalne zmienne w PHP i jak się ich używa?</summary>

#### PHP

Superglobalne w PHP to wbudowane tablice asocjacyjne dostępne we wszystkich zakresach (funkcje, metody, zakres globalny) bez użycia `global`.

1. **Główne superglobalne**

- `$_GET` - parametry query string z URL.
- `$_POST` - parametry formularza/body z żądań POST.
- `$_REQUEST` - scalone dane żądania (zależy od `request_order`/`variables_order`).
- `$_SERVER` - metadane serwera i żądania (nagłówki, metoda, URI, host itd.).
- `$_COOKIE` - cookies klienta wysyłane z żądaniem.
- `$_SESSION` - dane sesji przechowywane między żądaniami.
- `$_FILES` - metadane przesłanych plików.
- `$_ENV` - zmienne środowiskowe.
- `$GLOBALS` - referencja do wszystkich zmiennych globalnych.

2. **Typowe przykłady użycia**

```php
$page = $_GET['page'] ?? 'home';
$method = $_SERVER['REQUEST_METHOD'] ?? 'GET';
$token = $_COOKIE['csrf_token'] ?? null;
```

3. **Dlaczego są ważne**

- To podstawowy interfejs między kodem PHP a środowiskiem HTTP/runtime.
- Dostarczają dane wejściowe requestu, kontekst oraz utrwalony stan użytkownika/sesji.

4. **Praktyki bezpieczeństwa i niezawodności**

- Nigdy nie ufaj bezpośrednio danym z superglobalnych.
- Zawsze waliduj i sanityzuj dane zewnętrzne.
- Używaj rygorystycznych sprawdzeń i wartości domyślnych (`??`, `filter_input`, walidatory).
- Unikaj polegania na `$_REQUEST` w kodzie krytycznym, bo priorytet źródeł może się różnić.
- Escapuj output, aby zapobiegać XSS, i używaj prepared statements, aby zapobiegać SQL injection.

Superglobalne są fundamentem tworzenia aplikacji webowych w PHP, ale należy traktować je jako nieufną granicę wejścia.

</details>

<details>
<summary>11. Jaka jest różnica między żądaniami GET i POST?</summary>

#### PHP

GET i POST to metody HTTP o różnej semantyce i wzorcach użycia.

1. **Cel**

- **GET** służy do pobierania danych (operacje tylko do odczytu).
- **POST** służy do wysyłania danych, które mogą zmieniać stan serwera (akcje create/process).

2. **Gdzie przesyłane są dane**

- **GET** wysyła parametry w query string URL (`/users?page=2`).
- **POST** wysyła dane w body żądania.

3. **Widoczność i logowanie**

- Parametry **GET** są widoczne w URL, historii przeglądarki, logach i referrerach.
- Body **POST** nie jest pokazywane w URL, ale nadal należy je traktować jako nieufne wejście.

4. **Cache i zakładki**

- Żądania **GET** są przyjazne dla cache i można je zapisywać w zakładkach.
- Żądania **POST** z reguły nie są domyślnie cache’owane i nie są zakładkowalne z payloadem.

5. **Idempotencja i bezpieczeństwo semantyczne (HTTP)**

- **GET** powinien być bezpieczny i nie zmieniać stanu serwera.
- **POST** nie jest gwarantowanie idempotentny i zwykle wykonuje side effects.

6. **Dostęp w PHP**

```php
$search = $_GET['q'] ?? null;      // z query string
$email  = $_POST['email'] ?? null; // z body żądania
```

7. **Kiedy używać**

- Używaj **GET** do filtrowania, wyszukiwania, paginacji i odczytu zasobów.
- Używaj **POST** do wysyłki formularzy, akcji uwierzytelniania oraz tworzenia/aktualizacji danych po stronie serwera (lub PUT/PATCH tam, gdzie to właściwe w API).

Kluczowa zasada: używaj GET dla operacji odczytu i POST dla operacji zmieniających stan, jednocześnie walidując wszystkie dane wejściowe w obu przypadkach.

</details>

<details>
<summary>12. Jak PHP obsługuje żądania i odpowiedzi HTTP?</summary>

#### PHP

W typowej konfiguracji webowej PHP obsługuje HTTP przez cykl request-response koordynowany przez serwer webowy (Nginx/Apache) i runtime PHP (najczęściej PHP-FPM).

1. **Nadchodzi żądanie**

- Klient wysyła żądanie HTTP (metoda, URI, nagłówki, body).
- Serwer webowy je odbiera i kieruje żądania dynamiczne do PHP.

2. **Runtime PHP uruchamia skrypt**

- PHP inicjalizuje kontekst requestu i wypełnia superglobalne (`$_SERVER`, `$_GET`, `$_POST`, `$_COOKIE`, `$_FILES`).
- Uruchamia się bootstrap aplikacji (autoload, config, kontener DI, kernel frameworka).

3. **Aplikacja realizuje logikę biznesową**

- Router wybiera controller/handler.
- Uruchamiają się middleware/guardy/walidacja.
- Serwisy/repozytoria sięgają do bazy danych, cache lub zewnętrznych API.

4. **Budowana jest odpowiedź**

- Aplikacja ustawia status code, nagłówki i body (HTML/JSON/plik/stream).
- W czystym PHP zwykle przez `header()`, `http_response_code()` i output.
- W frameworkach zwracany jest obiekt Response, który następnie jest emitowany.

```php
http_response_code(200);
header('Content-Type: application/json; charset=utf-8');
echo json_encode(['ok' => true], JSON_THROW_ON_ERROR);
```

5. **Odpowiedź jest wysyłana**

- PHP wysyła output do serwera webowego.
- Serwer webowy odsyła finalną odpowiedź HTTP do klienta.
- W klasycznym PHP-FPM stan requestu kończy się po odpowiedzi (do trwałości używa się współdzielonego zewnętrznego storage).

6. **Obsługa błędów**

- Wyjątki są mapowane na odpowiedzi HTTP z błędem (np. `404`, `422`, `500`) przez framework/globalne handlery.
- Logi/monitoring rejestrują awarie do diagnostyki.

Model PHP jest prosty: przyjąć kontekst żądania, wykonać kod aplikacji, wygenerować odpowiedź HTTP i czysto zakończyć request.

</details>

<details>
<summary>13. Jak działają sesje i jakie są bezpieczne praktyki sesyjne?</summary>

#### PHP

Sesje PHP pozwalają utrzymywać stan specyficzny dla użytkownika między bezstanowymi żądaniami HTTP, przechowując dane po stronie serwera i wiążąc je z identyfikatorem sesji.

1. **Jak działają sesje**

- Klient wysyła pierwsze żądanie.
- Serwer tworzy identyfikator sesji (SID).
- SID jest wysyłany do klienta, zwykle przez cookie (najczęściej `PHPSESSID`).
- Przy kolejnych żądaniach klient odsyła SID.
- PHP ładuje odpowiadające dane sesji po stronie serwera do `$_SESSION`.

2. **Podstawowe użycie**

```php
session_start();

$_SESSION['user_id'] = 42;
$userId = $_SESSION['user_id'] ?? null;
```

3. **Gdzie przechowywane są dane**

- Domyślnie: filesystem session storage.
- W produkcji: często Redis/database/memcached przez custom handlery dla skalowalności.

4. **Bezpieczne praktyki sesyjne**

- Regeneruj SID po logowaniu/zmianie uprawnień:
  `session_regenerate_id(true);`
- Używaj flag cookie:
  `HttpOnly`, `Secure`, `SameSite` (`Lax` lub `Strict`, gdy to możliwe).
- Wymuszaj HTTPS dla aplikacji uwierzytelnionych.
- Ustaw timeout sesji i wygaszanie po bezczynności.
- Unieważniaj sesję przy wylogowaniu (unset danych + destroy session + wygaszenie cookie).
- Ostrożnie wiąż sesje z sygnałami kontekstu (np. częściowa kontrola IP/UA), aby zmniejszyć ryzyko hijackingu.
- Przechowuj w sesji minimum danych wrażliwych; preferuj ID/referencje zamiast pełnych sekretów.

5. **Typowe zagrożenia**

- **Session fixation:** atakujący wymusza znany SID przed uwierzytelnieniem.
- **Session hijacking:** skradziony SID jest ponownie używany przez atakującego.
- **Kradzież wsparta XSS:** złośliwe skrypty mogą wykorzystać niebezpieczną obsługę sesji.

6. **Hardening checklist**

- `session.use_strict_mode=1`
- `session.cookie_httponly=1`
- `session.cookie_secure=1` (na HTTPS)
- Poprawne `session.cookie_samesite`
- Regularna regeneracja SID dla przepływów uwierzytelnionych

Sesje są bezpieczne i skuteczne, gdy identyfikatory są chronione, odpowiednio rotowane i przesyłane wyłącznie zaufanymi kanałami.

</details>

<details>
<summary>14. Jak ustawia się i zabezpiecza cookies w nowoczesnych aplikacjach?</summary>

#### PHP

Cookies to małe dane klucz-wartość przechowywane przez przeglądarkę i wysyłane z pasującymi żądaniami. W nowoczesnych aplikacjach używa się ich do sesji, preferencji i bezpiecznych przepływów autoryzacji.

1. **Jak ustawia się cookies w PHP**

Użyj `setcookie()` (lub helperów odpowiedzi frameworka) przed wysłaniem outputu:

```php
setcookie(
    'session_token',
    $token,
    [
        'expires'  => time() + 3600,
        'path'     => '/',
        'domain'   => 'example.com',
        'secure'   => true,
        'httponly' => true,
        'samesite' => 'Lax',
    ]
);
```

2. **Jak odczytywać cookies**

```php
$token = $_COOKIE['session_token'] ?? null;
```

3. **Atrybuty bezpieczeństwa (krytyczne)**

- **`Secure`**: cookie wysyłane tylko przez HTTPS.
- **`HttpOnly`**: niedostępne z JavaScript (`document.cookie`), zmniejsza ryzyko kradzieży przy XSS.
- **`SameSite`**:
  `Strict` (silna ochrona CSRF), `Lax` (zbalansowane), `None` (wymaga `Secure`, dla use case’ów cross-site).
- **`Expires/Max-Age`**: ogranicza czas życia.
- **`Path/Domain`**: zawęża zakres cookie tak mocno, jak to możliwe.

4. **Najlepsze praktyki**

- Używaj HTTPS wszędzie i zawsze ustawiaj `Secure` dla wrażliwych cookies.
- Ustawiaj `HttpOnly` dla cookies sesyjnych/auth.
- Preferuj `SameSite=Lax` lub `Strict`, chyba że zachowanie cross-site jest jawnie wymagane.
- Rotuj tokeny auth/session i wygaszaj je w odpowiednim czasie.
- Nie przechowuj w cookies wrażliwych danych w plaintext.
- Rozważ podpisywanie lub szyfrowanie payloadu cookie, jeśli przechowujesz stan po stronie klienta.

5. **Typowe błędy**

- Brak `HttpOnly` lub `Secure`.
- Zbyt szerokie `domain`/`path`.
- Bardzo długi czas wygaśnięcia dla auth cookies.
- Ufanie wartościom cookie bez weryfikacji po stronie serwera.

Nowoczesne bezpieczeństwo cookies opiera się na ścisłym zakresie, bezpiecznym transporcie, bezpiecznych domyślnych ustawieniach i walidacji wszystkich wartości dostarczonych przez klienta po stronie serwera.

</details>

<details>
<summary>15. Czym jest CSRF i jak mu zapobiegać?</summary>

#### PHP

CSRF (Cross-Site Request Forgery) to atak, w którym przeglądarka ofiary jest nakłaniana do wysłania uwierzytelnionego żądania do Twojej aplikacji bez intencji użytkownika.

1. **Jak działa CSRF**

- Użytkownik jest zalogowany do `your-app.com`.
- Atakujący kieruje użytkownika na złośliwą stronę.
- Ta strona wywołuje żądanie do `your-app.com` (np. zmiana e-maila, przelew środków).
- Przeglądarka automatycznie dołącza cookies/sesję, więc żądanie może zostać zaakceptowane.

2. **Dlaczego to niebezpieczne**

- Serwer widzi poprawną, uwierzytelnioną sesję.
- Akcje zmieniające stan mogą zostać wykonane w imieniu ofiary.

3. **Główna obrona: token CSRF**

- Generuj losowy token per sesja/request.
- Umieszczaj token w formularzach lub nagłówkach żądań.
- Weryfikuj token po stronie serwera przed obsługą akcji zmieniających stan.

```php
session_start();

// Generate token once
$_SESSION['csrf_token'] ??= bin2hex(random_bytes(32));

// Validate on POST
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $token = $_POST['_csrf'] ?? '';
    if (!hash_equals($_SESSION['csrf_token'], $token)) {
        http_response_code(419);
        exit('Invalid CSRF token');
    }
}
```

4. **Dodatkowe zabezpieczenia**

- Używaj cookies `SameSite` (`Lax`/`Strict`), aby ograniczyć wysyłanie cookies cross-site.
- Waliduj nagłówki `Origin`/`Referer` dla wrażliwych endpointów (defense-in-depth).
- Wymagaj re-auth lub step-up confirmation dla krytycznych operacji.
- Nie używaj GET do akcji zmieniających stan.

5. **Najlepsza praktyka we frameworkach**

- Korzystaj z wbudowanego middleware CSRF (Laravel/Symfony itp.) zamiast własnej implementacji, gdy to możliwe.
- Upewnij się, że tokeny są dołączane do wszystkich mutujących żądań (POST/PUT/PATCH/DELETE), także AJAX.

Ochrona CSRF jest obowiązkowa przy uwierzytelnianiu opartym o cookies i powinna być częścią domyślnego middleware bezpieczeństwa.

</details>

<details>
<summary>16. Czym jest XSS i jak poprawnie mu zapobiegać?</summary>

#### PHP

XSS (Cross-Site Scripting) to podatność, w której dane kontrolowane przez atakującego są interpretowane przez przeglądarkę jako wykonywalny skrypt na stronach Twojej aplikacji.

1. **Główne typy XSS**

- **Stored XSS**: złośliwy payload jest zapisywany (DB/komentarz/profil) i później serwowany użytkownikom.
- **Reflected XSS**: payload pochodzi z inputu requestu i jest natychmiast odbijany w odpowiedzi.
- **DOM-based XSS**: JavaScript po stronie klienta zapisuje niebezpieczne dane do DOM.

2. **Przyczyna źródłowa**

- Nieufny input trafia do kontekstów HTML/JS/URL/CSS bez poprawnego kodowania outputu.

3. **Podstawowa obrona: kontekstowe escaping outputu**

- Escapuj dane **na wyjściu**, zgodnie z kontekstem renderowania.
- Dla kontekstu tekstu HTML w PHP:

```php
echo htmlspecialchars($userInput, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
```

4. **Reguły zależne od kontekstu**

- HTML body: `htmlspecialchars(...)`.
- Atrybuty HTML: także escapuj cudzysłowy (`ENT_QUOTES`).
- Kontekst JavaScript: koduj dane przez JSON, unikaj bezpośredniej konkatenacji stringów.
- Kontekst URL: `rawurlencode()` dla wartości parametrów.
- Unikaj bezpośredniego wstrzykiwania nieufnego HTML.

5. **Dodatkowe zabezpieczenia**

- Używaj auto-escapingu w silnikach szablonów/frameworkach.
- Sanityzuj rich HTML sanitizerami opartymi o allowlistę (jeśli input HTML jest wymagany).
- Ustaw silną Content Security Policy (CSP) jako defense-in-depth.
- W miarę możliwości unikaj inline scripts.
- Waliduj input, ale nie traktuj walidacji jako zamiennika kodowania outputu.

6. **Typowe błędy**

- Jednorazowe escapowanie inputu i używanie go ponownie w różnych kontekstach.
- Globalne wyłączanie auto-escapingu szablonów.
- Renderowanie surowego contentu użytkownika w panelach admina/narzędziach wewnętrznych.

Zapobieganie XSS to przede wszystkim ścisłe kontekstowe kodowanie w punkcie outputu plus CSP i bezpieczne wzorce renderowania.

</details>

<details>
<summary>17. Czym jest SQL Injection i jak prepared statements temu zapobiegają?</summary>

#### PHP

SQL Injection to podatność, w której input atakującego zmienia strukturę zapytań SQL, umożliwiając nieautoryzowany dostęp do danych lub ich modyfikację.

1. **Jak dochodzi do SQL Injection**

Występuje, gdy nieufny input jest bezpośrednio konkatenowany do stringów SQL.

```php
// Unsafe example
$sql = "SELECT * FROM users WHERE email = '" . $_POST['email'] . "'";
```

Atakujący może wstrzyknąć fragmenty SQL i zmienić logikę zapytania.

2. **Skutki**

- Ominięcie uwierzytelniania
- Wyciek/modyfikacja/usuwanie danych
- Eskalacja uprawnień
- W ciężkich przypadkach pełna kompromitacja bazy danych

3. **Jak prepared statements zapobiegają problemowi**

Prepared statements rozdzielają:
- **Strukturę SQL** (szablon zapytania)
- **Wartości danych** (bindowane parametry)

Baza danych traktuje bindowane wartości jako dane, a nie wykonywalny kod SQL.

```php
$pdo = new PDO($dsn, $user, $pass, [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
]);

$stmt = $pdo->prepare('SELECT * FROM users WHERE email = :email');
$stmt->execute(['email' => $_POST['email']]);
$user = $stmt->fetch(PDO::FETCH_ASSOC);
```

4. **Ważny niuans**

- Prepared statements chronią wartości, ale nie dynamiczne identyfikatory SQL (nazwy tabel/kolumn).
- Jeśli identyfikatory muszą być dynamiczne, używaj ścisłych allowlist.

5. **Najlepsze praktyki**

- Używaj prepared statements PDO/MySQLi wszędzie tam, gdzie jest input zewnętrzny.
- Nigdy nie buduj SQL przez konkatenację stringów z wartościami od użytkownika.
- Wymuszaj zasadę least-privilege dla kont DB.
- Waliduj input i loguj podejrzaną aktywność.
- Utrzymuj silnik DB i drivery w aktualnej wersji.

Prepared statements to podstawowa i obowiązkowa ochrona przed SQL injection we współczesnych aplikacjach PHP.

</details>

<details>
<summary>18. Czym jest Content Security Policy (CSP)?</summary>

#### PHP

Content Security Policy (CSP) to mechanizm bezpieczeństwa przeglądarki, który ogranicza, jakie zasoby (skrypty, style, obrazy, ramki itd.) mogą zostać załadowane i uruchomione na stronie.

1. **Przed czym chroni CSP**

- Przede wszystkim zmniejsza skutki XSS, blokując nieautoryzowane skrypty inline/zewnętrzne.
- Pomaga ograniczać exfiltrację danych przez złośliwe ładowanie zasobów.
- Ogranicza ryzykowne możliwości przeglądarki do zaufanych originów.

2. **Jak dostarcza się CSP**

- Najczęściej przez nagłówek odpowiedzi HTTP:
  `Content-Security-Policy: ...`
- Można też najpierw wysłać w trybie report-only:
  `Content-Security-Policy-Report-Only: ...`

3. **Podstawowy przykład**

```php
header("Content-Security-Policy: default-src 'self'; script-src 'self'; object-src 'none'; base-uri 'self'; frame-ancestors 'none'");
```

4. **Ważne dyrektywy**

- `default-src` - fallback policy dla źródeł.
- `script-src` - kontroluje źródła JavaScript.
- `style-src` - kontroluje źródła CSS.
- `img-src` - kontroluje źródła obrazów.
- `connect-src` - kontroluje cele XHR/fetch/WebSocket.
- `frame-ancestors` - zapobiega clickjackingowi przez kontrolę osadzania.
- `object-src 'none'` - wyłącza legacy plugin content.
- `base-uri` - ogranicza wstrzyknięcie znacznika `<base>`.

5. **Najlepsze praktyki**

- Zacznij od `Report-Only`, zbieraj naruszenia, potem egzekwuj.
- Dla skryptów inline preferuj nonce/hash zamiast `'unsafe-inline'`.
- Utrzymuj politykę ścisłą i jawną dla każdego środowiska.
- Łącz CSP z escapingiem outputu, ochroną CSRF i bezpiecznymi cookies.

6. **CSP nie jest „srebrną kulą”**

- To defense-in-depth, a nie zamiennik bezpiecznego kodowania.
- Nadal musisz sanityzować/escapować nieufny output i unikać niebezpiecznych wzorców DOM.

CSP znacząco wzmacnia bezpieczeństwo frontendu, jeśli jest starannie skonfigurowany i stale monitorowany.

</details>

<details>
<summary>19. Czym jest autoloading i jak działa PSR-4?</summary>

#### PHP

Autoloading to mechanizm, który automatycznie ładuje pliki klas/interfejsów/traitów PHP przy pierwszym użyciu, zamiast ręcznego dodawania wielu `require`/`include`.

1. **Dlaczego autoloading jest potrzebny**

- Eliminuje ręczne dołączanie plików.
- Utrzymuje skalowalną strukturę projektu.
- Ułatwia zarządzanie zależnościami i modułami.

2. **PSR-4 w skrócie**

PSR-4 to nowoczesny standard mapowania namespace’ów na ścieżki systemu plików.

- Prefix namespace mapuje się na katalog bazowy.
- Pozostałe części namespace mapują się na podkatalogi.
- Nazwa klasy mapuje się na nazwę pliku (`ClassName.php`).

3. **Przykład mapowania**

Jeśli konfiguracja Composer zawiera:

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

To:
- `App\Services\UserService` -> `src/Services/UserService.php`
- `App\Http\Controllers\HomeController` -> `src/Http/Controllers/HomeController.php`

4. **Jak Composer to włącza**

- Zdefiniuj `autoload.psr-4` w `composer.json`.
- Uruchom:

```bash
composer dump-autoload
```

- Dołącz autoloader Composer raz (zwykle w bootstrapie aplikacji):

```php
require __DIR__ . '/vendor/autoload.php';
```

5. **Najlepsze praktyki**

- Trzymaj zasadę: jedna klasa na plik.
- Utrzymuj zgodność nazw namespace i katalogów.
- Używaj znaczącego root namespace (`App\`, `Domain\`, `Company\Project\`).
- Regeneruj pliki autoload po zmianach namespace/ścieżek.

Autoloading zgodny z PSR-4 to domyślny fundament nowoczesnej struktury aplikacji PHP i ładowania zależności.

</details>

<details>
<summary>20. Czym jest Composer i jak działa zarządzanie zależnościami?</summary>

#### PHP

Composer to standardowy menedżer zależności dla PHP. Instaluje, aktualizuje i automatycznie ładuje biblioteki projektu w sposób powtarzalny.

1. **Kluczowe pliki**

- `composer.json` - deklaruje metadane projektu, wymagane pakiety, reguły autoloadingu i skrypty.
- `composer.lock` - blokuje dokładne wersje pakietów rozwiązane dla projektu.
- `vendor/` - zainstalowane zależności i autoloader Composer.

2. **Jak działa zarządzanie zależnościami**

- Deklarujesz ograniczenia wersji w `composer.json` (na przykład `^11.0`).
- Composer rozwiązuje kompatybilny graf zależności.
- Rozwiązane dokładne wersje są zapisywane w `composer.lock`.
- Zespół/CI instaluje dokładnie zablokowane wersje, aby buildy były deterministyczne.

3. **Podstawowy workflow**

```bash
# Dodanie zależności
composer require monolog/monolog

# Instalacja z lock file
composer install

# Aktualizacja zależności (ponowne rozwiązanie ograniczeń)
composer update
```

4. **Ograniczenia wersji**

- `^1.2` - pozwala na aktualizacje bez łamania kompatybilności aż do `<2.0.0`.
- `~1.2.3` - pozwala na poprawki/minor w obrębie tej gałęzi.
- Dokładne wersje są możliwe, ale zwykle są zbyt sztywne dla bibliotek.

5. **Integracja z autoloadingiem**

Composer generuje `vendor/autoload.php` i wspiera mapowanie autoloadingu PSR-4 z `composer.json`.

```php
require __DIR__ . '/vendor/autoload.php';
```

6. **Najlepsze praktyki**

- Commituj `composer.lock` w aplikacjach.
- Używaj `composer install` w CI/produkcji.
- Używaj `composer update` świadomie i przeglądaj zmiany w lock file.
- Preferuj stabilne wersje pakietów.
- Regularnie audytuj zależności (`composer audit`).

Composer jest kluczowy we współczesnym PHP, ponieważ standaryzuje zarządzanie pakietami, autoloading i powtarzalne buildy między środowiskami.

</details>

<details>
<summary>21. Czym są standardy PSR i dlaczego są ważne?</summary>

#### PHP

PSR (PHP Standards Recommendations) to standardy społecznościowe publikowane przez PHP-FIG (PHP Framework Interop Group), które poprawiają interoperacyjność i spójność między bibliotekami oraz frameworkami PHP.

1. **Co definiują PSR**

- Konwencje stylu kodowania (na przykład PSR-12).
- Konwencje autoloadingu (PSR-4).
- Wspólne interfejsy dla komunikatów HTTP, middleware, kontenerów, logowania, cache itd.

2. **Dlaczego są ważne**

- **Interoperacyjność:** biblioteki od różnych dostawców łatwiej współpracują.
- **Przewidywalność:** znajome interfejsy i struktura między projektami.
- **Utrzymywalność:** kod zespołowy jest bardziej spójny i łatwiejszy do przeglądu.
- **Przenośność między frameworkami:** mniejszy vendor lock-in, gdy architektura opiera się na standardowych kontraktach.

3. **Najczęściej używane PSR**

- **PSR-1 / PSR-12** - podstawowy i rozszerzony styl kodowania.
- **PSR-3** - interfejs loggera (`LoggerInterface`).
- **PSR-4** - standard autoloadingu.
- **PSR-6 / PSR-16** - interfejsy cache.
- **PSR-7** - interfejsy komunikatów HTTP (Request/Response/Stream).
- **PSR-11** - interfejs kontenera.
- **PSR-15** - handlery żądań HTTP po stronie serwera i middleware.
- **PSR-18** - interfejs klienta HTTP.

4. **Praktyczny efekt w realnych projektach**

- Możesz podmieniać implementacje (na przykład logger/klient/kontener) bez przepisywania logiki biznesowej.
- Frameworki i pakiety szybciej integrują się dzięki wspólnym interfejsom.
- Narzędzia (lintery/analizatory statyczne/adaptery frameworkowe) łatwiej wdrożyć.

PSR to nie tylko przewodniki stylu; to kontrakty na poziomie architektury, które sprawiają, że nowoczesny ekosystem PHP jest kompozycyjny i długoterminowo utrzymywalny.

</details>

<details>
<summary>22. Czym jest PSR-7 (komunikaty HTTP)?</summary>

#### PHP

PSR-7 to standard, który definiuje interfejsy komunikatów HTTP w PHP: żądania, odpowiedzi, strumienie i przesłane pliki.

1. **Co standaryzuje PSR-7**

- `ServerRequestInterface` - przychodzące żądanie HTTP z kontekstu klient/serwer.
- `RequestInterface` - ogólne żądanie wychodzące.
- `ResponseInterface` - odpowiedź HTTP (status, nagłówki, body).
- `StreamInterface` - abstrakcja treści komunikatu.
- `UploadedFileInterface` - abstrakcja przesłanego pliku.
- `UriInterface` - reprezentacja URI.

2. **Dlaczego to ważne**

- Zapewnia wspólny kontrakt między frameworkami i bibliotekami.
- Umożliwia pipeline middleware i wielokrotnego użytku komponenty HTTP.
- Ogranicza vendor lock-in dzięki kodowaniu pod interfejsy, a nie konkretne klasy frameworka.

3. **Zasada niemutowalności**

Komunikaty PSR-7 są niemutowalne. Metody takie jak `withHeader()` zwracają nową instancję zamiast modyfikować oryginalny obiekt.

```php
$newResponse = $response
    ->withStatus(201)
    ->withHeader('Content-Type', 'application/json');
```

4. **Typowe użycie**

- W middleware i handlerach (często razem z PSR-15).
- W frameworkach API do parsowania żądań i generowania odpowiedzi.
- W klientach/serwerach HTTP, które wymieniają standaryzowane obiekty komunikatów.

5. **Praktyczna korzyść**

Komponent napisany pod PSR-7 zwykle można ponownie użyć w różnych ekosystemach (Slim, Laminas, mostki Symfony, Mezzio itd.) z minimalną adaptacją.

PSR-7 to kluczowa warstwa interoperacyjności dla obsługi komunikatów HTTP w nowoczesnych aplikacjach PHP.

</details>

<details>
<summary>23. Czym jest PSR-11 (kontener zależności)?</summary>

#### PHP

PSR-11 to standardowy interfejs dla kontenerów dependency injection w PHP. Definiuje, w jaki sposób kod aplikacji może pobierać serwisy z kontenera w sposób niezależny od frameworka.

1. **Główne interfejsy PSR-11**

- `Psr\Container\ContainerInterface`
- `Psr\Container\ContainerExceptionInterface`
- `Psr\Container\NotFoundExceptionInterface`

Główne metody:
- `get(string $id): mixed`
- `has(string $id): bool`

2. **Jaki problem rozwiązuje**

- Standaryzuje dostęp do kontenera między bibliotekami/frameworkami.
- Pozwala komponentom zależeć od wspólnego kontraktu zamiast od konkretnych implementacji kontenera.
- Poprawia interoperacyjność i przenośność.

3. **Prosty przykład użycia**

```php
use Psr\Container\ContainerInterface;

function run(ContainerInterface $container): void
{
    if ($container->has('logger')) {
        $logger = $container->get('logger');
        $logger->info('Started');
    }
}
```

4. **Ważna uwaga projektowa**

PSR-11 definiuje **jak odczytywać serwisy**, a nie jak je rejestrować/budować. API rejestracji jest zależne od konkretnego kontenera.

5. **Najlepsze praktyki**

- Preferuj wstrzykiwanie przez konstruktor w kodzie aplikacji.
- Bezpośrednie odczyty z kontenera stosuj głównie w warstwie infrastruktury/bootstrapu.
- Unikaj antywzorca Service Locator w logice domenowej/biznesowej.
- Tam, gdzie to możliwe, type-hintuj interfejsy zamiast konkretnych implementacji.

PSR-11 to minimalny, ale ważny standard, który ujednolica użycie kontenerów zależności w ekosystemie PHP.

</details>

<details>
<summary>24. Czym jest PSR-15 (middleware)?</summary>

#### PHP

PSR-15 to standard, który definiuje middleware po stronie serwera HTTP oraz handlery żądań w PHP. Działa razem z interfejsami komunikatów żądanie/odpowiedź z PSR-7.

1. **Główne interfejsy PSR-15**

- `Psr\Http\Server\MiddlewareInterface`
- `Psr\Http\Server\RequestHandlerInterface`

Kontrakty metod:
- Middleware: `process(ServerRequestInterface $request, RequestHandlerInterface $handler): ResponseInterface`
- Handler: `handle(ServerRequestInterface $request): ResponseInterface`

2. **Jak działa pipeline middleware**

- Żądanie wchodzi do łańcucha middleware.
- Każde middleware może:
  walidować/modyfikować żądanie, zakończyć przepływ odpowiedzią albo przekazać żądanie dalej.
- Finalny handler generuje odpowiedź.
- Odpowiedź może być modyfikowana w drodze powrotnej przez stos middleware.

3. **Typowe odpowiedzialności middleware**

- Uwierzytelnianie/autoryzacja
- CORS
- Logowanie/tracing
- Rate limiting
- Walidacja żądań
- Konwersja wyjątków na odpowiedzi

4. **Prosty przykład middleware**

```php
use Psr\Http\Message\ResponseInterface;
use Psr\Http\Message\ServerRequestInterface;
use Psr\Http\Server\MiddlewareInterface;
use Psr\Http\Server\RequestHandlerInterface;

final class AuthMiddleware implements MiddlewareInterface
{
    public function process(ServerRequestInterface $request, RequestHandlerInterface $handler): ResponseInterface
    {
        // check auth, then continue
        return $handler->handle($request);
    }
}
```

5. **Dlaczego PSR-15 ma znaczenie**

- Umożliwia ponowne użycie middleware między frameworkami/ekosystemami.
- Standaryzuje punkty rozszerzania cyklu życia żądania.
- Wspiera czystą separację przekrojowych odpowiedzialności.

PSR-15 dostarcza kontrakt interoperacyjności dla potoków HTTP opartych o middleware w nowoczesnych aplikacjach PHP.

</details>

<details>
<summary>25. Czym jest PSR-18 (klient HTTP)?</summary>

#### PHP

PSR-18 to standardowy interfejs dla klientów HTTP w PHP. Definiuje, jak kod aplikacji wysyła wychodzące żądania HTTP w sposób niezależny od implementacji.

1. **Główny kontrakt PSR-18**

- Główny interfejs: `Psr\Http\Client\ClientInterface`
- Główna metoda: `sendRequest(RequestInterface $request): ResponseInterface`
- Działa z obiektami żądań/odpowiedzi PSR-7.

2. **Jaki problem rozwiązuje**

- Oddziela logikę biznesową od konkretnych bibliotek klienta HTTP.
- Czyni integracje bardziej przenośnymi i łatwiejszymi do testowania.
- Umożliwia podmianę implementacji klienta bez przepisywania kodu serwisów.

3. **Podstawowe użycie**

```php
use Psr\Http\Client\ClientInterface;
use Psr\Http\Message\RequestFactoryInterface;

final class GitHubApi
{
    public function __construct(
        private ClientInterface $client,
        private RequestFactoryInterface $requests,
    ) {}

    public function getUser(string $login): string
    {
        $request = $this->requests->createRequest('GET', "https://api.github.com/users/{$login}");
        $response = $this->client->sendRequest($request);

        return (string) $response->getBody();
    }
}
```

4. **Wyjątki**

PSR-18 definiuje standardowe interfejsy wyjątków dla błędów klienta (błędy żądania, błędy sieci/transportu), co pozwala na spójną obsługę błędów między implementacjami.

5. **Najlepsze praktyki**

- Używaj type-hintu `ClientInterface` w serwisach.
- Buduj żądania przez fabryki PSR-17.
- Konfiguruj timeouty/retry/circuit-breakery w warstwie infrastruktury.
- Mockuj interfejs klienta w testach dla deterministycznego zachowania.

PSR-18 standaryzuje wychodzącą komunikację HTTP i jest kluczowym elementem interoperacyjnego, utrzymywalnego kodu integracyjnego w nowoczesnych aplikacjach PHP.

</details>

<details>
<summary>26. Czym są dependency injection i inversion of control?</summary>

#### PHP

Dependency Injection (DI) i Inversion of Control (IoC) to zasady architektoniczne do budowania luźno powiązanego, testowalnego kodu.

1. **Inversion of Control (IoC)**

IoC oznacza, że klasa nie tworzy i nie kontroluje swoich zależności bezpośrednio; ta kontrola jest przeniesiona na zewnątrz (do warstwy frameworka/kontenera/bootstrapu).

2. **Dependency Injection (DI)**

DI to konkretny sposób implementacji IoC: zależności są dostarczane (wstrzykiwane) z zewnątrz zamiast być tworzone przez `new` wewnątrz klasy.

3. **Dlaczego to ważne**

- Zmniejsza sprzężenie między komponentami.
- Poprawia testowalność (łatwy mocking/stubbing).
- Ułatwia rozszerzanie i refaktoryzację kodu.
- Wspiera czyste granice architektury.

4. **Bez DI (silne sprzężenie)**

```php
final class OrderService
{
    private Mailer $mailer;

    public function __construct()
    {
        $this->mailer = new Mailer();
    }
}
```

5. **Z DI (luźne sprzężenie)**

```php
interface MailerInterface
{
    public function send(string $to, string $message): void;
}

final class OrderService
{
    public function __construct(private MailerInterface $mailer) {}
}
```

6. **Typowe style DI**

- Wstrzykiwanie przez konstruktor (preferowane).
- Wstrzykiwanie przez metodę.
- Wstrzykiwanie przez setter/właściwość (mniej preferowane dla wymaganych zależności).

7. **Relacja do kontenerów**

Kontener DI automatyzuje tworzenie obiektów i wiązanie zależności, ale DI jest zasadą projektową niezależną od konkretnego kontenera.

DI + IoC to fundamenty nowoczesnych frameworków PHP i klucz do utrzymywalnych, skalowalnych baz kodu.

</details>

<details>
<summary>27. Czym są kontenery serwisów i jak działają?</summary>

#### PHP

Kontener serwisów (kontener DI) to komponent, który zarządza tworzeniem obiektów, wiązaniem zależności i cyklem życia w aplikacji.

1. **Co robi kontener**

- Przechowuje definicje/bindingi serwisów.
- Automatycznie rozwiązuje zależności (często przez refleksję i type hinty).
- Buduje grafy obiektów (serwis + wszystkie zagnieżdżone zależności).
- Zarządza czasem życia instancji (singleton/scoped/transient w zależności od frameworka).

2. **Dlaczego jest przydatny**

- Centralizuje konfigurację zależności.
- Usuwa powtarzalne, ręczne wiązanie przez `new ...`.
- Upraszcza podmianę implementacji (interfejs -> konkretna klasa).
- Poprawia utrzymywalność w dużych aplikacjach.

3. **Typowy przepływ**

- Rejestrujesz bindingi:
  `LoggerInterface` -> `MonologLogger`
- Prosisz kontener o serwis:
  `OrderService`
- Kontener buduje `OrderService`, rekurencyjnie rozwiązując wymagane argumenty konstruktora.

4. **Przykład koncepcyjny**

```php
$container->set(LoggerInterface::class, MonologLogger::class);
$container->set(OrderService::class, fn($c) => new OrderService($c->get(LoggerInterface::class)));

$service = $container->get(OrderService::class);
```

5. **Pojęcia czasu życia serwisu**

- **Singleton/shared:** jedna instancja używana ponownie.
- **Transient/factory:** nowa instancja przy każdym rozwiązaniu.
- **Scoped/request:** jedna instancja na zakres żądania (zależnie od frameworka).

6. **Najlepsze praktyki**

- Rejestruj abstrakcje (interfejsy), a nie klasy konkretne, tam gdzie to możliwe.
- Utrzymuj kod biznesowy/domenowy niezależny od kontenera.
- Domyślnie używaj wstrzykiwania przez konstruktor.
- Unikaj bezpośredniego wywoływania kontenera głęboko w logice domenowej (antywzorzec Service Locator).

Kontenery serwisów to narzędzia infrastrukturalne, które automatyzują zarządzanie zależnościami i utrzymują nowoczesne aplikacje PHP modułowymi oraz kompozycyjnymi.

</details>

<details>
<summary>28. Czym są middleware i cykl życia żądania we frameworkach?</summary>

#### PHP

W nowoczesnych frameworkach PHP middleware to warstwy, które przetwarzają żądania i odpowiedzi HTTP wokół głównej logiki tras/kontrolerów. Cykl życia żądania to pełna droga od przychodzącego żądania do finalnej odpowiedzi.

1. **Czym jest middleware**

- Komponent pipeline, który może:
  sprawdzić/zmodyfikować żądanie, przerwać przetwarzanie własną odpowiedzią albo przekazać sterowanie do następnej warstwy.
- W nowoczesnych ekosystemach często implementowany przez kontrakty w stylu PSR-15.

2. **Typowe odpowiedzialności middleware**

- Uwierzytelnianie i autoryzacja
- CORS
- Rate limiting
- Normalizacja/walidacja inputu
- Logowanie, tracing, metryki
- Obsługa wyjątków i kształtowanie odpowiedzi

3. **Typowy cykl życia żądania**

1. Żądanie HTTP trafia do serwera webowego (Nginx/Apache) i runtime PHP.
2. Bootstrap frameworka ładuje konfigurację, serwisy i trasy.
3. Startuje globalny pipeline middleware.
4. Trasa zostaje dopasowana i uruchamia się middleware specyficzne dla trasy.
5. Kontroler/handler wykonuje logikę biznesową.
6. Odpowiedź wraca przez stos middleware (post-processing).
7. Finalna odpowiedź jest wysyłana do klienta.

4. **Dlaczego ten model jest użyteczny**

- Oddziela przekrojowe odpowiedzialności od kontrolerów.
- Utrzymuje handlery tras skupione na logice biznesowej.
- Czyni zachowanie kompozycyjnym i wielokrotnego użytku.
- Zapewnia spójne punkty rozszerzeń dla polityk platformowych.

5. **Praktyczne wskazówki**

- Utrzymuj middleware skupione na jednej odpowiedzialności.
- Ustalaj kolejność middleware świadomie (na przykład obsługa błędów najbardziej zewnętrznie).
- Unikaj ciężkiej logiki biznesowej w middleware.
- Preferuj middleware bezstanowe tam, gdzie to możliwe.

Middleware + cykl życia żądania to kluczowe koncepcje architektoniczne stojące za czystym i przewidywalnym przetwarzaniem HTTP we frameworkach PHP.

</details>

<details>
<summary>29. Czym jest MVC i jak jest implementowane we frameworkach PHP?</summary>

#### PHP

MVC (Model-View-Controller) to wzorzec architektoniczny, który rozdziela odpowiedzialności aplikacji na warstwę danych/logiki biznesowej, renderowanie UI i orkiestrację żądań.

1. **Komponenty MVC**

- **Model** - logika domenowa/danych, reguły i interakcja z persystencją.
- **View** - warstwa prezentacji (szablony/formatowanie HTML/JSON).
- **Controller** - odbiera żądanie, koordynuje przypadki użycia, zwraca odpowiedź.

2. **Jak to działa we frameworkach PHP**

Typowy przepływ:
1. Router dopasowuje URL do akcji kontrolera.
2. Kontroler waliduje input i wywołuje warstwę domeny/serwisu/modelu.
3. Model/serwis pobiera lub modyfikuje dane.
4. Kontroler przekazuje wynik do widoku/szablonu albo zwraca odpowiedź API.
5. Framework emituje finalną odpowiedź HTTP.

3. **Przykładowe odpowiedzialności**

- Kontroler: `UserController@show($id)`
- Model/Serwis: pobranie użytkownika, zastosowanie reguł biznesowych
- Widok: render `user/show.blade.php` (lub zasób JSON)

4. **Dlaczego MVC jest użyteczne**

- Jasny podział odpowiedzialności.
- Łatwiejsze utrzymanie i testowanie.
- Lepsza współpraca zespołu (oddzielenie odpowiedzialności frontend/backend).
- Przewidywalna struktura projektu.

5. **Typowe pułapki**

- Rozbudowane kontrolery z logiką biznesową.
- Rozbudowane modele mieszające zbyt wiele odpowiedzialności.
- Silne sprzężenie między kontrolerami a szczegółami persystencji.

6. **Nowoczesna praktyka w PHP**

Wiele projektów używa MVC jako bazy, ale przenosi logikę biznesową do warstw serwisów/case’ów użycia, utrzymując kontrolery cienkie i widoki proste.

MVC pozostaje praktycznym fundamentem we frameworkach takich jak Laravel i aplikacjach w stylu Symfony, szczególnie gdy jest łączone z zasadami czystego warstwowania.

</details>

<details>
<summary>30. Czym jest architektura heksagonalna / clean architecture w PHP?</summary>

#### PHP

Architektura heksagonalna (Ports and Adapters) i Clean Architecture to podejścia, które utrzymują logikę biznesową niezależną od frameworków, baz danych i usług zewnętrznych.

1. **Główna idea**

- Reguły biznesowe są umieszczone w centrum (domena/przypadki użycia).
- Systemy zewnętrzne są traktowane jako wymienne adaptery.
- Zależności wskazują do wewnątrz: infrastruktura zależy od domeny, nie odwrotnie.

2. **Główne elementy składowe**

- **Warstwa domenowa**: encje, value objecty, reguły domenowe.
- **Warstwa aplikacyjna/przypadków użycia**: orkiestruje scenariusze biznesowe.
- **Porty (interfejsy)**: kontrakty dla potrzebnych możliwości (repozytoria, gatewaye, busy).
- **Adaptery**: konkretne implementacje (repozytorium MySQL, klient HTTP, publisher kolejki).
- **Warstwa dostarczania**: kontrolery HTTP/CLI/consumery, które wywołują przypadki użycia.

3. **Dlaczego to ma znaczenie**

- Framework albo baza danych mogą zostać zmienione z minimalnym wpływem na rdzeń logiki biznesowej.
- Przypadki użycia łatwiej testować w izolacji.
- Jasne granice redukują sprzężenie i długoterminowe ryzyko utrzymaniowe.

4. **Przykład zorientowany na PHP**

- `CreateOrderUseCase` zależy od `OrderRepositoryInterface` i `PaymentGatewayInterface`.
- Kontroler Laravel/Symfony wywołuje ten przypadek użycia.
- Repozytorium MySQL i adapter Stripe implementują interfejsy w warstwie infrastruktury.

5. **Struktura folderów (koncepcyjnie)**

- `src/Domain/...`
- `src/Application/...`
- `src/Infrastructure/...`
- `src/Interface/Http/...` (lub `Presentation/...`)

6. **Praktyczne wskazówki**

- Trzymaj klasy frameworka poza warstwą domenową.
- Wyrażaj granice przez interfejsy na styku aplikacji/domeny.
- Mapuj DTO request/response frameworka na granicach, a nie wewnątrz domeny.
- Zaczynaj prosto i wprowadzaj warstwy tam, gdzie złożoność to uzasadnia.

Architektura heksagonalna/Clean pomaga systemom PHP pozostać adaptowalnymi, testowalnymi i stabilnymi, gdy produkt i infrastruktura ewoluują.

</details>

<details>
<summary>31. Czym jest wzorzec Repository?</summary>

#### PHP

Repository to wzorzec, który abstrahuje dostęp do danych za interfejsem zorientowanym domenowo, dzięki czemu logika biznesowa pracuje na kolekcjach/agregatach zamiast bezpośrednio na szczegółach SQL/ORM.

1. **Główna idea**

- Warstwy domeny/aplikacji zależą od interfejsów repozytoriów.
- Warstwa infrastruktury dostarcza konkretne implementacje (PDO/Doctrine/Eloquent/API).
- Szczegóły persystencji pozostają poza logiką przypadków użycia.

2. **Co zwykle zapewnia Repository**

- Pobieranie encji/agregatów (`findById`, `findByCriteria`).
- Utrwalanie zmian (`save`, `remove`).
- Operacje zapytań wyrażone w terminach domenowych.

3. **Przykładowy interfejs**

```php
interface OrderRepositoryInterface
{
    public function getById(string $id): ?Order;
    public function save(Order $order): void;
}
```

4. **Dlaczego jest użyteczny**

- Oddziela logikę biznesową od technologii przechowywania danych.
- Poprawia testowalność (łatwe implementacje in-memory/mock).
- Wspiera granice architektoniczne (hexagonal/clean).
- Ułatwia migracje/refaktoryzacje przy zmianach persystencji.

5. **Typowe błędy**

- Zamiana repozytorium w generyczny „zrzut” CRUD bez intencji domenowej.
- Niepotrzebne duplikowanie wszystkich metod ORM 1:1.
- Umieszczanie logiki biznesowej w implementacji repozytorium.

6. **Praktyczne wskazówki**

- Trzymaj interfejsy repozytoriów na granicy domeny/aplikacji.
- Udostępniaj metody znaczące dla przypadków użycia, nie dla wnętrza bazy.
- Przy złożonym filtrowaniu używaj specifications/query objects, gdy to potrzebne.
- Niech repozytoria obsługują persystencję; orkiestrację trzymaj w serwisach/case’ach użycia.

Wzorzec Repository jest najbardziej wartościowy w średnich i dużych systemach PHP, gdzie trwałość logiki domenowej jest ważniejsza niż krótkoterminowa szybkość CRUD.

</details>

<details>
<summary>32. Czym są DTO i Value Objects?</summary>

#### PHP

DTO i Value Objects to różne wzorce, które często są używane razem w nowoczesnej architekturze PHP.

1. **DTO (Data Transfer Object)**

- Prosty obiekt używany do przekazywania ustrukturyzowanych danych między warstwami/procesami.
- Zwykle zawiera pola i minimalną albo żadną logikę biznesową.
- Pomaga unikać przekazywania surowych tablic przez granice warstw.

```php
final class CreateUserDto
{
    public function __construct(
        public string $email,
        public string $name,
    ) {}
}
```

2. **Value Object (VO)**

- Obiekt domenowy definiowany przez wartość, a nie tożsamość.
- Zwykle niemutowalny i samowalidujący.
- Hermetyzuje reguły domenowe dla konkretnego pojęcia (Email, Money, Currency itd.).

```php
final class Email
{
    public function __construct(public readonly string $value)
    {
        if (!filter_var($value, FILTER_VALIDATE_EMAIL)) {
            throw new InvalidArgumentException('Invalid email');
        }
    }
}
```

3. **Kluczowe różnice**

- **Cel**: DTO przenosi dane; VO modeluje znaczenie domenowe.
- **Logika**: DTO minimalna; VO może egzekwować niezmienniki.
- **Tożsamość**: DTO często incydentalna; VO porównywane po wartości.
- **Mutowalność**: DTO może być mutowalny/niemutowalny; VO zasadniczo powinien być niemutowalny.

4. **Kiedy używać którego**

- Używaj DTO na granicach (HTTP request/response, messaging, input/output warstwy aplikacyjnej).
- Używaj Value Objects wewnątrz modelu domenowego, aby bezpiecznie wyrażać zwalidowane pojęcia.

DTO poprawiają klarowność przepływu danych, a Value Objects poprawiają poprawność domenową i zapobiegają nieprawidłowym stanom.

</details>

<details>
<summary>33. Czym jest OOP w PHP?</summary>

#### PHP

OOP (Object-Oriented Programming) w PHP to paradygmat programowania, w którym kod jest organizowany wokół obiektów łączących dane (stan) i zachowanie (metody).

1. **Podstawowe koncepcje OOP**

- **Klasa**: szablon definiujący właściwości i metody.
- **Obiekt**: instancja klasy.
- **Enkapsulacja**: kontroluje dostęp do wnętrza (`public/protected/private`).
- **Dziedziczenie**: klasy potomne używają/rozszerzają zachowanie klasy bazowej.
- **Polimorfizm**: wspólne interfejsy z zamiennymi implementacjami.
- **Abstrakcja**: ujawnia istotne kontrakty, ukrywa szczegóły implementacji.

2. **Dlaczego OOP jest używane w PHP**

- Czytelnie modeluje pojęcia domenowe.
- Wspiera modułowy kod wielokrotnego użytku.
- Poprawia utrzymywalność w średnich i dużych codebase’ach.
- Naturalnie współpracuje z DI, interfejsami i architekturą frameworków.

3. **Podstawowy przykład**

```php
interface NotifierInterface
{
    public function send(string $message): void;
}

final class EmailNotifier implements NotifierInterface
{
    public function send(string $message): void
    {
        // send email
    }
}

final class AlertService
{
    public function __construct(private NotifierInterface $notifier) {}

    public function alert(string $message): void
    {
        $this->notifier->send($message);
    }
}
```

4. **Nowoczesne funkcje OOP w PHP**

- Typowane właściwości i strict types
- Interfejsy i klasy abstrakcyjne
- Traity do horyzontalnego reuse kodu
- Atrybuty, enumy, właściwości/klasy readonly
- Constructor property promotion

5. **Najlepsze praktyki**

- Gdy to możliwe, preferuj kompozycję zamiast dziedziczenia.
- Programuj pod interfejsy, nie pod klasy konkretne.
- Utrzymuj klasy skupione (single responsibility).
- Unikaj „god objects” z nadmiarem odpowiedzialności.

OOP w PHP jest fundamentem większości nowoczesnych frameworków i projektowania aplikacji zorientowanych domenowo.

</details>

<details>
<summary>34. Jaka jest różnica między interfejsem a klasą abstrakcyjną?</summary>

#### PHP

Zarówno interfejsy, jak i klasy abstrakcyjne definiują kontrakty, ale służą różnym celom projektowym.

1. **Interfejs**

- Definiuje wyłącznie sygnatury metod (kontrakt) i stałe.
- Nie ma stanu instancji (brak właściwości ze stanem runtime).
- Klasa może implementować wiele interfejsów.
- Fokus: kontrakt możliwości i polimorfizm.

```php
interface PaymentGatewayInterface
{
    public function charge(int $amount): bool;
}
```

2. **Klasa abstrakcyjna**

- Może zawierać zarówno metody abstrakcyjne, jak i metody zaimplementowane.
- Może mieć współdzielony stan/zachowanie (właściwości, chronione helpery, logikę konstruktora).
- Klasa może dziedziczyć tylko po jednej klasie abstrakcyjnej/bazowej.
- Fokus: częściowa implementacja + wspólne zachowanie bazowe.

```php
abstract class BaseGateway
{
    public function __construct(protected string $apiKey) {}

    abstract public function charge(int $amount): bool;

    protected function log(string $message): void
    {
        // shared logic
    }
}
```

3. **Kluczowe różnice**

- **Wielokrotne dziedziczenie typu**: wiele interfejsów, tylko jedna klasa rodzic.
- **Wspólny kod**: klasa abstrakcyjna tak, interfejs nie.
- **Sprzężenie**: interfejs zwykle luźniejsze; klasa abstrakcyjna wprowadza sprzężenie dziedziczenia.

4. **Kiedy co wybrać**

- Używaj **interfejsu**, gdy potrzebujesz zamiennych implementacji i jasnych kontraktów.
- Używaj **klasy abstrakcyjnej**, gdy implementacje współdzielą istotną logikę/stany bazowe.

5. **Praktyczna zasada**

Preferuj interfejsy na publicznych granicach architektury; klas abstrakcyjnych używaj jako narzędzia wewnętrznego reuse tam, gdzie dziedziczenie jest uzasadnione.

Interfejs = „co potrafi zrobić”, klasa abstrakcyjna = „jak jest częściowo zaimplementowana”.

</details>

<details>
<summary>35. Czym są traity i kiedy należy ich używać?</summary>

#### PHP

Traity w PHP to mechanizm horyzontalnego współdzielenia kodu: pozwalają klasom współużywać metody (oraz powiązane elementy) bez dziedziczenia.

1. **Czym jest trait**

- Jednostka kodu wielokrotnego użytku deklarowana słowem `trait`.
- Dołączana do klas przez `use`.
- Pomaga współdzielić zachowanie między niepowiązanymi hierarchiami klas.

```php
trait Timestampable
{
    public function touch(): void
    {
        $this->updatedAt = new DateTimeImmutable();
    }
}

final class Post
{
    use Timestampable;
}
```

2. **Kiedy traity są przydatne**

- Współdzielone zachowania przekrojowe (helpery logowania, timestampy, małe zachowania użytkowe).
- Reuse między klasami, które nie mogą mieć wspólnej klasy bazowej.
- Redukcja duplikacji, gdy kompozycja byłaby zbyt rozbudowana dla małych bloków zachowania.

3. **Rozwiązywanie konfliktów traitów**

Jeśli dwa traity definiują tę samą metodę, PHP zapewnia mechanizm rozwiązywania konfliktów:
- `insteadof` do wyboru jednej implementacji.
- `as` do aliasowania/zmiany nazwy metod.

4. **Ograniczenia i ryzyka**

- Traity mogą ukrywać sprzężenie i zacierać odpowiedzialności klas, jeśli są nadużywane.
- Duże „god traits” stają się trudne do testowania i utrzymania.
- To mechanizm dołączania kodu, a nie prawdziwe kontrakty polimorficzne.

5. **Najlepsze praktyki**

- Utrzymuj traity małe i skupione.
- Używaj traitów do współdzielenia zachowań, nie do modelowania domeny.
- Dla głównych granic architektury preferuj interfejsy + kompozycję.
- Unikaj przechowywania złożonego, mutowalnego współdzielonego stanu w traitach.

Traity to praktyczne narzędzie PHP do celowanego reuse, ale najlepiej działają jako lekkie uzupełnienie dobrego projektowania obiektowego, a nie jego zamiennik.

</details>

<details>
<summary>36. Czym są metody magiczne i kiedy są wywoływane?</summary>

#### PHP

Metody magiczne to specjalne metody PHP (z prefiksem `__`), które są automatycznie wywoływane przez silnik przy określonych zdarzeniach cyklu życia obiektu lub interakcji z nim.

1. **Metody magiczne cyklu życia obiektu**

- `__construct()` - wywoływana przy tworzeniu obiektu.
- `__destruct()` - wywoływana przy niszczeniu obiektu (lub na końcu skryptu).
- `__clone()` - wywoływana po sklonowaniu obiektu.

2. **Metody magiczne dostępu do właściwości**

- `__get($name)` - odczyt niedostępnej/niezdefiniowanej właściwości.
- `__set($name, $value)` - zapis do niedostępnej/niezdefiniowanej właściwości.
- `__isset($name)` - `isset()`/`empty()` na niedostępnej/niezdefiniowanej właściwości.
- `__unset($name)` - `unset()` na niedostępnej/niezdefiniowanej właściwości.

3. **Przechwytywanie wywołań metod**

- `__call($name, $arguments)` - wywołanie niedostępnej/niezdefiniowanej metody instancji.
- `__callStatic($name, $arguments)` - wywołanie niedostępnej/niezdefiniowanej metody statycznej.

4. **String/invocation/serializacja**

- `__toString()` - obiekt użyty jako string.
- `__invoke(...$args)` - obiekt użyty jak funkcja.
- `__serialize()` / `__unserialize()` - własna logika serializacji.

5. **Helpery eksportu stanu/debugowania**

- `__set_state(array $properties)` - wywoływana przy odtwarzaniu przez `var_export()`.
- `__debugInfo()` - własny output dla `var_dump()`.

6. **Prosty przykład**

```php
final class User
{
    private array $data = [];

    public function __get(string $name): mixed
    {
        return $this->data[$name] ?? null;
    }

    public function __set(string $name, mixed $value): void
    {
        $this->data[$name] = $value;
    }
}
```

7. **Najlepsze praktyki**

- Używaj metod magicznych świadomie, a nie jako domyślnej architektury.
- Utrzymuj zachowanie jawne i przewidywalne.
- Unikaj ukrywania błędów przez zbyt liberalne `__get/__set`.
- Tam, gdzie to możliwe, preferuj typowane właściwości/metody.

Metody magiczne są potężnymi punktami rozszerzeń, ale należy ich używać ostrożnie, bo przy nadużyciu obniżają czytelność kodu.

</details>

<details>
<summary>37. Czym jest late static binding?</summary>

#### PHP

Late Static Binding (LSB) w PHP pozwala rozwiązywać statyczne metody/właściwości na podstawie klasy wywoływanej w runtime, a nie tylko klasy, w której metoda została zdefiniowana.

1. **`self::` vs `static::`**

- `self::` jest wiązane z klasą, w której metoda jest zadeklarowana (early binding).
- `static::` jest rozwiązywane do klasy wywołującej w runtime (late static binding).

2. **Dlaczego to ważne**

- Umożliwia polimorficzne zachowanie w kontekście statycznym.
- Jest użyteczne w hierarchiach dziedziczenia, gdzie klasy potomne powinny kontrolować zwracaną klasę/wartości.
- Często wykorzystywane we wzorcach factory i API w stylu Active Record.

3. **Przykład**

```php
class BaseModel
{
    public static function table(): string
    {
        return static::TABLE; // late static binding
    }
}

class User extends BaseModel
{
    protected const TABLE = 'users';
}

class Order extends BaseModel
{
    protected const TABLE = 'orders';
}

echo User::table();  // users
echo Order::table(); // orders
```

Gdyby użyto `self::TABLE`, zachowanie byłoby na stałe związane z kontekstem deklaracji klasy bazowej.

4. **Powiązane słowo kluczowe**

- Typ zwracany `static` (`public static function make(): static`) także używa semantyki late static i zwraca typ klasy wywołującej.

5. **Praktyczne wskazówki**

- Używaj `static::`, gdy klasy potomne muszą dostosować zachowanie statyczne.
- Używaj `self::`, gdy zachowanie ma celowo pozostać stałe względem implementacji klasy bazowej.

Late static binding to ważna cecha OOP dla rozszerzalnych hierarchii klas w PHP.

</details>

<details>
<summary>38. Jak obiekty są obsługiwane w pamięci w PHP?</summary>

#### PHP

W PHP obiekty są zarządzane przez Zend Engine jako struktury alokowane na stercie, do których odwołują się uchwyty obiektów, z automatycznym zarządzaniem pamięcią przez zliczanie referencji i garbage collection.

1. **Model przechowywania obiektów**

- Instancje obiektów są alokowane w pamięci zarządzanej przez silnik (heap).
- Zmienne przechowują referencje (uchwyty) do wpisów obiektów, a nie pełne kopie obiektów.
- Przypisanie jednej zmiennej obiektowej do drugiej kopiuje uchwyt, nie stan obiektu.

```php
$a = new stdClass();
$a->x = 1;

$b = $a;      // ta sama referencja obiektu
$b->x = 2;

echo $a->x;   // 2
```

2. **Zliczanie referencji**

- Silnik śledzi, ile zvali referencjonuje wartość/obiekt.
- Gdy licznik spadnie do zera, pamięć może zostać zwolniona.
- Dla obiektów zwykle oznacza to wywołanie destruktora i cleanup obiektu.

3. **Garbage collector (GC)**

- Samo zliczanie referencji nie usuwa referencji cyklicznych.
- GC w PHP wykrywa i czyści cykliczne śmieci (na przykład grafy obiektów referujące się wzajemnie).

4. **Zachowanie klonowania**

- `clone` tworzy nową instancję obiektu (oddzielna tożsamość).
- `__clone()` może dostosować logikę stanu po klonowaniu.

5. **Niuans pass-by-reference**

- Przekazywanie obiektów do funkcji działa efektywnie przez uchwyt (zmiany obiektu są widoczne na zewnątrz).
- Zwykle nie trzeba używać `&`, aby modyfikować stan obiektu poza granicą funkcji.

6. **Implikacje wydajnościowe/pamięciowe**

- Duże grafy obiektów zwiększają presję na pamięć.
- Długowieczne referencje (statyczne cache, domknięcia, globalne kontenery) mogą opóźniać cleanup.
- Referencje cykliczne w długodziałających workerach należy monitorować, by unikać wzrostu podobnego do wycieków.

7. **Praktyczne wskazówki**

- Utrzymuj grafy obiektów celowe i ograniczone.
- W razie potrzeby jawnie `unset` dużych struktur tymczasowych w długodziałających procesach.
- Używaj narzędzi profilujących do analizy hotspotów pamięci.
- Uważaj na statyczne singletony/globalny stan w workerach/daemonach.

Obsługa pamięci obiektów w PHP jest wydajna dla typowych cykli requestów, ale procesy długodziałające wymagają świadomej dyscypliny pamięciowej.

</details>

<details>
<summary>39. Czym jest PDO i dlaczego jest preferowane?</summary>

#### PHP

PDO (PHP Data Objects) to warstwa abstrakcji dostępu do bazy danych w PHP, która zapewnia spójne API do pracy z wieloma silnikami baz danych.

1. **Co zapewnia PDO**

- Ujednolicony interfejs operacji DB (`MySQL`, `PostgreSQL`, `SQLite` itd.).
- Prepared statements i wiązanie parametrów.
- Wsparcie transakcji.
- Konfigurowalne tryby pobierania i obsługa błędów.

2. **Dlaczego PDO jest preferowane**

- **Przenośność:** ten sam styl kodowania dla różnych baz danych.
- **Bezpieczeństwo:** prepared statements redukują ryzyko SQL injection.
- **Utrzymywalność:** czystszy, standaryzowany kod dostępu do DB.
- **Kontrola:** jawne zachowanie transakcji i błędów.

3. **Podstawowy przykład**

```php
$pdo = new PDO(
    'mysql:host=localhost;dbname=app;charset=utf8mb4',
    'user',
    'pass',
    [
        PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
        PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
    ]
);

$stmt = $pdo->prepare('SELECT id, email FROM users WHERE id = :id');
$stmt->execute(['id' => 42]);
$user = $stmt->fetch();
```

4. **PDO vs bezpośrednie API specyficzne dla drivera**

- PDO daje wspólną abstrakcję i czystsze granice architektoniczne.
- API specyficzne dla drivera może oferować niszowe funkcje, ale ogranicza przenośność.

5. **Najlepsze praktyki**

- Zawsze włączaj tryb wyjątków (`PDO::ERRMODE_EXCEPTION`).
- Używaj prepared statements dla każdego wejścia zewnętrznego.
- Ustawiaj jawny charset w DSN (na przykład `utf8mb4`).
- Jawnie obsługuj transakcje przy wieloetapowych zapisach.

PDO jest preferowane we współczesnym PHP, ponieważ łączy bezpieczeństwo, przenośność i czytelne wzorce dostępu do bazy danych.

</details>

<details>
<summary>40. Czym są prepared statements i wiązanie parametrów?</summary>

#### PHP

Prepared statements to zapytania SQL kompilowane jako szablony z placeholderami, gdzie wartości są dostarczane oddzielnie przez wiązanie parametrów.

1. **Jak to działa**

- Krok 1: przygotuj SQL z placeholderami (`:email`, `?`).
- Krok 2: zbindowanie/wykonanie wartości osobno.
- Baza danych traktuje zbindowane wartości ściśle jako dane, a nie składnię SQL.

2. **Dlaczego to ważne**

- Podstawowa ochrona przed SQL injection.
- Czystszy i bezpieczniejszy kod zapytań.
- Lepsza obsługa typów danych i escapingu przez driver.
- Może poprawić wydajność przy wielokrotnym wykonywaniu zapytań (zależnie od DB/drivera).

3. **Przykład z nazwanymi placeholderami (PDO)**

```php
$stmt = $pdo->prepare(
    'SELECT id, email FROM users WHERE email = :email AND status = :status'
);

$stmt->execute([
    'email' => $email,
    'status' => $status,
]);
```

4. **Przykład z pozycjonowanymi placeholderami**

```php
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = ?');
$stmt->execute([$id]);
```

5. **Wiązanie z jawnymi typami**

```php
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = :id');
$stmt->bindValue(':id', $id, PDO::PARAM_INT);
$stmt->execute();
```

6. **Ważny niuans**

- Prepared statements chronią wartości, ale nie identyfikatory SQL (nazwy tabel/kolumn).
- Dynamiczne identyfikatory muszą być kontrolowane przez ścisłe allowlisty.

7. **Najlepsze praktyki**

- Używaj prepared statements dla każdego zapytania zawierającego input zewnętrzny.
- Unikaj konkatenacji stringów przy warunkach SQL.
- Utrzymuj szablony SQL czytelne i jawne.
- Łącz to z kontami DB o minimalnych uprawnieniach i granicami transakcji.

Prepared statements + wiązanie parametrów to standardowa, obowiązkowa podstawa bezpiecznego dostępu do bazy danych w PHP.

</details>

<details>
<summary>41. Jak działają transakcje w PHP?</summary>

#### PHP

Transakcje w PHP (przez PDO/MySQLi) grupują wiele operacji bazodanowych w jedną atomową jednostkę: albo wszystkie zmiany są zatwierdzane, albo wszystkie są wycofywane.

1. **Podstawowe operacje transakcyjne**

- `beginTransaction()` - rozpoczyna transakcję.
- `commit()` - trwale zapisuje wszystkie zmiany.
- `rollBack()` - anuluje wszystkie niezacommitowane zmiany.

2. **Dlaczego transakcje są potrzebne**

- Zapewniają spójność danych przy wieloetapowych zapisach.
- Zapobiegają częściowym aktualizacjom, gdy wystąpi błąd.
- Chronią niezmienniki biznesowe (na przykład debet i kredyt muszą się udać jednocześnie).

3. **Podstawowy przykład PDO**

```php
try {
    $pdo->beginTransaction();

    $stmt1 = $pdo->prepare('UPDATE accounts SET balance = balance - :amount WHERE id = :from');
    $stmt1->execute(['amount' => 100, 'from' => 1]);

    $stmt2 = $pdo->prepare('UPDATE accounts SET balance = balance + :amount WHERE id = :to');
    $stmt2->execute(['amount' => 100, 'to' => 2]);

    $pdo->commit();
} catch (Throwable $e) {
    if ($pdo->inTransaction()) {
        $pdo->rollBack();
    }
    throw $e;
}
```

4. **Izolacja i współbieżność**

- Poziom izolacji DB kontroluje widoczność/zachowanie blokad między równoległymi transakcjami.
- Typowe anomalie: dirty reads, non-repeatable reads, phantom reads.
- Poziom izolacji dobieraj według kompromisu spójność/wydajność.

5. **Praktyczne pułapki**

- Długie transakcje trzymają blokady i pogarszają współbieżność.
- Wywołania zewnętrznych API/sieci wewnątrz transakcji DB zwiększają okno awarii.
- Brak rollbacka przy wyjątkach może zostawić niespójny workflow.

6. **Najlepsze praktyki**

- Utrzymuj transakcje możliwie krótkie.
- Obejmuj nimi tylko operacje DB, które muszą być atomowe.
- Stosuj jawne obsługiwanie błędów i gwarancje rollbacka.
- Projektuj retry logic dla deadlocków/konfliktów serializacji tam, gdzie trzeba.

Transakcje są kluczowym mechanizmem niezawodności dla finansów, stanów magazynowych i innych workflow krytycznych dla integralności w systemach PHP.

</details>
