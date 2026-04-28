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

<details>
<summary>42. Czym jest ORM (Eloquent / Doctrine) i jakie ma kompromisy?</summary>

#### PHP

ORM (Object-Relational Mapping) to technika mapowania tabel/wierszy bazy danych na obiekty PHP, dzięki czemu w większości kodu aplikacji pracujesz na encjach domenowych zamiast na surowym SQL.

1. **Co daje ORM**

- Klasy encji/modeli mapowane do schematów DB.
- API/buildery zapytań zamiast ręcznego SQL dla typowych operacji.
- Obsługa relacji (`hasMany`, `belongsTo` itd.).
- Unit-of-work/śledzenie zmian (szczególnie w Doctrine).
- Migracje i narzędzia ekosystemowe w wielu frameworkach.

2. **Popularne ORM-y w PHP**

- **Eloquent (Laravel)**:
  styl Active Record, szybka produktywność, ekspresyjna składnia.
- **Doctrine ORM**:
  styl Data Mapper, bogate modelowanie domeny, silniejsze rozdzielenie odpowiedzialności.

3. **Korzyści**

- Szybszy development dla funkcji opartych na CRUD.
- Czystszy i bardziej czytelny kod persystencji w typowych scenariuszach.
- Łatwiejsze przechodzenie po relacjach i workflow zorientowany na modele.
- Scaffoldingi oparte na konwencjach i integracje ekosystemowe.

4. **Kompromisy / wady**

- Narzut abstrakcji i potencjalny koszt wydajnościowy.
- Ukryte/niejawne zapytania (problem N+1).
- Złożone SQL/raportowanie często nadal wymaga ręcznego SQL.
- Wzorce specyficzne dla ORM mogą zwiększać próg wejścia i lock-in.

5. **Kiedy ORM działa najlepiej**

- Aplikacje biznesowe z częstymi operacjami na cyklu życia encji.
- Zespoły, które cenią produktywność i utrzymywalny kod model-centric.

6. **Kiedy preferować raw SQL/query buildery**

- Ścieżki krytyczne wydajnościowo.
- Złożone zapytania analityczne/raportowe.
- Funkcje specyficzne dla danego silnika DB i precyzyjna kontrola SQL.

7. **Praktyczna strategia**

- Domyślnie używaj ORM dla typowych operacji domenowych.
- Profiluj i optymalizuj wąskie gardła.
- Łącz ORM z zoptymalizowanym SQL tam, gdzie to potrzebne (podejście hybrydowe).
- Jawnie kontroluj eager/lazy loading, aby uniknąć eksplozji liczby zapytań.

ORM to mnożnik produktywności w PHP, ale dobre inżynierowanie wymaga zrozumienia, gdzie abstrakcja pomaga, a gdzie lepsza jest niższiopoziomowa kontrola SQL.

</details>

<details>
<summary>43. Czym jest connection pooling i dlaczego jest ważny?</summary>

#### PHP

Connection pooling to technika, w której połączenia z bazą danych są ponownie wykorzystywane z zarządzanej puli zamiast być tworzone i zamykane przy każdej operacji.

1. **Dlaczego połączenia są kosztowne**

- Otwieranie połączeń DB obejmuje handshake sieciowy, uwierzytelnienie i alokację zasobów serwera.
- Częste ponowne łączenie zwiększa opóźnienia i obciążenie CPU po stronie aplikacji i DB.

2. **Co robi pooling**

- Utrzymuje zestaw otwartych połączeń wielokrotnego użytku.
- Przydziela istniejące połączenie do nadchodzącej pracy.
- Po użyciu zwraca je do puli do ponownego użycia przez kolejne requesty/joby.

3. **Dlaczego to ważne**

- Zmniejsza opóźnienia requestów.
- Poprawia throughput pod obciążeniem.
- Ogranicza churn połączeń DB i narzut.
- Stabilizuje zachowanie systemów o wysokiej współbieżności.

4. **Niuans kontekstu PHP**

- W klasycznym modelu requestowym PHP-FPM każdy proces workera ma izolowany cykl życia, więc pooling jest mniej oczywisty niż w runtime’ach długodziałających.
- Typowe praktyczne podejścia:
  połączenia trwałe (`PDO::ATTR_PERSISTENT` z ostrożnością),
  zewnętrzne poolery/proxy (na przykład PgBouncer dla PostgreSQL),
  workery długodziałające (RoadRunner/Swoole/consumery kolejek), gdzie reuse jest bardziej bezpośredni.

5. **Kompromisy / ryzyka**

- Należy wykrywać i recyklingować nieaktualne/uszkodzone połączenia.
- Złe rozmiarowanie puli może powodować contention albo przeciążenie DB.
- Połączenia trwałe mogą trzymać zasoby serwera dłużej, niż oczekiwano.

6. **Najlepsze praktyki**

- Ustawiaj rozsądne limity puli/połączeń zgodne z pojemnością DB.
- Używaj health checków i timeoutów połączeń.
- Monitoruj liczbę połączeń, czas oczekiwania i error rates.
- Utrzymuj zapytania wydajne; pooling nie naprawi wolnego SQL.

Connection pooling to kluczowa technika skalowania dla systemów PHP intensywnie korzystających z bazy danych, szczególnie pod stałym ruchem współbieżnym.

</details>

<details>
<summary>44. Jak strukturyzować skalowalną aplikację PHP?</summary>

#### PHP

Skalowalna aplikacja PHP jest budowana wokół jasnych granic, przewidywalnej architektury i gotowości operacyjnej na wzrost ruchu, zespołu oraz złożoności funkcji.

1. **Używaj granic warstw/modułów**

- Dziel według odpowiedzialności i domen biznesowych, nie tylko według folderów technicznych.
- Typowe warstwy:
  `Domain`, `Application/UseCases`, `Infrastructure`, `Interface/HTTP`.

2. **Utrzymuj logikę biznesową niezależną od frameworka**

- Umieszczaj kluczowe reguły w warstwie domeny/przypadków użycia.
- Utrzymuj kontrolery cienkie.
- Zależyj od interfejsów; adaptery DB/frameworka trzymaj w warstwie infrastruktury.

3. **Projektuj pod bezstanowe skalowanie horyzontalne**

- Unikaj lokalnego mutowalnego stanu w instancjach aplikacji.
- Przechowuj stan współdzielony w systemach zewnętrznych:
  DB, Redis, object storage, kolejki.
- Przygotuj sesje/cache do wdrożeń wielowęzłowych.

4. **Strategia danych i persystencji**

- Używaj repozytoriów/serwisów jako granic persystencji.
- Wcześnie stosuj indeksowanie i optymalizację zapytań.
- Wprowadzaj cache (aplikacyjny/zapytań/HTTP), gdy jest to uzasadnione.
- Read/write separation i partycjonowanie stosuj tylko, gdy to potrzebne.

5. **Asynchroniczność i przetwarzanie w tle**

- Przenieś niekrytyczne/wolne zadania do kolejek (maile, eksporty, powiadomienia, webhooki).
- Utrzymuj ścieżkę requestu szybką i deterministyczną.

6. **Skalowalność operacyjna**

- Konteneryzuj workloady (Docker/K8s/platformy zarządzane).
- Używaj health checków, ustrukturyzowanego logowania, metryk i tracingu.
- Dodaj rate limiting, timeouty, retry, circuit breakery.
- Buduj CI/CD z bezpieczną strategią rolloutu i rollbacku.

7. **Skalowalność codebase’u dla zespołów**

- Egzekwuj standardy kodowania i analizę statyczną.
- Utrzymuj modularne granice pakietów.
- Używaj testów integracyjnych i kontraktowych wokół ścieżek krytycznych.
- Dokumentuj decyzje architektoniczne (ADR) i kontrakty serwisów.

8. **Praktyczna ścieżka ewolucji**

- Zaczynaj od modularnego monolitu i silnych granic.
- Wydzielaj serwisy tylko wtedy, gdy jasno uzasadniają to ograniczenia skali/zespołu.

Skalowalność w PHP to przede wszystkim dyscyplina architektury + operacji, a nie wybór jednego frameworka.

</details>

<details>
<summary>45. Jak zarządzać konfiguracją (zmienne środowiskowe)?</summary>

#### PHP

W nowoczesnych aplikacjach PHP konfiguracja powinna być wyniesiona poza kod i dostarczana przez zmienne środowiskowe, zgodnie z zasadami 12-factor.

1. **Główna zasada**

- Trzymaj konfigurację poza kodem źródłowym.
- Traktuj środowisko jako źródło ustawień specyficznych dla wdrożenia:
  dane logowania DB, URL-e API, hosty cache, feature flagi itd.

2. **Typowy setup**

- Development: plik `.env` (ładowany przez framework/bootstrap).
- Produkcja: realne zmienne środowiskowe z platformy/orchestratora (nie `.env` w repo).

3. **Jak konsumować wartości**

- Odczytuj env raz w bootstrapie konfiguracji.
- Mapuj do typowanej struktury/obiektu konfiguracji.
- Wstrzykuj konfigurację do serwisów przez DI.

4. **Dobre praktyki**

- Rozdzielaj konfigurację per środowisko (`dev`, `staging`, `prod`) przez wartości env.
- Domyślne wartości dawaj tylko dla niesensytywnych ustawień lokalnego developmentu.
- Waliduj wymaganą konfigurację przy starcie i fail-fast, jeśli brakuje/ma błędną wartość.
- Utrzymuj klucze konfiguracji spójne i udokumentowane.

5. **Czego nie robić**

- Nie hardcoduj danych uwierzytelniających w kodzie.
- Nie commituj sekretów produkcyjnych do repozytorium.
- Nie wywołuj `getenv()` losowo w logice domenowej.
- Nie mieszaj logiki biznesowej z logiką ładowania konfiguracji.

6. **Praktyczny wzorzec**

Używaj centralnych plików konfiguracyjnych, które pobierają wartości z env, na przykład:
- `config/database.php`
- `config/cache.php`
- `config/app.php`

Następnie wstrzykuj rozwiązaną konfigurację do zależnych serwisów.

7. **Uwaga bezpieczeństwa**

Zmienne środowiskowe są lepsze niż hardkodowane sekrety, ale nadal są wrażliwe:
ograniczaj dostęp, unikaj logowania pełnych wartości i łącz to z dedykowanymi secret managerami dla krytycznych danych.

Obsługa konfiguracji przez zmienne środowiskowe utrzymuje aplikacje PHP przenośnymi, bezpiecznymi i spójnymi między środowiskami.

</details>

<details>
<summary>46. Jak zarządzać sekretami (Vault, AWS Secrets Manager)?</summary>

#### PHP

Zarządzanie sekretami to praktyka bezpiecznego przechowywania, rotacji i dostępu do wrażliwych danych (klucze API, hasła DB, tokeny, certyfikaty) poza kodem aplikacji.

1. **Dlaczego potrzebne są dedykowane secret managery**

- Zapobiegają wyciekom sekretów do repozytorium/historii.
- Centralizują kontrolę dostępu i audyt.
- Umożliwiają bezpieczną rotację bez redeployu kodu.
- Ograniczają ryzyko operacyjne względem zwykłych plików `.env`.

2. **Popularne narzędzia**

- **HashiCorp Vault**: dynamiczne sekrety, lease’y, dostęp oparty o polityki, mocne możliwości audytowe.
- **AWS Secrets Manager**: zarządzane przechowywanie/rotacja sekretów zintegrowane z IAM i usługami AWS.
- (Często też: cloud-native parameter stores lub rozwiązania oparte o KMS.)

3. **Rekomendowany przepływ sekretów**

1. Tożsamość aplikacji jest ustalana (rola IAM, workload identity, metoda auth Vaulta).
2. Aplikacja pobiera wymagane sekrety przy starcie (lub on-demand z cache).
3. Sekrety są trzymane w pamięci tylko tak długo, jak to potrzebne.
4. Zdarzenia rotacji są obsługiwane bez hardkodowanych wartości.

4. **Najlepsze praktyki**

- Nigdy nie commituj sekretów do gita (także w plikach przykładowych z realnymi wartościami).
- Stosuj polityki least-privilege per serwis/środowisko.
- Rotuj sekrety regularnie i po incydentach.
- Loguj metadane dostępu, nigdy wartości sekretów.
- Rozdzielaj sekrety per środowisko (`dev/staging/prod`) i zakres serwisu.
- Gdy to możliwe, używaj krótkowiecznych poświadczeń (dynamiczne dane DB/tokeny).

5. **Wzorzec integracji w PHP**

- Pobieraj sekrety w warstwie bootstrap/infrastructure.
- Mapuj je do typowanych obiektów konfiguracji.
- Wstrzykuj konfigurację/sekrety do zależnych serwisów przez DI.
- Dodaj strategię fallback i retry na wypadek awarii secret managera.

6. **Aspekty operacyjne**

- Cache’uj sekrety z TTL, aby ograniczyć opóźnienia i limity API.
- Zaplanuj zachowanie bootstrapa, gdy backend sekretów jest chwilowo niedostępny.
- Testuj procedurę rotacji na stagingu przed rolloutem na produkcję.

Użycie Vault/AWS Secrets Manager zmienia obsługę sekretów z ad-hoc zmiennych środowiskowych w kontrolowany proces bezpieczeństwa odpowiedni dla produkcyjnych systemów PHP.

</details>

<details>
<summary>47. Czym jest 12-factor app w kontekście PHP?</summary>

#### PHP

12-factor app to zestaw cloud-native zasad inżynierskich do budowy przenośnych, skalowalnych i utrzymywalnych usług. W PHP te zasady pomagają przejść od „aplikacji związanych z serwerem” do nowoczesnych, łatwo wdrażalnych usług.

1. **Codebase**

- Jedna codebase utrzymywana w kontroli wersji.
- Wiele wdrożeń (`dev/staging/prod`) z tej samej codebase.

2. **Dependencies**

- Deklaruj zależności jawnie w `composer.json`.
- Unikaj polegania na globalnie zainstalowanych pakietach systemowych.

3. **Config**

- Trzymaj konfigurację w zmiennych środowiskowych, nie w kodzie.
- Trzymaj sekrety i wartości specyficzne dla środowiska poza repozytorium.

4. **Backing services**

- Traktuj DB, cache, kolejkę, object storage jako podłączone zasoby.
- Uzyskuj do nich dostęp przez config/URL-e, aby można je było podmieniać per środowisko.

5. **Rozdzielenie build, release, run**

- Buduj artefakt jeden raz.
- Promuj ten sam artefakt przez kolejne środowiska.
- Trzymaj konfigurację runtime oddzielnie od builda.

6. **Procesy**

- Uruchamiaj aplikację jako bezstanowe procesy.
- Trwały stan przechowuj w usługach zewnętrznych (DB/Redis/S3/itd.).

7. **Port binding i współbieżność**

- Wystawiaj usługi przez punkty wejścia HTTP/runtime.
- Skaluj przez replikację procesów/kontenerów, a nie tylko tuning wertykalny.

8. **Disposability i parity**

- Szybki startup/shutdown dla bezpiecznych deployów i autoskalowania.
- Utrzymuj środowiska dev/staging/prod możliwie podobne.

9. **Logi i zadania administracyjne**

- Traktuj logi jako strumienie zdarzeń (stdout/agregatory).
- Uruchamiaj zadania admin/migracje jako jednorazowe procesy używające tej samej codebase.

10. **Praktyczne implikacje specyficzne dla PHP**

- Używaj Composer + konfiguracja env + stan zewnętrzny.
- Runtime przyjazny kontenerom (PHP-FPM/workery CLI).
- Workery kolejek dla zadań w tle.
- Pipeline CI/CD z niemutowalnymi artefaktami.

Zastosowanie zasad 12-factor w PHP poprawia niezawodność wdrożeń, skalowalność operacyjną i długoterminową utrzymywalność.

</details>

<details>
<summary>48. Czym jest konteneryzacja (Docker) w aplikacjach PHP?</summary>

#### PHP

Konteneryzacja pakuje aplikację PHP wraz z zależnościami runtime do przenośnego obrazu, dzięki czemu działa ona spójnie lokalnie, w CI, na stagingu i na produkcji.

1. **Co Docker daje aplikacjom PHP**

- Powtarzalny runtime (wersja PHP, rozszerzenia, biblioteki systemowe).
- Zgodność środowiska między maszynami deweloperów a produkcją.
- Łatwiejsze wdrożenia, rollback i skalowanie.
- Izolację między usługami (aplikacja, DB, cache, kolejka, worker).

2. **Typowy konteneryzowany stack PHP**

- Kontener PHP-FPM (runtime aplikacji)
- Kontener Nginx/Apache (serwer web)
- Oddzielne kontenery dla DB/Redis/workerów kolejek/zadań cron

3. **Podstawowy wzorzec Dockerfile**

```dockerfile
FROM php:8.4-fpm-alpine

RUN docker-php-ext-install pdo pdo_mysql opcache
WORKDIR /var/www/html

COPY . .
RUN php -v
```

4. **Dlaczego to ważne dla skalowalności**

- Skalowanie horyzontalne staje się prostsze (replikacja kontenerów).
- Niemutowalne wdrożenia oparte o obrazy redukują drift/mismatch konfiguracji.
- Naturalnie współpracuje z platformami orkiestracji (Kubernetes, ECS, Nomad).

5. **Najlepsze praktyki**

- Używaj małych obrazów bazowych i buildów wieloetapowych.
- Przypinaj wersje obrazów/tagów dla powtarzalności.
- Trzymaj obrazy bezstanowe; dane trwałe przechowuj na zewnątrz.
- Wstrzykuj config/sekrety przez env/secret managery, nie „wypiekaj” ich w obrazie.
- Uruchamiaj health checki i wystawiaj ustrukturyzowane logi do stdout/stderr.

6. **Typowe pułapki**

- Uruchamianie wszystkiego w jednym kontenerze (web + DB + kolejka) na produkcji.
- Zapisywanie trwałych danych aplikacji do filesystemu kontenera.
- Duże obrazy z niepotrzebnymi narzędziami buildowymi w warstwie runtime.

Konteneryzacja to kluczowa praktyka nowoczesnych operacji PHP, bo standaryzuje zachowanie runtime i poprawia wdrażalność na skali.

</details>

<details>
<summary>49. Czym jest OPcache i jak poprawia wydajność?</summary>

#### PHP

OPcache to wbudowany cache bytecode PHP, który przechowuje skompilowany bytecode skryptów we współdzielonej pamięci, dzięki czemu PHP nie musi parsować i kompilować tych samych plików przy każdym requestcie.

1. **Jaki problem rozwiązuje OPcache**

- Bez OPcache każdy request wielokrotnie wykonuje:
  odczyt pliku PHP -> parsowanie -> kompilacja do opcode’ów -> wykonanie.
- Ta powtarzalna kompilacja zwiększa narzut CPU i opóźnienia.

2. **Jak OPcache poprawia wydajność**

- Skompilowane opcode’y są cache’owane w pamięci i używane ponownie między requestami.
- Redukuje zużycie CPU i czas requestu.
- Zwiększa throughput pod obciążeniem.
- Poprawia czas startu frameworków z wieloma plikami.

3. **Typowy setup produkcyjny**

- Włącz OPcache w runtime PHP (`opcache.enable=1`).
- Dostrań limity pamięci i liczby plików:
  `opcache.memory_consumption`, `opcache.max_accelerated_files`.
- Wyłącz walidację timestampów dla niemutowalnych artefaktów release:
  `opcache.validate_timestamps=0` (z resetem cache wyzwalanym przy deployu).

4. **Często używane ustawienia**

- `opcache.enable`
- `opcache.memory_consumption`
- `opcache.max_accelerated_files`
- `opcache.interned_strings_buffer`
- `opcache.validate_timestamps`
- `opcache.revalidate_freq`

5. **Aspekty wdrożeniowe**

- Gdy kod się zmienia, cache’owany bytecode musi zostać odświeżony.
- W niemutowalnych/kontenerowych deployach zwykle wystarczy restart workerów PHP.
- W mutowalnych deployach używaj kontrolowanej strategii unieważniania/restartu.

6. **Najlepsze praktyki**

- Zawsze używaj OPcache na produkcji.
- Monitoruj cache hit rate, zużycie pamięci i restarty.
- Dobieraj rozmiar cache do wzrostu codebase’u.
- Łącz OPcache z cache aplikacyjnym/bazodanowym dla pełnych zysków wydajnościowych.

OPcache to jedna z funkcji o najwyższym wpływie i najniższym koszcie wdrożenia dla wydajności środowisk produkcyjnych PHP.

</details>

<details>
<summary>50. Czym jest JIT w PHP i kiedy jest użyteczny?</summary>

#### PHP

JIT (Just-In-Time compilation) w PHP to optymalizacja silnika, która kompiluje wybrane opcode’y Zend do natywnego kodu maszynowego w runtime.

1. **Co robi JIT**

- Normalny przepływ PHP: skrypt -> opcode’y -> wykonanie przez interpreter.
- Z JIT: gorące ścieżki kodu mogą być kompilowane do kodu natywnego i wykonywane szybciej.

2. **Gdzie JIT może pomóc**

- Obciążenia CPU-intensive:
  ciężka matematyka, pętle, przetwarzanie danych, algorytmy obliczeniowe.
- Długodziałające workery CLI i wyspecjalizowane zadania obliczeniowe.

3. **Gdzie JIT często daje niewielką korzyść**

- Typowe aplikacje webowe zdominowane przez I/O:
  zapytania do bazy, wywołania sieciowe, dostęp do cache, renderowanie szablonów.
- W wielu workloadach CRUD/API OPcache i optymalizacja zapytań mają większe znaczenie niż JIT.

4. **Relacja do OPcache**

- JIT jest zbudowany na infrastrukturze OPcache.
- OPcache zwykle daje największy bazowy zysk dla większości aplikacji.
- JIT to dodatkowa warstwa optymalizacji dla kodu CPU-bound.

5. **Praktyczne wskazówki**

- Włącz i porównaj benchmarki before/after na rzeczywistym workloadzie.
- Nie zakładaj globalnych przyspieszeń dla wszystkich typów requestów.
- Najpierw priorytetyzuj usuwanie realnych bottlenecków:
  wolny SQL, zapytania N+1, nadmiarowe wywołania sieciowe, nieefektywny caching.

6. **Reguła kciuka**

- Dla klasycznych backendów webowych: wpływ JIT zwykle jest umiarkowany.
- Dla obliczeniowo ciężkich workloadów PHP: JIT może dać znaczące usprawnienia.

JIT jest użytecznym narzędziem optymalizacji, ale jego wartość silnie zależy od profilu obciążenia.

</details>

<details>
<summary>51. Czym jest lazy loading i gdzie jest używany?</summary>

#### PHP

Lazy loading to technika, w której dane lub obiekty są ładowane dopiero wtedy, gdy są faktycznie potrzebne, zamiast ładowania wszystkiego z góry.

1. **Główna idea**

- Opóźnij kosztowną inicjalizację do pierwszego użycia.
- Zmniejsz początkowe zużycie pamięci i czas startu.
- Płać koszt tylko za ścieżki, które naprawdę są używane.

2. **Gdzie lazy loading jest używany w PHP**

- Relacje ORM (proxy relacji Doctrine/Eloquent).
- Inicjalizacja serwisów w kontenerach DI (deferred services).
- Duże konfiguracje/zasoby ładowane na żądanie.
- Przetwarzanie strumieni/plików, gdzie fragmenty są ładowane progresywnie.

3. **Typowy przykład ORM**

- Encja `User` jest załadowana.
- `User->orders` nie jest pobierane od razu.
- Pierwszy dostęp do zamówień wyzwala zapytanie SQL.

4. **Korzyści**

- Szybsza odpowiedź początkowa w wielu use case’ach.
- Mniejszy footprint pamięci, gdy nie wszystkie dane są wymagane.
- Lepsza skalowalność dla złożonych grafów obiektów.

5. **Kompromisy i ryzyka**

- Ukryte zapytania mogą powodować problemy wydajnościowe N+1.
- Wzorce dostępu stają się mniej jawne.
- Lazy loading w ciasnych pętlach może eksplodować liczbą round-tripów DB.

6. **Najlepsze praktyki**

- Używaj eager loading, gdy wiesz, że dane powiązane będą potrzebne.
- Profiluj liczbę zapytań i opóźnienia.
- Utrzymuj granice lazy loading jawne w warstwie repozytorium/zapytań.
- Unikaj lazy loadingu wewnątrz pętli serializacji/outputu.

7. **Reguła kciuka**

- Używaj lazy loading dla opcjonalnych lub rzadko używanych zależności/danych.
- Używaj eager loading dla przewidywalnie i często używanych danych powiązanych.

Lazy loading to silna technika optymalizacji wydajności, ale tylko wtedy, gdy jest połączona z widocznością zachowania zapytań i świadomą strategią ładowania.

</details>

<details>
<summary>52. Jakie są typowe bottlenecki wydajności w PHP?</summary>

#### PHP

Większość problemów wydajnościowych PHP nie wynika z samego języka, tylko z nieefektywnego I/O, wzorców zapytań i decyzji architektonicznych.

1. **Bottlenecki bazodanowe (najczęstsze)**

- Zapytania N+1 przy użyciu ORM.
- Brak indeksów lub słabe plany zapytań.
- Nadmierne pobieranie danych (`SELECT *`, gdy niepotrzebne).
- Długie transakcje i contention na blokadach.

2. **Sieć i zewnętrzne I/O**

- Wolne API zewnętrzne bez timeoutów/retry.
- Zbyt wiele synchronicznych wywołań wychodzących w ścieżce requestu.
- Brak circuit breakerów/fallbacków.

3. **Nieefektywności na poziomie aplikacji**

- Ciężka logika biznesowa wykonywana przy każdym requestcie.
- Ponowne obliczanie kosztownych wyników zamiast cache’owania.
- Nadmierna serializacja/deserializacja lub przetwarzanie dużych payloadów.

4. **Narzut autoload/bootstrap**

- Duży bootstrap frameworka dla trywialnych endpointów.
- Zbyt wiele ładowanych klas/providerów konfiguracji.
- Błędnie skonfigurowany OPcache.

5. **Narzut filesystemu i logowania**

- Częste zapisy dyskowe w ścieżce requestu.
- Blokujące/zbyt gadatliwe logowanie bez async processing.
- Wolne wolumeny storage w kontenerach/VM-ach.

6. **Presja pamięci**

- Duże kolekcje in-memory i nieograniczone tablice.
- Nieefektywne pętle na ogromnych zbiorach danych.
- Długodziałające workery nieintencjonalnie trzymające referencje.

7. **Brak/nieefektywny caching**

- Brak cache dla danych read-heavy.
- Zła strategia unieważniania cache powodująca stale/frequent misses.
- Cache stampede pod obciążeniem.

8. **Jak podejść systemowo**

- Profiluj przed optymalizacją.
- Najpierw priorytetyzuj najgorętsze endpointy/zapytania.
- Dodaj optymalizację zapytań + caching + async offloading.
- Monitoruj p95/p99 latency, czas DB, cache hit ratio i error rates.

W systemach PHP najszybsze zyski najczęściej dają tuning zapytań, strategia cache i redukcja synchronicznego I/O w ścieżce requestu.

</details>

<details>
<summary>53. Jak profilować aplikację PHP?</summary>

#### PHP

Profilowanie to proces mierzenia, gdzie faktycznie zużywany jest czas wykonania, CPU, pamięć i I/O, aby optymalizacja opierała się na danych, a nie zgadywaniu.

1. **Co mierzyć najpierw**

- Request latency (p50/p95/p99)
- Czas DB i liczba zapytań
- Czas wywołań zewnętrznych API
- Zużycie pamięci i peak usage
- Najgorętsze funkcje/ścieżki kodu

2. **Popularne narzędzia profilowania PHP**

- **Blackfire** - profilowanie przyjazne produkcji i rekomendacje wydajnościowe.
- **Xdebug (tryb profiler)** - szczegółowe trace’y/callgrind do analizy lokalnej.
- **Rodzina Tideways/XHProf** - profilowanie na poziomie funkcji z opcjami niskiego narzutu.
- **Narzędzia APM** (Datadog/New Relic/itd.) do rozproszonej widoczności requestów.

3. **Praktyczny workflow profilowania**

1. Odtwórz wolny endpoint/job na realistycznych danych.
2. Zbierz trace profilowania.
3. Zidentyfikuj największych „kontrybutorów” (DB, zewnętrzne I/O, funkcje CPU-heavy).
4. Optymalizuj jedno wąskie gardło naraz.
5. Profiluj ponownie i porównaj metryki.

4. **Co zwykle wychodzi jako hotspoty**

- Zapytania ORM typu N+1
- Brak indeksów / kosztowne skany SQL
- Powtarzana serializacja i przetwarzanie dużych payloadów
- Synchroniczne wywołania sieciowe w ścieżce requestu
- Nadmierny narzut frameworka/bootstrapu

5. **Fokus profilowania pamięci**

- Duże tablice/kolekcje ładowane jednorazowo
- Długowieczne referencje w workerach
- Niepotrzebne grafy obiektów i duplikacja danych

6. **Najlepsze praktyki**

- Profiluj w środowiskach zbliżonych do produkcji.
- Benchmarkuj przed i po każdej optymalizacji.
- Śledź regresje w CI/CD przez budżety wydajnościowe dla krytycznych endpointów.
- Łącz profilowanie kodu z profilowaniem DB (`EXPLAIN`, slow query logs).

Profilowanie zamienia tuning wydajności w mierzalny proces inżynierski i jest najbardziej niezawodnym sposobem bezpiecznego przyspieszania aplikacji PHP.

</details>

<details>
<summary>54. Jak działa caching (Redis, Memcached)?</summary>

#### PHP

Caching przechowuje w szybkim storage (zwykle w pamięci) dane już obliczone lub często odczytywane, aby uniknąć powtarzania kosztownych operacji, takich jak zapytania DB czy ciężkie obliczenia.

1. **Jak działa caching (podstawowy przepływ)**

1. Aplikacja dostaje request o dane.
2. Sprawdza cache po kluczu.
3. Jeśli hit: szybko zwraca wartość z cache.
4. Jeśli miss: ładuje ze źródła (DB/API), zapisuje do cache z TTL i zwraca wartość.

2. **Popularne backendy cache**

- **Redis**:
  in-memory data store z bogatymi strukturami danych, opcjami persystencji, pub/sub i funkcjami rozproszonymi.
- **Memcached**:
  prosty rozproszony in-memory cache klucz-wartość, skupiony na szybkim efemerycznym cache’owaniu.

3. **Typowe use case’y cache w PHP**

- Cache wyników zapytań
- Przechowywanie sesji
- Cache odpowiedzi/fragmentów
- Liczniki rate limitingu
- Blokady i klucze idempotencyjne
- Dane referencyjne obliczeniowe/konfiguracyjne

4. **Ważne koncepcje projektowania cache**

- **Strategia kluczy**: przewidywalny namespacing i wersjonowanie (`user:42:v2`).
- **TTL**: dobieraj wygasanie do zmienności danych.
- **Unieważnianie**: jawne invalidation przy zapisach, gdy świeżość ma znaczenie.
- **Model spójności**: akceptuj eventual consistency tam, gdzie to odpowiednie.

5. **Typowe pułapki**

- Cache stampede (wiele równoległych missów).
- Nieświeże dane przez słabą strategię unieważniania.
- Zbyt duże wartości i słabe projektowanie kluczy.
- Traktowanie cache jako źródła prawdy.

6. **Najlepsze praktyki**

- Cache’uj tylko kosztowne/częste odczyty.
- Używaj krótkich, sensownych TTL i jittera, by ograniczyć zsynchronizowane wygasanie.
- Dodawaj ochronę przed stampede (locki, request coalescing, stale-while-revalidate).
- Monitoruj hit rate, latency, eviction i zużycie pamięci.
- Trzymaj DB jako source of truth; cache jest warstwą przyspieszającą.

Caching Redis/Memcached to jeden z najskuteczniejszych sposobów redukcji opóźnień i obciążenia bazy danych w produkcyjnych systemach PHP.

</details>

<details>
<summary>55. Czym jest przetwarzanie asynchroniczne w PHP?</summary>

#### PHP

Przetwarzanie asynchroniczne oznacza przeniesienie wolnych lub niekrytycznych zadań poza synchroniczny przepływ HTTP requestu, aby użytkownik otrzymywał szybką odpowiedź, a praca w tle była wykonywana osobno.

1. **Dlaczego async jest potrzebny**

- Cykle request-response powinny być krótkie.
- Niektóre operacje są kosztowne:
  e-maile, przetwarzanie plików, generowanie raportów, wywołania zewnętrznych API.
- Robienie tego wszystkiego inline zwiększa latency i wpływ awarii.

2. **Jak to działa w systemach PHP**

1. Główna aplikacja dostaje request.
2. Krytyczny stan jest szybko zapisywany.
3. Job/event w tle trafia do kolejki.
4. Proces worker konsumuje i wykonuje zadanie asynchronicznie.

3. **Typowe workloady async**

- Powiadomienia e-mail/SMS/push
- Przetwarzanie mediów (obrazy/wideo/PDF)
- Importy/eksporty danych
- Dostarczanie/retry webhooków
- Aktualizacje indeksu wyszukiwania
- Przetwarzanie analityki/zdarzeń

4. **Korzyści**

- Niższa latency widoczna dla użytkownika.
- Lepsza odporność (retry, dead-letter queues).
- Lepszy throughput dzięki odsprzęgleniu ciężkich zadań.
- Czytelniejsze rozdzielenie pracy online vs offline.

5. **Kompromisy**

- Dodatkowa złożoność operacyjna (kolejki/workery/monitoring).
- Eventual consistency między zapisem a efektami ubocznymi.
- Potrzeba idempotency i handlerów bezpiecznych na retry.

6. **Najlepsze praktyki**

- Utrzymuj payloady jobów minimalne (ID, nie pełne obiekty).
- Twórz handlery idempotentne.
- Konfiguruj retry/backoff i obsługę dead-letter.
- Monitoruj queue depth, worker lag i failure rate.
- Jasno określaj, które zadania są sync-krytyczne, a które async-deferred.

W architekturze PHP przetwarzanie asynchroniczne to kluczowa technika skalowania doświadczenia użytkownika i niezawodności pod realnym obciążeniem produkcyjnym.

</details>

<details>
<summary>56. Czym są kolejki (RabbitMQ, Kafka, kolejki Redis)?</summary>

#### PHP

Kolejki to mechanizmy messagingowe używane do odsprzęgania producentów i konsumentów, umożliwiające przetwarzanie asynchroniczne, buforowanie oraz niezawodne wykonywanie zadań w tle.

1. **Podstawowa koncepcja kolejki**

- Producent publikuje wiadomość/job.
- Broker przechowuje ją tymczasowo.
- Konsument/worker przetwarza ją później.
- Dzięki temu ciężka praca wypada z synchronicznego przepływu requestu.

2. **Dlaczego kolejki są ważne**

- Wygładzają piki ruchu (buforowanie).
- Poprawiają czas odpowiedzi (offload zadań w tle).
- Zwiększają niezawodność dzięki retry i obsłudze dead-letter.
- Odsprzęgają serwisy i komponenty.

3. **Popularne technologie kolejek w PHP**

- **RabbitMQ**:
  klasyczny broker wiadomości, silne wzorce routingu, acknowledgements, retry.
- **Kafka**:
  rozproszony event log, wysokoprzepustowe stream processing, wiadomości możliwe do odtworzenia.
- **Kolejki oparte o Redis** (na przykład kolejki Laravel):
  proste i szybkie dla wielu zadań backgroundowych na poziomie aplikacji.

4. **Typowe use case’y kolejek w PHP**

- Wysyłka e-maili/SMS/push
- Dostarczanie webhooków
- Przetwarzanie plików/obrazów/wideo
- Indeksowanie wyszukiwania
- Generowanie raportów
- Integracje/fan-out zdarzeń

5. **Koncepcje niezawodności**

- **Ack/Nack**: potwierdzenie sukcesu lub żądanie retry.
- **Polityka retry**: exponential backoff, maksymalna liczba prób.
- **Dead-letter queue (DLQ)**: izolacja poison/failing messages.
- **Idempotency**: bezpieczne ponowne przetwarzanie bez duplikowania efektów ubocznych.

6. **Najlepsze praktyki**

- Utrzymuj payloady wiadomości małe (preferuj ID zamiast dużych obiektów).
- Wersjonuj schematy wiadomości.
- Twórz konsumentów idempotentnych i obserwowalnych (logi/metryki/tracing).
- Monitoruj queue depth, processing lag, failure rate, retry rate.
- Ustal jasne SLA dla opóźnienia przetwarzania.

Kolejki to fundamentalny building block skalowalnych i odpornych systemów PHP z obciążeniami asynchronicznymi.

</details>

<details>
<summary>57. Czym jest architektura event-driven w PHP?</summary>

#### PHP

Architektura event-driven (EDA) to styl, w którym komponenty systemu komunikują się przez publikowanie i obsługę zdarzeń zamiast bezpośrednich synchronicznych wywołań.

1. **Podstawowa koncepcja**

- Producent emituje zdarzenie (na przykład `OrderPlaced`).
- Zainteresowani konsumenci subskrybują i obsługują je niezależnie.
- Publikujący nie musi wiedzieć, którzy konsumenci istnieją.

2. **Dlaczego EDA jest użyteczna**

- Odsprzęga moduły/serwisy.
- Poprawia rozszerzalność (nowych konsumentów można dodać bez zmiany publishującego).
- Wspiera przetwarzanie async i lepszą skalowalność.
- Czyni efekty uboczne jawnymi jako zdarzenia domenowe/integracyjne.

3. **Typowe use case’y PHP**

- Zamówienie utworzone -> wyślij e-mail, zarezerwuj stan magazynowy, opublikuj analitykę.
- Użytkownik zarejestrowany -> sekwencja powitalna, sync z CRM, audit log.
- Płatność zakończona sukcesem -> generowanie faktury, powiadomienia, fulfillment.

4. **Typy zdarzeń**

- **Zdarzenia domenowe**: fakty istotne biznesowo wewnątrz granicy domeny.
- **Zdarzenia integracyjne**: zdarzenia publikowane dla innych serwisów/systemów.

5. **Opcje dostarczania w ekosystemie PHP**

- In-process event bus/dispatcher (zdarzenia na poziomie frameworka).
- Dostarczanie przez kolejkę/brokera (RabbitMQ/Kafka/Redis streams/queues) dla async i dystrybucji między serwisami.

6. **Kluczowe zagadnienia projektowe**

- Idempotentne handlery (zdarzenia mogą być dostarczone więcej niż raz).
- Gwarancje kolejności (zależne od transportu/topic/strategii partycjonowania).
- Polityka retry i dead-letter dla błędów.
- Ewolucja schematów/wersji payloadów zdarzeń.

7. **Najlepsze praktyki**

- Używaj niemutowalnych, wersjonowanych payloadów zdarzeń.
- Utrzymuj handlery skupione i niezależne.
- Traktuj zdarzenia jako fakty (nazewnictwo w czasie przeszłym: `UserRegistered`).
- Dodawaj obserwowalność: correlation IDs, tracing, metryki processing lag.

EDA w PHP pomaga budować modułowe, skalowalne systemy, gdzie workflow mogą ewoluować bez ścisłego sprzężenia między komponentami.

</details>

<details>
<summary>58. Czym są WebSockety i kiedy ich używać?</summary>

#### PHP

WebSockety to protokół tworzący trwałe, dwukierunkowe połączenie między klientem a serwerem, umożliwiające wymianę danych w czasie rzeczywistym bez ciągłego HTTP pollingu.

1. **Czym WebSockety różnią się od HTTP**

- HTTP: request/response, zwykle krótkotrwałe i inicjowane przez klienta.
- WebSocket: jedno długotrwałe połączenie, gdzie obie strony mogą wysyłać wiadomości w dowolnym momencie.

2. **Kiedy WebSockety są użyteczne**

- Czat i komunikacja w czasie rzeczywistym.
- Live dashboardy/aktualizacje monitoringu.
- Edycja kolaboracyjna i wskaźniki obecności.
- Feedy tradingowe/rynkowe, zdarzenia gamingowe, powiadomienia.

3. **Dlaczego nie używać WebSocketów wszędzie**

- Dodają złożoność operacyjną (stan połączeń, skalowanie, routing).
- Nie są potrzebne dla prostych stron CRUD z rzadkimi aktualizacjami.
- W niektórych przypadkach SSE albo short polling są prostsze i wystarczające.

4. **Aspekty architektoniczne w PHP**

- Tradycyjny model requestowy PHP-FPM nie jest idealny do długowiecznych połączeń.
- Typowe podejścia:
  dedykowane serwery WebSocket (Ratchet/Swoole/RoadRunner),
  oddzielny serwis real-time + integracja backendu PHP przez Redis/message broker.

5. **Wyzwania skalowania**

- Efektywność fan-out połączeń i broadcastu.
- Sticky sessions vs współdzielony pub/sub backplane.
- Skalowanie horyzontalne z warstwami messagingowymi typu Redis/Kafka/NATS.

6. **Bezpieczeństwo i niezawodność**

- Uwierzytelniaj handshake/sesję WebSocket.
- Waliduj schemat wiadomości i egzekwuj autoryzację per kanał/topic.
- Stosuj rate limity i ochronę przed nadużyciami.
- Obsługuj reconnecty, heartbeaty i backpressure.

7. **Reguła kciuka**

- Używaj WebSocketów, gdy low-latency server push jest kluczowym wymaganiem produktu.
- Preferuj prostsze podejścia HTTP, gdy near-real-time jest wystarczające.

WebSockety są potężnym narzędziem real-time w ekosystemach PHP, jeśli są połączone z właściwym runtime i modelem skalowania.

</details>

<details>
<summary>59. Jak budować REST API w PHP?</summary>

#### PHP

Budowanie REST API w PHP oznacza wystawianie zasobów przez HTTP z czytelnymi trasami, standardowymi metodami, przewidywalnymi kodami statusu i spójnymi kontraktami JSON.

1. **Podstawowe zasady REST**

- Endpointy zorientowane na zasoby (`/users`, `/orders/{id}`).
- Poprawne metody HTTP:
  `GET`, `POST`, `PUT/PATCH`, `DELETE`.
- Bezstanowe requesty.
- Spójny format reprezentacji (zwykle JSON).

2. **Typowe warstwy API w PHP**

- Warstwa route/controller (wejście/wyjście HTTP).
- Warstwa walidacji/auth/middleware.
- Warstwa service/use-case (logika biznesowa).
- Warstwa repository/data (persystencja).

3. **Kluczowe elementy projektu**

- Strategia wersjonowania (`/api/v1/...` albo header-based).
- Standardowa obwiednia odpowiedzi i format błędów.
- Konwencje paginacji/filtrowania/sortowania.
- Idempotency dla istotnych operacji zapisu.

4. **Poprawność HTTP**

- Zwracaj znaczące kody statusu (`200`, `201`, `204`, `400`, `401`, `403`, `404`, `422`, `500`).
- Ustawiaj `Content-Type: application/json`.
- Używaj nagłówków cache tam, gdzie to właściwe.

5. **Bazowy poziom bezpieczeństwa**

- Uwierzytelnianie (token/JWT/sesja zależnie od kontekstu).
- Kontrole autoryzacji per zasób/akcja.
- Walidacja wejścia i kodowanie wyjścia.
- Rate limiting i ochrona przed nadużyciami.
- Ochrona CSRF dla API opartych o cookies.

6. **Jakość operacyjna**

- Ustrukturyzowane logowanie + request correlation IDs.
- Scentralizowana obsługa wyjątków.
- Dokumentacja OpenAPI/Swagger.
- Testy kontraktowe/integracyjne dla krytycznych endpointów.

7. **Przykładowy kształt endpointu**

- `POST /api/v1/orders`
- Waliduj payload -> uruchom use case -> zwróć `201 Created` z body/lokalizacją zasobu.

8. **Praktyczna wskazówka**

- Utrzymuj kontrolery cienkie.
- Trzymaj logikę biznesową poza warstwą HTTP.
- Kontrakty API rób jawne i stabilne.

Dobre REST API w PHP to nie tylko trasy, ale przede wszystkim spójne kontrakty, bezpieczne zachowanie i niezawodność operacyjna.

</details>

<details>
<summary>60. Czym jest GraphQL i jak jest używany w PHP?</summary>

#### PHP

GraphQL to język zapytań API i runtime, w którym klienci pobierają dokładnie te pola, których potrzebują, z typowanego schematu, zamiast konsumować sztywne payloady REST.

1. **Podstawowe koncepcje GraphQL**

- **Schema**: silnie typowany kontrakt (typy, pola, argumenty).
- **Queries**: operacje odczytu.
- **Mutations**: operacje zapisu.
- **Resolvers**: funkcje/metody PHP, które pobierają/wyliczają dane pól.

2. **Dlaczego zespoły używają GraphQL**

- Unikanie over-fetchingu/under-fetchingu typowego w REST.
- Jeden endpoint do elastycznego pobierania danych.
- Lepsza prędkość pracy frontendowej przy złożonych potrzebach danych UI.
- Silne wsparcie introspekcji i narzędzi.

3. **Jak jest używany w PHP**

- Definiowanie schematu GraphQL w kodzie/SDL.
- Implementacja resolverów wywołujących serwisy/repozytoria.
- Wykonanie zapytania względem schematu i zwrot odpowiedzi JSON.
- Integracja auth, walidacji, limitów złożoności i cache w warstwie wykonania.

4. **Typowe opcje stacku PHP**

- `webonyx/graphql-php` (główna implementacja GraphQL)
- Integracje/adaptery frameworkowe dla ekosystemów Laravel/Symfony

5. **Kompromisy**

- Większa złożoność niż podstawowy REST dla prostych API.
- Wymaga ścisłej kontroli depth/complexity zapytań, aby unikać kosztownych zapytań.
- Strategia cache może być trudniejsza niż cache endpointów REST.
- Niezbędna jest dyscyplina governance/versioning schematu.

6. **Najlepsze praktyki**

- Utrzymuj resolvery cienkie; deleguj do serwisów aplikacyjnych.
- Używaj wzorca DataLoader, aby unikać zaplecza N+1 calls.
- Egzekwuj auth per pole/zasób tam, gdzie trzeba.
- Ograniczaj depth/complexity zapytań i monitoruj ciężkie operacje.
- Publikuj dokumentację schematu i traktuj zmiany schematu jak kontrakty.

GraphQL w PHP jest najskuteczniejszy dla produktów data-rich z złożonymi potrzebami klientów, pod warunkiem że zespół świadomie zarządza złożonością zapytań i governance schematu.

</details>

<details>
<summary>61. Czym jest uwierzytelnianie API (JWT, OAuth)?</summary>

#### PHP

Uwierzytelnianie API weryfikuje, kto wywołuje API i z jakimi uprawnieniami. Dwa popularne podejścia to auth tokenowe oparte o JWT oraz flow OAuth 2.0 / OpenID Connect.

1. **Uwierzytelnianie oparte o JWT**

- Po udanym logowaniu serwer wydaje podpisany token (JWT).
- Klient wysyła token przy każdym requestcie (zwykle `Authorization: Bearer ...`).
- API waliduje podpis, ważność i claims.

Typowe claims JWT:
- `sub` (subject/user id)
- `exp` (expiration)
- `iss`/`aud` (issuer/audience)
- opcjonalnie role/scopes

2. **OAuth 2.0 (framework autoryzacji)**

- Zaprojektowany do delegated access i autoryzacji stron trzecich.
- Dostęp jest nadawany przez scopes i czas życia tokenów.
- Typowe flow: Authorization Code (+ PKCE), Client Credentials.

3. **OpenID Connect (OIDC)**

- Warstwa tożsamości nad OAuth 2.0.
- Dodaje ID token i standaryzowane claims tożsamości użytkownika.

4. **JWT vs OAuth (praktyczne rozróżnienie)**

- JWT to format/mechanizm tokena.
- OAuth to protokół autoryzacji.
- Tokeny OAuth mogą być JWT albo opaque.

5. **Najlepsze praktyki bezpieczeństwa**

- Używaj wyłącznie HTTPS.
- Trzymaj access tokeny krótkowieczne; bezpiecznie rotuj refresh tokeny.
- Przy każdym requestcie waliduj podpis, issuer, audience i expiration.
- Przechowuj tokeny bezpiecznie po stronie klienta (unikaj niebezpiecznych wzorców storage).
- Wdrażaj strategię revocation/introspection tam, gdzie potrzebna.

6. **Wskazówki implementacyjne w PHP**

- Używaj sprawdzonych bibliotek do walidacji JWT/OAuth/OIDC.
- Centralizuj middleware uwierzytelniania.
- Oddzielaj uwierzytelnianie (kto) od autoryzacji (co wolno).
- Reprezentuj uprawnienia jako role/scopes/policies sprawdzane na poziomie zasobu.

Silne uwierzytelnianie API w PHP to poprawność protokołu, higiena cyklu życia tokenów i ścisła walidacja na każdym chronionym endpoincie.

</details>

<details>
<summary>62. Czym jest rate limiting i bezpieczeństwo API?</summary>

#### PHP

Rate limiting to mechanizm kontroli, który ogranicza, ile requestów klient może wykonać w danym oknie czasu. To kluczowa część szerszego bezpieczeństwa API.

1. **Dlaczego rate limiting jest potrzebny**

- Zapobiega nadużyciom i atakom brute-force.
- Chroni zasoby backendu przed przeciążeniem.
- Zapewnia fair usage między klientami/tenantami.
- Ogranicza wpływ błędnych lub złośliwych integracji.

2. **Popularne strategie rate limitingu**

- Fixed window (proste liczniki na interwał).
- Sliding window (dokładniejszy rozkład).
- Token bucket / leaky bucket (przyjazne burstom z limitem długoterminowym).

3. **Gdzie stosuje się limity**

- Per adres IP
- Per API key/client id
- Per user/account/tenant
- Per czułość endpointu (ostrzej dla endpointów auth)

4. **Typowa implementacja w stackach PHP**

- Kontrole na poziomie middleware z użyciem liczników Redis/in-memory.
- Egzekwowanie przez reverse proxy/API gateway (Nginx, cloud API gateway).
- Zwracanie `429 Too Many Requests` z nagłówkami retry.

5. **Bazowy poziom bezpieczeństwa API (poza limitami)**

- Silne uwierzytelnianie (JWT/OAuth/OIDC).
- Kontrole autoryzacji per zasób/akcja.
- Walidacja wejścia i kodowanie wyjścia.
- HTTPS wszędzie + bezpieczne nagłówki.
- Limity rozmiaru requestu/czasu i kontrola timeoutów.
- Audit logging, wykrywanie anomalii i alerting.

6. **Najlepsze praktyki**

- Używaj warstwowych kontroli: gateway + middleware aplikacyjne.
- Stosuj różne kwoty według planu/poziomu zaufania.
- Dodaj obsługę burstów i graceful degradation.
- Chroń endpointy logowania/tokenów ostrzejszymi regułami i lockoutami.
- Monitoruj trafienia limitów, zablokowane requesty i wzorce ataków.

Rate limiting to jeden filar bezpieczeństwa API; realna ochrona wynika z połączenia go z uwierzytelnianiem, autoryzacją, walidacją i obserwowalnością.

</details>

<details>
<summary>63. Czym jest piramida testów w PHP?</summary>

#### PHP

Piramida testów to model strategii testowania, który rekomenduje wiele szybkich testów niskiego poziomu i mniej wolnych testów wysokiego poziomu, aby zbalansować pewność, szybkość i koszt utrzymania.

1. **Warstwy piramidy**

- **Podstawa (największa): testy jednostkowe**
  szybkie, izolowane testy funkcji/klas/reguł biznesowych.
- **Środek: testy integracyjne**
  weryfikują współpracę modułów (DB, cache, kolejka, adaptery zewnętrzne).
- **Szczyt (najmniejszy): testy end-to-end/API/UI**
  walidują pełne przepływy użytkownika przez cały system.

2. **Dlaczego ten model działa**

- Testy jednostkowe są tanie i uruchamiają się szybko w dużej liczbie.
- Testy integracyjne wyłapują problemy na granicach i w połączeniach.
- Testy E2E dają realistyczną pewność, ale są wolniejsze i bardziej kruche.

3. **Mapowanie specyficzne dla PHP**

- Unit: PHPUnit/Pest z mockami/stubami.
- Integration: realne kontenery DB, repozytoria, klienci HTTP w kontrolowanym środowisku.
- E2E/API: testy na poziomie requestów przeciwko uruchomionej aplikacji/usłudze.

4. **Typowe antywzorce**

- „Lodowy rożek”: za dużo testów UI/E2E, za mało testów jednostkowych.
- Nadmierne mockowanie wszystkiego i utrata pewności integracyjnej.
- Brak testów kontraktowych dla krytycznych integracji zewnętrznych.

5. **Praktyczne rekomendacje**

- Utrzymuj większość testów na poziomie unit.
- Dodawaj celowane testy integracyjne wokół krytycznych granic.
- Utrzymuj zestaw E2E mały, stabilny i biznesowo krytyczny.
- Uruchamiaj szybkie zestawy na każdym commicie; cięższe zestawy na bramkach main/pre-release.

6. **Rezultat**

Zdrowa piramida daje szybki feedback deweloperom i wysoką pewność release’ów bez nadmiernego czasu CI i kosztownego utrzymania flaky testów.

</details>

<details>
<summary>64. Czym jest testowanie jednostkowe (PHPUnit / Pest)?</summary>

#### PHP

Testowanie jednostkowe weryfikuje zachowanie najmniejszych testowalnych fragmentów kodu (funkcje, metody, klasy) w izolacji od systemów zewnętrznych.

1. **Co powinny obejmować testy jednostkowe**

- Reguły biznesowe i obliczenia.
- Edge case’y i walidację inputu.
- Zachowanie błędów/wyjątków.
- Deterministyczne gałęzie logiki.

2. **Zasada izolacji**

- Testy jednostkowe nie powinny zależeć od realnej DB, sieci, filesystemu ani usług kolejkowych.
- Zależności zewnętrzne zastępuje się test doubles (mocki/stuby/fake’i).

3. **Narzędzia PHP**

- **PHPUnit**: klasyczny i szeroko stosowany framework testowy.
- **Pest**: ekspresyjna składnia zbudowana na ekosystemie PHPUnit.

4. **Prosty przykład (styl PHPUnit)**

```php
final class PriceCalculatorTest extends TestCase
{
    public function test_applies_discount(): void
    {
        $calc = new PriceCalculator();
        self::assertSame(90, $calc->applyDiscount(100, 10));
    }
}
```

5. **Dlaczego testy jednostkowe są ważne**

- Szybki feedback podczas developmentu.
- Bezpieczniejsza refaktoryzacja.
- Lepsza dokumentacja oczekiwanego zachowania.
- Wczesne wykrywanie regresji.

6. **Najlepsze praktyki**

- Utrzymuj testy małe, skupione i deterministyczne.
- Stosuj czytelną strukturę arrange-act-assert.
- Nazywaj testy według oczekiwanego zachowania.
- Unikaj nadmiernego mockowania logiki wewnętrznej.
- Uruchamiaj testy jednostkowe na każdym commicie w CI.

Testowanie jednostkowe z PHPUnit/Pest to fundament niezawodnego dostarczania PHP, bo daje szybkie i precyzyjne potwierdzenie poprawności logiki rdzeniowej.

</details>

<details>
<summary>65. Czym jest testowanie integracyjne?</summary>

#### PHP

Testowanie integracyjne weryfikuje, czy wiele komponentów współpracuje poprawnie (na przykład logika aplikacji + baza danych + cache + adaptery zewnętrzne), pozostając jednocześnie węższe niż pełne testy end-to-end.

1. **Na czym skupiają się testy integracyjne**

- Granice modułów i współpraca.
- Poprawność persystencji/odczytu danych.
- Zachowanie adapterów infrastrukturalnych.
- Poprawność konfiguracji i połączeń (wiring).

2. **Czym różni się od testów jednostkowych**

- Testy jednostkowe izolują jeden komponent i mockują zależności.
- Testy integracyjne używają realnych lub zbliżonych do realnych zależności, aby zweryfikować interakcje.

3. **Typowe scenariusze integracyjne w PHP**

- Repozytorium z realną testową DB/kontenerem.
- Adapter klienta HTTP przeciwko sandboxowi/mock serverowi.
- Flow publikowania/konsumowania kolejki w kontrolowanym środowisku.
- Interakcja framework route + middleware + controller + service.

4. **Dlaczego testy integracyjne są ważne**

- Wyłapują problemy, których mocki nie pokażą (mismatch schematu SQL, błędy serializacji, błędy konfiguracji).
- Zwiększają pewność na krytycznych granicach.
- Ograniczają produkcyjne niespodzianki wynikające ze sprzężenia z infrastrukturą.

5. **Najlepsze praktyki**

- Uruchamiaj na dedykowanej infrastrukturze testowej (izolowane DB/cache).
- Deterministycznie kontroluj setup/teardown danych.
- Utrzymuj skupiony zakres: jeden aspekt integracji na test.
- Unikaj zbędnej zależności od sieci, gdy wystarczą contract stuby.
- Uwzględniaj suite integracyjny w CI dla krytycznych ścieżek.

6. **Kompromis**

- Są wolniejsze i cięższe niż testy jednostkowe, więc powinny być rzadsze i celowane.

Testy integracyjne są pomostem między szybką pewnością unit a pełną pewnością systemową w pipeline’ach dostarczania PHP.

</details>

<details>
<summary>66. Czym jest mocking i dlaczego jest potrzebny?</summary>

#### PHP

Mocking to technika testowania, w której realne zależności są zastępowane kontrolowanymi test doubles, aby izolować testowaną jednostkę i weryfikować interakcje.

1. **Dlaczego mocking jest potrzebny**

- Izoluje logikę biznesową od systemów zewnętrznych (DB, HTTP, kolejka, filesystem).
- Czyni testy szybkimi i deterministycznymi.
- Pozwala symulować rzadkie/scenariusze błędów trudne do odtworzenia na realnych usługach.
- Umożliwia weryfikację kontraktów współpracy (metoda wywołana z oczekiwanymi argumentami).

2. **Typowe rodzaje test doubles**

- **Stub**: zwraca predefiniowane wartości.
- **Mock**: weryfikuje oczekiwane interakcje/wywołania.
- **Fake**: lekka działająca implementacja (na przykład repozytorium in-memory).
- **Spy**: zapisuje wywołania do późniejszych asercji.

3. **Koncepcja przykładu PHP**

Przetestuj `OrderService`, mockując `PaymentGatewayInterface` i `OrderRepositoryInterface`, a następnie asercje:
- serwis zwraca oczekiwany wynik
- gateway wywołany raz z poprawną kwotą
- zapis repozytorium wywołany z oczekiwanym stanem encji

4. **Gdzie mocking jest odpowiedni**

- Testy jednostkowe serwisów domenowych/aplikacyjnych.
- Testowanie ścieżek błędów zależności zewnętrznych.
- Weryfikacja kontraktów na granicach modułów.

5. **Gdzie mocking nie wystarcza**

- Zachowanie integracyjne z realnymi protokołami DB/sieci.
- Problemy wiringu/konfiguracji frameworka.
- Charakterystyki wydajnościowe i semantyka transakcji.

6. **Najlepsze praktyki**

- Mockuj tylko granice zewnętrzne, nie wewnętrzną czystą logikę.
- Utrzymuj oczekiwania skupione na obserwowalnym zachowaniu.
- Preferuj interfejsy dla zależności podlegających mockowaniu.
- Łącz testy unit + integration (sam mocking nie jest pełną strategią).

Mocking jest kluczowy dla szybkich, izolowanych testów jednostkowych PHP, ale powinien być równoważony testami integracyjnymi dla pewności działania realnego systemu.

</details>

<details>
<summary>67. Czym jest code coverage?</summary>

#### PHP

Code coverage to metryka pokazująca, które części kodu źródłowego zostały wykonane przez testy automatyczne.

1. **Co mierzy coverage**

- **Line coverage**: wykonane linie.
- **Branch/condition coverage**: wykonane gałęzie decyzyjne.
- **Function/method coverage**: wykonane jednostki wywoływalne.

2. **Dlaczego jest użyteczne**

- Wskazuje nieprzetestowane obszary.
- Pomaga priorytetyzować miejsca, gdzie brakuje testów.
- Wspiera ocenę ryzyka regresji podczas refaktoryzacji.

3. **Czego coverage NIE gwarantuje**

- Wysokie coverage nie oznacza automatycznie wysokiej jakości testów.
- Testy mogą wykonywać kod bez asercji poprawnego zachowania.
- Krytyczne edge case’y nadal mogą zostać pominięte mimo dobrych procentów.

4. **Narzędzia PHP**

- PHPUnit/Pest potrafią generować raporty coverage.
- Zwykle opiera się to o drivery Xdebug albo PCOV.
- Raporty mogą być generowane jako tekst, HTML albo formaty CI.

5. **Praktyczne użycie w zespołach**

- Śledź trendy w czasie zamiast gonić jedną absolutną liczbę.
- Ustawiaj sensowne minimalne progi dla krytycznych modułów.
- Używaj delta coverage w checkach PR, aby zapobiegać regresjom testów.

6. **Najlepsze praktyki**

- Najpierw skup się na testowaniu krytycznej logiki biznesowej i ryzykownych ścieżek.
- Łącz coverage z mutation testing/statyczną analizą tam, gdzie to możliwe.
- Oceniaj jakość asercji, nie tylko wykonane linie.
- Nie „pompuj” coverage przez flaky lub niskowartościowe testy.

Code coverage to użyteczny sygnał kompletności testów, ale należy go interpretować w kontekście jakości testów i ryzyka, a nie jako samodzielny cel.

</details>

<details>
<summary>68. Czym jest analiza statyczna (PHPStan, Psalm)?</summary>

#### PHP

Analiza statyczna sprawdza kod PHP bez jego uruchamiania, aby wcześnie wykrywać problemy typów, potencjalne błędy, martwy kod i naruszenia architektury.

1. **Co wykrywa analiza statyczna**

- Niezgodności typów i typy niemożliwe.
- Problemy z nullowalnością oraz dostęp do niezdefiniowanych zmiennych/właściwości/metod.
- Niepoprawne typy zwracane i niebezpieczne rzutowania.
- Nieosiągalny/martwy kod i część wzorców błędnego użycia API.

2. **Główne narzędzia**

- **PHPStan**: szeroko stosowany, poziomy ścisłości, mocna integracja z ekosystemem.
- **Psalm**: zaawansowany system typów, silna inferencja, opcje taint analysis.

3. **Dlaczego jest wartościowa**

- Znajduje defekty przed runtime i zanim obejmą je testy.
- Poprawia bezpieczeństwo refaktoryzacji w dużych codebase’ach.
- Wspiera silniejsze typowanie i czytelniejsze kontrakty.
- Ogranicza incydenty produkcyjne wynikające z podstawowych błędów typów/przepływu.

4. **Jak zespoły jej używają**

- Uruchamianie w CI przy każdym PR.
- Start od umiarkowanej ścisłości i stopniowe podnoszenie poziomu.
- Utrzymywanie baseline dla legacy issue przy jednoczesnym blokowaniu nowych.

5. **Najlepsze praktyki**

- Konsekwentnie dodawaj type hinty/return types.
- Używaj adnotacji generyków tam, gdzie to potrzebne (kolekcje, repozytoria).
- Naprawiaj źródłowe problemy typowania zamiast tłumienia ostrzeżeń.
- Trzymaj konfigurację analizy wersjonowaną i reviewowaną jak kod.

6. **Analiza statyczna vs testy**

- Analiza statyczna nie zastępuje testów.
- Uzupełnia testy unit/integration, dowodząc poprawności strukturalnej/typów na ścieżkach, które testy mogą pominąć.

Analiza statyczna z PHPStan/Psalm to wysokodźwigniowa bramka jakości dla nowoczesnych projektów PHP, szczególnie przy ciągłej refaktoryzacji.

</details>

<details>
<summary>69. Czym jest Rector i jak używa się go do refaktoryzacji?</summary>

#### PHP

Rector to narzędzie do automatycznej refaktoryzacji PHP, które transformuje kod źródłowy przy użyciu predefiniowanych i własnych reguł, pomagając bezpiecznie modernizować codebase’y na dużą skalę.

1. **Co robi Rector**

- Wykonuje transformacje kodu oparte o AST.
- Aktualizuje składnię/funkcje między wersjami PHP.
- Refaktoryzuje wzorce użycia frameworków/bibliotek.
- Automatyzuje powtarzalne, mechaniczne zmiany.

2. **Typowe use case’y**

- Upgrade ze starszych wersji PHP do nowszych standardów.
- Migracja deprecated API do aktualnych alternatyw.
- Egzekwowanie nowoczesnych konstrukcji języka (typed properties, constructor promotion itd.).
- Duże porządki w codebase przed adopcją ścisłej analizy statycznej.

3. **Jak używa się go w praktyce**

1. Skonfiguruj `rector.php` z zestawami reguł.
2. Uruchom Rectora na wybranych ścieżkach.
3. Przejrzyj wygenerowany diff.
4. Uruchom testy/analizę statyczną.
5. Commituj inkrementalne, bezpieczne paczki zmian.

4. **Dlaczego zespoły używają Rectora**

- Radykalnie przyspiesza modernizację.
- Ogranicza ludzki błąd przy powtarzalnych refaktorach.
- Utrzymuje spójność refaktoryzacji między modułami.

5. **Najlepsze praktyki**

- Uruchamiaj Rectora na skupionych zakresach, nie na całym legacy codebase naraz.
- Utrzymuj zmiany małe i łatwe do review.
- Zawsze waliduj wynik testami + PHPStan/Psalm po transformacji.
- Przypinaj wersję Rectora w toolingu dla powtarzalności.
- Łącz automatyczną refaktoryzację z ręcznym przeglądem architektonicznym.

6. **Ważne ograniczenie**

- Rector świetnie obsługuje transformacje mechaniczne, ale nie zastąpi decyzji architektonicznych ani redesignu specyficznego dla domeny.

Rector jest najskuteczniejszy jako część pipeline’u refaktoryzacji razem z analizą statyczną i testami, a nie jako samodzielne narzędzie „one-click migration”.

</details>

<details>
<summary>70. Czym jest egzekwowanie standardów kodowania (PHP-CS-Fixer)?</summary>

#### PHP

Egzekwowanie standardów kodowania to praktyka automatycznego sprawdzania i poprawiania reguł stylu kodu, aby codebase pozostawał spójny, czytelny i przyjazny do review.

1. **Dlaczego standardy kodowania są ważne**

- Poprawiają czytelność w zespołach.
- Redukują „szum stylu” w pull requestach.
- Pozwalają skupić review kodu na logice, nie formatowaniu.
- Utrzymują spójność długowiecznych codebase’ów.

2. **Co robi PHP-CS-Fixer**

- Skanuje pliki PHP względem skonfigurowanych reguł stylu.
- Automatycznie przepisuje problemy formatowania/stylu.
- Wspiera standardowe zestawy reguł (na przykład PSR-12) oraz reguły własne.

3. **Typowy workflow**

- Konfiguruj reguły w `.php-cs-fixer.php`.
- Uruchamiaj checker w CI, aby zapobiegać driftowi.
- Uruchamiaj fixer lokalnie/pre-commit, aby autoformatować zmienione pliki.

4. **Typowe kategorie reguł**

- Kolejność importów i usuwanie nieużywanych importów.
- Styl odstępów/wcięć/nawiasów klamrowych.
- Normalizacja składni tablic/funkcji.
- Reguły preferujące strict typing i nowoczesną składnię.

5. **Najlepsze praktyki**

- Wcześnie uzgodnij jeden standard dla całego projektu.
- Stosuj auto-fix w workflow deweloperskim (pre-commit/hooks/integracja z edytorem).
- Utrzymuj CI jako bramkę egzekwującą (`--dry-run`).
- Duże reformatowanie stosuj oddzielnie od zmian feature’owych, aby diffy były czytelne.

6. **Narzędzia powiązane**

- PHP-CS-Fixer (auto-fix formatowania/stylu).
- PHP_CodeSniffer (sprawdzanie reguł i analiza standardów kodowania).
- Łącz narzędzia stylu z PHPStan/Psalm, aby zapewnić jakość wykraczającą poza formatowanie.

Egzekwowanie standardów kodowania narzędziami takimi jak PHP-CS-Fixer to niskokosztowy sposób poprawy utrzymywalności i szybkości pracy zespołu w projektach PHP.

</details>

<details>
<summary>71. Czym jest pipeline CI/CD dla aplikacji PHP?</summary>

#### PHP

Pipeline CI/CD to zautomatyzowany workflow, który buduje, testuje, weryfikuje i wdraża aplikacje PHP w sposób spójny od commita do produkcji.

1. **Cele CI (Continuous Integration)**

- Szybka walidacja każdej zmiany.
- Wczesne wykrywanie błędów przez automatyczne checki.
- Utrzymywanie gałęzi main zawsze w stanie releasable.

2. **Typowe etapy CI dla PHP**

1. Instalacja zależności (`composer install`).
2. Checki statyczne (PHPStan/Psalm, standardy kodowania).
3. Testy unit/integration (PHPUnit/Pest).
4. Build/package artefaktów (obraz Docker lub paczka wdrożeniowa).

3. **Cele CD (Continuous Delivery/Deployment)**

- Bezpieczne dostarczanie zwalidowanych artefaktów do środowisk.
- Automatyzacja kroków rolloutu i minimalizacja błędów manualnych.
- Wsparcie szybkiego rollbacku przy incydentach.

4. **Typowe etapy CD**

- Wdrożenie na staging.
- Uruchomienie smoke checków/health checków.
- Promocja tego samego artefaktu na produkcję.
- Monitoring metryk i logów po wdrożeniu.

5. **Najlepsze praktyki specyficzne dla PHP**

- Używaj powtarzalnych instalacji opartych o lockfile.
- Buduj niemutowalne artefakty raz i używaj ich ponownie między środowiskami.
- Uruchamiaj migracje DB według kontrolowanej strategii.
- Trzymaj sekrety/konfigurację poza artefaktem.
- Stosuj wzorce rolloutu zero-downtime (blue-green/canary/rolling).

6. **Bramki jakości**

- Wymagany status zaliczenia testów.
- Próg analizy statycznej.
- Checki bezpieczeństwa (dependency audit/SAST).
- Opcjonalne smoke-checki wydajności dla krytycznych endpointów.

7. **Efekt**

Solidny pipeline CI/CD poprawia częstotliwość wydań, niezawodność i pewność zespołu, jednocześnie redukując ryzyko produkcyjne w dostarczaniu PHP.

</details>

<details>
<summary>72. Jak wdrażać aplikacje PHP?</summary>

#### PHP

Wdrażanie aplikacji PHP oznacza dostarczenie przetestowanego artefaktu na produkcję z przewidywalną konfiguracją runtime, minimalnym downtime i bezpiecznym rollbackiem.

1. **Popularne cele wdrożeń**

- Tradycyjny VM/bare metal z Nginx/Apache + PHP-FPM.
- Platformy kontenerowe (Docker, Kubernetes, ECS).
- Usługi platformowe (warianty PaaS/serverless).

2. **Rekomendowany przepływ wdrożenia**

1. Zbuduj niemutowalny artefakt (obraz/paczkę) w CI.
2. Uruchom testy/checki statyczne/skany bezpieczeństwa.
3. Wdróż artefakt na staging.
4. Wykonaj smoke checki i health checki.
5. Promuj ten sam artefakt na produkcję.

3. **Podstawy runtime**

- Konfiguracja i sekrety zależne od środowiska (bez hardcodowania).
- Poprawne rozszerzenia PHP i ustawienia OPcache.
- Zweryfikowana łączność z DB/cache/kolejką przy starcie.
- Włączone ustrukturyzowane logowanie i monitoring.

4. **Strategia migracji bazy danych**

- Stosuj migracje backward-compatible przed przełączeniem ruchu.
- Używaj podejścia expand-and-contract dla ryzykownych zmian schematu.
- Utrzymuj skrypty migracyjne wersjonowane i powtarzalne.

5. **Techniki zero/low-downtime**

- Wdrożenia blue-green, rolling albo canary.
- Graceful reload workerów (PHP-FPM/process manager).
- Przełączanie ruchu przez load balancer oparte o health-checki.

6. **Strategia rollbacku**

- Szybki rollback do poprzedniej wersji artefaktu.
- Kontrolowany rollback DB albo plan forward-fix.
- Okno monitoringu po wdrożeniu z alertingiem.

7. **Najlepsze praktyki**

- Nigdy nie wdrażaj bezpośrednio z lokalnej maszyny.
- Utrzymuj proces wdrożeń zautomatyzowany i audytowalny.
- Używaj infrastructure as code tam, gdzie to możliwe.
- Wyraźnie oddzielaj concerns build-time i runtime.

Dobre wdrażanie PHP to system inżynierski: powtarzalne artefakty, bezpieczna mechanika rolloutu, obserwowalność i niezawodny rollback.

</details>

<details>
<summary>73. Czym jest wdrożenie blue-green?</summary>

#### PHP

Wdrożenie blue-green to strategia release’u, w której utrzymywane są dwa identyczne środowiska produkcyjne: jedno aktywne (obsługujące ruch) i jedno bezczynne (kandydat na następny release).

1. **Jak to działa**

- **Blue**: aktualne środowisko live.
- **Green**: nowa wersja wdrożona i zweryfikowana równolegle.
- Po przejściu checków ruch jest przełączany z Blue na Green.
- Stare środowisko pozostaje dostępne dla szybkiego rollbacku.

2. **Dlaczego zespoły tego używają**

- Minimalizuje downtime wdrożenia.
- Redukuje ryzyko release’u dzięki niemal natychmiastowemu rollbackowi.
- Umożliwia realistyczną weryfikację przed przełączeniem na stacku zbliżonym do produkcji.

3. **Typowy przebieg rolloutu**

1. Wdróż nowy release PHP na bezczynne środowisko.
2. Uruchom health checki/smoke testy/strategię migracji.
3. Przełącz load balancer/router na nowe środowisko.
4. Monitoruj error rates/latency.
5. Utrzymuj poprzednie środowisko tymczasowo na wypadek rollbacku.

4. **Kluczowe kwestie dla aplikacji PHP**

- Strategia sesji musi wspierać przełączanie środowisk (współdzielony Redis/session store).
- Static assets/versioning powinny być kompatybilne między obiema wersjami środowiska.
- Zmiany DB muszą być backward-compatible w oknie przejściowym.
- Workery kolejek i cron joby muszą unikać duplikacji efektów ubocznych.

5. **Zalety**

- Szybka ścieżka rollbacku.
- Bezpieczniejsze wdrożenia dla systemów high-traffic.
- Jasne rozdzielenie „current” vs „candidate” release.

6. **Kompromisy**

- Wyższy koszt infrastruktury (dwa środowiska).
- Większa złożoność operacyjna wokół kompatybilności danych/schematu.

Blue-green to mocny wzorzec wdrożeń dla produkcyjnych systemów PHP, gdy krytyczne są uptime i szybkość rollbacku.

</details>

<details>
<summary>74. Czym jest strategia rollbacku?</summary>

#### PHP

Strategia rollbacku to zdefiniowany z góry plan szybkiego przywrócenia stabilnej poprzedniej wersji, gdy wdrożenie powoduje incydenty (błędy, regresje, spadki wydajności, problemy z danymi).

1. **Dlaczego strategia rollbacku jest krytyczna**

- Skraca czas trwania incydentu i wpływ na klientów.
- Zapobiega ad-hoc działaniom awaryjnym podczas awarii.
- Zwiększa pewność przy częstych release’ach.

2. **Co powinno być rollback-ready**

- Wersja artefaktu/obrazu aplikacji.
- Wersja infrastruktury/konfiguracji.
- Stan feature flagów/togli.
- Plan kompatybilności migracji bazy danych.

3. **Popularne podejścia rollbacku**

- **Artifact rollback**: ponowne wdrożenie poprzedniego known-good buildu.
- **Traffic rollback**: przełączenie ruchu z powrotem na poprzednie środowisko (blue-green/canary revert).
- **Feature rollback**: wyłączenie problematycznej feature flagi bez pełnego redeployu.

4. **Rzeczywistość rollbacku bazy danych**

- Rollback DB bywa najtrudniejszą częścią.
- Preferuj migracje backward-compatible:
  najpierw expand, potem contract.
- Używaj forward-fix, gdy rzeczywisty rollback schematu jest ryzykowny.

5. **Checklist operacyjny**

- Zdefiniuj progi wyzwalające rollback (error rate, latency, nieudane checki).
- Utrzymuj poprzedni release natychmiastowo wdrażalny.
- Automatyzuj kroki rollbacku w pipeline/runbookach.
- Zweryfikuj health po rollbacku i kontynuuj monitoring.

6. **Najlepsze praktyki**

- Regularnie ćwicz rollback na stagingu.
- Utrzymuj małe release’y, aby zmniejszyć blast radius.
- Łącz rollout i rollback z obserwowalnością (logi/metryki/traces).
- Dokumentuj ownership i przepływ decyzji incydentowych.

Silna strategia rollbacku to kluczowy mechanizm niezawodności dla produkcyjnego dostarczania PHP, szczególnie w środowiskach o wysokiej częstotliwości wdrożeń.

</details>

<details>
  <summary><strong>#75. Czym jest serverless PHP (Laravel Vapor, Bref)?</strong></summary>

Serverless PHP oznacza uruchamianie aplikacji PHP bez zarządzania własnymi serwerami. Kod działa jako funkcje uruchamiane na żądanie (np. AWS Lambda), a dostawca chmury odpowiada za skalowanie, utrzymanie i infrastrukturę.

### 1. Jak to działa
- Aplikacja jest pakowana jako funkcja (lub zestaw funkcji).
- Każde żądanie uruchamia funkcję, która przetwarza logikę i zwraca odpowiedź.
- Nie utrzymujesz stale działających maszyn ani konfiguracji Nginx/Apache.

### 2. Popularne rozwiązania
- **Laravel Vapor** — oficjalna platforma serverless dla Laravel oparta na AWS.
- **Bref** — warstwa/runtime dla PHP na AWS Lambda, działa z wieloma frameworkami (Laravel, Symfony i inne).

### 3. Zalety
- **Automatyczne skalowanie** przy nagłych skokach ruchu.
- **Płatność za użycie** (często niższe koszty przy nieregularnym obciążeniu).
- Mniej pracy operacyjnej związanej z serwerami.

### 4. Wyzwania
- **Cold starts** (dodatkowe opóźnienie przy pierwszym uruchomieniu funkcji).
- Ograniczenia środowiska Lambda (czas wykonania, system plików, rozmiar paczki).
- Inne podejście do debugowania i monitorowania niż na tradycyjnych serwerach.

### 5. Kiedy warto
- API, webhooki, zadania asynchroniczne, aplikacje o zmiennym ruchu.
- Projekty, gdzie zespół chce skupić się na logice biznesowej zamiast na administracji infrastrukturą.

Podsumowując: serverless PHP (np. z Laravel Vapor lub Bref) to model wdrożenia, w którym kod PHP działa w funkcjach w chmurze, a zarządzanie serwerami jest maksymalnie ograniczone.

</details>

<details>
  <summary><strong>#76. Czym są mikroserwisy a monolit w PHP?</strong></summary>

#### PHP

Monolit i mikroserwisy to style architektoniczne budowy systemów. W PHP oba podejścia mogą działać bardzo dobrze, jeśli wybór zależy od wielkości zespołu, złożoności domeny i dojrzałości operacyjnej.

1. **Monolit (jedna aplikacja wdrożeniowa)**

- Jeden codebase/jednostka wdrożeniowa zawierająca wiele możliwości biznesowych.
- Wspólny runtime i zwykle wspólna baza danych.

**Zalety**
- Prostszy development, testowanie i wdrożenia.
- Niższy narzut operacyjny.
- Łatwiejsze lokalne debugowanie i transakcje między modułami.

**Wady**
- Trudniejsza ewolucja, jeśli granice między modułami są słabe.
- Duże wdrożenia mogą zwiększać ryzyko release’u.
- Skalowanie jest często zgrubne (cała aplikacja naraz).

2. **Mikroserwisy (wiele niezależnie wdrażanych usług)**

- System podzielony na małe usługi powiązane z domenami biznesowymi.
- Każda usługa posiada własną logikę i często własny datastore.

**Zalety**
- Niezależne skalowanie/wdrożenia dla każdej usługi.
- Jasne granice odpowiedzialności.
- Elastyczność technologii/runtime per usługa.

**Wady**
- Wyższa złożoność (sieć, obserwowalność, auth, retry, spójność danych).
- Trudniejszy lokalny development i debugowanie między usługami.
- Wymagana znaczna dojrzałość DevOps/platformowa.

3. **Praktyczna rzeczywistość w PHP**

- Wiele zespołów osiąga sukces, zaczynając od modularnego monolitu.
- Mikroserwisy stają się opłacalne, gdy wyraźne bounded contexts i skala zespołu uzasadniają koszty operacyjne.

4. **Wytyczna decyzyjna**

- Wybierz **monolit/modularny monolit**, gdy:
  produkt jest na wczesnym etapie, zespół jest mały/średni i najważniejsza jest szybkość.
- Wybierz **mikroserwisy**, gdy:
  domeny są wyraźnie separowalne, potrzeby skalowania mocno się różnią, a możliwości platformowe są dojrzałe.

5. **Częsty błąd**

- Start od mikroserwisów zbyt wcześnie tworzy przypadkową złożoność bez realnego efektu biznesowego.

W ekosystemie PHP pragmatyczna ścieżka najczęściej wygląda tak: najpierw dobrze ustrukturyzowany monolit, a potem selektywna ekstrakcja usług dopiero wtedy, gdy wymuszą to obiektywne ograniczenia.

</details>

<details>
  <summary><strong>#77. Czym jest architektura modularnego monolitu?</strong></summary>

#### PHP

Modularny monolit to pojedyncza aplikacja wdrożeniowa zorganizowana jako wyraźnie odseparowane moduły wewnętrzne z jawnymi granicami i kontraktami.

1. **Główna idea**

- Jedna aplikacja / jeden runtime / jedna jednostka wdrożeniowa.
- Wewnątrz wiele modułów biznesowych (bounded contexts).
- Silne granice wewnętrzne ograniczające sprzężenie.

2. **Czym się różni**

- W porównaniu do klasycznego monolitu:
  modularny monolit wymusza ścisłe granice modułów i reguły zależności.
- W porównaniu do mikroserwisów:
  zachowuje pojedynczą jednostkę wdrożeniową i unika złożoności systemów rozproszonych.

3. **Typowa struktura modułów w PHP**

- `Modules/Orders/...`
- `Modules/Billing/...`
- `Modules/Users/...`

Każdy moduł zawiera własne:
- logikę domenową,
- serwisy aplikacyjne/use-case,
- adaptery infrastrukturalne,
- handlery HTTP/API (lub mapowane interfejsy).

4. **Dlaczego zespoły to wybierają**

- Szybszy rozwój niż w mikroserwisach.
- Łatwiejsze lokalne debugowanie i transakcje.
- Niższy narzut operacyjny.
- Dobra ścieżka do organizacji domain-driven i przyszłej ekstrakcji usług.

5. **Praktyki egzekwowania granic**

- Komunikacja między modułami przez interfejsy/zdarzenia, nie przez bezpośrednie wnętrza.
- Unikanie współdzielonych, mutowalnych „god utilities” między modułami.
- Używanie analizy statycznej/testów do wymuszania kierunku zależności.
- Jasna własność danych w bazie (nawet jeśli fizycznie jest współdzielona).

6. **Kiedy to dobre dopasowanie**

- Produkt i zespół rosną, ale złożoność mikroserwisów byłaby przedwczesna.
- Potrzebna jest silna separacja domen przy prostym modelu wdrożenia.

7. **Ścieżka ewolucji**

- Start od modularnego monolitu.
- Ekstrakcja wybranych modułów do usług dopiero wtedy, gdy presja skali/zespołu/odpowiedzialności jest realna i mierzalna.

Modularny monolit to często najbardziej pragmatyczna architektura dla zespołów PHP, które chcą czystych granic już dziś, bez zbyt wczesnego narzutu systemu rozproszonego.

</details>

<details>
  <summary><strong>#78. Jakie są najczęstsze podatności PHP w realnych projektach?</strong></summary>

#### PHP

Większość realnych incydentów bezpieczeństwa w projektach PHP wynika nie z samego języka, lecz z niebezpiecznej obsługi wejścia, słabej kontroli auth/sesji oraz problemów z zależnościami i konfiguracją.

1. **Podatności typu injection**

- SQL Injection przez niebezpieczne budowanie zapytań.
- Command Injection przy przekazywaniu niezaufanego wejścia do wywołań shell/system.
- Wstrzyknięcia typu header/LDAP/NoSQL w warstwach integracyjnych.

2. **Podatności cross-site**

- XSS (stored/reflected/DOM) z powodu braku kontekstowego escapingu wyjścia.
- CSRF w flow opartym o cookies bez tokenów i zabezpieczeń SameSite.

3. **Błędy uwierzytelniania i autoryzacji**

- Słaba obsługa haseł lub brak MFA dla ról krytycznych.
- Broken access control (IDOR/BOLA): użytkownik uzyskuje dostęp do cudzych zasobów przez zmianę ID.
- Brak serwerowych kontroli autoryzacji na wrażliwych endpointach.

4. **Problemy sesji i tokenów**

- Niezabezpieczone flagi cookies (`Secure`, `HttpOnly`, `SameSite` nieustawione).
- Session fixation/hijacking przez słabą rotację identyfikatorów.
- Wyciekłe lub długowieczne tokeny API bez strategii unieważniania.

5. **Ryzyka obsługi plików**

- Niebezpieczny upload plików (brak walidacji typu/zawartości, upload wykonywalnych plików).
- Path traversal (`../`) przez brak kontroli ścieżek.
- Niebezpieczna deserializacja lub niebezpieczne parsowanie niezaufanych plików.

6. **Ryzyka konfiguracji i zależności**

- Włączony tryb debug w produkcji.
- Ujawnione sekrety w repozytorium/logach/zrzutach środowiska.
- Nieaktualne zależności z CVE.
- Błędna konfiguracja nagłówków CORS/CSP/security.

7. **Jak systemowo ograniczać ryzyko**

- Ścisła walidacja wejścia + kodowanie wyjścia zależnie od kontekstu.
- Prepared statements i bezpieczne warstwy zapytań.
- Scentralizowane polityki authz i kontrole deny-by-default.
- Bezpieczny cykl życia sesji/tokenów.
- Skanowanie/łatanie zależności i utwardzona konfiguracja produkcyjna.
- Regularne testy bezpieczeństwa (SAST/DAST), logowanie i playbooki incydentowe.

Bezpieczeństwo projektów PHP to przede wszystkim dyscyplina: bezpieczny design, bezpieczne ustawienia domyślne i ciągła weryfikacja w kodzie, runtime oraz operacjach.

</details>

<details>
  <summary><strong>#79. Jak wykrywać wycieki pamięci w PHP?</strong></summary>

#### PHP

W PHP „wycieki pamięci” często nie są klasycznymi, trwałymi wyciekami na poziomie kodu skryptu, lecz wzrostem użycia pamięci powodowanym przez długotrwałe procesy, utrzymywane referencje, duże bufory w pamięci, wycieki na poziomie rozszerzeń albo fragmentację alokatora.

1. **Najpierw ustal, gdzie pojawia się zachowanie podobne do wycieku**

- Model FPM/request: pamięć powinna wracać po zakończeniu requestu; wzrost zwykle wskazuje problemy na poziomie workerów lub zbyt ciężkie żądania.
- Długotrwałe workery (consumerzy kolejek, demony, Swoole/RoadRunner): częstym źródłem jest stan utrzymywany między jobami.
- Skrypty CLI batch: nieograniczone tablice/cache mogą symulować wycieki.

2. **Instrumentuj pamięć w kodzie**

- Używaj `memory_get_usage(true)` i `memory_get_peak_usage(true)` wokół kluczowych etapów pipeline.
- Loguj pamięć per iteracja/job, aby wykryć trend monotonicznego wzrostu.
- Dodaj liczniki przetworzonych elementów, by skorelować pamięć z wielkością obciążenia.

3. **Stosuj diagnostykę runtime/procesową**

- Obserwuj RSS workerów w czasie przez `ps`, `top`, metryki kontenera lub APM.
- Porównuj zużycie na poziomie PHP i OS, aby wykryć zachowanie alokatora/fragmentacji.
- W FPM monitoruj pamięć worker pool i wzorce restartów.

4. **Używaj profilerów i wyspecjalizowanych narzędzi**

- Xdebug/Blackfire/Tideways do hotspotów alokacji i ciężkich ścieżek wywołań.
- Valgrind/ASan dla wycieków na poziomie rozszerzeń C/native (buildy debug, wolniejsze, ale precyzyjne).
- Frameworkowe paski debug/profilery do snapshotów pamięci requestów.

5. **Typowe przyczyny źródłowe do sprawdzenia**

- Statyczne/globalne tablice akumulujące dane między jobami.
- Listenery zdarzeń/closures nieintencjonalnie przechwytujące duże obiekty.
- ORM identity map lub wyniki zapytań trzymane zbyt długo.
- Duże kopie stringów/payloadów JSON podczas transformacji.
- Referencje cykliczne + opóźniony GC w długich pętlach.

6. **Wzorce mitygacji po wykryciu**

- Przetwarzaj dane w chunkach/streamach zamiast pełnych kolekcji in-memory.
- Jawnie `unset()` dużych zmiennych i okazjonalnie `gc_collect_cycles()` w długich pętlach.
- Odtwarzaj proces workera po N jobach/czasie (`--max-jobs`, restarty supervisora).
- Ustaw rozsądne limity pamięci i fail-fast behavior.
- Aktualizuj zależności/rozszerzenia, gdy wycieki natywne są naprawiane upstream.

Praktyczne podejście to: zmierzyć trend, odizolować hotspot, potwierdzić profilowaniem i wymusić granice cyklu życia dla procesów długotrwałych.

</details>

<details>
  <summary><strong>#80. Jak optymalizować zużycie pamięci?</strong></summary>

#### PHP

Optymalizacja pamięci w PHP to głównie kontrola cyklu życia danych, ograniczanie zbędnych kopii oraz stosowanie przetwarzania strumieniowego/chunkowego zamiast ładowania wszystkiego naraz.

1. **Przetwarzaj dane przyrostowo**

- Dla dużych zbiorów preferuj generatory (`yield`) zamiast budowania ogromnych tablic.
- Czytaj pliki/strumienie linia po linii albo w chunkach.
- Stronicuj odczyty z bazy (`LIMIT/OFFSET` lub cursor/chunk API) w jobach batch.

2. **Unikaj niepotrzebnych kopii**

- Ograniczaj konkatenację stringów w ciasnych pętlach; stosuj strategie buforowania.
- Unikaj wielokrotnego `array_merge` na dużych tablicach wewnątrz pętli.
- Uważaj na transformacje duplikujące duże struktury.

3. **Zwalniaj pamięć wcześnie w skryptach długotrwałych**

- Używaj `unset()` dla dużych zmiennych tymczasowych po użyciu.
- Dziel pracę na ograniczone iteracje; czyść stan per iteracja.
- Przy referencjach cyklicznych w długich pętlach okresowo wywołuj `gc_collect_cycles()`.

4. **Wybieraj wydajne wzorce dostępu do danych**

- W SQL pobieraj tylko potrzebne kolumny, nie `SELECT *`.
- Hydratuj lekkie DTO/tablice, gdy pełne modele ORM nie są potrzebne.
- Ostrożnie używaj lazy-loading; unikaj zapytań N+1 i nadmiernych grafów obiektów.

5. **Stosuj limity runtime i kontrolę cyklu życia workerów**

- Ustaw rozsądny `memory_limit`, aby system fail-fast zamiast degradować hosta.
- Dla workerów kolejek restartuj proces po N jobach/czasie, aby unikać długoterminowego dryfu pamięci.
- Monitoruj trend pamięci przez `memory_get_usage(true)` oraz metryki OS.

6. **Cache’uj mądrze, nie bezrefleksyjnie**

- Cache’uj tylko kosztowne i wartościowe obliczenia.
- Przechowuj kompaktowe payloady cache; kompresuj, gdy to korzystne.
- Używaj TTL/inwalidacji, by zapobiegać nieograniczonemu wzrostowi cache.

7. **Profiluj przed i po**

- Używaj Xdebug/Blackfire/Tideways/APM do znalezienia realnych hotspotów.
- Najpierw optymalizuj zmierzone bottlenecks; unikaj przedwczesnych mikrooptymalizacji.

W praktyce największe zyski dają: streaming/chunking, kontrola cyklu życia obiektów oraz ograniczanie dużych alokacji tymczasowych.

</details>

<details>
  <summary><strong>#81. Jak odwrócić string bez funkcji wbudowanych?</strong></summary>

#### PHP

Główna idea: przejść po stringu od końca do początku i zbudować nowy string znak po znaku.

```php
<?php
function reverseString(string $s): string
{
    $result = '';
    $length = strlen($s);

    for ($i = $length - 1; $i >= 0; $i--) {
        $result .= $s[$i];
    }

    return $result;
}
```

Złożoność czasowa to `O(n)`, a dodatkowa pamięć to `O(n)` na odwrócony wynik.

Uwagi na rozmowie:

- Ta wersja oparta na bajtach działa dla ASCII.
- Dla UTF-8/stringów wielobajtowych indeksowanie po bajtach może psuć znaki, więc potrzebne jest podejście multibyte-safe.

</details>

<details>
  <summary><strong>#82. Jak usunąć duplikaty z tablicy?</strong></summary>

#### PHP

Standardowe podejście to śledzenie już widzianych wartości w mapie haszującej i pozostawienie tylko pierwszego wystąpienia.

```php
<?php
function removeDuplicates(array $input): array
{
    $seen = [];
    $result = [];

    foreach ($input as $value) {
        $key = is_scalar($value) || $value === null
            ? (string) $value . ':' . gettype($value)
            : serialize($value);

        if (!isset($seen[$key])) {
            $seen[$key] = true;
            $result[] = $value;
        }
    }

    return $result;
}
```

Dlaczego ta wersja jest dobra na rozmowie:

- Zachowuje kolejność wstawiania.
- Działa średnio w czasie liniowym: `O(n)`.
- Obsługuje skalary, `null` i wartości złożone przez `serialize`.

Jeśli pytanie dopuszcza funkcje wbudowane, `array_unique()` jest krótsze, ale ręczna logika hash-set lepiej pokazuje fundamenty.

</details>

<details>
  <summary><strong>#83. Jak znaleźć drugą największą liczbę?</strong></summary>

#### PHP

Solidne rozwiązanie w jednym przebiegu polega na śledzeniu największej i drugiej największej **różnej** wartości podczas iteracji po tablicy.

```php
<?php
function secondLargest(array $numbers): ?int
{
    $max = null;
    $second = null;

    foreach ($numbers as $n) {
        if (!is_int($n)) {
            continue;
        }

        if ($max === null || $n > $max) {
            if ($max !== $n) {
                $second = $max;
            }
            $max = $n;
            continue;
        }

        if ($n !== $max && ($second === null || $n > $second)) {
            $second = $n;
        }
    }

    return $second;
}
```

Zachowanie:

- Zwraca `null`, jeśli nie ma drugiego różnego maksimum (np. `[5]`, `[7, 7]`).
- Złożoność czasowa: `O(n)`.
- Złożoność pamięciowa: `O(1)`.

</details>

<details>
  <summary><strong>#84. Jak sprawdzić, czy string jest palindromem?</strong></summary>

#### PHP

Palindrom czyta się tak samo od przodu i od tyłu. Wydajnie można to sprawdzić, porównując znaki z obu końców i przesuwając się do środka.

```php
<?php
function isPalindrome(string $s): bool
{
    $left = 0;
    $right = strlen($s) - 1;

    while ($left < $right) {
        if ($s[$left] !== $s[$right]) {
            return false;
        }
        $left++;
        $right--;
    }

    return true;
}
```

Złożoność:

- Czas: `O(n)`
- Pamięć: `O(1)`

Uwagi na rozmowie:

- To podejście bajtowe, dobre dla ASCII.
- Dla UTF-8 użyj podejścia bezpiecznego dla stringów wielobajtowych przed indeksowaniem znaków.
- Ustal, czy należy ignorować spacje, interpunkcję i wielkość liter; jeśli tak, najpierw znormalizuj wejście.

</details>

<details>
  <summary><strong>#85. Jak sprawdzić, czy liczba jest pierwsza?</strong></summary>

#### PHP

Liczba `n` jest pierwsza, jeśli ma dokładnie dwa dodatnie dzielniki: `1` i `n`.  
Wydajne sprawdzenie: testuj podzielność tylko do `sqrt(n)`.

```php
<?php
function isPrime(int $n): bool
{
    if ($n < 2) {
        return false;
    }

    if ($n === 2) {
        return true;
    }

    if ($n % 2 === 0) {
        return false;
    }

    $limit = (int) sqrt($n);
    for ($i = 3; $i <= $limit; $i += 2) {
        if ($n % $i === 0) {
            return false;
        }
    }

    return true;
}
```

Złożoność:

- Czas: `O(sqrt(n))`
- Pamięć: `O(1)`

To standardowe rozwiązanie na rozmowie: poprawne, wystarczająco szybkie i łatwe do uzasadnienia.

</details>

<details>
  <summary><strong>#86. Jak zaimplementować silnię rekurencyjnie?</strong></summary>

#### PHP

Rekurencyjna silnia używa definicji `n! = n * (n - 1)!` z przypadkiem bazowym `0! = 1` (oraz `1! = 1`).

```php
<?php
function factorial(int $n): int
{
    if ($n < 0) {
        throw new InvalidArgumentException('Silnia nie jest zdefiniowana dla liczb ujemnych.');
    }

    if ($n === 0 || $n === 1) {
        return 1;
    }

    return $n * factorial($n - 1);
}
```

Złożoność:

- Czas: `O(n)`
- Pamięć: `O(n)` ze względu na stos rekurencji.

Uwaga na rozmowie: wersja iteracyjna używa `O(1)` pamięci stosu i jest bezpieczniejsza dla bardzo dużych `n`.

</details>

<details>
  <summary><strong>#87. Jak zaimplementować sortowanie ręcznie?</strong></summary>

#### PHP

Na rozmowie czytelnym manualnym przykładem jest Bubble Sort: wielokrotnie zamieniasz sąsiednie elementy, jeśli są w złej kolejności.

```php
<?php
function bubbleSort(array $arr): array
{
    $n = count($arr);

    for ($i = 0; $i < $n - 1; $i++) {
        $swapped = false;

        for ($j = 0; $j < $n - 1 - $i; $j++) {
            if ($arr[$j] > $arr[$j + 1]) {
                $tmp = $arr[$j];
                $arr[$j] = $arr[$j + 1];
                $arr[$j + 1] = $tmp;
                $swapped = true;
            }
        }

        if (!$swapped) {
            break;
        }
    }

    return $arr;
}
```

Złożoność:

- Najgorszy/średni czas: `O(n^2)`
- Najlepszy przypadek (już posortowane z early break): `O(n)`
- Pamięć: `O(1)` dodatkowo (pomijając semantykę kopiowania wyniku)

Jeśli padnie pytanie o wydajniejszy algorytm, wyjaśnij Merge Sort (`O(n log n)`) albo Quick Sort średnio (`O(n log n)`).

</details>

<details>
  <summary><strong>#88. Jak wygenerować ciąg Fibonacciego?</strong></summary>

#### PHP

Najbardziej praktyczne podejście jest iteracyjne: zaczynasz od `0, 1` i dopisujesz sumę dwóch poprzednich liczb.

```php
<?php
function fibonacciSequence(int $count): array
{
    if ($count <= 0) {
        return [];
    }

    if ($count === 1) {
        return [0];
    }

    $result = [0, 1];

    for ($i = 2; $i < $count; $i++) {
        $result[] = $result[$i - 1] + $result[$i - 2];
    }

    return $result;
}
```

Złożoność:

- Czas: `O(n)`
- Pamięć: `O(n)` na przechowanie sekwencji

Uwaga na rozmowie:

- Rekurencyjny Fibonacci bez memoizacji ma złożoność wykładniczą i zwykle nie jest akceptowalny w odpowiedziach nastawionych na wydajność.
- Jeśli potrzebna jest tylko n-ta wartość, pamięć można zredukować do `O(1)`, trzymając tylko dwie poprzednie liczby.

</details>

<details>
  <summary><strong>#89. Jak znaleźć najczęściej występujący element?</strong></summary>

#### PHP

Użyj mapy częstotliwości (hash table): zliczaj wystąpienia każdej wartości, a potem zwróć klucz z maksymalnym licznikiem.

```php
<?php
function mostFrequentElement(array $items): mixed
{
    if ($items === []) {
        return null;
    }

    $freq = [];
    $bestKey = null;
    $bestCount = 0;

    foreach ($items as $item) {
        $key = is_scalar($item) || $item === null
            ? (string) $item . ':' . gettype($item)
            : serialize($item);

        if (!isset($freq[$key])) {
            $freq[$key] = ['value' => $item, 'count' => 0];
        }

        $freq[$key]['count']++;

        if ($freq[$key]['count'] > $bestCount) {
            $bestCount = $freq[$key]['count'];
            $bestKey = $key;
        }
    }

    return $bestKey !== null ? $freq[$bestKey]['value'] : null;
}
```

Złożoność:

- Czas: `O(n)`
- Pamięć: `O(k)`, gdzie `k` to liczba różnych elementów

Zachowanie przy remisie: ta implementacja zwraca pierwszy element, który osiągnął najwyższą częstotliwość.

</details>

<details>
  <summary><strong>#90. Jak zaprojektować system PHP pod wysokie obciążenie?</strong></summary>

#### PHP

W systemach PHP o wysokim obciążeniu kluczowa zasada to: utrzymać aplikację bezstanową, wynieść ciężkie operacje poza ścieżkę requestu i skalować horyzontalnie za niezawodną infrastrukturą.

1. **Bazowa architektura**

- Bezstanowe instancje aplikacji PHP za load balancerem.
- Nginx/Envoy + PHP-FPM (lub RoadRunner/Swoole, gdy to uzasadnione).
- Osobne warstwy danych, cache, kolejek i object storage.

2. **Strategia danych**

- Primary DB + read replicas; rozdzielenie ścieżek read/write.
- Poprawne indeksowanie, optymalizacja zapytań i monitoring slow queries.
- Partycjonowanie/sharding dopiero, gdy wyczerpano skalowanie pojedynczego węzła.

3. **Warstwy cache**

- CDN/edge cache dla statycznych i cache’owalnych odpowiedzi dynamicznych.
- Redis/Memcached dla danych aplikacyjnych i „gorących” wyników zapytań.
- Jasna polityka inwalidacji cache (TTL + inwalidacja zdarzeniowa).

4. **Przetwarzanie asynchroniczne**

- Wynoś kosztowne zadania do kolejek (maile, raporty, przetwarzanie mediów).
- Używaj idempotentnych workerów z retry i dead-letter queues.
- Utrzymuj requesty HTTP krótkie i przewidywalne.

5. **Niezawodność i odporność**

- Timeouty, circuit breakery, bulkheads dla zależności zewnętrznych.
- Graceful degradation, gdy usługi niekrytyczne zawodzą.
- Health checki, auto-restarty i rolling deployments.

6. **Obserwowalność**

- Scentralizowane logi z correlation IDs.
- Metryki: p95/p99 latency, error rate, queue lag, saturacja DB/cache.
- Tracing dla ścieżek requestów między usługami.

7. **Praktyki operacyjne**

- Capacity planning i load testing przed wydarzeniami szczytowymi.
- Wdrożenia blue-green/canary dla redukcji ryzyka.
- Hardening bezpieczeństwa i rate limiting na poziomie edge i aplikacji.

Skalowalny projekt PHP to głównie dyscyplina infrastrukturalna i architektoniczna: bezstanowa warstwa aplikacji, wydajny dostęp do danych, agresywne cache’owanie i asynchroniczne wykonanie zadań w tle.

</details>

<details>
  <summary><strong>#91. Jak skalować PHP horyzontalnie?</strong></summary>

#### PHP

Skalowanie horyzontalne w PHP oznacza dodawanie większej liczby identycznych węzłów aplikacji i dopilnowanie, aby każde żądanie mogło zostać obsłużone przez dowolny węzeł, bez polegania na lokalnym stanie.

1. **Uczyń warstwę aplikacji bezstanową**

- Przechowuj sesje w Redis/DB, nie na lokalnym dysku.
- Przenoś uploadowane pliki do współdzielonego/object storage (np. zgodnego z S3).
- Traktuj cache lokalny węzła jako opcjonalny, a nie jako źródło prawdy.

2. **Umieść węzły za load balancerem**

- Użyj load balancera L4/L7 (Nginx, HAProxy, cloud LB).
- Włącz health checki i automatyczne usuwanie niezdrowych węzłów.
- Sticky sessions to obejście tymczasowe; preferuj prawdziwie bezstanowy projekt.

3. **Skaluj zależności read-heavy**

- Dodaj read replicas DB i poprawnie kieruj ruch odczytowy.
- Dodaj rozproszony cache (Redis/Memcached), aby odciążyć primary DB.
- Używaj CDN dla zasobów statycznych i odpowiedzi cache’owalnych.

4. **Kontroluj obciążenia w tle**

- Używaj workerów kolejkowych dla ciężkich zadań.
- Skaluj workerów niezależnie od węzłów HTTP.
- Zapewnij idempotencję zadań i bezpieczny retry.

5. **Ustandaryzuj runtime przez kontenery/obrazy**

- Niezmienne obrazy dla spójnych wdrożeń.
- Polityki autoskalowania oparte na sygnałach CPU, pamięci i opóźnień.
- Scentralizowane zarządzanie konfiguracją/sekretami.

6. **Obserwowalność i sygnały skalowania**

- Śledź p95/p99 latency, saturację, error rate, queue lag.
- Monitoruj presję puli połączeń DB i cache hit ratio.
- Używaj tych metryk do autoskalowania i capacity planningu.

W praktyce skalowanie horyzontalne PHP jest proste, gdy stan jest eksternalizowany, a infrastruktura obsługuje dystrybucję ruchu, health i elastyczność.

</details>

<details>
  <summary><strong>#92. Jak obsłużyć miliony użytkowników?</strong></summary>

#### PHP

Obsługa milionów użytkowników to zadanie projektowania systemu, a nie pojedynczy trik w PHP. Rozwiązanie wymaga warstwowego skalowania: edge, aplikacja, dane i operacje.

1. **Dystrybucja ruchu i warstwa edge**

- Globalny CDN dla zasobów statycznych i cache’owalnych odpowiedzi API.
- Load balancery z autoskalowanymi, bezstanowymi węzłami aplikacji PHP.
- Rate limiting i ochrona przed botami na poziomie edge.

2. **Architektura aplikacji**

- Dziel bottlenecki monolitu na bounded services, gdy to potrzebne.
- Minimalizuj synchroniczną ścieżkę requestu; ciężkie zadania przenoś do kolejek.
- Używaj kluczy idempotencji dla krytycznych operacji zapisu.

3. **Warstwa danych w skali**

- Primary DB dla zapisów, wiele read replicas dla ruchu odczytowego.
- Agresywne indeksowanie i tuning zapytań; unikaj antywzorców ORM.
- Partycjonowanie/sharding dla bardzo dużych zbiorów i „hot tenants”.

4. **Strategia cache**

- Wielowarstwowy cache: CDN -> Redis/Memcached -> DB.
- Cache’uj hot objects, widoki obliczane i kosztowne zapytania.
- Silne reguły inwalidacji, by zapobiegać przestarzałym krytycznym danym.

5. **Przetwarzanie asynchroniczne i event-driven**

- Workery kolejkowe dla e-maili, powiadomień, mediów i pipeline’ów analitycznych.
- Retry z backoff, dead-letter queues i idempotentne handlery.
- Strumieniowanie zdarzeń do odbiorców downstream zamiast blokowania requestów.

6. **Niezawodność i odporność**

- Graceful degradation dla funkcji niekrytycznych pod presją.
- Budżety timeoutów i circuit breakery dla zależności.
- Wdrożenia multi-AZ i przetestowane procedury failover.

7. **Obserwowalność i dyscyplina pojemnościowa**

- SLO dla opóźnień/błędów; śledź p95/p99 i saturację.
- Ciągłe load/stress testy przed dużymi premierami.
- Prognozowanie pojemności na podstawie realnych wzorców użycia.

Przy skali „milionów” sukces daje przewidywalna architektura, kontrolowany wzrost danych i silne praktyki operacyjne bardziej niż optymalizacje na poziomie samego języka.

</details>

<details>
  <summary><strong>#93. Jak zaprojektować strategię cache’owania?</strong></summary>

#### PHP

Dobra strategia cache’owania zaczyna się od wzorców dostępu i wymagań spójności, a nie wyłącznie od wyboru technologii.

1. **Zdefiniuj, co cache’ować**

- Kosztowne wyniki zapytań DB.
- Agregowane/obliczane odpowiedzi API.
- Kontekst sesji i autoryzacji (gdy to bezpieczne).
- Dane statyczne/konfiguracyjne/referencyjne o niskiej częstotliwości zmian.

2. **Stosuj cache wielowarstwowy**

- Cache edge/CDN dla zasobów statycznych i cache’owalnych odpowiedzi HTTP.
- Cache aplikacyjny (Redis/Memcached) dla hot objects i wyników zapytań.
- Optymalizacje in-process/OPcache dla kodu i niezmiennej konfiguracji.

3. **Dobierz właściwe wzorce cache**

- Cache-aside dla danych read-heavy (najczęstsze).
- Write-through/write-behind dla konkretnych przypadków spójności/wydajności.
- Read-through, jeśli provider cache wspiera transparentne ładowanie.

4. **Projektuj klucze i TTL świadomie**

- Klucze namespacowane: `entity:{id}:v{version}`.
- Różne TTL zależnie od zmienności danych i krytyczności biznesowej.
- Dodawaj jitter do TTL, by ograniczyć thundering herd.

5. **Obsługuj inwalidację jawnie**

- Inwalidacja zdarzeniowa po zapisach.
- Klucze wersjonowane do łatwej logicznej inwalidacji.
- Inwalidacja tagowa, gdy jest wspierana.

6. **Zabezpieczaj się przed awariami cache**

- Ścieżka fallback, gdy cache nie działa (degradacja, ale funkcjonalność zachowana).
- Coalescing/locking żądań, aby zapobiegać stampede.
- Warm-up krytycznych kluczy po deployu/restarcie.

7. **Mierz i stroń stale**

- Monitoruj hit ratio, latency, eviction rate i presję pamięci.
- Śledź incydenty stale-read i koszt cache-miss.
- Optymalizuj na podstawie realnych śladów produkcyjnych.

Silna strategia cache’owania to balans: maksymalizacja hit rate i zysków latency przy zachowaniu poprawności oraz przewidywalnego zachowania inwalidacji.

</details>

<details>
  <summary><strong>#94. Czym nowoczesne frameworki PHP (Laravel, Symfony) różnią się wewnętrznie?</strong></summary>

#### PHP

Laravel i Symfony mają wiele wspólnych fundamentów (cykl życia żądania HTTP, DI, koncepcje middleware/zdarzeń), ale różnią się filozofią architektury, ustawieniami domyślnymi i modelem rozszerzalności.

1. **Filozofia bazowa**

- Symfony: podejście component-first, jawna konfiguracja, wysoka kompozycyjność.
- Laravel: zintegrowane doświadczenie deweloperskie, silne konwencje, szybsze dostarczanie „out of the box”.

2. **Dependency Injection i kontener**

- Symfony ma kompilowany kontener DI z mocną walidacją i optymalizacją na etapie kompilacji.
- Laravel używa bardzo dynamicznego kontenera usług z rozwiązywaniem w runtime i auto-wiringiem nastawionym na ergonomię dewelopera.

3. **Model konfiguracji**

- Symfony: konfiguracja-centric (`yaml/xml/php`), bundlery zależne od środowiska, jawne wiązanie.
- Laravel: konwencje + service providery + facades; wiele funkcji działa przy minimalnej konfiguracji.

4. **Wnętrze pipeline HTTP**

- W Symfony przepływ requestu opiera się na `HttpKernel` i listenerach event dispatchera.
- W Laravel przepływ requestu jest oparty na pipeline middleware z ekspresyjną integracją route/controller.

5. **Domyślna warstwa ORM/danych**

- Symfony najczęściej używa Doctrine ORM (wzorzec Data Mapper, jawne zachowanie unit-of-work).
- Laravel dostarcza Eloquent (wzorzec Active Record, szybka ergonomia CRUD).

6. **Struktura ekosystemu**

- Komponenty Symfony są szeroko używane samodzielnie w całym ekosystemie PHP.
- Ekosystem Laravel jest mocno zintegrowany (kolejki, joby, scheduler, Horizon, wzorce narzędzi typu Nova).

7. **Profil wydajności i produkcyjny**

- Oba mogą działać produkcyjnie w dużej skali.
- Symfony często stawia na przewidywalność i jawną kontrolę w dużych systemach enterprise.
- Laravel podkreśla szybkość implementacji i spójny workflow deweloperski.

W skrócie: Symfony optymalizuje pod jawną architekturę i kompozycję komponentów; Laravel optymalizuje pod zintegrowaną produktywność i szybkie dostarczanie funkcji.

</details>

<details>
  <summary><strong>#95. Jak działa routing we frameworkach?</strong></summary>

#### PHP

Routing mapuje przychodzące żądanie HTTP do konkretnego handlera (controller/action/closure) na podstawie metody, wzorca ścieżki, hosta i opcjonalnych ograniczeń.

1. **Etap definicji tras**

- Framework ładuje tabelę tras podczas uruchamiania (z plików/atrybutów/adnotacji).
- Każda trasa przechowuje metodę(y), wzorzec ścieżki, handler, middleware i metadane.
- Wiele frameworków prekompiluje/cache’uje definicje tras dla szybszego dopasowania.

2. **Etap dopasowania żądania**

- Router otrzymuje znormalizowaną ścieżkę żądania + metodę.
- Najpierw próbuje dopasować trasy statyczne, potem dynamiczne parametryzowane.
- Walidowane są ograniczenia (regex, host, scheme, locale).

3. **Ekstrakcja parametrów**

- Segmenty dynamiczne, np. `/users/{id}`, są wyciągane ze ścieżki.
- Wartości są rzutowane/walidowane (jawnie lub przez reguły bindowania frameworka).
- Dla brakujących parametrów opcjonalnych stosowane są wartości domyślne.

4. **Middleware i guardy**

- Przed wykonaniem handlera uruchamia się łańcuch middleware globalnych/grupowych/trasy.
- Typowe kontrole: auth, rate limiting, CSRF, uprawnienia, tenant resolution.
- Middleware może przerwać przepływ i zwrócić odpowiedź wcześniej.

5. **Dispatch do kontrolera**

- Kontener rozwiązuje zależności kontrolera.
- Parametry trasy + wstrzyknięte serwisy są przekazywane do metody akcji.
- Akcja zwraca obiekt odpowiedzi/dane do serializacji.

6. **Reverse routing**

- Framework potrafi generować URL-e z nazw tras + parametrów.
- To eliminuje hardcoded URL-e i zwiększa bezpieczeństwo refaktoryzacji.

7. **Aspekty wydajnościowe**

- Cache/prekompilacja tras w produkcji.
- Preferowanie tras specyficznych/statycznych nad zbyt szerokimi wildcardami.
- Utrzymywanie minimalnego łańcucha middleware dla „gorących” endpointów.

Wewnętrznie routing to zasadniczo indeksowane dopasowanie wzorców i pipeline dispatchu opakowany middleware i dependency injection.

</details>

<details>
  <summary><strong>#96. Jak wewnętrznie działa pipeline middleware?</strong></summary>

#### PHP

Pipeline middleware to łańcuch odpowiedzialności: każdy middleware otrzymuje żądanie i callable „next”, po czym albo przekazuje sterowanie dalej, albo od razu zwraca odpowiedź.

1. **Budowa pipeline’u**

- Framework zbiera middleware globalne, grupowe i przypisane do trasy.
- Rozwiązywana jest kolejność middleware (mogą obowiązywać reguły priorytetu).
- Finalny handler docelowy (controller/action) ustawiany jest jako ostatni krok.

2. **Model wykonania**

- Sygnatura middleware koncepcyjnie: `handle(Request $request, Closure $next): Response`.
- Middleware może zrobić pre-processing, potem wywołać `$next($request)`.
- Po powrocie z next middleware może wykonać post-processing odpowiedzi.

3. **Zachowanie short-circuit**

- Middleware może zwrócić odpowiedź bez wywołania `$next`.
- Typowe przypadki: błąd auth, błąd CSRF, przekroczony rate limit, maintenance mode.
- To blokuje wykonanie dalszych middleware/kontrolera.

4. **Zagnieżdżony stos wywołań**

- Łańcuch często budowany jest przez owijanie closure od końca do początku.
- Wykonanie „schodzi w dół” ścieżki requestu, a potem „odwija się” ścieżką odpowiedzi.
- To umożliwia concerns przekrojowe, np. logowanie, pomiar czasu, wstrzykiwanie nagłówków.

5. **Obsługa błędów i wyjątków**

- Middleware/handler wyjątków może przechwytywać i normalizować błędy.
- W części frameworków obsługa błędów jest poza stosem middleware, jako top-level logika kernela.
- Spójne mapowanie błędów utrzymuje przewidywalność odpowiedzi API.

6. **Typowe odpowiedzialności middleware**

- Kontrole uwierzytelniania/autoryzacji.
- Walidacja/sanitizacja żądań.
- Rate limiting i mechanizmy anti-abuse.
- Tracing, logowanie, metryki, correlation IDs.
- Nagłówki CORS/security i transformacja odpowiedzi.

7. **Aspekty wydajnościowe**

- Utrzymuj minimalny łańcuch dla „gorących” tras.
- Umieszczaj tanie kontrole reject-fast na początku.
- Unikaj ciężkiego synchronicznego I/O w ogólnych middleware.

Wewnętrznie middleware to po prostu uporządkowana kompozycja callable, która centralizuje concerns przekrojowe wokół przepływu request/response.

</details>

<details>
  <summary><strong>#97. Jak działa mechanizm rozwiązywania zależności pod maską?</strong></summary>

#### PHP

Rozwiązywanie zależności w nowoczesnych frameworkach PHP realizuje kontener DI, który buduje obiekty na podstawie wiązań i metadanych konstruktorów, zwykle przez refleksję i cache’owane definicje.

1. **Wiązania kontenera**

- Interfejsy/abstrakcje mapowane są na konkretne implementacje.
- Wiązania mogą być singleton, scoped albo transient.
- Fabryki/closure mogą definiować niestandardową logikę tworzenia.

2. **Żądanie rozwiązania**

- Framework prosi kontener o typ (controller, service, middleware itp.).
- Kontener sprawdza, czy instancja już istnieje (dla singleton/scoped lifetimes).
- Jeśli nie, rozpoczyna budowę grafu obiektów.

3. **Inspekcja konstruktora**

- Kontener analizuje parametry konstruktora (refleksja albo metadane skompilowane).
- Dla parametrów typowanych klasą rekurencyjnie rozwiązuje zależności.
- Dla skalarów/wartości konfiguracyjnych używa jawnych parametrów, wiązań env/config albo wartości domyślnych.

4. **Rekurencyjna budowa grafu obiektów**

- Zależności są rozwiązywane metodą depth-first.
- Wykrywanie zależności cyklicznych zapobiega nieskończonej rekurencji.
- Zależności opcjonalne mogą być nullable/domyslne, jeśli nie są zbindowane.

5. **Cykl życia i cache**

- Singletony są cache’owane po pierwszym utworzeniu.
- Instancje scoped są cache’owane per request/job scope.
- Część kontenerów kompiluje metadane dla szybszego rozwiązywania w produkcji.

6. **Wstrzykiwanie do metod/akcji**

- Poza konstruktorami frameworki mogą wstrzykiwać zależności do akcji kontrolerów, handlerów komend i metod middleware.
- Parametry trasy i serwisy z kontenera są łączone podczas dispatchu.

7. **Tryby awarii**

- Niezwiązany interfejs/abstrakcja.
- Niejednoznaczny lub nieinstancjowalny łańcuch zależności.
- Skalarne parametry konstruktora bez defaults/bindings.
- Zależności cykliczne między serwisami.

Pod maską rozwiązywanie DI to deterministyczna budowa grafu z regułami cyklu życia, refleksją/metadanymi i cache’owaniem dla wydajności.

</details>

<details>
  <summary><strong>#98. Jakie są best practices nowoczesnego developmentu PHP w 2026 roku?</strong></summary>

#### PHP

Nowoczesne best practices PHP w 2026 roku koncentrują się na ścisłej dyscyplinie inżynierskiej: mocnym typowaniu, automatycznych bramkach jakości, bezpiecznych domyślnych ustawieniach i obserwowalnych systemach produkcyjnych.

1. **Używaj świadomie aktualnych funkcji języka**

- `declare(strict_types=1);` w kodzie aplikacji.
- Typowane właściwości, typy zwracane, enumy, wzorce readonly/value-object.
- Gdzie to możliwe, preferuj jawne kontrakty zamiast dynamicznej „magii”.

2. **Architektura i organizacja kodu**

- Granice modułów (domain/application/infrastructure lub odpowiednik).
- Jasna separacja logiki biznesowej od kodu „klejącego” framework.
- Dependency inversion przez interfejsy dla testowalności.

3. **Automatyzacja jakości**

- CI ze statyczną analizą (PHPStan/Psalm) na wysokiej restrykcyjności.
- Spójny styl kodu przez PHP-CS-Fixer/Pint.
- Testy unit + integracyjne + kontraktowe z realistycznymi fixture’ami.

4. **Wydajność i efektywność runtime**

- PHP 8.3/8.4+ z OPcache i dostrojonym PHP-FPM/process manager.
- Najpierw profilowanie (Blackfire/XHProf/APM), potem optymalizacja hotspotów.
- Cache/kolejki dla odchudzenia synchronicznej ścieżki requestu.

5. **Security by default**

- Prepared statements, kontekstowe escapowanie wyjścia, ochrona CSRF.
- Zarządzanie sekretami poza repo; rotacja kluczy i least privilege.
- Skanowanie podatności zależności w CI.

6. **Dojrzałość operacyjna**

- Ustrukturyzowane logi, metryki, tracing, correlation IDs.
- Monitoring oparty o SLO z kontrolą alert fatigue.
- Bezpieczne releasy: canary/blue-green i procedury rollbacku.

7. **Higiena zależności i ekosystemu**

- Utrzymuj zależności Composer aktualne według kontrolowanego harmonogramu.
- Pinuj i audytuj pakiety krytyczne.
- Unikaj zbędnego sprzęgania kodu domenowego z frameworkiem.

8. **Konwencje zespołowe**

- ADR-y dla kluczowych decyzji i jasne standardy code review.
- Reguły kompatybilności wstecznej dla API publicznych/wewnętrznych.
- Dokumentacja blisko kodu dla onboardingu i response na incydenty.

Najsilniejsze zespoły PHP w 2026 traktują zdrowie codebase’u jak produkt: typowany, testowany, obserwowalny i stale ulepszany.

</details>

<details>
  <summary><strong>#99. Jakie narzędzia są kluczowe dla nowoczesnego developera PHP?</strong></summary>

#### PHP

Skuteczny nowoczesny toolkit PHP obejmuje kodowanie, jakość, debugowanie, dostarczanie i operacje.

1. **Podstawy języka i zarządzania pakietami**

- Runtime PHP 8.3/8.4+.
- Composer do zależności i autoloadingu.
- Narzędzia lokalnego środowiska: Docker/DDEV/Lando albo natywny, odtwarzalny setup.

2. **Jakość kodu i analiza statyczna**

- PHPStan albo Psalm do analizy statycznej.
- PHP-CS-Fixer albo Pint do standardów kodowania.
- PHP_CodeSniffer tam, gdzie potrzebne są niestandardowe standardy.

3. **Stos testowy**

- PHPUnit albo Pest do testów unit/integracyjnych.
- Biblioteki mocking/test doubles według potrzeb.
- Raportowanie pokrycia zintegrowane z CI.

4. **Debugowanie i profilowanie**

- Xdebug do debugowania krokowego.
- Blackfire/Tideways/XHProf/APM profiler do bottlenecków wydajności.
- Narzędzia structured logging i scentralizowany podgląd logów.

5. **Narzędzia frameworkowe i DX**

- Laravel Artisan albo Symfony Console.
- Narzędzia debug/profiler specyficzne dla frameworka.
- Narzędzia API: Postman/Insomnia + walidacja OpenAPI.

6. **Narzędzia danych i infrastruktury**

- Redis i DB CLI (`redis-cli`, `psql`, `mysql`) do diagnostyki.
- Dashboardy monitoringu kolejek/workerów.
- Narzędzia migracji i zarządzania schematem.

7. **CI/CD i automatyzacja**

- GitHub Actions/GitLab CI albo odpowiednik.
- Automatyczne bramki: lint, analiza statyczna, testy, security scan.
- Automatyzacja wdrożeń z możliwością rollbacku.

8. **Bezpieczeństwo i higiena zależności**

- `composer audit` i/lub skanery SCA.
- Secret scanning i hooki pre-commit.
- SAST/DAST tam, gdzie wymaga tego profil ryzyka.

9. **Obserwowalność i operacje**

- Stack metryk, tracingu i alertingu (Prometheus/Grafana/APM).
- Error tracking (Sentry/Bugsnag).
- Korelacja logów z request IDs.

Niezbędny zestaw to ten, który wymusza szybkie pętle feedbacku: kontrolę jakości kodu, wiarygodne testy, bezpieczne dostarczanie i widoczność produkcji.

</details>

<details>
  <summary><strong>#100. Jak utrzymać długoterminową utrzymywalność codebase’u PHP?</strong></summary>

#### PHP

Długoterminową utrzymywalność osiąga się przez połączenie standardów technicznych, dyscypliny architektonicznej i ciągłego feedbacku operacyjnego.

1. **Utrzymuj jawną architekturę**

- Egzekwuj czytelne granice modułów i ownership.
- Oddziel logikę domenową od szczegółów frameworka/infrastruktury.
- Ograniczaj ukryte sprzężenia i globalny stan.

2. **Stawiaj czytelność ponad „spryt”**

- Małe, skupione klasy/funkcje z jasnym nazewnictwem.
- Spójne konwencje w całym codebase.
- Preferuj jawne zachowanie zamiast magicznych abstrakcji.

3. **Traktuj bezpieczeństwo typów poważnie**

- `strict_types=1` tam, gdzie to możliwe.
- Silne typowanie parametrów/wartości zwracanych/właściwości.
- Analiza statyczna (PHPStan/Psalm) jako obowiązkowa bramka CI.

4. **Buduj odporny portfel testów**

- Szybkie testy unit dla logiki core.
- Testy integracyjne dla granic DB/zależności zewnętrznych.
- Testy kontraktowe dla API/zdarzeń współdzielonych z innymi usługami.

5. **Kontroluj zależności i aktualizacje**

- Regularny cykl aktualizacji zależności zamiast rzadkich „big-bang” upgrade’ów.
- Śledzenie changelogów i deprecacji frameworka/runtime.
- Proaktywne usuwanie nieużywanych pakietów i martwych abstrakcji.

6. **Projektuj pod bezpieczne zmiany**

- Reguły kompatybilności wstecznej dla publicznych API.
- Feature flagi dla ryzykownych rolloutów.
- Migracje i zmiany danych z planami rollback/repair.

7. **Instytucjonalizuj proces jakości kodu**

- Checklisty code review (poprawność, bezpieczeństwo, wydajność, czytelność).
- Automatyczne formatowanie/linting, aby zmniejszyć szum podczas review.
- ADR-y dla kluczowych decyzji, by zachować kontekst w czasie.

8. **Pętla feedbacku operacyjnego**

- Obserwowalność produkcji: logi, metryki, tracing, error tracking.
- Post-incident review z konkretnymi usprawnieniami kodu/procesu.
- Priorytetyzacja oparta o SLO, aby utrzymać widoczność niezawodności.

9. **Chroń ciągłość zespołu**

- Aktualna dokumentacja setupu, architektury i runbooków.
- Przewodniki onboardingowe i wspólne standardy inżynierskie.
- Redukcja ryzyka „single expert” przez dzielenie wiedzy i rotację.

Utrzymywalny codebase PHP nie jest statyczny; jest stale pielęgnowany przez standardy, automatyzację i świadome upraszczanie.

</details>
