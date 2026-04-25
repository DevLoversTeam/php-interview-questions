**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  PHP <img src="./assets/php.svg" width="40" height="40" alt="PHP logo"/>
</h1>

<h2>Die beliebtesten PHP-Interviewfragen und Antworten</h2>

<details>
<summary>1. Was ist PHP und welche Probleme löst es in der modernen Backend-Entwicklung?</summary>

#### PHP

PHP ist eine serverseitige Programmiersprache, die in erster Linie für die Webentwicklung konzipiert wurde. In der modernen Backend-Entwicklung löst PHP mehrere praktische Probleme:

1. **Schnelle Entwicklung von HTTP-Backends:** Mit PHP lassen sich APIs, Webanwendungen und serverseitig gerenderte Seiten schnell erstellen.

2. **Request-Verarbeitung und Business-Logik:** PHP verarbeitet eingehende HTTP-Requests, validiert Daten, führt Geschäftsregeln aus und liefert Responses zurück.

3. **Datenbankintegration:** PHP bietet ausgereifte Werkzeuge für Datenbanken (MySQL, PostgreSQL, SQLite) über PDO und ORMs.

4. **Session- und Authentifizierungs-Workflows:** Es unterstützt Benutzersessions, Login-Systeme, Cookie-Verarbeitung und Zugriffskontrolle.

5. **Ökosystem für produktive Anwendungen:** Frameworks wie Laravel und Symfony liefern Routing, Dependency Injection, Queues, Events und Test-Infrastruktur.

6. **Hintergrundverarbeitung:** PHP kann asynchrone Jobs über Queues ausführen (E-Mails, Reports, Benachrichtigungen, Importe) außerhalb des Request-Response-Flows.

7. **Skalierbarkeit in realen Systemen:** Mit OPcache, Caching-Schichten (Redis), Containern und horizontaler Skalierung betreibt PHP auch High-Load-Systeme.

8. **Integration externer Services:** PHP wird häufig für Payment-Gateways, Message-Broker, Drittanbieter-APIs und Cloud-Services eingesetzt.

Kurz gesagt löst PHP den gesamten Backend-Zyklus: Requests empfangen, Daten verarbeiten, mit Storage interagieren und sichere, wartbare Webservices bereitstellen.

</details>

<details>
<summary>2. Was sind die wichtigsten Unterschiede zwischen PHP und JavaScript (Runtime, Ausführungsmodell)?</summary>

#### PHP

PHP und JavaScript werden beide häufig in der Webentwicklung eingesetzt, unterscheiden sich aber deutlich im Runtime-Modell, im Ausführungsfluss und im typischen Backend-Verhalten.

1. **Primäre Runtime-Umgebung:**
   PHP läuft auf dem Server (PHP-FPM, CLI, Swoole/RoadRunner), während JavaScript im Browser und serverseitig über Node.js/Deno/Bun läuft.

2. **Ausführungsmodell (klassisch):**
   Traditionelles PHP arbeitet als Request-pro-Prozess/Request-pro-Worker: Jeder HTTP-Request startet, wird ausgeführt und endet mit isoliertem Zustand.
   JavaScript (Node.js) läuft typischerweise als langlebiger Prozess mit gemeinsamem In-Memory-Zustand.

3. **Nebenläufigkeitsmodell:**
   Bei PHP wird Nebenläufigkeit meist durch mehrere Worker/Prozesse erreicht, die Requests parallel verarbeiten.
   JavaScript-Serverruntimes nutzen einen Event-Loop mit asynchronem I/O und nicht-blockierenden Operationen in einem Prozess (plus Worker-Threads/Prozess-Skalierung bei Bedarf).

4. **Lebenszyklus des Zustands:**
   In klassischem PHP ist In-Memory-Zustand nicht über Requests hinweg dauerhaft, daher liegt persistenter Zustand meist in Redis/DB/Cache.
   In Node.js kann Prozessspeicher zwischen Requests bestehen bleiben, was praktisch ist, aber sorgfältiges State-Management erfordert.

5. **Typische Web-Rolle:**
   PHP ist traditionell backend-first (SSR, APIs, Business-Logik).
   JavaScript ist von Natur aus Full-Stack: Frontend-UI-Sprache plus Backend-Option.

6. **Ökosystem-Fokus:**
   Das PHP-Ökosystem betont Backend-Frameworks (Laravel, Symfony), Server-Templating und Enterprise-Web-Backends.
   Das JavaScript-Ökosystem betont stark Frontend-Frameworks plus universelle/Full-Stack-Tooling-Ansätze.

7. **Betriebsprofil:**
   PHP wird häufig hinter Nginx/Apache mit PHP-FPM-Pools betrieben.
   JavaScript-Backends werden meist als langlebige App-Prozesse hinter Reverse-Proxys betrieben.

In der Praxis wird PHP meist wegen vorhersehbarer Request-Isolation und ausgereifter Backend-Frameworks gewählt, während JavaScript oft gewählt wird, wenn Teams eine Sprache für Frontend und Backend mit asynchroner Serverentwicklung als Standard wollen.

</details>

<details>
<summary>3. Was sind die wichtigsten in PHP 8.x (8.1-8.5) eingeführten Features?</summary>

#### PHP

PHP 8.1-8.5 brachte große Verbesserungen der Sprache und Runtime. Die wichtigsten Highlights nach Version:

1. **PHP 8.1 (veröffentlicht am 25. November 2021):**
   Enums, readonly-Properties, Fibers, First-Class-Callable-Syntax, Intersection Types und der Return-Typ `never`.

2. **PHP 8.2 (veröffentlicht am 8. Dezember 2022):**
   Readonly-Klassen, DNF-Types, eigenständige Typen `null`/`false`/`true`, neue `Random`-Extension und Deprecation dynamischer Properties.

3. **PHP 8.3 (veröffentlicht am 23. November 2023):**
   Typisierte Klassenkonstanten, Attribut `#[\Override]`, dynamischer Zugriff auf Klassenkonstanten (`Class::{$name}`) sowie Verbesserungen bei readonly/Klonen.

4. **PHP 8.4 (veröffentlicht am 21. November 2024):**
   Property Hooks, asymmetrische Sichtbarkeit (Stil `public private(set)`), Attribut `#[\Deprecated]`, aktualisierte DOM-API und Lazy-Object-Unterstützung.

5. **PHP 8.5 (veröffentlicht am 20. November 2025):**
   Pipe-Operator (`|>`), URI-Extension, Clone-with-Updates via `clone(...)`, `#[\NoDiscard]`, Closures in konstanten Ausdrücken und zusätzliche API/Runtime-Verbesserungen.

#### Warum das wichtig ist

- **Bessere Typsicherheit:** stärkere Typisierung, sicherere Verträge, weniger Runtime-Überraschungen.
- **Saubereres Domain Modeling:** Enums, readonly-Konstrukte und moderne Property-Semantik.
- **Ausdrucksstärkerer Code:** Pipe-Operator, Attribute und verbesserte Callable-Unterstützung.
- **Performance und Wartbarkeit:** kontinuierliche Weiterentwicklung von Engine, Tooling und Standardbibliothek.

Kurz gesagt hat PHP 8.x die Sprache deutlich modernisiert und den Aufbau moderner Backend-Architekturen erleichtert.

</details>

<details>
<summary>4. Was sind Enums, Attribute und readonly-Properties in PHP?</summary>

#### PHP

Enums, Attribute und readonly-Properties sind moderne Sprachfeatures in PHP, die Korrektheit, Lesbarkeit und Wartbarkeit verbessern.

1. **Enums**

- Enums definieren eine feste Menge erlaubter Werte als echten Typ.
- Sie verhindern ungültige String/Int-Zustände und machen Domain Modeling sicherer.
- PHP unterstützt:
  Backed Enums (`enum Status: string { ... }`) und Unit Enums (`enum Role { ... }`).

```php
enum OrderStatus: string
{
    case Draft = 'draft';
    case Paid = 'paid';
    case Shipped = 'shipped';
}
```

2. **Attribute**

- Attribute sind native Metadaten (`#[...]`), die an Klassen, Methoden, Properties, Parameter und mehr angehängt werden.
- Sie ersetzen viele Docblock-Annotationen durch strukturierte, maschinenlesbare Metadaten.
- Häufige Anwendungsfälle: Routing, Validierung, Dependency Injection, Serialisierungsregeln, Deprecation-Marker.

```php
#[Deprecated(reason: 'Use NewService instead')]
class LegacyService {}
```

3. **Readonly-Properties**

- Eine `readonly`-Property kann nur einmal beschrieben werden (typischerweise im Konstruktor).
- Nach der Initialisierung ist Mutation verboten.
- Das ist nützlich für immutable DTOs, Value Objects und ein sichereres Objektdesign.

```php
final class UserDto
{
    public function __construct(
        public readonly int $id,
        public readonly string $email,
    ) {}
}
```

#### Warum sie zusammen wichtig sind

- **Enums** schützen erlaubte Zustände.
- **Attribute** liefern explizite Metadaten für Frameworks und Tools.
- **Readonly-Properties** erzwingen Immutabilität kritischer Daten.

Zusammen reduzieren diese Features Bugs, machen APIs klarer und verbessern die Qualität statischer Analysen in modernen PHP-Codebasen.

</details>

<details>
<summary>5. Was ist strikte Typisierung in PHP und warum ist sie wichtig?</summary>

#### PHP

Strikte Typisierung in PHP wird pro Datei aktiviert mit:

```php
declare(strict_types=1);
```

Wenn strikte Typisierung aktiviert ist, werden skalare Typdeklarationen bei Funktionsargumenten und Rückgabewerten deutlich strenger erzwungen.

1. **Ohne strikte Typisierung (`strict_types=0`, Standard):**
   PHP kann skalare Werte konvertieren (zum Beispiel `'10'` zu `10`), wenn es möglich ist.

2. **Mit strikter Typisierung (`strict_types=1`):**
   PHP wirft einen `TypeError`, statt inkompatible skalare Werte stillschweigend zu konvertieren.

```php
declare(strict_types=1);

function add(int $a, int $b): int
{
    return $a + $b;
}

add('2', 3); // TypeError im strikten Modus
```

#### Warum das wichtig ist

- **Frühe Fehlererkennung:** Typkonflikte schlagen sofort fehl.
- **Sichereres Refactoring:** klarere Verträge reduzieren versteckte Brüche.
- **Vorhersehbareres Verhalten:** weniger implizite Konvertierungs-Magie.
- **Bessere statische Analyse:** Tools wie PHPStan/Psalm werden effektiver.
- **Sauberere API-Grenzen:** Funktionssignaturen werden als strikte Verträge behandelt.

#### Praktische Empfehlung

Verwende `declare(strict_types=1);` in allen neuen PHP-Dateien und kombiniere es mit expliziten Type Hints, DTOs/Value Objects und statischer Analyse für produktionsreife Zuverlässigkeit.

</details>

<details>
<summary>6. Was sind Union Types und Intersection Types?</summary>

#### PHP

Union Types und Intersection Types in PHP sind Werkzeuge, um strengere und explizitere Typverträge auszudrücken.

1. **Union Types (`A|B`)**

- Ein Wert kann **einer von mehreren erlaubten Typen** sein.
- Nützlich, wenn ein Argument oder Rückgabewert legitimerweise variieren kann.

```php
function formatId(int|string $id): string
{
    return (string) $id;
}
```

2. **Intersection Types (`A&B`)**

- Ein Wert muss **alle aufgelisteten Typen gleichzeitig** erfüllen.
- Häufig mit Interfaces genutzt, um mehrere Fähigkeiten zu verlangen.

```php
interface Cacheable {}
interface Jsonable { public function toJson(): string; }

function store(Cacheable&Jsonable $entity): void
{
    // $entity muss beide Interfaces implementieren
}
```

3. **Wesentlicher Unterschied**

- `A|B` bedeutet **entweder A oder B**.
- `A&B` bedeutet **A und B zusammen**.

4. **Warum das wichtig ist**

- Bessere API-Verträge und selbstdokumentierender Code.
- Weniger Laufzeitfehler durch ungültige Objekt-/Wertformen.
- Stärkere statische Analyse und sichereres Refactoring.

5. **Praktische Hinweise**

- Nutze Union Types für flexible Eingabegrenzen.
- Nutze Intersection Types für capability-basiertes Design (insbesondere mit Interfaces).
- Bevorzuge spezifische Typen statt `mixed`, wenn möglich.

</details>

<details>
<summary>7. Was ist der Nullsafe-Operator und wann verwendet man ihn?</summary>

#### PHP

Der Nullsafe-Operator in PHP ist `?->`. Er ermöglicht einen sicheren Methoden-/Property-Zugriff auf Objekte, die `null` sein können.

1. **Was er macht**

- Wenn die linke Seite ein Objekt ist, läuft der Zugriff normal weiter.
- Wenn die linke Seite `null` ist, stoppt die Auswertung und liefert `null` statt eines Fehlers.

```php
$country = $user?->getProfile()?->getAddress()?->country;
```

2. **Warum er nützlich ist**

- Verhindert ausführliche verschachtelte Null-Prüfungen.
- Reduziert Boilerplate in optionalen Objektketten.
- Macht die Absicht klarer, wenn Werte legitimerweise nullable sind.

3. **Typische Anwendungsfälle**

- API-/DTO-Strukturen mit optionalen verschachtelten Feldern.
- ORM-Relationen, die fehlen können.
- Request-Context-Objekte, bei denen einige Teile optional sind.

4. **Äquivalent ohne Nullsafe (ausführlicher)**

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

5. **Wichtige Hinweise**

- `?->` funktioniert nur für Objektzugriffe (Methoden/Properties), nicht für Array-Offests.
- Er short-circuited von links nach rechts.
- Wenn die Kette zu `null` aufgelöst wird, ist das Endergebnis `null`.

Verwende den Nullsafe-Operator, wenn `null` ein erwarteter Zustand ist und du Objektgraphen kurz und sicher traversieren willst.

</details>

<details>
<summary>8. Was sind Property Hooks (PHP 8.4+)?</summary>

#### PHP

Property Hooks (eingeführt in PHP 8.4) erlauben es, Logik direkt an Lese-/Schreiboperationen von Properties zu binden, über `get`- und `set`-Hooks.

1. **Welches Problem sie lösen**

- Reduzieren Boilerplate durch klassische Getter/Setter-Methoden.
- Halten Validierung/Transformation nah an der Property-Definition.
- Ermöglichen berechnete (virtuelle) Properties mit klarerer Syntax.

2. **Grundidee**

```php
class User
{
    public string $name {
        set => trim($value);
    }
}
```

Jede Zuweisung an `$user->name` läuft durch den `set`-Hook.

3. **Beispiel für berechnete Property**

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

`$fullName` wird aus anderen Feldern abgeleitet und braucht keine manuelle Getter-Methode.

4. **Beispiel für Validierung/Transformation**

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

5. **Wann man sie einsetzen sollte**

- Domain-Entities mit strikten Invarianten.
- DTO-/Value-ähnliche Objekte mit kontrollierten Schreibvorgängen.
- Fälle, in denen alte get/set-Methoden überwiegend Boilerplate waren.

Property Hooks machen Objektmodelle ausdrucksstärker und reduzieren repetitiven Accessor-Code, während starke Validierung und Kapselung erhalten bleiben.

</details>

<details>
<summary>9. Was ist der Pipe-Operator (PHP 8.5) und wann ist er nützlich?</summary>

#### PHP

Der Pipe-Operator in PHP 8.5 ist `|>`. Er übergibt das Ergebnis des linken Ausdrucks an das Callable auf der rechten Seite und ermöglicht so gut lesbare Transformationen von links nach rechts.

1. **Kernidee**

Statt tief verschachtelter Aufrufe kann man eine lineare Verarbeitungspipeline aufbauen.

```php
$result = " Hello World "
    |> trim(...)
    |> strtolower(...)
    |> (fn(string $s) => str_replace(' ', '-', $s));
```

2. **Warum er nützlich ist**

- Verbessert die Lesbarkeit mehrstufiger Transformationen.
- Reduziert temporäre Variablen.
- Vermeidet „inside-out“ verschachtelte Funktionsaufrufe.
- Erleichtert Refactoring von Transformationsketten.

3. **Vorher vs. nachher**

Ohne Pipe:

```php
$slug = strtolower(str_replace(' ', '-', trim($title)));
```

Mit Pipe:

```php
$slug = $title
    |> trim(...)
    |> (fn(string $s) => str_replace(' ', '-', $s))
    |> strtolower(...);
```

4. **Geeignete Einsatzfälle**

- String-/Datennormalisierungs-Pipelines.
- DTO-Mapping- und Transformations-Flows.
- Funktionale Datenverarbeitung in Services.

5. **Praktischer Hinweis**

Nutze den Pipe-Operator für klare sequenzielle Transformationen. Bei komplexer Verzweigungslogik sind normale Zwischenvariablen oft weiterhin leichter zu verstehen.

</details>

<details>
<summary>10. Was sind Superglobals in PHP und wie werden sie verwendet?</summary>

#### PHP

Superglobals in PHP sind eingebaute assoziative Arrays, die in allen Scopes (Funktionen, Methoden, globaler Scope) ohne `global` verfügbar sind.

1. **Wichtige Superglobals**

- `$_GET` - Query-String-Parameter aus der URL.
- `$_POST` - Formular-/Body-Parameter aus POST-Requests.
- `$_REQUEST` - zusammengeführte Request-Daten (abhängig von `request_order`/`variables_order`).
- `$_SERVER` - Server- und Request-Metadaten (Header, Methode, URI, Host usw.).
- `$_COOKIE` - vom Client gesendete Cookies.
- `$_SESSION` - Session-Daten, die zwischen Requests gespeichert werden.
- `$_FILES` - Metadaten hochgeladener Dateien.
- `$_ENV` - Umgebungsvariablen.
- `$GLOBALS` - Referenz auf alle globalen Variablen.

2. **Typische Verwendungsbeispiele**

```php
$page = $_GET['page'] ?? 'home';
$method = $_SERVER['REQUEST_METHOD'] ?? 'GET';
$token = $_COOKIE['csrf_token'] ?? null;
```

3. **Warum sie wichtig sind**

- Sie sind die primäre Schnittstelle zwischen PHP-Code und HTTP-/Runtime-Umgebung.
- Sie liefern Request-Input, Kontext und persistierten Benutzer-/Session-Status.

4. **Sicherheits- und Zuverlässigkeitsregeln**

- Vertraue Superglobal-Input niemals direkt.
- Externe Daten immer validieren und sanitizen.
- Strikte Prüfungen und Defaults verwenden (`??`, `filter_input`, Validatoren).
- In kritischem Code nicht auf `$_REQUEST` verlassen, da die Quellen-Priorität variieren kann.
- Output escapen, um XSS zu verhindern, und Prepared Statements gegen SQL-Injection verwenden.

Superglobals sind grundlegend für die PHP-Webentwicklung, sollten aber als nicht vertrauenswürdige Eingabegrenzen behandelt werden.

</details>

<details>
<summary>11. Was ist der Unterschied zwischen GET- und POST-Requests?</summary>

#### PHP

GET und POST sind HTTP-Methoden mit unterschiedlicher Semantik und unterschiedlichen Einsatzmustern.

1. **Zweck**

- **GET** wird zum Abrufen von Daten verwendet (read-only Operationen).
- **POST** wird zum Senden von Daten verwendet, die den Serverzustand ändern können (Create-/Process-Aktionen).

2. **Wo die Daten gesendet werden**

- **GET** sendet Parameter im URL-Query-String (`/users?page=2`).
- **POST** sendet Daten im Request-Body.

3. **Sichtbarkeit und Logging**

- **GET**-Parameter sind in URL, Browserverlauf, Logs und Referrern sichtbar.
- **POST**-Body erscheint nicht in der URL, muss aber trotzdem als nicht vertrauenswürdiger Input behandelt werden.

4. **Caching und Bookmarks**

- **GET**-Requests sind cache-freundlich und bookmarkbar.
- **POST**-Requests sind standardmäßig meist nicht cachebar und mit Payload nicht bookmarkbar.

5. **Idempotenz und Sicherheit (HTTP-Semantik)**

- **GET** sollte safe sein und keinen Serverzustand verändern.
- **POST** ist nicht garantiert idempotent und hat meist Side Effects.

6. **Zugriff in PHP**

```php
$search = $_GET['q'] ?? null;      // aus Query-String
$email  = $_POST['email'] ?? null; // aus Request-Body
```

7. **Wann man was nutzt**

- Nutze **GET** für Filterung, Suche, Pagination und Resource-Reads.
- Nutze **POST** für Formular-Submissions, Authentifizierungsaktionen und das Erstellen/Aktualisieren serverseitiger Daten (oder in APIs ggf. PUT/PATCH).

Die Kernregel: GET für Leseoperationen, POST für zustandsändernde Operationen - bei beiden Input immer validieren.

</details>

<details>
<summary>12. Wie verarbeitet PHP HTTP-Requests und Responses?</summary>

#### PHP

In einem typischen Web-Setup verarbeitet PHP HTTP über einen Request-Response-Lifecycle, der von einem Webserver (Nginx/Apache) und einer PHP-Runtime (meist PHP-FPM) koordiniert wird.

1. **Request kommt an**

- Der Client sendet einen HTTP-Request (Methode, URI, Header, Body).
- Der Webserver empfängt ihn und leitet dynamische Requests an PHP weiter.

2. **PHP-Runtime führt das Skript aus**

- PHP initialisiert den Request-Kontext und befüllt Superglobals (`$_SERVER`, `$_GET`, `$_POST`, `$_COOKIE`, `$_FILES`).
- Der Application-Bootstrap läuft (Autoload, Konfiguration, DI-Container, Framework-Kernel).

3. **Die Anwendung führt Business-Logik aus**

- Der Router löst Controller/Handler auf.
- Middleware/Guards/Validierung werden ausgeführt.
- Services/Repositories greifen auf Datenbank, Cache oder externe APIs zu.

4. **Response wird aufgebaut**

- Die App setzt Status-Code, Header und Body (HTML/JSON/Datei/Stream).
- In Plain PHP geschieht das typischerweise über `header()`, `http_response_code()` und Output.
- In Frameworks wird ein Response-Objekt zurückgegeben und anschließend emittiert.

```php
http_response_code(200);
header('Content-Type: application/json; charset=utf-8');
echo json_encode(['ok' => true], JSON_THROW_ON_ERROR);
```

5. **Response wird gesendet**

- PHP sendet den Output an den Webserver.
- Der Webserver sendet die finale HTTP-Response an den Client.
- Bei klassischem PHP-FPM endet der Request-Status nach der Response (persistenter Zustand liegt in externem Storage).

6. **Fehlerbehandlung**

- Exceptions werden durch Framework-/globale Handler in HTTP-Fehlerresponses umgewandelt (z. B. `404`, `422`, `500`).
- Logs/Monitoring erfassen Fehler zur Diagnose.

Das PHP-Modell ist geradlinig: Request-Kontext empfangen, Anwendungscode ausführen, HTTP-Response erzeugen und den Request sauber abschließen.

</details>

<details>
<summary>13. Wie funktionieren Sessions und welche sicheren Session-Praktiken gibt es?</summary>

#### PHP

PHP-Sessions erlauben es, benutzerspezifischen Zustand zwischen zustandslosen HTTP-Requests zu speichern, indem Daten serverseitig gehalten und über eine Session-ID verknüpft werden.

1. **Wie Sessions funktionieren**

- Der Client macht den ersten Request.
- Der Server erstellt eine Session-ID (SID).
- Die SID wird an den Client gesendet, meist per Cookie (typisch `PHPSESSID`).
- Bei folgenden Requests sendet der Client die SID zurück.
- PHP lädt die zugehörigen serverseitigen Session-Daten in `$_SESSION`.

2. **Grundlegende Verwendung**

```php
session_start();

$_SESSION['user_id'] = 42;
$userId = $_SESSION['user_id'] ?? null;
```

3. **Wo Daten gespeichert werden**

- Standardmäßig: Dateisystem-Session-Storage.
- In Produktion: häufig Redis/Datenbank/Memcached über Custom Handler für bessere Skalierung.

4. **Sichere Session-Praktiken**

- Session-ID nach Login/Rechteänderung regenerieren:
  `session_regenerate_id(true);`
- Cookie-Flags setzen:
  `HttpOnly`, `Secure`, `SameSite` (`Lax` oder `Strict`, wenn möglich).
- HTTPS für authentifizierte Anwendungen erzwingen.
- Session-Timeout und Inaktivitätsablauf setzen.
- Session beim Logout invalidieren (Daten löschen + Session zerstören + Cookie ablaufen lassen).
- Sessions vorsichtig an Kontext-Signale binden (z. B. partieller IP/UA-Check), um Hijacking-Risiko zu reduzieren.
- Möglichst wenige sensible Daten in Sessions speichern; IDs/Referenzen statt Geheimnisse.

5. **Häufige Bedrohungen**

- **Session Fixation:** Angreifer erzwingt bekannte SID vor Authentifizierung.
- **Session Hijacking:** Gestohlene SID wird vom Angreifer wiederverwendet.
- **XSS-gestützter Diebstahl:** Bösartige Skripte nutzen unsicheres Session-Handling aus.

6. **Hardening-Checkliste**

- `session.use_strict_mode=1`
- `session.cookie_httponly=1`
- `session.cookie_secure=1` (unter HTTPS)
- Korrektes `session.cookie_samesite`
- Regelmäßige SID-Regeneration bei authentifizierten Flows

Sessions sind sicher und effektiv, wenn IDs geschützt, sinnvoll rotiert und nur über vertrauenswürdige Kanäle transportiert werden.

</details>

<details>
<summary>14. Wie werden Cookies in modernen Anwendungen gesetzt und abgesichert?</summary>

#### PHP

Cookies sind kleine Key-Value-Daten, die vom Browser gespeichert und bei passenden Requests mitgesendet werden. In modernen Apps werden sie für Sessions, Präferenzen und sichere Auth-Flows verwendet.

1. **Wie Cookies in PHP gesetzt werden**

Verwende `setcookie()` (oder Framework-Response-Helper), bevor Output gesendet wird:

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

2. **Wie Cookies gelesen werden**

```php
$token = $_COOKIE['session_token'] ?? null;
```

3. **Sicherheitsattribute (kritisch)**

- **`Secure`**: Cookie wird nur über HTTPS gesendet.
- **`HttpOnly`**: kein Zugriff aus JavaScript (`document.cookie`), reduziert XSS-Diebstahlrisiko.
- **`SameSite`**:
  `Strict` (starker CSRF-Schutz), `Lax` (ausgewogen), `None` (erfordert `Secure`, für Cross-Site-Use-Cases).
- **`Expires/Max-Age`**: Lebensdauer begrenzen.
- **`Path/Domain`**: Cookie möglichst eng scoped setzen.

4. **Best Practices**

- HTTPS überall nutzen und für sensible Cookies immer `Secure` setzen.
- `HttpOnly` für Session-/Auth-Cookies setzen.
- `SameSite=Lax` oder `Strict` bevorzugen, außer Cross-Site-Verhalten ist explizit erforderlich.
- Auth-/Session-Tokens regelmäßig rotieren und passend ablaufen lassen.
- Keine sensiblen Klartextdaten in Cookies speichern.
- Bei clientseitig gespeichertem Zustand Cookie-Payload signieren oder verschlüsseln.

5. **Häufige Fehler**

- Fehlendes `HttpOnly` oder `Secure`.
- Zu breit gefasstes `domain`/`path`.
- Sehr lange Laufzeiten für Auth-Cookies.
- Cookie-Werten ohne serverseitige Verifikation zu vertrauen.

Moderne Cookie-Sicherheit basiert auf engem Scope, sicherem Transport, sicheren Defaults und serverseitiger Validierung aller vom Client gelieferten Werte.

</details>

<details>
<summary>15. Was ist CSRF und wie verhindert man es?</summary>

#### PHP

CSRF (Cross-Site Request Forgery) ist ein Angriff, bei dem der Browser eines Opfers dazu gebracht wird, ohne Absicht des Nutzers einen authentifizierten Request an deine Anwendung zu senden.

1. **Wie CSRF funktioniert**

- Der Nutzer ist bei `your-app.com` eingeloggt.
- Ein Angreifer lockt den Nutzer auf eine bösartige Seite.
- Diese Seite löst einen Request an `your-app.com` aus (z. B. E-Mail ändern, Geld überweisen).
- Der Browser sendet Cookies/Session automatisch mit, daher kann der Request akzeptiert werden.

2. **Warum das gefährlich ist**

- Der Server sieht eine gültige authentifizierte Session.
- Zustandsändernde Aktionen können im Namen des Opfers ausgeführt werden.

3. **Primäre Abwehr: CSRF-Token**

- Ein zufälliges Token pro Session/Request erzeugen.
- Token in Formulare oder Request-Header einbetten.
- Token serverseitig verifizieren, bevor zustandsändernde Aktionen verarbeitet werden.

```php
session_start();

// Token einmalig erzeugen
$_SESSION['csrf_token'] ??= bin2hex(random_bytes(32));

// Bei POST validieren
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $token = $_POST['_csrf'] ?? '';
    if (!hash_equals($_SESSION['csrf_token'], $token)) {
        http_response_code(419);
        exit('Invalid CSRF token');
    }
}
```

4. **Zusätzliche Schutzmaßnahmen**

- `SameSite`-Cookies (`Lax`/`Strict`) nutzen, um Cross-Site-Cookie-Sendungen zu reduzieren.
- `Origin`-/`Referer`-Header für sensible Endpunkte validieren (Defense-in-Depth).
- Re-Auth oder Step-up-Bestätigung für kritische Operationen verlangen.
- GET nicht für zustandsändernde Aktionen verwenden.

5. **Best Practice in Frameworks**

- Wenn möglich, eingebaute CSRF-Middleware (Laravel/Symfony/etc.) statt eigener Logik nutzen.
- Sicherstellen, dass Tokens in allen mutierenden Requests enthalten sind (POST/PUT/PATCH/DELETE), inklusive AJAX-Calls.

CSRF-Schutz ist für cookiebasierte Authentifizierungs-Flows verpflichtend und sollte Teil der Standard-Sicherheitsmiddleware sein.

</details>

<details>
<summary>16. Was ist XSS und wie verhindert man es korrekt?</summary>

#### PHP

XSS (Cross-Site Scripting) ist eine Schwachstelle, bei der vom Angreifer kontrollierte Daten im Browser als ausführbares Skript auf den Seiten deiner Anwendung interpretiert werden.

1. **Haupttypen von XSS**

- **Stored XSS**: bösartige Payload wird gespeichert (DB/Kommentar/Profil) und später an Nutzer ausgeliefert.
- **Reflected XSS**: Payload kommt aus Request-Input und wird sofort in der Response reflektiert.
- **DOM-based XSS**: clientseitiges JavaScript schreibt unsichere Daten in das DOM.

2. **Root Cause**

- Nicht vertrauenswürdiger Input gelangt ohne korrektes Output-Encoding in HTML/JS/URL/CSS-Kontexte.

3. **Primäre Abwehr: kontextbezogenes Output-Escaping**

- Daten **beim Output** escapen, abhängig vom Rendering-Kontext.
- Für HTML-Textkontext in PHP:

```php
echo htmlspecialchars($userInput, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
```

4. **Kontextspezifische Regeln**

- HTML-Body: `htmlspecialchars(...)`.
- HTML-Attribute: auch Quotes escapen (`ENT_QUOTES`).
- JavaScript-Kontext: Daten JSON-encoden, direkte String-Konkatenation vermeiden.
- URL-Kontext: `rawurlencode()` für Parameterwerte.
- Keine nicht vertrauenswürdigen HTML-Inhalte direkt injizieren.

5. **Zusätzliche Schutzmaßnahmen**

- Auto-Escaping von Templating-Engines/Frameworks nutzen.
- Rich-HTML mit allowlist-basierten Sanitizern bereinigen (falls HTML-Input erforderlich ist).
- Strenge Content Security Policy (CSP) als Defense-in-Depth setzen.
- Inline-Skripte möglichst vermeiden.
- Input validieren, aber Validierung nicht als Ersatz für Output-Encoding behandeln.

6. **Häufige Fehler**

- Input einmal escapen und in mehreren Kontexten wiederverwenden.
- Template-Auto-Escaping global deaktivieren.
- Rohe User-Inhalte in Admin-Panels/internen Tools rendern.

XSS-Prävention ist vor allem striktes kontextbezogenes Encoding am Output-Punkt plus CSP und sichere Rendering-Patterns.

</details>

<details>
<summary>17. Was ist SQL Injection und wie verhindern Prepared Statements sie?</summary>

#### PHP

SQL Injection ist eine Schwachstelle, bei der Angreifer-Input die Struktur von SQL-Queries verändert und dadurch unbefugten Datenzugriff oder Manipulation ermöglicht.

1. **Wie SQL Injection entsteht**

Sie entsteht, wenn nicht vertrauenswürdiger Input direkt in SQL-Strings konkateniert wird.

```php
// Unsicheres Beispiel
$sql = "SELECT * FROM users WHERE email = '" . $_POST['email'] . "'";
```

Ein Angreifer kann SQL-Fragmente injizieren und die Query-Logik verändern.

2. **Auswirkungen**

- Umgehung der Authentifizierung
- Datenabfluss/-änderung/-löschung
- Privilegieneskalation
- In schweren Fällen vollständige Kompromittierung der Datenbank

3. **Wie Prepared Statements schützen**

Prepared Statements trennen:
- **SQL-Struktur** (Query-Template)
- **Datenwerte** (gebundene Parameter)

Die Datenbank behandelt gebundene Werte als Daten, nicht als ausführbaren SQL-Code.

```php
$pdo = new PDO($dsn, $user, $pass, [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
]);

$stmt = $pdo->prepare('SELECT * FROM users WHERE email = :email');
$stmt->execute(['email' => $_POST['email']]);
$user = $stmt->fetch(PDO::FETCH_ASSOC);
```

4. **Wichtige Nuance**

- Prepared Statements schützen Werte, aber keine dynamischen SQL-Identifier (Tabellen-/Spaltennamen).
- Wenn Identifier dynamisch sein müssen, strikte Allowlists verwenden.

5. **Best Practices**

- Für externen Input überall PDO/MySQLi-Prepared-Statements einsetzen.
- SQL für user-provided Werte niemals per String-Konkatenation bauen.
- Least-Privilege-Datenbankkonten erzwingen.
- Input validieren und verdächtige Aktivität loggen.
- DB-Engine/Treiber aktuell halten.

Prepared Statements sind die primäre und verpflichtende Abwehr gegen SQL Injection in modernen PHP-Anwendungen.

</details>

<details>
<summary>18. Was ist Content Security Policy (CSP)?</summary>

#### PHP

Content Security Policy (CSP) ist ein Browser-Sicherheitsmechanismus, der einschränkt, welche Ressourcen (Skripte, Styles, Bilder, Frames usw.) auf einer Seite geladen und ausgeführt werden dürfen.

1. **Wogegen CSP schützt**

- Reduziert vor allem XSS-Auswirkungen, indem nicht autorisierte Inline-/externe Skripte blockiert werden.
- Hilft, Datenexfiltration über bösartige Resource-Loads zu mindern.
- Beschränkt riskante Browser-Fähigkeiten auf vertrauenswürdige Origins.

2. **Wie CSP ausgeliefert wird**

- Üblicherweise per HTTP-Response-Header:
  `Content-Security-Policy: ...`
- Kann zunächst auch im Report-Only-Modus gesendet werden:
  `Content-Security-Policy-Report-Only: ...`

3. **Basisbeispiel**

```php
header("Content-Security-Policy: default-src 'self'; script-src 'self'; object-src 'none'; base-uri 'self'; frame-ancestors 'none'");
```

4. **Wichtige Direktiven**

- `default-src` - Fallback-Source-Policy.
- `script-src` - steuert JavaScript-Quellen.
- `style-src` - steuert CSS-Quellen.
- `img-src` - steuert Bildquellen.
- `connect-src` - steuert XHR/fetch/WebSocket-Ziele.
- `frame-ancestors` - verhindert Clickjacking durch Steuerung der Einbettung.
- `object-src 'none'` - deaktiviert Legacy-Plugin-Content.
- `base-uri` - beschränkt `<base>`-Tag-Injection.

5. **Best Practices**

- Mit `Report-Only` starten, Verstöße sammeln, dann Enforcement aktivieren.
- Für Inline-Skripte Nonces/Hashes statt `'unsafe-inline'` bevorzugen.
- Policy pro Umgebung strikt und explizit halten.
- CSP mit Output-Escaping, CSRF-Schutz und sicheren Cookies kombinieren.

6. **CSP ist kein Allheilmittel**

- Es ist Defense-in-Depth, kein Ersatz für sicheres Coding.
- Nicht vertrauenswürdiger Output muss weiterhin escaped/sanitized werden, und unsichere DOM-Patterns müssen vermieden werden.

CSP stärkt die Frontend-Sicherheitslage deutlich, wenn es sorgfältig konfiguriert und kontinuierlich überwacht wird.

</details>

<details>
<summary>19. Was ist Autoloading und wie funktioniert PSR-4?</summary>

#### PHP

Autoloading ist ein Mechanismus, der PHP-Klassen/Interfaces/Traits automatisch lädt, sobald sie das erste Mal verwendet werden, statt viele `require`/`include`-Anweisungen manuell zu schreiben.

1. **Warum Autoloading nötig ist**

- Entfernt manuelle File-Includes.
- Hält die Projektstruktur skalierbar.
- Erleichtert das Verwalten von Abhängigkeiten und Modulen.

2. **PSR-4 in Kürze**

PSR-4 ist der moderne Standard, um Namespaces auf Dateisystempfade abzubilden.

- Namespace-Präfix wird auf ein Basisverzeichnis gemappt.
- Verbleibende Namespace-Teile werden auf Unterverzeichnisse gemappt.
- Der Klassenname wird auf den Dateinamen gemappt (`ClassName.php`).

3. **Beispiel-Mapping**

Wenn die Composer-Konfiguration enthält:

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

Dann:
- `App\Services\UserService` -> `src/Services/UserService.php`
- `App\Http\Controllers\HomeController` -> `src/Http/Controllers/HomeController.php`

4. **Wie Composer das aktiviert**

- `autoload.psr-4` in `composer.json` definieren.
- Ausführen:

```bash
composer dump-autoload
```

- Composer-Autoloader einmal einbinden (meist im App-Bootstrap):

```php
require __DIR__ . '/vendor/autoload.php';
```

5. **Best Practices**

- Eine Klasse pro Datei.
- Namespace- und Verzeichnisnamen konsistent halten.
- Aussagekräftigen Root-Namespace verwenden (`App\\`, `Domain\\`, `Company\\Project\\`).
- Autoload-Dateien nach Namespace-/Pfadänderungen neu generieren.

Autoloading mit PSR-4 ist das Standard-Fundament moderner PHP-Anwendungsstruktur und Dependency-Ladung.

</details>

<details>
<summary>20. Was ist Composer und wie funktioniert Dependency Management?</summary>

#### PHP

Composer ist der Standard-Dependency-Manager für PHP. Er installiert, aktualisiert und autoloadet Projektbibliotheken auf reproduzierbare Weise.

1. **Kern-Dateien**

- `composer.json` - definiert Projektmetadaten, benötigte Pakete, Autoload-Regeln und Skripte.
- `composer.lock` - fixiert die exakten für das Projekt aufgelösten Paketversionen.
- `vendor/` - installierte Abhängigkeiten und Composer-Autoloader.

2. **Wie Dependency Management funktioniert**

- Du deklarierst Constraints in `composer.json` (z. B. `^11.0`).
- Composer löst einen kompatiblen Dependency-Graphen auf.
- Aufgelöste exakte Versionen werden in `composer.lock` geschrieben.
- Team/CI installiert exakt diese gelockten Versionen für deterministische Builds.

3. **Basis-Workflow**

```bash
# Dependency hinzufügen
composer require monolog/monolog

# Aus Lock-Datei installieren
composer install

# Dependencies aktualisieren (Constraints neu auflösen)
composer update
```

4. **Versions-Constraints**

- `^1.2` - erlaubt nicht-brechende Updates bis `<2.0.0`.
- `~1.2.3` - erlaubt Patch/Minor innerhalb dieses Zweigs.
- Exakte Versionen sind möglich, für Libraries aber meist zu starr.

5. **Autoload-Integration**

Composer generiert `vendor/autoload.php` und unterstützt PSR-4-Autoload-Mapping aus `composer.json`.

```php
require __DIR__ . '/vendor/autoload.php';
```

6. **Best Practices**

- `composer.lock` für Anwendungen committen.
- In CI/Produktion `composer install` verwenden.
- `composer update` bewusst ausführen und Lock-File-Änderungen prüfen.
- Stabile Paketversionen bevorzugen.
- Abhängigkeiten regelmäßig prüfen (`composer audit`).

Composer ist in modernem PHP essenziell, weil es Paketmanagement, Autoloading und reproduzierbare Builds über Umgebungen hinweg standardisiert.

</details>

<details>
<summary>21. Was sind PSR-Standards und warum sind sie wichtig?</summary>

#### PHP

PSR (PHP Standards Recommendations) sind Community-Standards, veröffentlicht von der PHP-FIG (PHP Framework Interop Group), um Interoperabilität und Konsistenz zwischen PHP-Libraries und Frameworks zu verbessern.

1. **Was PSRs definieren**

- Coding-Style-Konventionen (z. B. PSR-12).
- Autoloading-Konventionen (PSR-4).
- Gemeinsame Interfaces für HTTP-Messages, Middleware, Container, Logging, Caching usw.

2. **Warum sie wichtig sind**

- **Interoperabilität:** Libraries verschiedener Anbieter arbeiten leichter zusammen.
- **Vorhersehbarkeit:** vertraute Interfaces und Struktur über Projekte hinweg.
- **Wartbarkeit:** Team-Codebasen sind konsistenter und leichter reviewbar.
- **Framework-Portabilität:** weniger Vendor-Lock-in, wenn Architektur auf Standard-Contracts basiert.

3. **Häufig verwendete PSRs**

- **PSR-1 / PSR-12** - grundlegender und erweiterter Coding Style.
- **PSR-3** - Logger-Interface (`LoggerInterface`).
- **PSR-4** - Autoloading-Standard.
- **PSR-6 / PSR-16** - Cache-Interfaces.
- **PSR-7** - HTTP-Message-Interfaces (Request/Response/Stream).
- **PSR-11** - Container-Interface.
- **PSR-15** - HTTP-Server-Request-Handler und Middleware.
- **PSR-18** - HTTP-Client-Interface.

4. **Praktischer Effekt in realen Projekten**

- Implementierungen (z. B. Logger/Client/Container) lassen sich austauschen, ohne Business-Logik umzuschreiben.
- Frameworks und Pakete integrieren sich schneller über gemeinsame Interfaces.
- Tooling (Linter/static analyzers/framework adapters) lässt sich leichter einführen.

PSRs sind nicht nur Style-Guides; sie sind Architektur-Contracts, die moderne PHP-Ökosysteme komponierbar und nachhaltig machen.

</details>

<details>
<summary>22. Was ist PSR-7 (HTTP-Messages)?</summary>

#### PHP

PSR-7 ist ein Standard, der Interfaces für HTTP-Messages in PHP definiert: Requests, Responses, Streams und Upload-Dateien.

1. **Was PSR-7 standardisiert**

- `ServerRequestInterface` - eingehender HTTP-Request aus Client/Server-Kontext.
- `RequestInterface` - generischer ausgehender Request.
- `ResponseInterface` - HTTP-Response (Status, Header, Body).
- `StreamInterface` - Abstraktion des Message-Bodys.
- `UploadedFileInterface` - Abstraktion für hochgeladene Dateien.
- `UriInterface` - URI-Repräsentation.

2. **Warum es wichtig ist**

- Liefert einen gemeinsamen Contract über Frameworks und Libraries hinweg.
- Ermöglicht Middleware-Pipelines und wiederverwendbare HTTP-Komponenten.
- Reduziert Vendor-Lock-in, weil auf Interfaces statt auf konkrete Framework-Klassen programmiert wird.

3. **Immutability-Prinzip**

PSR-7-Messages sind immutable. Methoden wie `withHeader()` geben eine neue Instanz zurück, statt das Original zu verändern.

```php
$newResponse = $response
    ->withStatus(201)
    ->withHeader('Content-Type', 'application/json');
```

4. **Typische Nutzung**

- In Middleware und Handlern (oft mit PSR-15).
- In API-Frameworks für Request-Parsing und Response-Erzeugung.
- In HTTP-Clients/-Servern, die standardisierte Message-Objekte austauschen.

5. **Praktischer Vorteil**

Eine für PSR-7 geschriebene Komponente kann meist in verschiedenen Ökosystemen (Slim, Laminas, Symfony-Bridges, Mezzio usw.) mit minimaler Anpassung wiederverwendet werden.

PSR-7 ist die zentrale Interoperabilitäts-Schicht für HTTP-Message-Handling in modernen PHP-Anwendungen.

</details>

<details>
<summary>23. Was ist PSR-11 (Dependency Container)?</summary>

#### PHP

PSR-11 ist das Standard-Interface für Dependency-Injection-Container in PHP. Es definiert, wie Anwendungscode services aus einem Container framework-agnostisch beziehen kann.

1. **Kern-Interfaces von PSR-11**

- `Psr\Container\ContainerInterface`
- `Psr\Container\ContainerExceptionInterface`
- `Psr\Container\NotFoundExceptionInterface`

Hauptmethoden:
- `get(string $id): mixed`
- `has(string $id): bool`

2. **Was es löst**

- Standardisiert den Containerzugriff über Libraries/Frameworks hinweg.
- Erlaubt Komponenten, von einem gemeinsamen Contract statt von konkreten Container-Implementierungen abzuhängen.
- Verbessert Interoperabilität und Portabilität.

3. **Einfaches Nutzungsbeispiel**

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

4. **Wichtiger Design-Hinweis**

PSR-11 definiert **wie services gelesen werden**, nicht wie sie registriert/gebaut werden. Registrierungs-APIs sind containerspezifisch.

5. **Best Practices**

- In Anwendungscode Constructor Injection bevorzugen.
- Direkten Container-Lookup vor allem in Infrastruktur-/Bootstrap-Layern nutzen.
- Service-Locator-Anti-Pattern in Domain-/Business-Logik vermeiden.
- Wo möglich Interfaces statt konkreter Implementierungen type-hinten.

PSR-11 ist ein minimalistischer, aber wichtiger Standard, der die Nutzung von Dependency-Containern im PHP-Ökosystem konsistent macht.

</details>

<details>
<summary>24. Was ist PSR-15 (Middleware)?</summary>

#### PHP

PSR-15 ist der Standard, der serverseitige HTTP-Middleware und Request-Handler in PHP definiert. Er arbeitet zusammen mit den PSR-7-Request/Response-Interfaces.

1. **Kern-Interfaces von PSR-15**

- `Psr\Http\Server\MiddlewareInterface`
- `Psr\Http\Server\RequestHandlerInterface`

Methodenverträge:
- Middleware: `process(ServerRequestInterface $request, RequestHandlerInterface $handler): ResponseInterface`
- Handler: `handle(ServerRequestInterface $request): ResponseInterface`

2. **Wie die Middleware-Pipeline funktioniert**

- Der Request tritt in die Middleware-Kette ein.
- Jede Middleware kann:
  Request validieren/modifizieren, mit Response short-circuiten oder den Request weiterreichen.
- Der finale Handler erzeugt die Response.
- Auf dem Rückweg durch den Middleware-Stack kann die Response weiter modifiziert werden.

3. **Typische Middleware-Aufgaben**

- Authentifizierung/Autorisierung
- CORS
- Logging/Tracing
- Rate Limiting
- Request-Validierung
- Exception-zu-Response-Konvertierung

4. **Einfaches Middleware-Beispiel**

```php
use Psr\Http\Message\ResponseInterface;
use Psr\Http\Message\ServerRequestInterface;
use Psr\Http\Server\MiddlewareInterface;
use Psr\Http\Server\RequestHandlerInterface;

final class AuthMiddleware implements MiddlewareInterface
{
    public function process(ServerRequestInterface $request, RequestHandlerInterface $handler): ResponseInterface
    {
        // Auth prüfen, dann fortfahren
        return $handler->handle($request);
    }
}
```

5. **Warum PSR-15 wichtig ist**

- Macht Middleware über Frameworks/Ökosysteme hinweg wiederverwendbar.
- Standardisiert Erweiterungspunkte im Request-Lifecycle.
- Fördert saubere Trennung von Querschnittsaspekten.

PSR-15 liefert den Interoperabilitäts-Contract für middlewarebasierte HTTP-Pipelines in modernen PHP-Anwendungen.

</details>

<details>
<summary>25. Was ist PSR-18 (HTTP-Client)?</summary>

#### PHP

PSR-18 ist das Standard-Interface für HTTP-Clients in PHP. Es definiert, wie Anwendungscode ausgehende HTTP-Requests implementationsagnostisch sendet.

1. **Kern-Contract von PSR-18**

- Haupt-Interface: `Psr\Http\Client\ClientInterface`
- Hauptmethode: `sendRequest(RequestInterface $request): ResponseInterface`
- Arbeitet mit PSR-7-Request/Response-Objekten.

2. **Welches Problem es löst**

- Entkoppelt Business-Logik von konkreten HTTP-Client-Libraries.
- Macht Integrationen portabler und leichter testbar.
- Ermöglicht den Austausch von Client-Implementierungen, ohne Service-Code umzuschreiben.

3. **Grundlegende Verwendung**

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

4. **Exceptions**

PSR-18 definiert Standard-Exception-Interfaces für Client-Fehler (Request-Fehler, Netzwerk-/Transportfehler), wodurch konsistentes Error-Handling über Implementierungen hinweg möglich wird.

5. **Best Practices**

- `ClientInterface` in Services type-hinten.
- Requests über PSR-17-Factories bauen.
- Timeouts/Retries/Circuit-Breaker in der Infrastruktur-Schicht konfigurieren.
- In Tests das Client-Interface mocken für deterministisches Verhalten.

PSR-18 standardisiert ausgehende HTTP-Kommunikation und ist ein zentraler Baustein für interoperablen, wartbaren Integrationscode in modernen PHP-Apps.

</details>

<details>
<summary>26. Was sind Dependency Injection und Inversion of Control?</summary>

#### PHP

Dependency Injection (DI) und Inversion of Control (IoC) sind Architekturprinzipien zum Bau locker gekoppelten, testbaren Codes.

1. **Inversion of Control (IoC)**

IoC bedeutet, dass eine Klasse ihre Abhängigkeiten nicht selbst erstellt und steuert; diese Kontrolle wird nach außen verlagert (in Framework-/Container-/Bootstrap-Layer).

2. **Dependency Injection (DI)**

DI ist eine konkrete Umsetzung von IoC: Abhängigkeiten werden von außen bereitgestellt (injiziert), statt innerhalb der Klasse mit `new` erstellt zu werden.

3. **Warum das wichtig ist**

- Reduziert Kopplung zwischen Komponenten.
- Verbessert Testbarkeit (einfaches Mocking/Stubbing).
- Macht Code leichter erweiterbar und refaktorierbar.
- Unterstützt klare Architekturgrenzen.

4. **Ohne DI (eng gekoppelt)**

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

5. **Mit DI (locker gekoppelt)**

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

6. **Gängige DI-Stile**

- Constructor Injection (bevorzugt).
- Method Injection.
- Setter/Property Injection (weniger geeignet für erforderliche Abhängigkeiten).

7. **Beziehung zu Containern**

Ein DI-Container automatisiert Objekterstellung und Wiring, aber DI ist ein Designprinzip, das unabhängig von einem konkreten Container ist.

DI + IoC sind grundlegend für moderne PHP-Frameworks und entscheidend für wartbare, skalierbare Codebasen.

</details>

<details>
<summary>27. Was sind Service Container und wie funktionieren sie?</summary>

#### PHP

Ein Service Container (DI-Container) ist eine Komponente, die Objekterstellung, Dependency-Wiring und Lifecycle in einer Anwendung verwaltet.

1. **Was ein Container macht**

- Speichert Service-Definitionen/Bindings.
- Löst Abhängigkeiten automatisch auf (oft per Reflection und Type Hints).
- Baut Objektgraphen (Service + alle verschachtelten Abhängigkeiten).
- Verwaltet Lebensdauern (Singleton/scoped/transient je nach Framework).

2. **Warum er nützlich ist**

- Zentralisiert Dependency-Konfiguration.
- Entfernt repetitives manuelles `new ...`-Wiring.
- Vereinfacht den Austausch von Implementierungen (Interface -> konkrete Klasse).
- Verbessert Wartbarkeit in größeren Anwendungen.

3. **Typischer Ablauf**

- Du registrierst Bindings:
  `LoggerInterface` -> `MonologLogger`
- Du fragst den Container nach einem Service:
  `OrderService`
- Der Container baut `OrderService` und löst erforderliche Konstruktorargumente rekursiv auf.

4. **Konzeptionelles Beispiel**

```php
$container->set(LoggerInterface::class, MonologLogger::class);
$container->set(OrderService::class, fn($c) => new OrderService($c->get(LoggerInterface::class)));

$service = $container->get(OrderService::class);
```

5. **Service-Lifetime-Konzepte**

- **Singleton/shared:** eine Instanz wird wiederverwendet.
- **Transient/factory:** bei jeder Auflösung neue Instanz.
- **Scoped/request:** eine Instanz pro Request-Scope (frameworkabhängig).

6. **Best Practices**

- Möglichst Abstraktionen (Interfaces), nicht konkrete Klassen registrieren.
- Business-/Domain-Code container-agnostisch halten.
- Constructor Injection als Standard nutzen.
- Container nicht tief in Domain-Logik direkt aufrufen (Service-Locator-Anti-Pattern).

Service Container sind Infrastrukturwerkzeuge, die Dependency-Management automatisieren und moderne PHP-Anwendungen modular und komponierbar halten.

</details>

<details>
<summary>28. Was sind Middleware und der Request-Lifecycle in Frameworks?</summary>

#### PHP

In modernen PHP-Frameworks sind Middleware Schichten, die HTTP-Requests und Responses rund um deine zentrale Route-/Controller-Logik verarbeiten. Der Request-Lifecycle ist der gesamte Weg vom eingehenden Request bis zur finalen Response.

1. **Was Middleware ist**

- Eine Pipeline-Komponente, die:
  Request inspizieren/modifizieren, Verarbeitung mit eigener Response stoppen oder Kontrolle an die nächste Schicht weitergeben kann.
- In modernen Ökosystemen oft über PSR-15-ähnliche Contracts umgesetzt.

2. **Typische Middleware-Aufgaben**

- Authentifizierung und Autorisierung
- CORS
- Rate Limiting
- Input-Normalisierung/Validierung
- Logging, Tracing, Metriken
- Exception-Handling und Response-Shaping

3. **Typischer Request-Lifecycle**

1. HTTP-Request erreicht Webserver (Nginx/Apache) und PHP-Runtime.
2. Framework-Bootstrap lädt Konfiguration, Services und Routen.
3. Globale Middleware-Pipeline startet.
4. Route wird gematcht und route-spezifische Middleware läuft.
5. Controller/Handler führt Business-Logik aus.
6. Response läuft durch den Middleware-Stack zurück (Post-Processing).
7. Finale Response wird an den Client gesendet.

4. **Warum dieses Modell nützlich ist**

- Trennt Querschnittsaspekte von Controllern.
- Hält Route-Handler fokussiert auf Business-Logik.
- Macht Verhalten komponierbar und wiederverwendbar.
- Bietet konsistente Erweiterungspunkte für Plattform-Policies.

5. **Praktische Hinweise**

- Middleware auf eine Verantwortung fokussieren.
- Middleware-Reihenfolge bewusst festlegen (z. B. Error-Handling ganz außen).
- Schwere Business-Logik in Middleware vermeiden.
- Nach Möglichkeit stateless Middleware bevorzugen.

Middleware + Request-Lifecycle sind Kernkonzepte hinter sauberer, vorhersehbarer HTTP-Verarbeitung in PHP-Frameworks.

</details>

<details>
<summary>29. Was ist MVC und wie wird es in PHP-Frameworks umgesetzt?</summary>

#### PHP

MVC (Model-View-Controller) ist ein Architekturpattern, das Anwendungsaspekte in Daten-/Business-Layer, UI-Rendering und Request-Orchestrierung trennt.

1. **MVC-Komponenten**

- **Model** - Domain-/Datenlogik, Regeln und Persistenzinteraktion.
- **View** - Präsentationsschicht (Templates/HTML/JSON-Formatierung).
- **Controller** - empfängt Request, koordiniert Use Cases, gibt Response zurück.

2. **Wie es in PHP-Frameworks funktioniert**

Typischer Ablauf:
1. Router matched URL auf eine Controller-Action.
2. Controller validiert Input und ruft Domain-/Service-/Model-Layer auf.
3. Model/Service liest oder mutiert Daten.
4. Controller übergibt Ergebnis an View/Template oder gibt API-Response zurück.
5. Framework emittiert die finale HTTP-Response.

3. **Beispiel-Verantwortlichkeiten**

- Controller: `UserController@show($id)`
- Model/Service: User laden, Business-Regeln anwenden
- View: `user/show.blade.php` rendern (oder JSON-Resource)

4. **Warum MVC nützlich ist**

- Klare Trennung von Verantwortlichkeiten.
- Einfachere Wartung und Tests.
- Bessere Team-Zusammenarbeit (Frontend-/Backend-Anliegen getrennt).
- Vorhersehbare Projektstruktur.

5. **Häufige Stolperfallen**

- Fette Controller mit Business-Logik.
- Fette Models mit zu vielen Verantwortlichkeiten.
- Enge Kopplung zwischen Controllern und Persistenzdetails.

6. **Moderne Praxis in PHP**

Viele Projekte nutzen MVC als Basis, verschieben Business-Logik aber in Service-/Use-Case-Layer, sodass Controller schlank und Views einfach bleiben.

MVC bleibt eine praktische Grundlage in Frameworks wie Laravel und Symfony-ähnlichen Anwendungen, besonders in Kombination mit klaren Layering-Prinzipien.

</details>

<details>
<summary>30. Was ist hexagonale / Clean Architecture in PHP?</summary>

#### PHP

Hexagonale (Ports and Adapters) und Clean Architecture sind Ansätze, die Business-Logik unabhängig von Frameworks, Datenbanken und externen Services halten.

1. **Kernidee**

- Business-Regeln stehen im Zentrum (Domain/Use Cases).
- Externe Systeme werden als austauschbare Adapter behandelt.
- Abhängigkeiten zeigen nach innen: Infrastruktur hängt von der Domain ab, nicht umgekehrt.

2. **Haupt-Bausteine**

- **Domain-Layer**: Entities, Value Objects, Domain-Regeln.
- **Application-/Use-Case-Layer**: orchestriert Business-Szenarien.
- **Ports (Interfaces)**: Contracts für benötigte Fähigkeiten (Repositories, Gateways, Busse).
- **Adapter**: konkrete Implementierungen (MySQL-Repository, HTTP-Client, Queue-Publisher).
- **Delivery-Layer**: HTTP-Controller/CLI/Consumer, die Use Cases aufrufen.

3. **Warum das wichtig ist**

- Framework oder DB können mit minimalem Einfluss auf die Kern-Business-Logik ausgetauscht werden.
- Use Cases sind isoliert leichter testbar.
- Klare Grenzen reduzieren Kopplung und langfristiges Wartungsrisiko.

4. **PHP-orientiertes Beispiel**

- `CreateOrderUseCase` hängt von `OrderRepositoryInterface` und `PaymentGatewayInterface` ab.
- Laravel-/Symfony-Controller ruft den Use Case auf.
- MySQL-Repository und Stripe-Adapter implementieren Interfaces in der Infrastruktur-Schicht.

5. **Ordnerstruktur (konzeptionell)**

- `src/Domain/...`
- `src/Application/...`
- `src/Infrastructure/...`
- `src/Interface/Http/...` (oder `Presentation/...`)

6. **Praktische Leitlinien**

- Framework-Klassen aus der Domain-Schicht heraushalten.
- Grenzen über Interfaces am Application-/Domain-Rand ausdrücken.
- Framework-Request/Response-DTOs an den Grenzen mappen, nicht in der Domain.
- Einfach starten und zusätzliche Layer dort einführen, wo die Komplexität es rechtfertigt.

Hexagonale/Clean Architecture hilft PHP-Systemen, anpassbar, testbar und stabil zu bleiben, wenn sich Produkt und Infrastruktur weiterentwickeln.

</details>

<details>
<summary>31. Was ist das Repository-Pattern?</summary>

#### PHP

Repository ist ein Pattern, das Datenzugriff hinter einem domain-orientierten Interface abstrahiert, sodass Business-Logik mit Collections/Aggregates arbeitet statt direkt mit SQL/ORM-Details.

1. **Kernidee**

- Domain-/Application-Layer hängen von Repository-Interfaces ab.
- Infrastruktur-Layer liefert konkrete Implementierungen (PDO/Doctrine/Eloquent/API).
- Persistenzaspekte bleiben außerhalb der Use-Case-Logik.

2. **Was ein Repository typischerweise bereitstellt**

- Entities/Aggregates laden (`findById`, `findByCriteria`).
- Änderungen persistieren (`save`, `remove`).
- Query-Operationen in Domain-Begriffen ausdrücken.

3. **Beispiel-Interface**

```php
interface OrderRepositoryInterface
{
    public function getById(string $id): ?Order;
    public function save(Order $order): void;
}
```

4. **Warum es nützlich ist**

- Entkoppelt Business-Logik von Storage-Technologie.
- Verbessert Testbarkeit (einfache In-Memory-/Mock-Implementierungen).
- Unterstützt Architekturgrenzen (hexagonal/clean).
- Macht Migrationen/Refactorings sicherer, wenn sich Persistenz ändert.

5. **Häufige Fehler**

- Repository in einen generischen CRUD-Dump ohne Domain-Intent verwandeln.
- Alle ORM-Methoden unnötig 1:1 duplizieren.
- Business-Logik in Repository-Implementierungen legen.

6. **Praktische Leitlinien**

- Repository-Interfaces an der Domain-/Application-Grenze halten.
- Methoden anbieten, die für Use Cases sinnvoll sind, nicht für DB-Interna.
- Für komplexes Filtering bei Bedarf Specifications/Query-Objects nutzen.
- Repositories Persistenz handhaben lassen; Orchestrierung in Services/Use Cases belassen.

Das Repository-Pattern ist besonders wertvoll in mittleren/großen PHP-Systemen, in denen Langlebigkeit der Domain-Logik wichtiger ist als kurzfristige CRUD-Geschwindigkeit.

</details>

<details>
<summary>32. Was sind DTOs und Value Objects?</summary>

#### PHP

DTOs und Value Objects sind unterschiedliche Patterns, die in moderner PHP-Architektur oft zusammen verwendet werden.

1. **DTO (Data Transfer Object)**

- Ein einfaches Objekt zum Transfer strukturierter Daten zwischen Layers/Prozessen.
- Enthält üblicherweise Felder und minimale/keine Business-Logik.
- Hilft, rohe Arrays über Grenzen hinweg zu vermeiden.

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

- Ein Domain-Objekt, das durch seinen Wert definiert ist, nicht durch Identität.
- Üblicherweise immutable und selbstvalidierend.
- Kapselt Domain-Regeln für ein bestimmtes Konzept (Email, Money, Currency usw.).

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

3. **Zentrale Unterschiede**

- **Zweck**: DTO transportiert Daten; VO modelliert Domain-Bedeutung.
- **Logik**: DTO minimal; VO kann Invarianten erzwingen.
- **Identität**: DTO oft nebensächlich; VO wird nach Wert verglichen.
- **Mutabilität**: DTO kann mutable/immutable sein; VO sollte in der Regel immutable sein.

4. **Wann man welches verwendet**

- DTOs an Grenzen verwenden (HTTP Request/Response, Messaging, Application-Layer Input/Output).
- Value Objects innerhalb des Domain-Modells verwenden, um validierte Konzepte sicher auszudrücken.

DTOs verbessern die Klarheit von Datenflüssen, während Value Objects Domain-Korrektheit verbessern und ungültige Zustände verhindern.

</details>

<details>
<summary>33. Was ist OOP in PHP?</summary>

#### PHP

OOP (Objektorientierte Programmierung) in PHP ist ein Programmierparadigma, bei dem Code rund um Objekte organisiert wird, die Daten (Zustand) und Verhalten (Methoden) kombinieren.

1. **Kernkonzepte von OOP**

- **Klasse**: Bauplan, der Properties und Methoden definiert.
- **Objekt**: Instanz einer Klasse.
- **Kapselung (Encapsulation)**: kontrolliert den Zugriff auf Interna (`public/protected/private`).
- **Vererbung (Inheritance)**: Kindklassen nutzen/erweitern Verhalten der Elternklasse.
- **Polymorphie**: gemeinsame Interfaces mit austauschbaren Implementierungen.
- **Abstraktion**: wesentliche Contracts freilegen, Implementierungsdetails verbergen.

2. **Warum OOP in PHP verwendet wird**

- Modelliert Domain-Konzepte klar.
- Fördert modularen, wiederverwendbaren Code.
- Verbessert Wartbarkeit in mittleren/großen Codebasen.
- Passt natürlich zu DI, Interfaces und Framework-Architektur.

3. **Grundlegendes Beispiel**

```php
interface NotifierInterface
{
    public function send(string $message): void;
}

final class EmailNotifier implements NotifierInterface
{
    public function send(string $message): void
    {
        // E-Mail senden
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

4. **Moderne OOP-Features in PHP**

- Typisierte Properties und strict types
- Interfaces und abstrakte Klassen
- Traits für horizontale Code-Wiederverwendung
- Attribute, Enums, readonly Properties/Klassen
- Constructor Property Promotion

5. **Best Practices**

- Wo möglich Komposition statt Vererbung bevorzugen.
- Gegen Interfaces programmieren, nicht gegen konkrete Klassen.
- Klassen fokussiert halten (Single Responsibility).
- „God Objects“ mit zu vielen Verantwortlichkeiten vermeiden.

OOP in PHP ist die Grundlage für die meisten modernen Framework- und Domain-Driven-Anwendungsdesigns.

</details>

<details>
<summary>34. Was ist der Unterschied zwischen Interface und abstrakter Klasse?</summary>

#### PHP

Sowohl Interfaces als auch abstrakte Klassen definieren Contracts, dienen aber unterschiedlichen Designzwecken.

1. **Interface**

- Definiert nur Methodensignaturen (Contract) und Konstanten.
- Kein Instanzzustand (keine Properties mit Laufzeitzustand).
- Eine Klasse kann mehrere Interfaces implementieren.
- Fokus: Fähigkeits-Contract und Polymorphie.

```php
interface PaymentGatewayInterface
{
    public function charge(int $amount): bool;
}
```

2. **Abstrakte Klasse**

- Kann sowohl abstrakte als auch implementierte Methoden enthalten.
- Kann gemeinsamen Zustand/Verhalten haben (Properties, protected Helper, Konstruktorlogik).
- Eine Klasse kann nur eine abstrakte/Basis-Klasse erweitern.
- Fokus: partielle Implementierung + gemeinsames Basisverhalten.

```php
abstract class BaseGateway
{
    public function __construct(protected string $apiKey) {}

    abstract public function charge(int $amount): bool;

    protected function log(string $message): void
    {
        // gemeinsame Logik
    }
}
```

3. **Zentrale Unterschiede**

- **Mehrfachvererbung von Typen**: viele Interfaces, aber nur eine Elternklasse.
- **Geteilter Code**: abstrakte Klasse ja, Interface nein.
- **Kopplung**: Interface ist meist loser; abstrakte Klasse führt Vererbungskopplung ein.

4. **Wann man was wählt**

- **Interface** nutzen, wenn austauschbare Implementierungen und klare Contracts benötigt werden.
- **Abstrakte Klasse** nutzen, wenn Implementierungen sinnvolle gemeinsame Basislogik/-zustand teilen.

5. **Praktische Regel**

Für öffentliche Architekturgrenzen Interfaces bevorzugen; abstrakte Klassen als internes Reuse-Werkzeug verwenden, wenn Vererbung gerechtfertigt ist.

Interface = „was es kann“, abstrakte Klasse = „was teilweise bereits implementiert ist“.

</details>

<details>
<summary>35. Was sind Traits und wann sollten sie verwendet werden?</summary>

#### PHP

Traits in PHP sind ein Mechanismus für horizontale Code-Wiederverwendung: Sie erlauben Klassen, Methoden (und zugehörige Member) ohne Vererbung wiederzuverwenden.

1. **Was ein Trait ist**

- Eine wiederverwendbare Code-Einheit, deklariert mit `trait`.
- Wird über `use` in Klassen eingebunden.
- Hilft, Verhalten über nicht verwandte Klassenhierarchien hinweg zu teilen.

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

2. **Wann Traits nützlich sind**

- Geteiltes, querschnittliches Verhalten (Logging-Helper, Timestamps, kleine Utility-Verhaltensweisen).
- Wiederverwendung über Klassen, die keine gemeinsame Elternklasse haben können.
- Reduzierung von Duplikation, wenn Komposition für kleine Verhaltensblöcke zu ausführlich wäre.

3. **Trait-Konfliktauflösung**

Wenn zwei Traits dieselbe Methode definieren, bietet PHP Konfliktauflösung:
- `insteadof`, um eine Implementierung zu wählen.
- `as`, um Methoden zu aliasen/umzubenennen.

4. **Einschränkungen und Risiken**

- Traits können Kopplung verstecken und Verantwortlichkeiten verwischen, wenn sie übernutzt werden.
- Große „God Traits“ werden schwer testbar und wartbar.
- Sie sind Code-Inklusion, keine echten polymorphen Contracts.

5. **Best Practices**

- Traits klein und fokussiert halten.
- Traits für Verhaltens-Reuse nutzen, nicht für Domain-Modellierung.
- Für zentrale Architekturgrenzen Interfaces + Komposition bevorzugen.
- Komplexen mutablen Shared State in Traits vermeiden.

Traits sind ein praktisches PHP-Werkzeug für gezielte Wiederverwendung, funktionieren aber am besten als leichtgewichtige Ergänzung zu gutem Objektdesign, nicht als Ersatz dafür.

</details>

<details>
<summary>36. Was sind Magic Methods und wann werden sie ausgelöst?</summary>

#### PHP

Magic Methods sind spezielle PHP-Methoden (mit Präfix `__`), die von der Engine bei bestimmten Ereignissen im Objektlebenszyklus oder bei Interaktionen automatisch ausgelöst werden.

1. **Magic Methods des Objektlebenszyklus**

- `__construct()` - wird beim Erzeugen eines Objekts aufgerufen.
- `__destruct()` - wird beim Zerstören des Objekts (oder am Skriptende) aufgerufen.
- `__clone()` - wird nach dem Klonen eines Objekts aufgerufen.

2. **Magic Methods für Property-Zugriffe**

- `__get($name)` - Lesen einer nicht zugänglichen/nicht definierten Property.
- `__set($name, $value)` - Schreiben einer nicht zugänglichen/nicht definierten Property.
- `__isset($name)` - `isset()`/`empty()` auf nicht zugänglicher/nicht definierter Property.
- `__unset($name)` - `unset()` auf nicht zugänglicher/nicht definierter Property.

3. **Interception von Methodenaufrufen**

- `__call($name, $arguments)` - Aufruf einer nicht zugänglichen/nicht definierten Instanzmethode.
- `__callStatic($name, $arguments)` - Aufruf einer nicht zugänglichen/nicht definierten statischen Methode.

4. **String/Invocation/Serialisierung**

- `__toString()` - Objekt wird als String verwendet.
- `__invoke(...$args)` - Objekt wird wie eine Funktion verwendet.
- `__serialize()` / `__unserialize()` - benutzerdefinierte Serialisierungslogik.

5. **State-Export/Debug-Helfer**

- `__set_state(array $properties)` - wird bei Rekonstruktion via `var_export()` aufgerufen.
- `__debugInfo()` - benutzerdefinierte Ausgabe für `var_dump()`.

6. **Einfaches Beispiel**

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

7. **Best Practices**

- Magic Methods bewusst einsetzen, nicht als Standardarchitektur.
- Verhalten explizit und vorhersehbar halten.
- Fehler nicht durch zu permissive `__get/__set` verstecken.
- Wenn möglich typisierte Properties/Methoden bevorzugen.

Magic Methods sind mächtige Erweiterungspunkte, sollten aber vorsichtig eingesetzt werden, da sie bei Übernutzung die Klarheit reduzieren können.

</details>

<details>
<summary>37. Was ist Late Static Binding?</summary>

#### PHP

Late Static Binding (LSB) in PHP ermöglicht die Auflösung statischer Methoden/Properties basierend auf der Klasse, die zur Laufzeit aufgerufen wird, nicht nur auf der Klasse, in der die Methode definiert ist.

1. **`self::` vs `static::`**

- `self::` ist an die Klasse gebunden, in der die Methode deklariert ist (early binding).
- `static::` wird zur Laufzeit auf die aufrufende Klasse aufgelöst (late static binding).

2. **Warum das wichtig ist**

- Ermöglicht polymorphes Verhalten im statischen Kontext.
- Nützlich in Vererbungshierarchien, in denen Child-Klassen die zurückgegebene Klasse/Werte steuern sollen.
- Häufig in Factory-Patterns und Active-Record-ähnlichen APIs.

3. **Beispiel**

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

Würde stattdessen `self::TABLE` verwendet, wäre das Verhalten auf den Basis-Deklarationskontext fixiert.

4. **Verwandtes Keyword**

- Der Return-Typ `static` (`public static function make(): static`) nutzt ebenfalls late-static-Semantik und gibt den Typ der aufrufenden Klasse zurück.

5. **Praktische Leitlinien**

- `static::` verwenden, wenn Subklassen statisches Verhalten anpassen müssen.
- `self::` verwenden, wenn Verhalten absichtlich auf die Basis-Klassenimplementierung fixiert bleiben soll.

Late Static Binding ist ein wichtiges OOP-Feature für erweiterbare Klassenhierarchien in PHP.

</details>

<details>
<summary>38. Wie werden Objekte in PHP im Speicher behandelt?</summary>

#### PHP

In PHP werden Objekte von der Zend Engine als auf dem Heap allokierte Strukturen verwaltet, auf die über Object Handles referenziert wird; Memory-Management läuft automatisch über Reference Counting und Garbage Collection.

1. **Objekt-Speichermodell**

- Objektinstanzen werden im von der Engine verwalteten Speicher (Heap) allokiert.
- Variablen halten Referenzen (Handles) auf Objekteinträge, keine vollständigen Objektkopien.
- Die Zuweisung einer Objektvariable an eine andere kopiert den Handle, nicht den Objektzustand.

```php
$a = new stdClass();
$a->x = 1;

$b = $a;      // gleiche Objekt-Referenz
$b->x = 2;

echo $a->x;   // 2
```

2. **Reference Counting**

- Die Engine verfolgt, wie viele zvals einen Wert/ein Objekt referenzieren.
- Fällt der Count auf null, kann Speicher freigegeben werden.
- Bei Objekten bedeutet das typischerweise Destruktor-Aufruf und Objekt-Cleanup.

3. **Garbage Collector (GC)**

- Allein mit Reference Counting lassen sich zyklische Referenzen nicht einsammeln.
- Der PHP-GC erkennt und bereinigt zyklischen Garbage (z. B. Objektgraphen, die sich gegenseitig referenzieren).

4. **Klonverhalten**

- `clone` erzeugt eine neue Objektinstanz (separate Identität).
- `__clone()` kann Post-Clone-Logik anpassen.

5. **Nuance bei Pass-by-reference**

- Das Übergeben von Objekten an Funktionen erfolgt effektiv per Handle (Objektänderungen sind außerhalb sichtbar).
- Für Mutationen des Objektzustands über Funktionsgrenzen hinweg braucht man in der Regel kein `&`.

6. **Performance-/Memory-Implikationen**

- Große Objektgraphen erhöhen den Memory-Druck.
- Langlebige Referenzen (statische Caches, Closures, globale Container) können Cleanup verzögern.
- Zyklische Referenzen in long-running Workern sollten beobachtet werden, um leak-artiges Wachstum zu vermeiden.

7. **Praktische Leitlinien**

- Objektgraphen bewusst und begrenzt halten.
- Große temporäre Strukturen in long-running Prozessen bei Bedarf explizit `unset`ten.
- Profiling-Tools nutzen, um Memory-Hotspots zu analysieren.
- Bei statischen Singletons/globalem State in Workern/Daemons vorsichtig sein.

Die PHP-Objektspeicherverwaltung ist für typische Request-Lifecycles effizient, aber long-running Prozesse erfordern bewusste Memory-Disziplin.

</details>

<details>
<summary>39. Was ist PDO und warum wird es bevorzugt?</summary>

#### PHP

PDO (PHP Data Objects) ist eine Datenbankzugriffs-Abstraktionsschicht in PHP, die eine konsistente API für die Arbeit mit mehreren Datenbank-Engines bereitstellt.

1. **Was PDO bietet**

- Einheitliches Interface für DB-Operationen (`MySQL`, `PostgreSQL`, `SQLite` usw.).
- Prepared Statements und Parameter Binding.
- Transaction-Support.
- Konfigurierbare Fetch-Modi und Fehlerbehandlung.

2. **Warum PDO bevorzugt wird**

- **Portabilität:** gleicher Coding-Stil über verschiedene Datenbanken hinweg.
- **Sicherheit:** Prepared Statements reduzieren SQL-Injection-Risiko.
- **Wartbarkeit:** saubererer, standardisierter DB-Zugriffscode.
- **Kontrolle:** explizites Transaction-/Error-Verhalten.

3. **Basisbeispiel**

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

4. **PDO vs. direkte treiberspezifische APIs**

- PDO bietet eine gemeinsame Abstraktion und sauberere Architekturgrenzen.
- Treiberspezifische APIs können Nischenfeatures bieten, reduzieren aber Portabilität.

5. **Best Practices**

- Exception-Mode immer aktivieren (`PDO::ERRMODE_EXCEPTION`).
- Für jeden externen Input Prepared Statements verwenden.
- Expliziten Charset im DSN setzen (z. B. `utf8mb4`).
- Transactions bei mehrstufigen Writes explizit handhaben.

PDO wird in modernem PHP bevorzugt, weil es Sicherheit, Portabilität und klare Datenbankzugriffsmuster kombiniert.

</details>

<details>
<summary>40. Was sind Prepared Statements und Parameter Binding?</summary>

#### PHP

Prepared Statements sind SQL-Queries, die als Templates mit Platzhaltern kompiliert werden; Werte werden separat per Parameter Binding übergeben.

1. **Wie sie funktionieren**

- Schritt 1: SQL mit Platzhaltern vorbereiten (`:email`, `?`).
- Schritt 2: Werte separat binden/ausführen.
- Die Datenbank behandelt gebundene Werte strikt als Daten, nicht als SQL-Syntax.

2. **Warum sie wichtig sind**

- Primäre Abwehr gegen SQL Injection.
- Saubererer und sichererer Query-Code.
- Bessere Behandlung von Datentypen und Escaping durch den Treiber.
- Kann Performance bei wiederholter Query-Ausführung verbessern (DB-/treiberabhängig).

3. **Beispiel mit benannten Platzhaltern (PDO)**

```php
$stmt = $pdo->prepare(
    'SELECT id, email FROM users WHERE email = :email AND status = :status'
);

$stmt->execute([
    'email' => $email,
    'status' => $status,
]);
```

4. **Beispiel mit positionalen Platzhaltern**

```php
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = ?');
$stmt->execute([$id]);
```

5. **Binding mit expliziten Typen**

```php
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = :id');
$stmt->bindValue(':id', $id, PDO::PARAM_INT);
$stmt->execute();
```

6. **Wichtige Nuance**

- Prepared Statements schützen Werte, nicht SQL-Identifier (Tabellen-/Spaltennamen).
- Dynamische Identifier müssen über strikte Allowlists kontrolliert werden.

7. **Best Practices**

- Für jede Query mit externem Input Prepared Statements verwenden.
- String-Konkatenation für SQL-Bedingungen vermeiden.
- SQL-Templates lesbar und explizit halten.
- Mit Least-Privileged-DB-Usern und klaren Transaction-Grenzen kombinieren.

Prepared Statements + Parameter Binding sind der standardmäßige, nicht optionale Mindeststandard für sicheren DB-Zugriff in PHP.

</details>

<details>
<summary>41. Wie funktionieren Transactions in PHP?</summary>

#### PHP

Transactions in PHP (über PDO/MySQLi) gruppieren mehrere Datenbankoperationen zu einer atomaren Einheit: Entweder werden alle Änderungen committed oder alle werden zurückgerollt.

1. **Kern-Transaktionsoperationen**

- `beginTransaction()` - startet die Transaction.
- `commit()` - speichert alle Änderungen dauerhaft.
- `rollBack()` - verwirft alle nicht commiteten Änderungen.

2. **Warum Transactions nötig sind**

- Stellen Datenkonsistenz bei mehrstufigen Writes sicher.
- Verhindern Teil-Updates bei Fehlern.
- Bewahren Business-Invarianten (z. B. Debit und Credit müssen beide erfolgreich sein).

3. **Einfaches PDO-Beispiel**

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

4. **Isolation und Concurrency**

- Das DB-Isolation-Level steuert Sichtbarkeit/Locking-Verhalten zwischen konkurrierenden Transactions.
- Häufige Anomalien: Dirty Reads, Non-Repeatable Reads, Phantom Reads.
- Isolation-Level je nach Konsistenz-/Performance-Trade-off wählen.

5. **Praktische Stolperfallen**

- Lange Transactions halten Locks und verschlechtern Concurrency.
- Externe API-/Netzwerkaufrufe innerhalb der DB-Transaction vergrößern das Fehlerfenster.
- Vergessener Rollback bei Exceptions kann den Workflow inkonsistent machen.

6. **Best Practices**

- Transactions so kurz wie möglich halten.
- Nur DB-Operationen aufnehmen, die atomar sein müssen.
- Explizites Error-Handling und Rollback-Garantien verwenden.
- Retry-Logik für Deadlocks/Serialisierungs-Konflikte bei Bedarf designen.

Transactions sind ein zentraler Zuverlässigkeitsmechanismus für Finanz-, Inventar- und andere Integritäts-kritische Workflows in PHP-Systemen.

</details>

<details>
<summary>42. Was ist ORM (Eloquent / Doctrine) und welche Trade-offs gibt es?</summary>

#### PHP

ORM (Object-Relational Mapping) ist eine Technik, die Datenbanktabellen/-zeilen auf PHP-Objekte abbildet, sodass man in den meisten Teilen des Anwendungscodes mit Domain-Entities statt mit rohem SQL arbeitet.

1. **Was ORM liefert**

- Entity-/Model-Klassen, die auf DB-Schemas gemappt sind.
- Query-APIs/Builder statt manuellem SQL für gängige Operationen.
- Relationship-Handling (`hasMany`, `belongsTo` usw.).
- Unit-of-work/Change-Tracking (insbesondere in Doctrine).
- Migrations-/Ecosystem-Tooling in vielen Frameworks.

2. **Gängige PHP-ORMs**

- **Eloquent (Laravel)**:
  Active-Record-Stil, schnelle Produktivität, ausdrucksstarke Syntax.
- **Doctrine ORM**:
  Data-Mapper-Stil, reiches Domain-Modeling, stärkere Trennung von Verantwortlichkeiten.

3. **Vorteile**

- Schnellere Entwicklung bei CRUD-lastigen Features.
- Saubererer und besser lesbarer Persistenzcode für gängige Szenarien.
- Einfachere Traversierung von Relationen und model-zentrierte Workflows.
- Konventionsbasiertes Scaffolding und Ecosystem-Integrationen.

4. **Trade-offs / Nachteile**

- Abstraktions-Overhead und potenzielle Performance-Kosten.
- Versteckte/implizite Queries (N+1-Problem).
- Komplexes SQL/Reporting erfordert oft weiterhin manuelles SQL.
- ORM-spezifische Patterns können Lernkurve und Lock-in erhöhen.

5. **Wann ORM am besten funktioniert**

- Business-Anwendungen mit häufigen Entity-Lifecycle-Operationen.
- Teams, die Produktivität und wartbaren model-zentrierten Code priorisieren.

6. **Wann man raw SQL/Query-Builder bevorzugen sollte**

- Performance-kritische Hot Paths.
- Komplexe analytische/Reporting-Queries.
- DB-vendor-spezifische Features und fein granularer SQL-Control.

7. **Praktische Strategie**

- ORM standardmäßig für gängige Domain-Operationen nutzen.
- Bottlenecks profilieren und optimieren.
- ORM bei Bedarf mit optimiertem SQL kombinieren (hybrider Ansatz).
- Eager-/Lazy-Loading explizit steuern, um Query-Explosionen zu vermeiden.

ORM ist in PHP ein starker Produktivitätshebel, aber gute Engineering-Praxis erfordert zu verstehen, wo Abstraktion hilft und wo niedrigere SQL-Kontrolle besser ist.

</details>

<details>
<summary>43. Was ist Connection Pooling und warum ist es wichtig?</summary>

#### PHP

Connection Pooling ist eine Technik, bei der Datenbankverbindungen aus einem verwalteten Pool wiederverwendet werden, statt für jede Operation neu aufgebaut und geschlossen zu werden.

1. **Warum Verbindungen teuer sind**

- Das Öffnen von DB-Verbindungen umfasst Network-Handshake, Authentifizierung und Server-Resource-Allokation.
- Häufige Reconnects erhöhen Latenz und CPU-Last auf App und DB.

2. **Was Pooling macht**

- Hält einen wiederverwendbaren Satz offener Verbindungen.
- Weist eingehender Arbeit eine bestehende Verbindung zu.
- Gibt sie nach Nutzung in den Pool zurück, damit sie von nächsten Requests/Jobs wiederverwendet wird.

3. **Warum es wichtig ist**

- Reduziert Request-Latenz.
- Verbessert Throughput unter Last.
- Senkt DB-Connection-Churn und Overhead.
- Stabilisiert Verhalten bei hoher Concurrency.

4. **Nuance im PHP-Kontext**

- Im klassischen PHP-FPM-Request-Modell hat jeder Worker-Prozess einen isolierten Lifecycle, daher ist Pooling weniger direkt als in long-lived Runtimes.
- Gängige praktische Ansätze:
  persistente Verbindungen (`PDO::ATTR_PERSISTENT` mit Vorsicht),
  externe Pooler/Proxys (z. B. PgBouncer für PostgreSQL),
  long-running Worker (RoadRunner/Swoole/Queue-Consumer), wo Reuse direkter ist.

5. **Trade-offs / Risiken**

- Stale/defekte Verbindungen müssen erkannt und recycelt werden.
- Schlechte Pool-Größe kann Contention oder DB-Overload verursachen.
- Persistente Verbindungen können Server-Ressourcen länger als erwartet binden.

6. **Best Practices**

- Sinnvolle Pool-/Connection-Limits entsprechend der DB-Kapazität setzen.
- Connection-Health-Checks/Timeouts verwenden.
- Connection Count, Wait Time und Error Rates überwachen.
- Queries effizient halten; Pooling ist keine Lösung für langsames SQL.

Connection Pooling ist eine zentrale Skalierungstechnik für datenbanklastige PHP-Systeme, besonders bei dauerhaftem, konkurrierendem Traffic.

</details>

<details>
<summary>44. Wie strukturierst du eine skalierbare PHP-Anwendung?</summary>

#### PHP

Eine skalierbare PHP-Anwendung wird rund um klare Grenzen, vorhersehbare Architektur und operative Bereitschaft für Wachstum bei Traffic, Teamgröße und Feature-Komplexität strukturiert.

1. **Layer-/Modulgrenzen verwenden**

- Nach Verantwortlichkeiten und Business-Domains schneiden, nicht nur nach technischen Ordnern.
- Typische Layer:
  `Domain`, `Application/UseCases`, `Infrastructure`, `Interface/HTTP`.

2. **Business-Logik framework-agnostisch halten**

- Kernregeln in Domain-/Use-Case-Layer platzieren.
- Controller schlank halten.
- Von Interfaces abhängen; DB-/Framework-Adapter in der Infrastruktur-Schicht halten.

3. **Für stateless horizontale Skalierung designen**

- Lokalen mutablen Zustand in App-Instanzen vermeiden.
- Geteilten Zustand in externen Systemen speichern:
  DB, Redis, Object Storage, Queues.
- Sessions/Cache für Multi-Node-Deployments vorbereiten.

4. **Daten- und Persistenzstrategie**

- Repositories/Services für Persistenzgrenzen verwenden.
- Indexing und Query-Optimierung früh anwenden.
- Caching (Application/Query/HTTP) dort einführen, wo es gerechtfertigt ist.
- Read/Write-Separation und Partitionierung nur bei Bedarf einsetzen.

5. **Async- und Background-Processing**

- Nicht-kritische/langsame Tasks in Queues verschieben (E-Mails, Exporte, Notifications, Webhooks).
- Request-Pfad schnell und deterministisch halten.

6. **Operative Skalierbarkeit**

- Workloads containerisieren (Docker/K8s/managed platforms).
- Health Checks, strukturiertes Logging, Metriken, Tracing nutzen.
- Rate Limiting, Timeouts, Retries, Circuit Breaker hinzufügen.
- CI/CD mit sicherer Rollout-/Rollback-Strategie aufbauen.

7. **Codebase-Skalierbarkeit für Teams**

- Coding-Standards und statische Analyse durchsetzen.
- Modulare Package-Grenzen erhalten.
- Integration- und Contract-Tests um kritische Pfade nutzen.
- Architekturentscheidungen (ADRs) und Service-Contracts dokumentieren.

8. **Praktischer Evolutionspfad**

- Mit modularem Monolithen und starken Grenzen starten.
- Services nur dann extrahieren, wenn klare Skalierungs-/Team-Constraints es rechtfertigen.

Skalierbarkeit in PHP ist primär eine Architektur- und Operations-Disziplin, nicht die Wahl eines einzelnen Frameworks.

</details>

<details>
<summary>45. Wie handhabst du Konfiguration (Env-Variablen)?</summary>

#### PHP

In modernen PHP-Anwendungen sollte Konfiguration aus dem Code ausgelagert und über Umgebungsvariablen bereitgestellt werden, gemäß 12-Factor-Prinzipien.

1. **Kernprinzip**

- Konfiguration aus dem Source Code heraushalten.
- Environment als Quelle deploy-spezifischer Einstellungen behandeln:
  DB-Credentials, API-URLs, Cache-Hosts, Feature-Flags usw.

2. **Typisches Setup**

- Development: `.env`-Datei (vom Framework/Bootstrap geladen).
- Production: echte Umgebungsvariablen von Plattform/Orchestrator (kein `.env` im Repo).

3. **Wie Werte konsumiert werden**

- Env einmal im Config-Bootstrap lesen.
- In typisierte Config-Struktur/-Objekte mappen.
- Config per DI in Services injizieren.

4. **Gute Praktiken**

- Konfiguration per Environment (`dev`, `staging`, `prod`) über Env-Werte trennen.
- Defaults nur für nicht-sensitive lokale Entwicklungswerte bereitstellen.
- Erforderliche Konfiguration beim Startup validieren und bei fehlenden/ungültigen Werten fast failen.
- Config-Keys konsistent und dokumentiert halten.

5. **Was man nicht tun sollte**

- Credentials nicht im Code hardcoden.
- Produktions-Secrets nicht ins Repository committen.
- `getenv()` nicht zufällig quer durch die Domain-Logik aufrufen.
- Business-Logik nicht mit Config-Loading-Logik vermischen.

6. **Praktisches Pattern**

Zentrale Config-Dateien verwenden, die aus Env lesen, z. B.:
- `config/database.php`
- `config/cache.php`
- `config/app.php`

Danach aufgelöste Config in abhängige Services injizieren.

7. **Sicherheits-Hinweis**

Umgebungsvariablen sind besser als hardcodete Secrets, aber weiterhin sensibel:
Zugriff begrenzen, keine vollständigen Werte loggen und für kritische Credentials mit dedizierten Secret-Managern kombinieren.

Konfigurationshandling über Env-Variablen hält PHP-Apps portabel, sicher und konsistent über Umgebungen hinweg.

</details>

<details>
<summary>46. Wie verwaltest du Secrets (Vault, AWS Secrets Manager)?</summary>

#### PHP

Secrets Management ist die Praxis, sensitive Werte (API-Keys, DB-Passwörter, Tokens, Zertifikate) sicher außerhalb des Anwendungscodes zu speichern, zu rotieren und abzurufen.

1. **Warum dedizierte Secret-Manager nötig sind**

- Verhindern, dass Secrets in Repository/History geleakt werden.
- Zentralisieren Zugriffskontrolle und Auditing.
- Ermöglichen sichere Rotation ohne Code-Redployment.
- Reduzieren operatives Risiko gegenüber reinen `.env`-Dateien.

2. **Gängige Tools**

- **HashiCorp Vault**: dynamische Secrets, Leases, policy-basierter Zugriff, starke Audit-Fähigkeiten.
- **AWS Secrets Manager**: verwaltete Secret-Speicherung/Rotation, integriert mit IAM und AWS-Services.
- (Ebenfalls verbreitet: cloud-native Parameter Stores oder KMS-basierte Lösungen.)

3. **Empfohlener Secret-Flow**

1. App-Identität wird hergestellt (IAM-Rolle, Workload-Identity, Vault-Auth-Method).
2. App lädt benötigte Secrets beim Startup (oder on demand mit Cache).
3. Secrets werden nur so lange wie nötig im Speicher gehalten.
4. Rotationsereignisse werden ohne hardcodete Werte gehandhabt.

4. **Best Practices**

- Secrets niemals in git committen (auch keine Sample-Dateien mit realen Werten).
- Least-Privilege-Access-Policies pro Service/Environment verwenden.
- Secrets regelmäßig und bei Incident-Triggern rotieren.
- Zugriff-Metadaten loggen, niemals Secret-Werte.
- Secrets nach Environment (`dev/staging/prod`) und Service-Scope trennen.
- Wenn möglich kurzlebige Credentials nutzen (dynamische DB-Creds/Tokens).

5. **PHP-Integrationsmuster**

- Secrets im Bootstrap-/Infrastruktur-Layer laden.
- In typisierte Config-Objekte mappen.
- Config/Secrets per DI in abhängige Services injizieren.
- Fallback- und Retry-Strategie für Secret-Manager-Outages hinzufügen.

6. **Operative Aspekte**

- Secrets mit TTL cachen, um Latenz und API-Limits zu reduzieren.
- Bootstrap-Verhalten planen, wenn Secret-Backend temporär nicht verfügbar ist.
- Rotationsprozess in Staging vor dem Production-Rollout testen.

Der Einsatz von Vault/AWS Secrets Manager macht Secret-Handling aus ad-hoc Env-Variablen zu einem kontrollierten Sicherheitsprozess für produktive PHP-Systeme.

</details>

<details>
<summary>47. Was ist eine 12-Factor-App im Kontext von PHP?</summary>

#### PHP

Die 12-Factor-App ist ein Set cloud-nativer Engineering-Prinzipien zum Bau portabler, skalierbarer und wartbarer Services. In PHP helfen diese Prinzipien beim Übergang von „servergekoppelten Apps“ zu modernen deploybaren Services.

1. **Codebase**

- Eine Codebase, versioniert in Version Control.
- Viele Deploys (dev/staging/prod) aus derselben Codebase.

2. **Dependencies**

- Dependencies explizit in `composer.json` deklarieren.
- Nicht auf global installierte Systempakete verlassen.

3. **Config**

- Config in Umgebungsvariablen speichern, nicht im Code.
- Secrets und umgebungsspezifische Werte außerhalb des Repositories halten.

4. **Backing Services**

- DB, Cache, Queue, Object Storage als angebundene Ressourcen behandeln.
- Zugriff über Config/URLs, damit sie je Environment austauschbar sind.

5. **Trennung von Build, Release, Run**

- Artifact einmal bauen.
- Dasselbe Artifact durch Environments promoten.
- Runtime-Config vom Build getrennt halten.

6. **Processes**

- App als stateless Prozesse ausführen.
- Persistenten Zustand in externen Services speichern (DB/Redis/S3 usw.).

7. **Port Binding und Concurrency**

- Services über HTTP-/Runtime-Entrypoints bereitstellen.
- Über Prozess-/Container-Replikation skalieren, nicht nur vertikal tunen.

8. **Disposability und Parity**

- Schneller Startup/Shutdown für sichere Deploys und Autoscaling.
- Dev/staging/prod-Environments so ähnlich wie möglich halten.

9. **Logs und Admin-Tasks**

- Logs als Event-Streams behandeln (stdout/Aggregatoren).
- Admin-/Migration-Tasks als One-off-Prozesse mit derselben Codebase ausführen.

10. **PHP-spezifische praktische Implikationen**

- Composer + Env-Config + externalisierten State verwenden.
- Container-freundliche Runtime (PHP-FPM/CLI-Worker).
- Queue-Worker für Background-Tasks.
- CI/CD-Pipeline mit unveränderlichen Artifacts.

Die Anwendung von 12-Factor-Prinzipien in PHP verbessert Deploy-Zuverlässigkeit, operative Skalierbarkeit und langfristige Wartbarkeit.

</details>

<details>
<summary>48. Was ist Containerisierung (Docker) in PHP-Apps?</summary>

#### PHP

Containerisierung verpackt eine PHP-Anwendung mit ihren Runtime-Abhängigkeiten in ein portables Image, sodass sie konsistent in lokal, CI, Staging und Produktion läuft.

1. **Was Docker PHP-Apps gibt**

- Reproduzierbare Runtime (PHP-Version, Extensions, System-Libs).
- Environment-Parity zwischen Developer-Maschinen und Produktion.
- Einfacheres Deployment, Rollback und Skalierung.
- Isolation zwischen Services (App, DB, Cache, Queue, Worker).

2. **Typischer containerisierter PHP-Stack**

- PHP-FPM-Container (Application Runtime)
- Nginx/Apache-Container (Webserver)
- Separate Container für DB/Redis/Queue-Worker/Cron-Jobs

3. **Grundlegendes Dockerfile-Pattern**

```dockerfile
FROM php:8.4-fpm-alpine

RUN docker-php-ext-install pdo pdo_mysql opcache
WORKDIR /var/www/html

COPY . .
RUN php -v
```

4. **Warum es für Skalierung wichtig ist**

- Horizontale Skalierung wird einfacher (Container replizieren).
- Unveränderliche image-basierte Deploys reduzieren Drift/Config-Mismatch.
- Funktioniert natürlich mit Orchestrierungsplattformen (Kubernetes, ECS, Nomad).

5. **Best Practices**

- Kleine Base-Images und Multi-Stage-Builds verwenden.
- Image-/Tag-Versionen für Reproduzierbarkeit pinnen.
- Images stateless halten; persistente Daten extern speichern.
- Config/Secrets via Env/Secret-Manager injizieren, nicht ins Image backen.
- Health Checks ausführen und strukturierte Logs nach stdout/stderr ausgeben.

6. **Häufige Stolperfallen**

- Alles in einem Container laufen lassen (web + DB + queue) in Produktion.
- Persistente App-Daten ins Container-Dateisystem schreiben.
- Große Images mit unnötigen Build-Tools im Runtime-Layer.

Containerisierung ist eine Kernpraxis für moderne PHP-Operations, weil sie Runtime-Verhalten standardisiert und Deploybarkeit im großen Maßstab verbessert.

</details>

<details>
<summary>49. Was ist OPcache und wie verbessert es die Performance?</summary>

#### PHP

OPcache ist ein eingebauter PHP-Bytecode-Cache, der kompilierten Script-Bytecode im Shared Memory speichert, sodass PHP dieselben Dateien nicht bei jedem Request erneut parsen und kompilieren muss.

1. **Welches Problem OPcache löst**

- Ohne OPcache macht jeder Request wiederholt:
  PHP-Datei lesen -> parsen -> zu Opcodes kompilieren -> ausführen.
- Diese wiederholte Kompilierung erzeugt CPU-Overhead und Latenz.

2. **Wie OPcache die Performance verbessert**

- Kompilierte Opcodes werden im Speicher gecacht und über Requests hinweg wiederverwendet.
- Reduziert CPU-Nutzung und Request-Zeit.
- Erhöht Throughput unter Last.
- Verbessert Startup-Performance bei Frameworks mit vielen Dateien.

3. **Typisches Produktions-Setup**

- OPcache in der PHP-Runtime aktivieren (`opcache.enable=1`).
- Memory- und Dateianzahl-Limits tunen:
  `opcache.memory_consumption`, `opcache.max_accelerated_files`.
- Timestamp-Validierung für immutable Release-Artifacts deaktivieren:
  `opcache.validate_timestamps=0` (mit deploy-getriggertem Cache-Reset).

4. **Häufig nützliche Settings**

- `opcache.enable`
- `opcache.memory_consumption`
- `opcache.max_accelerated_files`
- `opcache.interned_strings_buffer`
- `opcache.validate_timestamps`
- `opcache.revalidate_freq`

5. **Deployment-Aspekte**

- Bei Code-Änderungen muss gecachter Bytecode aktualisiert werden.
- In immutable/container Deploys reicht meist ein Restart der PHP-Worker.
- In mutable Deploys kontrollierte Invalidation-/Restart-Strategie verwenden.

6. **Best Practices**

- OPcache in Produktion immer verwenden.
- Cache-Hit-Rate, Memory-Nutzung und Restarts überwachen.
- Cache-Größe entsprechend Codebase-Wachstum dimensionieren.
- OPcache mit Application-/Database-Caching für volle Performance-Gewinne kombinieren.

OPcache ist eines der wirkungsstärksten, aufwandsarmen Performance-Features für PHP-Produktionsumgebungen.

</details>

<details>
<summary>50. Was ist JIT in PHP und wann ist es nützlich?</summary>

#### PHP

JIT (Just-In-Time-Kompilierung) in PHP ist eine Engine-Optimierung, die ausgewählte Zend-Opcodes zur Laufzeit in nativen Maschinencode kompiliert.

1. **Was JIT macht**

- Normaler PHP-Flow: Script -> Opcodes -> Interpreter-Ausführung.
- Mit JIT: heiße Codepfade können in nativen Code kompiliert und schneller ausgeführt werden.

2. **Wo JIT helfen kann**

- CPU-intensive Workloads:
  schwere Mathematik, Loops, Datenverarbeitung, rechenintensive Algorithmen.
- Long-running CLI-Worker und spezialisierte Compute-Tasks.

3. **Wo JIT oft wenig bringt**

- Typische Web-Apps mit I/O-Dominanz:
  Datenbankqueries, Netzwerkaufrufe, Cache-Zugriffe, Template-Rendering.
- In vielen CRUD/API-Workloads sind OPcache und Query-Optimierung wichtiger als JIT.

4. **Beziehung zu OPcache**

- JIT baut auf der OPcache-Infrastruktur auf.
- OPcache liefert für die meisten Apps den größten Baseline-Gewinn.
- JIT ist eine zusätzliche Optimierungsschicht für CPU-bound Code.

5. **Praktische Leitlinien**

- Aktivieren und vor/nachher auf realer Workload benchmarken.
- Keine globalen Speedups für alle Request-Typen annehmen.
- Bottleneck-Fixes zuerst priorisieren:
  langsames SQL, N+1-Queries, übermäßige Netzwerkaufrufe, ineffizientes Caching.

6. **Faustregel**

- Für klassische Web-Backends: JIT-Effekt meist moderat.
- Für compute-lastige PHP-Workloads: JIT kann spürbare Verbesserungen liefern.

JIT ist ein nützliches Optimierungswerkzeug, aber sein Wert hängt stark vom Workload-Profil ab.

</details>

<details>
<summary>51. Was ist Lazy Loading und wo wird es eingesetzt?</summary>

#### PHP

Lazy Loading ist eine Technik, bei der Daten oder Objekte erst dann geladen werden, wenn sie tatsächlich benötigt werden, statt alles vorab zu laden.

1. **Kernidee**

- Teure Initialisierung bis zum ersten Zugriff verzögern.
- Initialen Memory-Verbrauch und Startup-Zeit reduzieren.
- Kosten nur für tatsächlich genutzte Pfade zahlen.

2. **Wo Lazy Loading in PHP eingesetzt wird**

- ORM-Relationen (Doctrine/Eloquent Relation-Proxys).
- Service-Initialisierung in DI-Containern (deferred services).
- Große Konfigurationen/Ressourcen on demand laden.
- Stream-/Dateiverarbeitung, bei der Chunks schrittweise geladen werden.

3. **Typisches ORM-Beispiel**

- `User`-Entity wird geladen.
- `User->orders` wird nicht sofort geladen.
- Erstzugriff auf Orders triggert die SQL-Query.

4. **Vorteile**

- Schnellere initiale Response für viele Use Cases.
- Geringerer Memory-Footprint, wenn nicht alle Daten benötigt werden.
- Bessere Skalierbarkeit für komplexe Objektgraphen.

5. **Trade-offs und Risiken**

- Versteckte Queries können N+1-Performanceprobleme verursachen.
- Zugriffsmuster werden weniger explizit.
- Lazy Loading in engen Loops kann DB-Round-Trips explodieren lassen.

6. **Best Practices**

- Eager Loading verwenden, wenn klar ist, dass Related Data benötigt wird.
- Query Count und Latenz profilieren.
- Lazy-Grenzen im Repository-/Query-Layer explizit halten.
- Lazy Loading in Serialisierungs-/Output-Loops vermeiden.

7. **Faustregel**

- Lazy Loading für optionale oder selten genutzte Dependencies/Daten verwenden.
- Eager Loading für vorhersehbar häufig genutzte Related Data verwenden.

Lazy Loading ist ein starkes Performance-Werkzeug, aber nur zusammen mit Sichtbarkeit des Query-Verhaltens und bewusster Loading-Strategie.

</details>

<details>
<summary>52. Was sind häufige PHP-Performance-Bottlenecks?</summary>

#### PHP

Die meisten PHP-Performanceprobleme werden nicht von der Sprache selbst verursacht, sondern durch ineffizientes I/O, Query-Muster und Architekturentscheidungen.

1. **Datenbank-Bottlenecks (am häufigsten)**

- N+1-Queries bei ORM-Nutzung.
- Fehlende Indizes oder schlechte Query-Pläne.
- Over-Fetching von Daten (`SELECT *`, obwohl nicht nötig).
- Lange Transactions und Lock-Contention.

2. **Netzwerk und externes I/O**

- Langsame Third-Party-APIs ohne Timeouts/Retries.
- Zu viele synchrone Outbound-Calls im Request-Pfad.
- Fehlende Circuit Breaker/Fallbacks.

3. **Ineffizienzen auf Anwendungsebene**

- Schwere Business-Logik bei jedem Request.
- Teure Ergebnisse neu berechnen statt cachen.
- Exzessive Serialisierung/Deserialisierung oder große Payload-Verarbeitung.

4. **Autoload-/Bootstrap-Overhead**

- Große Framework-Bootstraps für triviale Endpoints.
- Zu viele geladene Klassen/Config-Provider.
- Falsch konfiguriertes OPcache.

5. **Filesystem- und Logging-Overhead**

- Häufige Disk-Writes im Request-Pfad.
- Blockierendes/zu ausführliches Logging ohne Async-Verarbeitung.
- Langsame Storage-Volumes in Containern/VMs.

6. **Memory-Druck**

- Große In-Memory-Collections und ungebundene Arrays.
- Ineffiziente Loops über riesige Datasets.
- Long-lived Worker, die unbeabsichtigt Referenzen behalten.

7. **Fehlendes/ineffektives Caching**

- Kein Caching für read-heavy Data.
- Falsche Cache-Invalidierungsstrategie mit stale/häufigen Misses.
- Cache Stampede unter Last.

8. **Wie man systematisch vorgeht**

- Vor dem Optimieren profilieren.
- Zuerst die heißesten Endpoints/Queries priorisieren.
- Query-Optimierung + Caching + Async-Offloading ergänzen.
- p95/p99-Latenz, DB-Zeit, Cache-Hit-Ratio und Error-Rates überwachen.

In PHP-Systemen kommen die schnellsten Gewinne meist aus Query-Tuning, Caching-Strategie und der Reduktion synchronen I/O im Request-Pfad.

</details>

<details>
<summary>53. Wie profilierst du eine PHP-Anwendung?</summary>

#### PHP

Profiling ist der Prozess, zu messen, wo Ausführungszeit, CPU, Memory und I/O tatsächlich verbraucht werden, damit Optimierung auf Evidenz statt auf Vermutungen basiert.

1. **Was man zuerst messen sollte**

- Request-Latenz (p50/p95/p99)
- Datenbankzeit und Query Count
- Dauer externer API-Calls
- Memory-Nutzung und Peak-Nutzung
- Hot Functions/Code-Pfade

2. **Gängige PHP-Profiling-Tools**

- **Blackfire** - produktionsfreundliches Profiling und Performance-Empfehlungen.
- **Xdebug (profiler mode)** - detaillierte Traces/Callgrind für lokale Analyse.
- **Tideways/XHProf-Familie** - Function-Level-Profiling mit Low-Overhead-Optionen.
- **APM-Tools** (Datadog/New Relic/etc.) für verteilte Request-Sichtbarkeit.

3. **Praktischer Profiling-Workflow**

1. Langsamen Endpoint/Job mit realistischen Daten reproduzieren.
2. Profil-Trace erfassen.
3. Top-Driver identifizieren (DB, externes I/O, CPU-lastige Funktionen).
4. Jeweils einen Bottleneck optimieren.
5. Re-profilen und Metriken vergleichen.

4. **Was typischerweise als Hotspots erscheint**

- N+1-ORM-Queries
- Fehlende Indizes / teure SQL-Scans
- Wiederholte Serialisierung und große Payload-Verarbeitung
- Synchrone Netzwerkaufrufe im Request-Pfad
- Übermäßiger Framework-/Bootstrap-Overhead

5. **Memory-Profiling-Fokus**

- Große Arrays/Collections auf einmal laden
- Long-lived Referenzen in Workern
- Unnötige Objektgraphen und duplizierte Daten

6. **Best Practices**

- In Environments profilieren, die dem Produktionsverhalten nahekommen.
- Vor und nach jeder Optimierung benchmarken.
- Regressionen in CI/CD mit Performance-Budgets für kritische Endpoints tracken.
- Code-Profiling mit DB-Profiling kombinieren (`EXPLAIN`, slow query logs).

Profiling macht Performance-Tuning zu einem messbaren Engineering-Prozess und ist der zuverlässigste Weg, PHP-Anwendungsgeschwindigkeit sicher zu verbessern.

</details>

<details>
<summary>54. Wie funktioniert Caching (Redis, Memcached)?</summary>

#### PHP

Caching speichert vorab berechnete oder häufig angefragte Daten in schnellem Storage (meist Memory), um wiederholte teure Operationen wie DB-Queries oder schwere Berechnungen zu vermeiden.

1. **Wie Caching funktioniert (Basis-Flow)**

1. App erhält Request auf Daten.
2. Cache per Key prüfen.
3. Bei Hit: gecachten Wert schnell zurückgeben.
4. Bei Miss: aus Quelle (DB/API) laden, mit TTL in Cache speichern, Wert zurückgeben.

2. **Gängige Cache-Backends**

- **Redis**:
  In-Memory-Data-Store mit reichen Datenstrukturen, Persistenzoptionen, Pub/Sub und verteilten Features.
- **Memcached**:
  einfacher verteilter In-Memory-Key-Value-Cache, fokussiert auf High-Speed-Ephemeral-Caching.

3. **Typische PHP-Cache-Use-Cases**

- Query-Result-Caching
- Session-Storage
- Response-/Fragment-Caching
- Rate-Limiting-Counter
- Locks und Idempotency-Keys
- Berechnete/konfigurationsbezogene Referenzdaten

4. **Wichtige Cache-Design-Konzepte**

- **Key-Strategie**: vorhersehbares Namespacing und Versionierung (`user:42:v2`).
- **TTL**: Ablaufzeit je nach Datenvolatilität wählen.
- **Invalidierung**: explizite Invalidierung bei Writes, wenn Freshness wichtig ist.
- **Konsistenzmodell**: Eventual Consistency dort akzeptieren, wo angemessen.

5. **Häufige Stolperfallen**

- Cache Stampede (viele konkurrierende Misses).
- Stale Data durch schwache Invalidierungsstrategie.
- Überdimensionierte Werte und schlechtes Key-Design.
- Cache als Source of Truth behandeln.

6. **Best Practices**

- Nur teure/high-frequency Reads cachen.
- Kurze, sinnvolle TTLs plus Jitter verwenden, um synchrones Expiry zu reduzieren.
- Stampede-Protection hinzufügen (Locks, Request-Coalescing, stale-while-revalidate).
- Hit Rate, Latenz, Eviction und Memory-Nutzung überwachen.
- DB als Source of Truth beibehalten; Cache ist eine Beschleunigungsschicht.

Redis-/Memcached-Caching ist eine der effektivsten Methoden, Latenz und Datenbanklast in PHP-Produktionssystemen zu reduzieren.

</details>

<details>
<summary>55. Was ist asynchrone Verarbeitung in PHP?</summary>

#### PHP

Asynchrone Verarbeitung bedeutet, langsame oder nicht-kritische Tasks aus dem synchronen HTTP-Request-Flow auszulagern, sodass Nutzer schnelle Responses erhalten, während Background-Arbeit separat ausgeführt wird.

1. **Warum Async nötig ist**

- Request-Response-Zyklen sollten kurz bleiben.
- Manche Operationen sind teuer:
  E-Mails, Dateiverarbeitung, Report-Generierung, externe API-Aufrufe.
- Alles inline zu erledigen erhöht Latenz und Fehlerauswirkung.

2. **Wie es in PHP-Systemen funktioniert**

1. Haupt-App erhält Request.
2. Kritischer Zustand wird schnell gespeichert.
3. Background-Job/Event wird in die Queue geschrieben.
4. Worker-Prozess konsumiert und führt Task asynchron aus.

3. **Typische Async-Workloads**

- E-Mail/SMS/Push-Benachrichtigungen
- Medienverarbeitung (Bilder/Video/PDF)
- Datenimporte/-exporte
- Webhook-Delivery/Retries
- Search-Index-Updates
- Analytics-/Event-Processing

4. **Vorteile**

- Niedrigere nutzerseitige Latenz.
- Bessere Resilienz (Retries, Dead-Letter-Queues).
- Verbesserter Throughput durch Entkopplung schwerer Jobs.
- Klarere Trennung von Online- vs. Offline-Arbeit.

5. **Trade-offs**

- Zusätzliche operative Komplexität (Queues/Worker/Monitoring).
- Eventual Consistency zwischen Write und Side Effects.
- Bedarf an Idempotenz und retry-sicheren Handlern.

6. **Best Practices**

- Job-Payloads minimal halten (IDs statt voller Objekte).
- Handler idempotent machen.
- Retry/Backoff und Dead-Letter-Handling konfigurieren.
- Queue-Tiefe, Worker-Lag und Failure-Rate überwachen.
- Definieren, welche Tasks sync-kritisch vs. async-deferred sind.

In der PHP-Architektur ist asynchrone Verarbeitung eine Schlüsseltechnik, um User Experience und Zuverlässigkeit unter realer Produktionslast zu skalieren.

</details>

<details>
<summary>56. Was sind Queues (RabbitMQ, Kafka, Redis-Queues)?</summary>

#### PHP

Queues sind Messaging-Mechanismen, die Producer und Consumer entkoppeln und so asynchrone Verarbeitung, Buffering und zuverlässige Background-Ausführung ermöglichen.

1. **Kernkonzept von Queues**

- Producer publiziert eine Nachricht/einen Job.
- Broker speichert sie temporär.
- Consumer/Worker verarbeitet sie später.
- Damit wird schwere Arbeit aus dem synchronen Request-Flow entfernt.

2. **Warum Queues wichtig sind**

- Glätten Traffic-Spitzen (Buffering).
- Verbessern Response-Zeit (Offloading von Background-Tasks).
- Erhöhen Zuverlässigkeit mit Retries und Dead-Letter-Handling.
- Entkoppeln Services und Komponenten.

3. **Gängige Queue-Technologien in PHP**

- **RabbitMQ**:
  klassischer Message-Broker, starke Routing-Patterns, Acknowledgements, Retries.
- **Kafka**:
  verteiltes Event-Log, High-Throughput-Stream-Processing, replaybare Messages.
- **Redis-basierte Queues** (z. B. Laravel Queues):
  einfach und schnell für viele app-seitige Background-Jobs.

4. **Typische PHP-Queue-Use-Cases**

- E-Mail/SMS/Push-Dispatch
- Webhook-Delivery
- Datei-/Bild-/Video-Verarbeitung
- Search-Indexing
- Report-Generierung
- Integrations-/Event-Fan-out

5. **Zuverlässigkeitskonzepte**

- **Ack/Nack**: Erfolg bestätigen oder Retry anfordern.
- **Retry-Policy**: exponentieller Backoff, maximale Versuche.
- **Dead-letter queue (DLQ)**: problematische/fehlgeschlagene Messages isolieren.
- **Idempotenz**: sichere Wiederverarbeitung ohne doppelte Side Effects.

6. **Best Practices**

- Message-Payloads klein halten (IDs statt großer Objekte bevorzugen).
- Message-Schemas versionieren.
- Consumer idempotent und observable machen (Logs/Metriken/Tracing).
- Queue-Tiefe, Processing-Lag, Failure-Rate, Retry-Rate überwachen.
- Klare SLAs für Processing-Latenz definieren.

Queues sind ein grundlegender Baustein für skalierbare und resiliente PHP-Systeme mit asynchronen Workloads.

</details>

<details>
<summary>57. Was ist eine ereignisgesteuerte Architektur (Event-Driven Architecture) in PHP?</summary>

#### PHP

Eine ereignisgesteuerte Architektur (Event-Driven Architecture, EDA) ist ein Stil, bei dem Systemkomponenten über das Veröffentlichen und Reagieren auf Ereignisse kommunizieren, statt über direkte synchrone Aufrufe.

1. **Grundkonzept**

- Ein Producer emittiert ein Ereignis (zum Beispiel `OrderPlaced`).
- Interessierte Consumer abonnieren es und verarbeiten es unabhängig.
- Der Publisher muss nicht wissen, welche Consumer existieren.

2. **Warum EDA nützlich ist**

- Entkoppelt Module/Services.
- Verbessert die Erweiterbarkeit (neue Consumer können hinzugefügt werden, ohne den Publisher zu ändern).
- Unterstützt asynchrone Verarbeitung und bessere Skalierbarkeit.
- Macht Side Effects als Domain-/Integrationsereignisse explizit.

3. **Typische PHP-Anwendungsfälle**

- Bestellung erstellt -> E-Mail senden, Bestand reservieren, Analytics publizieren.
- Benutzer registriert -> Welcome-Sequenz, CRM-Sync, Audit-Log.
- Zahlung erfolgreich -> Rechnungserstellung, Benachrichtigungen, Fulfillment.

4. **Ereignistypen**

- **Domain Events**: geschäftlich relevante Fakten innerhalb der Domänengrenze.
- **Integration Events**: Ereignisse, die für andere Services/Systeme veröffentlicht werden.

5. **Zustellungsoptionen im PHP-Ökosystem**

- In-Process Event Bus/Dispatcher (Framework-Level-Events).
- Queue-/Broker-basierte Zustellung (RabbitMQ/Kafka/Redis Streams/Queues) für asynchrone und serviceübergreifende Verteilung.

6. **Wichtige Designaspekte**

- Idempotente Handler (Ereignisse können mehr als einmal zugestellt werden).
- Ordering-Garantien (abhängig von Transport-/Topic-/Partitionierungsstrategie).
- Retry- und Dead-Letter-Policy bei Fehlern.
- Schema-/Versionsentwicklung für Event-Payloads.

7. **Best Practices**

- Unveränderliche, versionierte Event-Payloads verwenden.
- Handler fokussiert und unabhängig halten.
- Events als Fakten behandeln (Benennung in der Vergangenheit: `UserRegistered`).
- Observability ergänzen: Correlation IDs, Tracing, Processing-Lag-Metriken.

EDA in PHP hilft dabei, modulare, skalierbare Systeme zu bauen, in denen sich Workflows ohne enge Kopplung zwischen Komponenten weiterentwickeln können.

</details>

<details>
<summary>58. Was sind WebSockets und wann sollte man sie verwenden?</summary>

#### PHP

WebSockets sind ein Protokoll, das eine persistente, bidirektionale Verbindung zwischen Client und Server herstellt und damit Echtzeit-Datenaustausch ohne wiederholtes HTTP-Polling ermöglicht.

1. **Wie sich WebSockets von HTTP unterscheiden**

- HTTP: Request/Response, meist kurzlebig und vom Client initiiert.
- WebSocket: eine langlebige Verbindung, bei der beide Seiten jederzeit Nachrichten senden können.

2. **Wann WebSockets sinnvoll sind**

- Echtzeit-Chat und Messaging.
- Live-Dashboards/Monitoring-Updates.
- Kollaborative Bearbeitung und Presence-Indikatoren.
- Trading-/Markt-Feeds, Gaming-Events, Benachrichtigungen.

3. **Warum man WebSockets nicht überall einsetzen sollte**

- Erhöht die operative Komplexität (Verbindungszustand, Skalierung, Routing).
- Für einfache CRUD-Seiten mit seltenen Updates nicht notwendig.
- In manchen Fällen sind SSE oder Short Polling einfacher und ausreichend.

4. **Architekturüberlegungen in PHP**

- Das klassische PHP-FPM-Request-Modell ist für langlebige Verbindungen nicht ideal.
- Gängige Ansätze:
  dedizierte WebSocket-Server (Ratchet/Swoole/RoadRunner),
  separater Echtzeit-Service + PHP-Backend-Integration über Redis/Message-Broker.

5. **Skalierungsaspekte**

- Connection-Fan-out und Broadcast-Effizienz.
- Sticky Sessions vs. gemeinsame Pub/Sub-Backplane.
- Horizontale Skalierung mit Messaging-Layern wie Redis/Kafka/NATS.

6. **Sicherheit und Zuverlässigkeit**

- WebSocket-Handshake/Session authentifizieren.
- Message-Schema validieren und Autorisierung pro Channel/Topic erzwingen.
- Rate Limits und Schutz vor Missbrauch anwenden.
- Reconnects, Heartbeats und Backpressure behandeln.

7. **Faustregel**

- WebSockets nutzen, wenn Server-Push mit niedriger Latenz eine Kernanforderung des Produkts ist.
- Einfachere HTTP-basierte Ansätze bevorzugen, wenn Near-Real-Time ausreicht.

WebSockets sind im PHP-Ökosystem ein starkes Echtzeit-Tool, wenn sie mit dem richtigen Runtime- und Skalierungsmodell kombiniert werden.

</details>

<details>
<summary>59. Wie baut man REST-APIs in PHP?</summary>

#### PHP

REST-APIs in PHP zu bauen bedeutet, Ressourcen über HTTP bereitzustellen: mit klaren Routen, Standardmethoden, vorhersehbaren Statuscodes und konsistenten JSON-Verträgen.

1. **Zentrale REST-Prinzipien**

- Ressourcenorientierte Endpunkte (`/users`, `/orders/{id}`).
- Korrekte HTTP-Methoden:
  `GET`, `POST`, `PUT/PATCH`, `DELETE`.
- Zustandslose Requests.
- Konsistentes Repräsentationsformat (meist JSON).

2. **Typische API-Schichten in PHP**

- Route-/Controller-Schicht (HTTP In/Out).
- Validation-/Auth-/Middleware-Schicht.
- Service-/Use-Case-Schicht (Business-Logik).
- Repository-/Daten-Schicht (Persistenz).

3. **Wichtige Designgrundlagen**

- Versionierungsstrategie (`/api/v1/...` oder header-basiert).
- Standardisierte Response-Hülle und Fehlerformat.
- Konventionen für Pagination/Filtering/Sorting.
- Idempotenz für relevante Schreiboperationen.

4. **HTTP-Korrektheit**

- Aussagekräftige Statuscodes zurückgeben (`200`, `201`, `204`, `400`, `401`, `403`, `404`, `422`, `500`).
- `Content-Type: application/json` setzen.
- Caching-Header einsetzen, wo sinnvoll.

5. **Security-Baseline**

- Authentifizierung (Token/JWT/Session je nach Kontext).
- Autorisierungsprüfungen pro Ressource/Aktion.
- Input-Validierung und Output-Encoding.
- Rate Limiting und Schutz vor Missbrauch.
- CSRF-Schutz bei cookie-basierten APIs.

6. **Betriebliche Qualität**

- Strukturiertes Logging + Request-Correlation-IDs.
- Zentrale Exception-Behandlung.
- OpenAPI/Swagger-Dokumentation.
- Contract-/Integrationstests für kritische Endpunkte.

7. **Beispiel für Endpoint-Form**

- `POST /api/v1/orders`
- Payload validieren -> Use Case ausführen -> `201 Created` mit Resource-Body/Location zurückgeben.

8. **Praktische Leitlinie**

- Controller schlank halten.
- Business-Logik aus der HTTP-Schicht heraushalten.
- API-Verträge explizit und stabil machen.

Eine gute PHP-REST-API besteht nicht nur aus Routen, sondern aus konsistenten Verträgen, sicherem Verhalten und betrieblicher Zuverlässigkeit.

</details>

<details>
<summary>60. Was ist GraphQL und wie wird es in PHP verwendet?</summary>

#### PHP

GraphQL ist eine API-Query-Sprache und Runtime, bei der Clients aus einem typisierten Schema genau die Felder anfordern, die sie benötigen, statt feste REST-Payloads zu konsumieren.

1. **Zentrale GraphQL-Konzepte**

- **Schema**: stark typisierter Vertrag (Typen, Felder, Argumente).
- **Queries**: Leseoperationen.
- **Mutations**: Schreiboperationen.
- **Resolvers**: PHP-Funktionen/-Methoden, die Felddaten laden/berechnen.

2. **Warum Teams GraphQL nutzen**

- Vermeidet Over-Fetching/Under-Fetching, wie es bei REST oft vorkommt.
- Ein einzelner Endpoint für flexible Datenabfragen.
- Höhere Frontend-Geschwindigkeit bei komplexen UI-Datenanforderungen.
- Starke Introspection- und Tooling-Unterstützung.

3. **Wie es in PHP eingesetzt wird**

- GraphQL-Schema in Code/SDL definieren.
- Resolver implementieren, die Services/Repositories aufrufen.
- Query gegen das Schema ausführen und JSON-Response zurückgeben.
- Auth, Validierung, Komplexitätslimits und Caching in die Execution-Schicht integrieren.

4. **Typische PHP-Stack-Optionen**

- `webonyx/graphql-php` (Kernimplementierung von GraphQL)
- Framework-Integrationen/Adapter für Laravel-/Symfony-Ökosysteme

5. **Trade-offs**

- Für einfache APIs komplexer als grundlegendes REST.
- Erfordert strikte Controls für Query-Tiefe/-Komplexität, um teure Abfragen zu vermeiden.
- Caching-Strategie kann schwieriger sein als bei REST-Endpoint-Caching.
- Schema-Governance/Versionierungsdisziplin ist essenziell.

6. **Best Practices**

- Resolver schlank halten; an Application Services delegieren.
- DataLoader-Pattern nutzen, um N+1-Backend-Calls zu vermeiden.
- Auth pro Feld/Ressource erzwingen, wo nötig.
- Query-Tiefe/-Komplexität begrenzen und schwere Operationen überwachen.
- Schema-Dokumentation veröffentlichen und Schema-Änderungen als Verträge behandeln.

GraphQL in PHP ist besonders effektiv für datenreiche Produkte mit komplexen Client-Anforderungen, wenn das Team Query-Komplexität und Schema-Governance sauber steuert.

</details>

<details>
<summary>61. Was ist API-Authentifizierung (JWT, OAuth)?</summary>

#### PHP

API-Authentifizierung verifiziert, wer Ihre API aufruft und mit welchen Berechtigungen. Zwei häufige Ansätze sind JWT-basierte Token-Authentifizierung und OAuth 2.0 / OpenID Connect Flows.

1. **JWT-basierte Authentifizierung**

- Nach erfolgreichem Login stellt der Server ein signiertes Token (JWT) aus.
- Der Client sendet das Token bei jedem Request mit (meist `Authorization: Bearer ...`).
- Die API validiert Signatur, Ablaufzeit und Claims.

Typische JWT-Claims:
- `sub` (Subject/User-ID)
- `exp` (Ablaufzeit)
- `iss`/`aud` (Issuer/Audience)
- optionale Rollen/Scopes

2. **OAuth 2.0 (Autorisierungs-Framework)**

- Entwickelt für delegierten Zugriff und Third-Party-Autorisierung.
- Zugriff wird über Scopes und Token-Laufzeiten gewährt.
- Häufige Flows: Authorization Code (+ PKCE), Client Credentials.

3. **OpenID Connect (OIDC)**

- Identitätsschicht auf OAuth 2.0.
- Ergänzt ID-Token und standardisierte User-Identity-Claims.

4. **JWT vs. OAuth (praktische Unterscheidung)**

- JWT ist ein Token-Format/-Mechanismus.
- OAuth ist ein Autorisierungsprotokoll.
- OAuth-Tokens können JWT oder opaque sein.

5. **Security Best Practices**

- Nur HTTPS verwenden.
- Access Tokens kurzlebig halten; Refresh Tokens sicher rotieren.
- Bei jedem Request Signatur, Issuer, Audience und Ablaufzeit validieren.
- Tokens clientseitig sicher speichern (unsichere Storage-Muster vermeiden).
- Bei Bedarf Revocation-/Introspection-Strategie umsetzen.

6. **PHP-Implementierungsleitlinien**

- Bewährte Libraries für JWT/OAuth/OIDC-Validierung nutzen.
- Authentifizierungs-Middleware zentralisieren.
- Authentifizierung (wer) von Autorisierung (was erlaubt) trennen.
- Berechtigungen als Rollen/Scopes/Policies modellieren und auf Ressourcenebene prüfen.

Starke API-Authentifizierung in PHP basiert auf korrekter Protokollumsetzung, sauberem Token-Lifecycle-Management und strikter Validierung auf jedem geschützten Endpoint.

</details>

<details>
<summary>62. Was sind Rate Limiting und API-Sicherheit?</summary>

#### PHP

Rate Limiting ist ein Kontrollmechanismus, der einschränkt, wie viele Requests ein Client in einem bestimmten Zeitfenster senden darf. Es ist ein zentraler Teil umfassender API-Sicherheit.

1. **Warum Rate Limiting nötig ist**

- Missbrauch und Brute-Force-Angriffe verhindern.
- Backend-Ressourcen vor Überlastung schützen.
- Faire Nutzung über Clients/Tenants hinweg sicherstellen.
- Auswirkungen fehlerhafter oder böswilliger Integrationen reduzieren.

2. **Häufige Rate-Limiting-Strategien**

- Fixed Window (einfache Counter pro Intervall).
- Sliding Window (genauere Verteilung).
- Token Bucket / Leaky Bucket (burst-freundlich bei stabilen Limits).

3. **Wo Limits angewendet werden**

- Pro IP-Adresse
- Pro API-Key/Client-ID
- Pro User/Account/Tenant
- Pro Endpoint-Sensitivität (strenger für Auth-Endpunkte)

4. **Typische Umsetzung in PHP-Stacks**

- Middleware-Level-Checks mit Redis/In-Memory-Countern.
- Durchsetzung über Reverse Proxy/API Gateway (Nginx, Cloud API Gateway).
- `429 Too Many Requests` mit Retry-Headern zurückgeben.

5. **API-Sicherheits-Baseline (über Rate Limits hinaus)**

- Starke Authentifizierung (JWT/OAuth/OIDC).
- Autorisierungsprüfungen pro Ressource/Aktion.
- Input-Validierung und Output-Encoding.
- HTTPS überall + sichere Header.
- Request-Größen-/Zeitlimits und Timeout-Kontrolle.
- Audit-Logging, Anomalieerkennung und Alerting.

6. **Best Practices**

- Mehrschichtige Kontrollen nutzen: Gateway + App-Middleware.
- Unterschiedliche Quotas je nach Plan/Vertrauensniveau anwenden.
- Burst-Handling und Graceful Degradation ergänzen.
- Login-/Token-Endpunkte mit strengeren Regeln und Lockouts schützen.
- Limit-Treffer, geblockte Requests und Angriffsmuster überwachen.

Rate Limiting ist eine Säule der API-Sicherheit; echter Schutz entsteht durch die Kombination mit Authentifizierung, Autorisierung, Validierung und Observability.

</details>
