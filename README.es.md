**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  PHP <img src="./assets/php.svg" width="40" height="40" alt="PHP logo"/>
</h1>

<h2>Las preguntas y respuestas de entrevista de PHP más populares</h2>

<details>
<summary>1. ¿Qué es PHP y qué problemas resuelve en el desarrollo backend moderno?</summary>

#### PHP

PHP es un lenguaje de programación del lado del servidor, diseñado principalmente para el desarrollo web. En el desarrollo backend moderno, PHP resuelve varios problemas prácticos:

1. **Desarrollo rápido de backends HTTP:** PHP facilita crear APIs, aplicaciones web y páginas renderizadas en servidor con rapidez.

2. **Procesamiento de solicitudes y lógica de negocio:** Maneja solicitudes HTTP entrantes, valida datos, ejecuta reglas de negocio y devuelve respuestas.

3. **Integración con bases de datos:** PHP tiene herramientas maduras para trabajar con bases de datos (MySQL, PostgreSQL, SQLite) mediante PDO y ORMs.

4. **Flujos de sesión y autenticación:** Soporta sesiones de usuario, sistemas de inicio de sesión, manejo de cookies y control de acceso.

5. **Ecosistema para aplicaciones en producción:** Frameworks como Laravel y Symfony ofrecen enrutamiento, inyección de dependencias, colas, eventos e infraestructura de pruebas.

6. **Procesamiento en segundo plano:** PHP puede ejecutar trabajos asíncronos mediante colas (correos, reportes, notificaciones, importaciones) fuera del flujo solicitud-respuesta.

7. **Escalabilidad en sistemas reales:** Con OPcache, capas de caché (Redis), contenedores y escalado horizontal, PHP soporta sistemas de alta carga.

8. **Integración con servicios externos:** PHP se usa ampliamente con pasarelas de pago, brokers de mensajería, APIs de terceros y servicios en la nube.

En resumen, PHP cubre todo el ciclo backend: recibir solicitudes, procesar datos, interactuar con almacenamiento y entregar servicios web seguros y mantenibles.

</details>

<details>
<summary>2. ¿Cuáles son las diferencias clave entre PHP y JavaScript (runtime, modelo de ejecución)?</summary>

#### PHP

PHP y JavaScript se usan ampliamente en desarrollo web, pero difieren de forma importante en el modelo de runtime, el flujo de ejecución y el comportamiento típico en backend.

1. **Entorno de runtime principal:**
   PHP se ejecuta en el servidor (PHP-FPM, CLI, Swoole/RoadRunner), mientras que JavaScript se ejecuta en el navegador y en el servidor mediante Node.js/Deno/Bun.

2. **Modelo de ejecución (clásico):**
   El PHP tradicional sigue request-por-proceso/request-por-worker: cada solicitud HTTP empieza, se ejecuta y termina con estado aislado.
   JavaScript (Node.js) normalmente se ejecuta como un proceso de larga vida con estado compartido en memoria.

3. **Modelo de concurrencia:**
   La concurrencia en PHP suele lograrse con múltiples workers/procesos que manejan solicitudes en paralelo.
   Los runtimes de servidor en JavaScript usan un event loop con I/O asíncrono y operaciones no bloqueantes en un solo proceso (más threads/procesos de workers para escalar cuando hace falta).

4. **Ciclo de vida del estado:**
   En PHP clásico, el estado en memoria no persiste entre solicitudes, por eso el estado persistente suele vivir en Redis/BD/caché.
   En Node.js, la memoria del proceso puede persistir entre solicitudes, lo que es conveniente, pero exige una gestión cuidadosa del estado.

5. **Rol web típico:**
   PHP ha sido tradicionalmente backend-first (SSR, APIs, lógica de negocio).
   JavaScript es full-stack por naturaleza: lenguaje de UI frontend más opción de backend.

6. **Enfoque del ecosistema:**
   El ecosistema PHP enfatiza frameworks backend (Laravel, Symfony), plantillas en servidor y backends web empresariales.
   El ecosistema JavaScript enfatiza fuertemente frameworks frontend junto con tooling universal/full-stack.

7. **Perfil operativo:**
   PHP suele desplegarse detrás de Nginx/Apache con pools de PHP-FPM.
   Los backends JavaScript suelen desplegarse como procesos de aplicación de larga vida detrás de reverse proxies.

En la práctica, PHP suele elegirse por su aislamiento predecible por solicitud y frameworks backend maduros, mientras que JavaScript suele elegirse cuando los equipos quieren un solo lenguaje en frontend y backend con desarrollo de servidor asíncrono por defecto.

</details>

<details>
<summary>3. ¿Cuáles son las principales características introducidas en PHP 8.x (8.1–8.5)?</summary>

#### PHP

PHP 8.1–8.5 introdujo mejoras importantes del lenguaje y del runtime. Los puntos más relevantes por versión:

1. **PHP 8.1 (publicado el 25 de noviembre de 2021):**
   Enums, propiedades readonly, fibers, sintaxis de callable de primera clase, tipos de intersección y tipo de retorno `never`.

2. **PHP 8.2 (publicado el 8 de diciembre de 2022):**
   Clases readonly, tipos DNF, tipos independientes `null`/`false`/`true`, nueva extensión `Random` y deprecación de propiedades dinámicas.

3. **PHP 8.3 (publicado el 23 de noviembre de 2023):**
   Constantes de clase tipadas, atributo `#[\Override]`, acceso dinámico a constantes de clase (`Class::{$name}`) y mejoras en readonly/clonado.

4. **PHP 8.4 (publicado el 21 de noviembre de 2024):**
   Property hooks, visibilidad asimétrica (estilo `public private(set)`), atributo `#[\Deprecated]`, API DOM actualizada y soporte para objetos perezosos (lazy objects).

5. **PHP 8.5 (publicado el 20 de noviembre de 2025):**
   Operador pipe (`|>`), extensión URI, actualizaciones clone-with mediante `clone(...)`, `#[\NoDiscard]`, closures en expresiones constantes y mejoras adicionales de API/runtime.

#### Por qué importa

- **Mejor seguridad de tipos:** tipado más fuerte, contratos más seguros y menos sorpresas en runtime.
- **Modelado de dominio más limpio:** enums, construcciones readonly y semántica moderna de propiedades.
- **Código más expresivo:** operador pipe, atributos y mejor soporte para callables.
- **Rendimiento y mantenibilidad:** evolución continua del motor, tooling y biblioteca estándar.

En resumen, PHP 8.x modernizó significativamente el lenguaje y facilitó construir y mantener arquitecturas backend modernas.

</details>

<details>
<summary>4. ¿Qué son los enums, los atributos y las propiedades readonly en PHP?</summary>

#### PHP

Los enums, los atributos y las propiedades readonly son características modernas del lenguaje PHP que mejoran la corrección, la legibilidad y la mantenibilidad.

1. **Enums**

- Los enums definen un conjunto fijo de valores permitidos como un tipo real.
- Evitan estados inválidos de string/int y hacen más seguro el modelado del dominio.
- PHP soporta:
  enums respaldados (`enum Status: string { ... }`) y enums unitarios (`enum Role { ... }`).

```php
enum OrderStatus: string
{
    case Draft = 'draft';
    case Paid = 'paid';
    case Shipped = 'shipped';
}
```

2. **Atributos**

- Los atributos son metadatos nativos (`#[...]`) adjuntos a clases, métodos, propiedades, parámetros y más.
- Sustituyen muchos casos de anotaciones en docblocks con metadatos estructurados y legibles por máquina.
- Casos de uso comunes: enrutamiento, validación, inyección de dependencias, reglas de serialización, marcadores de deprecación.

```php
#[Deprecated(reason: 'Use NewService instead')]
class LegacyService {}
```

3. **Propiedades readonly**

- Una propiedad `readonly` solo puede escribirse una vez (normalmente en el constructor).
- Después de la inicialización, su mutación está prohibida.
- Esto es útil para DTOs inmutables, value objects y un diseño de objetos más seguro.

```php
final class UserDto
{
    public function __construct(
        public readonly int $id,
        public readonly string $email,
    ) {}
}
```

#### Por qué importan juntas

- **Enums** protegen los estados permitidos.
- **Atributos** proporcionan metadatos explícitos para frameworks y herramientas.
- **Propiedades readonly** refuerzan la inmutabilidad de datos críticos.

Juntas, estas características reducen errores, hacen las APIs más claras y mejoran la calidad del análisis estático en codebases PHP modernas.

</details>

<details>
<summary>5. ¿Qué es el tipado estricto en PHP y por qué es importante?</summary>

#### PHP

El tipado estricto en PHP se habilita por archivo con:

```php
declare(strict_types=1);
```

Cuando el tipado estricto está habilitado, las declaraciones de tipos escalares se aplican con más rigor para argumentos y valores de retorno de funciones.

1. **Sin tipado estricto (`strict_types=0`, por defecto):**
   PHP puede convertir valores escalares (por ejemplo, `'10'` a `10`) cuando es posible.

2. **Con tipado estricto (`strict_types=1`):**
   PHP lanza un `TypeError` en lugar de convertir silenciosamente valores escalares incompatibles.

```php
declare(strict_types=1);

function add(int $a, int $b): int
{
    return $a + $b;
}

add('2', 3); // TypeError en modo estricto
```

#### Por qué es importante

- **Detección temprana de errores:** las incompatibilidades de tipos fallan de inmediato.
- **Refactorización más segura:** contratos más claros reducen rupturas ocultas.
- **Comportamiento más predecible:** menos “magia” de conversiones implícitas.
- **Mejor análisis estático:** herramientas como PHPStan/Psalm se vuelven más efectivas.
- **Límites de API más limpios:** las firmas de funciones se tratan como contratos estrictos.

#### Recomendación práctica

Usa `declare(strict_types=1);` en todos los archivos PHP nuevos y combínalo con type hints explícitos, DTOs/value objects y análisis estático para lograr fiabilidad de nivel producción.

</details>

<details>
<summary>6. ¿Qué son los tipos unión y de intersección?</summary>

#### PHP

Los tipos unión y de intersección en PHP son herramientas para expresar contratos de tipos más estrictos y explícitos.

1. **Tipos unión (`A|B`)**

- Un valor puede ser de **uno de varios tipos permitidos**.
- Es útil cuando un argumento o valor de retorno puede variar legítimamente.

```php
function formatId(int|string $id): string
{
    return (string) $id;
}
```

2. **Tipos de intersección (`A&B`)**

- Un valor debe cumplir **todos los tipos listados al mismo tiempo**.
- Se usa comúnmente con interfaces para exigir múltiples capacidades.

```php
interface Cacheable {}
interface Jsonable { public function toJson(): string; }

function store(Cacheable&Jsonable $entity): void
{
    // $entity debe implementar ambas interfaces
}
```

3. **Diferencia clave**

- `A|B` significa **A o B**.
- `A&B` significa **A y B a la vez**.

4. **Por qué importan**

- Mejores contratos de API y código que se documenta solo.
- Menos errores de runtime por formas inválidas de objetos/valores.
- Análisis estático más fuerte y refactorización más segura.

5. **Guía práctica**

- Usa tipos unión para límites de entrada flexibles.
- Usa tipos de intersección para diseño basado en capacidades (especialmente con interfaces).
- Prefiere tipos específicos sobre `mixed` cuando sea posible.

</details>

<details>
<summary>7. ¿Qué es el operador nullsafe y cuándo lo usarías?</summary>

#### PHP

El operador nullsafe en PHP es `?->`. Permite acceso seguro a métodos/propiedades en objetos que pueden ser `null`.

1. **Qué hace**

- Si el lado izquierdo es un objeto, el acceso continúa normalmente.
- Si el lado izquierdo es `null`, la evaluación se detiene y devuelve `null` en lugar de lanzar un error.

```php
$country = $user?->getProfile()?->getAddress()?->country;
```

2. **Por qué es útil**

- Evita comprobaciones anidadas de null demasiado verbosas.
- Reduce boilerplate en cadenas de objetos opcionales.
- Hace más clara la intención cuando los valores son nullable de forma legítima.

3. **Casos de uso típicos**

- Estructuras API/DTO con campos anidados opcionales.
- Relaciones ORM que pueden no existir.
- Objetos de contexto de request donde algunas partes son opcionales.

4. **Equivalente sin nullsafe (más verboso)**

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

5. **Notas importantes**

- `?->` funciona solo para acceso a objetos (métodos/propiedades), no para índices de arrays.
- Hace short-circuit de izquierda a derecha.
- Si la cadena termina en `null`, el resultado final es `null`.

Usa el operador nullsafe cuando `null` es un estado esperado y quieres recorrer grafos de objetos de forma concisa y segura.

</details>

<details>
<summary>8. ¿Qué son los property hooks (PHP 8.4+)?</summary>

#### PHP

Los property hooks (introducidos en PHP 8.4) te permiten adjuntar lógica directamente a las operaciones de lectura/escritura de propiedades usando hooks `get` y `set`.

1. **Qué problema resuelven**

- Reducen el boilerplate de métodos getter/setter.
- Mantienen la validación/transformación cerca de la definición de la propiedad.
- Permiten propiedades calculadas (virtuales) con una sintaxis más clara.

2. **Idea básica**

```php
class User
{
    public string $name {
        set => trim($value);
    }
}
```

Cualquier asignación a `$user->name` pasa por el hook `set`.

3. **Ejemplo de propiedad calculada**

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

`$fullName` se deriva de otros campos y no necesita métodos getter manuales.

4. **Ejemplo de validación/transformación**

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

5. **Cuándo usarlos**

- Entidades de dominio con invariantes estrictos.
- Objetos tipo DTO/value object que necesitan escrituras controladas.
- Casos donde los métodos get/set clásicos eran mayormente boilerplate.

Los property hooks hacen los modelos de objetos más expresivos y reducen código repetitivo de acceso, manteniendo validación fuerte y encapsulación.

</details>

<details>
<summary>9. ¿Qué es el operador pipe (PHP 8.5) y cuándo es útil?</summary>

#### PHP

El operador pipe en PHP 8.5 es `|>`. Pasa el resultado de la expresión de la izquierda al callable de la derecha, permitiendo una transformación de datos legible de izquierda a derecha.

1. **Idea principal**

En lugar de llamadas profundamente anidadas, puedes construir un pipeline de procesamiento lineal.

```php
$result = " Hello World "
    |> trim(...)
    |> strtolower(...)
    |> (fn(string $s) => str_replace(' ', '-', $s));
```

2. **Por qué es útil**

- Mejora la legibilidad de transformaciones de varios pasos.
- Reduce variables temporales.
- Evita llamadas a funciones anidadas de adentro hacia afuera.
- Facilita refactorizar cadenas de transformación.

3. **Antes vs después**

Sin pipe:

```php
$slug = strtolower(str_replace(' ', '-', trim($title)));
```

Con pipe:

```php
$slug = $title
    |> trim(...)
    |> (fn(string $s) => str_replace(' ', '-', $s))
    |> strtolower(...);
```

4. **Buenos casos de uso**

- Pipelines de normalización de strings/datos.
- Flujos de mapeo/transformación de DTO.
- Procesamiento de datos en estilo funcional dentro de servicios.

5. **Nota práctica**

Usa el operador pipe para transformaciones secuenciales claras. Para lógica de ramificación compleja, las variables intermedias tradicionales pueden seguir siendo más fáciles de entender.

</details>

<details>
<summary>10. ¿Qué son las superglobales en PHP y cómo se usan?</summary>

#### PHP

Las superglobales en PHP son arrays asociativos integrados disponibles en todos los ámbitos (funciones, métodos, ámbito global) sin usar `global`.

1. **Superglobales principales**

- `$_GET` - parámetros de query string desde la URL.
- `$_POST` - parámetros de formulario/cuerpo en solicitudes POST.
- `$_REQUEST` - datos de request combinados (depende de `request_order`/`variables_order`).
- `$_SERVER` - metadatos del servidor y de la solicitud (headers, método, URI, host, etc.).
- `$_COOKIE` - cookies del cliente enviadas con la solicitud.
- `$_SESSION` - datos de sesión almacenados entre solicitudes.
- `$_FILES` - metadatos de archivos subidos.
- `$_ENV` - variables de entorno.
- `$GLOBALS` - referencia a todas las variables globales.

2. **Ejemplos típicos de uso**

```php
$page = $_GET['page'] ?? 'home';
$method = $_SERVER['REQUEST_METHOD'] ?? 'GET';
$token = $_COOKIE['csrf_token'] ?? null;
```

3. **Por qué importan**

- Son la interfaz principal entre el código PHP y el entorno HTTP/runtime.
- Proporcionan entrada de solicitud, contexto y estado persistente del usuario/sesión.

4. **Prácticas de seguridad y fiabilidad**

- Nunca confíes directamente en entradas de superglobales.
- Siempre valida y sanitiza datos externos.
- Usa comprobaciones estrictas y valores por defecto (`??`, `filter_input`, validadores).
- Evita depender de `$_REQUEST` en código crítico porque la precedencia de origen puede variar.
- Escapa la salida para prevenir XSS y usa prepared statements para prevenir inyección SQL.

Las superglobales son fundamentales para el desarrollo web en PHP, pero deben tratarse como límites de entrada no confiables.

</details>

<details>
<summary>11. ¿Cuál es la diferencia entre las solicitudes GET y POST?</summary>

#### PHP

GET y POST son métodos HTTP con semánticas y patrones de uso diferentes.

1. **Propósito**

- **GET** se usa para recuperar datos (operaciones de solo lectura).
- **POST** se usa para enviar datos que pueden cambiar el estado del servidor (acciones de creación/procesamiento).

2. **Dónde se envían los datos**

- **GET** envía parámetros en el query string de la URL (`/users?page=2`).
- **POST** envía datos en el cuerpo de la solicitud.

3. **Visibilidad y registro**

- Los parámetros de **GET** son visibles en la URL, el historial del navegador, logs y referrers.
- El cuerpo de **POST** no se muestra en la URL, pero igualmente debe tratarse como entrada no confiable.

4. **Caché y marcadores**

- Las solicitudes **GET** son amigables con la caché y se pueden guardar en marcadores.
- Las solicitudes **POST** por lo general no son cacheables por defecto y no se pueden guardar en marcadores con payload.

5. **Idempotencia y seguridad (semántica HTTP)**

- **GET** debe ser seguro y no cambiar el estado del servidor.
- **POST** no garantiza idempotencia y normalmente produce efectos secundarios.

6. **Acceso en PHP**

```php
$search = $_GET['q'] ?? null;      // desde query string
$email  = $_POST['email'] ?? null; // desde el cuerpo de la solicitud
```

7. **Cuándo usar**

- Usa **GET** para filtrar, buscar, paginar y leer recursos.
- Usa **POST** para envíos de formularios, acciones de autenticación y crear/actualizar datos del lado del servidor (o usa PUT/PATCH donde sea apropiado en APIs).

Regla clave: usa GET para operaciones de lectura y POST para operaciones que cambian estado, validando toda entrada en ambos casos.

</details>

<details>
<summary>12. ¿Cómo maneja PHP las solicitudes y respuestas HTTP?</summary>

#### PHP

En una configuración web típica, PHP maneja HTTP mediante un ciclo de solicitud-respuesta coordinado por un servidor web (Nginx/Apache) y un runtime de PHP (comúnmente PHP-FPM).

1. **Llega la solicitud**

- El cliente envía una solicitud HTTP (método, URI, headers, cuerpo).
- El servidor web la recibe y enruta las solicitudes dinámicas hacia PHP.

2. **El runtime de PHP ejecuta el script**

- PHP inicializa el contexto de la solicitud y completa superglobales (`$_SERVER`, `$_GET`, `$_POST`, `$_COOKIE`, `$_FILES`).
- Se ejecuta el bootstrap de la aplicación (autoload, config, contenedor DI, kernel del framework).

3. **La aplicación maneja la lógica de negocio**

- El router resuelve el controlador/handler.
- Se ejecutan middleware/guards/validación.
- Servicios/repositorios acceden a base de datos, caché o APIs externas.

4. **Se construye la respuesta**

- La app establece código de estado, headers y cuerpo (HTML/JSON/archivo/stream).
- En PHP puro, normalmente se hace con `header()`, `http_response_code()` y salida.
- En frameworks, se retorna un objeto Response y luego se emite.

```php
http_response_code(200);
header('Content-Type: application/json; charset=utf-8');
echo json_encode(['ok' => true], JSON_THROW_ON_ERROR);
```

5. **Se envía la respuesta**

- PHP envía la salida al servidor web.
- El servidor web envía la respuesta HTTP final al cliente.
- En PHP-FPM clásico, el estado de la solicitud termina después de la respuesta (se usa almacenamiento externo compartido para persistencia).

6. **Manejo de errores**

- Las excepciones se convierten en respuestas HTTP de error (por ejemplo, `404`, `422`, `500`) mediante handlers globales/del framework.
- Logs/monitoring capturan fallos para diagnóstico.

El modelo de PHP es directo: recibir el contexto de la solicitud, ejecutar código de la aplicación, producir una respuesta HTTP y finalizar la solicitud de forma limpia.

</details>

<details>
<summary>13. ¿Cómo funcionan las sesiones y cuáles son las prácticas seguras para sesiones?</summary>

#### PHP

Las sesiones de PHP te permiten persistir estado específico del usuario entre solicitudes HTTP sin estado, almacenando datos en el servidor y vinculándolos a un ID de sesión.

1. **Cómo funcionan las sesiones**

- El cliente hace la primera solicitud.
- El servidor crea un ID de sesión (SID).
- El SID se envía al cliente, normalmente mediante cookie (comúnmente `PHPSESSID`).
- En las siguientes solicitudes, el cliente devuelve el SID.
- PHP carga en `$_SESSION` los datos de sesión correspondientes almacenados en servidor.

2. **Uso básico**

```php
session_start();

$_SESSION['user_id'] = 42;
$userId = $_SESSION['user_id'] ?? null;
```

3. **Dónde se almacenan los datos**

- Por defecto: almacenamiento de sesiones en filesystem.
- En producción: con frecuencia Redis/base de datos/memcached mediante handlers personalizados para escalabilidad.

4. **Prácticas seguras para sesiones**

- Regenera el ID de sesión después del login/cambio de privilegios:
  `session_regenerate_id(true);`
- Usa flags de cookie:
  `HttpOnly`, `Secure`, `SameSite` (`Lax` o `Strict` cuando sea posible).
- Fuerza HTTPS en aplicaciones autenticadas.
- Configura timeout de sesión y expiración por inactividad.
- Invalida la sesión al cerrar sesión (unset de datos + destroy de sesión + expiración de cookie).
- Vincula sesiones cuidadosamente a señales de contexto (por ejemplo, comprobaciones parciales de IP/UA) para reducir riesgo de secuestro.
- Guarda la mínima cantidad de datos sensibles en sesión; prefiere IDs/referencias en lugar de secretos completos.

5. **Amenazas comunes**

- **Session fixation:** el atacante fuerza un SID conocido antes de la autenticación.
- **Session hijacking:** el atacante reutiliza un SID robado.
- **Robo asistido por XSS:** scripts maliciosos pueden explotar un manejo inseguro de sesiones.

6. **Checklist de hardening**

- `session.use_strict_mode=1`
- `session.cookie_httponly=1`
- `session.cookie_secure=1` (en HTTPS)
- `session.cookie_samesite` correctamente configurado
- Regeneración regular de SID en flujos autenticados

Las sesiones son seguras y efectivas cuando los IDs están protegidos, se rotan adecuadamente y se transportan solo por canales confiables.

</details>

<details>
<summary>14. ¿Cómo se establecen y aseguran las cookies en aplicaciones modernas?</summary>

#### PHP

Las cookies son pequeños datos clave-valor almacenados por el navegador y enviados con las solicitudes coincidentes. En apps modernas, se usan para sesiones, preferencias y flujos de autenticación seguros.

1. **Cómo se establecen cookies en PHP**

Usa `setcookie()` (o helpers de respuesta del framework) antes de que se envíe salida:

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

2. **Cómo se leen cookies**

```php
$token = $_COOKIE['session_token'] ?? null;
```

3. **Atributos de seguridad (críticos)**

- **`Secure`**: la cookie se envía solo por HTTPS.
- **`HttpOnly`**: no es accesible desde JavaScript (`document.cookie`), reduce el riesgo de robo por XSS.
- **`SameSite`**:
  `Strict` (protección CSRF fuerte), `Lax` (equilibrado), `None` (requiere `Secure`, para casos cross-site).
- **`Expires/Max-Age`**: limita el tiempo de vida.
- **`Path/Domain`**: limita el alcance de la cookie lo máximo posible.

4. **Buenas prácticas**

- Usa HTTPS en todas partes y establece siempre `Secure` para cookies sensibles.
- Establece `HttpOnly` para cookies de sesión/autenticación.
- Prefiere `SameSite=Lax` o `Strict` salvo que el comportamiento cross-site sea explícitamente necesario.
- Rota tokens de auth/sesión y haz que expiren adecuadamente.
- No almacenes datos sensibles en texto plano en cookies.
- Considera firmar o cifrar el payload de cookies si almacenas estado del lado del cliente.

5. **Errores comunes**

- Falta de `HttpOnly` o `Secure`.
- `domain`/`path` demasiado amplios.
- Expiración muy larga en cookies de autenticación.
- Confiar en valores de cookies sin verificación del lado del servidor.

La seguridad moderna de cookies se basa en alcance estricto, transporte seguro, valores por defecto seguros y validación en servidor de todos los valores proporcionados por el cliente.

</details>

<details>
<summary>15. ¿Qué es CSRF y cómo se previene?</summary>

#### PHP

CSRF (Cross-Site Request Forgery) es un ataque donde el navegador de la víctima es engañado para enviar una solicitud autenticada a tu aplicación sin la intención del usuario.

1. **Cómo funciona CSRF**

- El usuario está autenticado en `your-app.com`.
- El atacante atrae al usuario a una página maliciosa.
- Esa página dispara una solicitud a `your-app.com` (por ejemplo, cambiar email, transferir fondos).
- El navegador incluye automáticamente cookies/sesión, por lo que la solicitud puede ser aceptada.

2. **Por qué es peligroso**

- El servidor ve una sesión autenticada válida.
- Acciones que cambian estado pueden ejecutarse en nombre de la víctima.

3. **Defensa principal: token CSRF**

- Genera un token aleatorio por sesión/solicitud.
- Inserta el token en formularios o headers de solicitud.
- Verifica el token en servidor antes de procesar acciones que cambian estado.

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

4. **Protecciones adicionales**

- Usa cookies `SameSite` (`Lax`/`Strict`) para reducir el envío de cookies cross-site.
- Valida headers `Origin`/`Referer` en endpoints sensibles (como defensa en profundidad).
- Requiere reautenticación o confirmación adicional para operaciones críticas.
- No uses GET para acciones que cambian estado.

5. **Buena práctica en frameworks**

- Usa middleware CSRF integrado (Laravel/Symfony/etc.) en lugar de lógica custom cuando sea posible.
- Asegura que los tokens se incluyan en todas las solicitudes mutables (POST/PUT/PATCH/DELETE), incluidas llamadas AJAX.

La protección CSRF es obligatoria en flujos de autenticación basados en cookies y debe formar parte del middleware de seguridad por defecto.

</details>

<details>
<summary>16. ¿Qué es XSS y cómo se previene correctamente?</summary>

#### PHP

XSS (Cross-Site Scripting) es una vulnerabilidad en la que datos controlados por un atacante son interpretados por el navegador como script ejecutable en las páginas de tu aplicación.

1. **Tipos principales de XSS**

- **Stored XSS**: el payload malicioso se guarda (DB/comentario/perfil) y se sirve a usuarios más tarde.
- **Reflected XSS**: el payload viene de la entrada de la solicitud y se refleja inmediatamente en la respuesta.
- **DOM-based XSS**: JavaScript del lado cliente escribe datos inseguros en el DOM.

2. **Causa raíz**

- Entrada no confiable llega a contextos HTML/JS/URL/CSS sin codificación de salida correcta.

3. **Defensa principal: escape contextual de salida**

- Escapa datos **en la salida**, según el contexto de renderizado.
- Para contexto de texto HTML en PHP:

```php
echo htmlspecialchars($userInput, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
```

4. **Reglas específicas por contexto**

- Cuerpo HTML: `htmlspecialchars(...)`.
- Atributos HTML: también escapar comillas (`ENT_QUOTES`).
- Contexto JavaScript: codifica con JSON, evita concatenación directa de strings.
- Contexto URL: `rawurlencode()` para valores de parámetros.
- Evita inyectar HTML no confiable directamente.

5. **Protecciones adicionales**

- Usa features de auto-escaping de motores de plantillas/frameworks.
- Sanitiza HTML enriquecido con sanitizadores basados en allowlist (si se requiere entrada HTML).
- Configura una Content Security Policy (CSP) fuerte como defensa en profundidad.
- Evita scripts inline cuando sea posible.
- Valida entrada, pero no trates la validación como sustituto de la codificación de salida.

6. **Errores comunes**

- Escapar entrada una vez y reutilizarla en múltiples contextos.
- Desactivar globalmente el auto-escaping de plantillas.
- Renderizar contenido de usuario sin escape en paneles de admin/herramientas internas.

La prevención de XSS consiste principalmente en codificación contextual estricta en el punto de salida, junto con CSP y patrones de renderizado seguros.

</details>

<details>
<summary>17. ¿Qué es SQL Injection y cómo lo previenen los prepared statements?</summary>

#### PHP

SQL Injection es una vulnerabilidad donde la entrada del atacante cambia la estructura de consultas SQL, permitiendo acceso o manipulación no autorizados de datos.

1. **Cómo ocurre SQL Injection**

Ocurre cuando entrada no confiable se concatena directamente en strings SQL.

```php
// Unsafe example
$sql = "SELECT * FROM users WHERE email = '" . $_POST['email'] . "'";
```

Un atacante puede inyectar fragmentos SQL y alterar la lógica de la consulta.

2. **Impacto**

- Bypass de autenticación
- Filtración/modificación/eliminación de datos
- Escalada de privilegios
- En casos graves, compromiso total de la base de datos

3. **Cómo los prepared statements lo previenen**

Los prepared statements separan:
- **Estructura SQL** (plantilla de consulta)
- **Valores de datos** (parámetros vinculados)

La base de datos trata los valores vinculados como datos, no como código SQL ejecutable.

```php
$pdo = new PDO($dsn, $user, $pass, [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
]);

$stmt = $pdo->prepare('SELECT * FROM users WHERE email = :email');
$stmt->execute(['email' => $_POST['email']]);
$user = $stmt->fetch(PDO::FETCH_ASSOC);
```

4. **Matiz importante**

- Los prepared statements protegen valores, pero no identificadores SQL dinámicos (nombres de tabla/columna).
- Si los identificadores deben ser dinámicos, usa allowlists estrictas.

5. **Buenas prácticas**

- Usa prepared statements de PDO/MySQLi en todas partes para entrada externa.
- Nunca construyas SQL con concatenación de strings para valores proporcionados por el usuario.
- Aplica cuentas de BD con mínimo privilegio.
- Valida entrada y registra actividad sospechosa.
- Mantén actualizado el motor de BD/drivers.

Los prepared statements son la defensa principal y obligatoria contra SQL injection en aplicaciones PHP modernas.

</details>

<details>
<summary>18. ¿Qué es Content Security Policy (CSP)?</summary>

#### PHP

Content Security Policy (CSP) es un mecanismo de seguridad del navegador que restringe qué recursos (scripts, estilos, imágenes, frames, etc.) pueden cargarse y ejecutarse en una página.

1. **Contra qué protege CSP**

- Principalmente reduce el impacto de XSS al bloquear scripts inline/externos no autorizados.
- Ayuda a mitigar la exfiltración de datos mediante cargas de recursos maliciosos.
- Restringe capacidades riesgosas del navegador a orígenes confiables.

2. **Cómo se entrega CSP**

- Normalmente vía header de respuesta HTTP:
  `Content-Security-Policy: ...`
- También puede enviarse primero en modo solo reporte:
  `Content-Security-Policy-Report-Only: ...`

3. **Ejemplo básico**

```php
header("Content-Security-Policy: default-src 'self'; script-src 'self'; object-src 'none'; base-uri 'self'; frame-ancestors 'none'");
```

4. **Directivas importantes**

- `default-src` - política de origen por defecto.
- `script-src` - controla fuentes de JavaScript.
- `style-src` - controla fuentes de CSS.
- `img-src` - controla fuentes de imágenes.
- `connect-src` - controla destinos XHR/fetch/WebSocket.
- `frame-ancestors` - previene clickjacking controlando el embebido.
- `object-src 'none'` - deshabilita contenido legacy de plugins.
- `base-uri` - restringe inyección de etiqueta `<base>`.

5. **Buenas prácticas**

- Empieza con `Report-Only`, recopila violaciones y luego aplica enforcement.
- Prefiere nonces/hashes para scripts inline en lugar de `'unsafe-inline'`.
- Mantén la política estricta y explícita por entorno.
- Combina CSP con escape de salida, protección CSRF y cookies seguras.

6. **CSP no es una bala de plata**

- Es defensa en profundidad, no un reemplazo de codificación segura.
- Aun así debes sanitizar/escapar salida no confiable y evitar patrones DOM inseguros.

CSP fortalece significativamente la postura de seguridad frontend cuando se configura con cuidado y se monitoriza continuamente.

</details>

<details>
<summary>19. ¿Qué es el autoloading y cómo funciona PSR-4?</summary>

#### PHP

Autoloading es un mecanismo que carga automáticamente archivos de clases/interfaces/traits de PHP cuando se usan por primera vez, en lugar de escribir manualmente muchos `require`/`include`.

1. **Por qué se necesita autoloading**

- Elimina includes manuales de archivos.
- Mantiene escalable la estructura del proyecto.
- Hace más fácil gestionar dependencias y módulos.

2. **PSR-4 en resumen**

PSR-4 es el estándar moderno para mapear namespaces a rutas del filesystem.

- El prefijo de namespace se mapea a un directorio base.
- Las partes restantes del namespace se mapean a subdirectorios.
- El nombre de clase se mapea al nombre de archivo (`ClassName.php`).

3. **Ejemplo de mapeo**

Si la config de Composer contiene:

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

Entonces:
- `App\Services\UserService` -> `src/Services/UserService.php`
- `App\Http\Controllers\HomeController` -> `src/Http/Controllers/HomeController.php`

4. **Cómo lo habilita Composer**

- Define `autoload.psr-4` en `composer.json`.
- Ejecuta:

```bash
composer dump-autoload
```

- Incluye una vez el autoloader de Composer (normalmente en el bootstrap de la app):

```php
require __DIR__ . '/vendor/autoload.php';
```

5. **Buenas prácticas**

- Sigue la regla de una clase por archivo.
- Mantén alineados namespace y nombres de directorio.
- Usa un namespace raíz con significado (`App\\`, `Domain\\`, `Company\\Project\\`).
- Regenera archivos de autoload tras cambios de namespace/rutas.

Autoloading con PSR-4 es la base por defecto de la estructura y carga de dependencias en aplicaciones PHP modernas.

</details>

<details>
<summary>20. ¿Qué es Composer y cómo funciona la gestión de dependencias?</summary>

#### PHP

Composer es el gestor de dependencias estándar para PHP. Instala, actualiza y autoloads librerías del proyecto de forma reproducible.

1. **Archivos principales**

- `composer.json` - declara metadatos del proyecto, paquetes requeridos, reglas de autoload, scripts.
- `composer.lock` - fija versiones exactas de paquetes resueltas para el proyecto.
- `vendor/` - dependencias instaladas y autoloader de Composer.

2. **Cómo funciona la gestión de dependencias**

- Declaras restricciones en `composer.json` (por ejemplo, `^11.0`).
- Composer resuelve un grafo de dependencias compatible.
- Las versiones exactas resueltas se escriben en `composer.lock`.
- El equipo/CI instala exactamente las versiones fijadas para builds deterministas.

3. **Flujo básico**

```bash
# Add dependency
composer require monolog/monolog

# Install from lock file
composer install

# Update dependencies (re-resolve constraints)
composer update
```

4. **Restricciones de versión**

- `^1.2` - permite actualizaciones no disruptivas hasta `<2.0.0`.
- `~1.2.3` - permite parches/minor dentro de esa rama.
- Son posibles versiones exactas, pero normalmente son demasiado rígidas para librerías.

5. **Integración de autoload**

Composer genera `vendor/autoload.php` y soporta mapeo de autoload PSR-4 desde `composer.json`.

```php
require __DIR__ . '/vendor/autoload.php';
```

6. **Buenas prácticas**

- Haz commit de `composer.lock` para aplicaciones.
- Usa `composer install` en CI/producción.
- Usa `composer update` de forma intencional y revisa cambios del lock file.
- Prefiere versiones estables de paquetes.
- Audita dependencias regularmente (`composer audit`).

Composer es esencial en PHP moderno porque estandariza la gestión de paquetes, el autoloading y los builds reproducibles entre entornos.

</details>

<details>
<summary>21. ¿Qué son los estándares PSR y por qué son importantes?</summary>

#### PHP

PSR (PHP Standards Recommendations) son estándares de la comunidad publicados por PHP-FIG (PHP Framework Interop Group) para mejorar la interoperabilidad y la consistencia entre librerías y frameworks de PHP.

1. **Qué definen los PSR**

- Convenciones de estilo de código (por ejemplo, PSR-12).
- Convenciones de autoloading (PSR-4).
- Interfaces comunes para mensajes HTTP, middleware, contenedores, logging, caché, etc.

2. **Por qué son importantes**

- **Interoperabilidad:** librerías de distintos proveedores funcionan juntas más fácilmente.
- **Previsibilidad:** interfaces y estructura familiares entre proyectos.
- **Mantenibilidad:** los codebases de equipo son más consistentes y fáciles de revisar.
- **Portabilidad entre frameworks:** menos vendor lock-in cuando la arquitectura usa contratos estándar.

3. **PSR usados con más frecuencia**

- **PSR-1 / PSR-12** - estilo de código básico y estilo extendido.
- **PSR-3** - interfaz de logger (`LoggerInterface`).
- **PSR-4** - estándar de autoloading.
- **PSR-6 / PSR-16** - interfaces de caché.
- **PSR-7** - interfaces de mensajes HTTP (Request/Response/Stream).
- **PSR-11** - interfaz de contenedor.
- **PSR-15** - handlers de solicitudes HTTP de servidor y middleware.
- **PSR-18** - interfaz de cliente HTTP.

4. **Efecto práctico en proyectos reales**

- Puedes intercambiar implementaciones (por ejemplo, logger/cliente/contenedor) sin reescribir lógica de negocio.
- Frameworks y paquetes se integran más rápido mediante interfaces compartidas.
- Las herramientas (linters/analizadores estáticos/adaptadores de framework) se vuelven más fáciles de adoptar.

Los PSR no son solo guías de estilo; son contratos a nivel de arquitectura que hacen que los ecosistemas PHP modernos sean componibles y sostenibles.

</details>

<details>
<summary>22. ¿Qué es PSR-7 (mensajes HTTP)?</summary>

#### PHP

PSR-7 es un estándar que define interfaces para mensajes HTTP en PHP: solicitudes, respuestas, streams y archivos subidos.

1. **Qué estandariza PSR-7**

- `ServerRequestInterface` - solicitud HTTP entrante desde contexto cliente/servidor.
- `RequestInterface` - solicitud saliente genérica.
- `ResponseInterface` - respuesta HTTP (estado, headers, body).
- `StreamInterface` - abstracción del cuerpo del mensaje.
- `UploadedFileInterface` - abstracción de archivo subido.
- `UriInterface` - representación de URI.

2. **Por qué importa**

- Proporciona un contrato común entre frameworks y librerías.
- Habilita pipelines de middleware y componentes HTTP reutilizables.
- Reduce vendor lock-in al programar contra interfaces, no contra clases concretas del framework.

3. **Principio de inmutabilidad**

Los mensajes PSR-7 son inmutables. Métodos como `withHeader()` devuelven una nueva instancia en lugar de modificar el objeto original.

```php
$newResponse = $response
    ->withStatus(201)
    ->withHeader('Content-Type', 'application/json');
```

4. **Uso típico**

- En middleware y handlers (a menudo con PSR-15).
- En frameworks API para parseo de solicitudes y generación de respuestas.
- En clientes/servidores HTTP que intercambian objetos de mensaje estandarizados.

5. **Beneficio práctico**

Un componente escrito para PSR-7 normalmente puede reutilizarse en distintos ecosistemas (Slim, Laminas, bridges de Symfony, Mezzio, etc.) con adaptación mínima.

PSR-7 es la capa central de interoperabilidad para el manejo de mensajes HTTP en aplicaciones PHP modernas.

</details>

<details>
<summary>23. ¿Qué es PSR-11 (contenedor de dependencias)?</summary>

#### PHP

PSR-11 es la interfaz estándar para contenedores de inyección de dependencias en PHP. Define cómo el código de la aplicación puede obtener servicios desde un contenedor de forma agnóstica al framework.

1. **Interfaces principales de PSR-11**

- `Psr\Container\ContainerInterface`
- `Psr\Container\ContainerExceptionInterface`
- `Psr\Container\NotFoundExceptionInterface`

Métodos principales:
- `get(string $id): mixed`
- `has(string $id): bool`

2. **Qué resuelve**

- Estandariza el acceso al contenedor entre librerías/frameworks.
- Permite que componentes dependan de un contrato común en lugar de implementaciones específicas del contenedor.
- Mejora interoperabilidad y portabilidad.

3. **Ejemplo simple de uso**

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

4. **Nota importante de diseño**

PSR-11 define **cómo leer servicios**, no cómo registrarlos/construirlos. Las APIs de registro son específicas de cada contenedor.

5. **Buenas prácticas**

- Prefiere inyección por constructor en el código de aplicación.
- Usa lookup directo del contenedor sobre todo en capas de infraestructura/bootstrap.
- Evita el anti-patrón Service Locator en lógica de dominio/negocio.
- Usa type hints con interfaces en lugar de implementaciones concretas siempre que sea posible.

PSR-11 es un estándar mínimo pero importante que hace consistente el uso de contenedores de dependencias en el ecosistema PHP.

</details>

<details>
<summary>24. ¿Qué es PSR-15 (middleware)?</summary>

#### PHP

PSR-15 es el estándar que define middleware y handlers HTTP del lado servidor en PHP. Funciona junto con las interfaces de mensajes request/response de PSR-7.

1. **Interfaces principales de PSR-15**

- `Psr\Http\Server\MiddlewareInterface`
- `Psr\Http\Server\RequestHandlerInterface`

Contratos de métodos:
- Middleware: `process(ServerRequestInterface $request, RequestHandlerInterface $handler): ResponseInterface`
- Handler: `handle(ServerRequestInterface $request): ResponseInterface`

2. **Cómo funciona el pipeline de middleware**

- La solicitud entra en la cadena de middleware.
- Cada middleware puede:
  validar/modificar la solicitud, cortar el flujo con una respuesta o pasar la solicitud hacia adelante.
- El handler final genera la respuesta.
- La respuesta puede modificarse de regreso a través del stack de middleware.

3. **Responsabilidades típicas de middleware**

- Autenticación/autorización
- CORS
- Logging/tracing
- Rate limiting
- Validación de solicitudes
- Conversión de excepciones a respuesta

4. **Ejemplo simple de middleware**

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

5. **Por qué importa PSR-15**

- Hace que middleware sea reutilizable entre frameworks/ecosistemas.
- Estandariza puntos de extensión del ciclo de vida de la solicitud.
- Fomenta una separación limpia de preocupaciones transversales.

PSR-15 proporciona el contrato de interoperabilidad para pipelines HTTP basados en middleware en aplicaciones PHP modernas.

</details>

<details>
<summary>25. ¿Qué es PSR-18 (cliente HTTP)?</summary>

#### PHP

PSR-18 es la interfaz estándar para clientes HTTP en PHP. Define cómo el código de aplicación envía solicitudes HTTP salientes de forma agnóstica a la implementación.

1. **Contrato principal de PSR-18**

- Interfaz principal: `Psr\Http\Client\ClientInterface`
- Método principal: `sendRequest(RequestInterface $request): ResponseInterface`
- Funciona con objetos request/response de PSR-7.

2. **Qué problema resuelve**

- Desacopla la lógica de negocio de librerías específicas de cliente HTTP.
- Hace las integraciones portables y más fáciles de testear.
- Permite intercambiar implementaciones de cliente sin reescribir código de servicios.

3. **Uso básico**

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

4. **Excepciones**

PSR-18 define interfaces estándar de excepciones para fallos del cliente (errores de solicitud, errores de red/transporte), permitiendo manejo de errores consistente entre implementaciones.

5. **Buenas prácticas**

- Usa type hints con `ClientInterface` en servicios.
- Construye solicitudes con factorías PSR-17.
- Configura timeouts/retries/circuit-breakers en la capa de infraestructura.
- Haz mock de la interfaz del cliente en tests para comportamiento determinista.

PSR-18 estandariza la comunicación HTTP saliente y es una pieza clave de código de integración interoperable y mantenible en apps PHP modernas.

</details>

<details>
<summary>26. ¿Qué es dependency injection e inversion of control?</summary>

#### PHP

Dependency Injection (DI) e Inversion of Control (IoC) son principios de arquitectura para construir código desacoplado y testeable.

1. **Inversion of Control (IoC)**

IoC significa que una clase no crea ni controla directamente sus dependencias; ese control se mueve fuera (a la capa de framework/contenedor/bootstrap).

2. **Dependency Injection (DI)**

DI es una forma concreta de implementar IoC: las dependencias se proporcionan (inyectan) desde fuera en lugar de crearlas con `new` dentro de la clase.

3. **Por qué importa**

- Reduce el acoplamiento entre componentes.
- Mejora la testabilidad (mocking/stubbing sencillo).
- Hace el código más fácil de extender y refactorizar.
- Soporta límites limpios de arquitectura.

4. **Sin DI (fuertemente acoplado)**

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

5. **Con DI (débilmente acoplado)**

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

6. **Estilos comunes de DI**

- Inyección por constructor (preferida).
- Inyección por método.
- Inyección por setter/propiedad (menos preferida para dependencias obligatorias).

7. **Relación con contenedores**

Un contenedor DI automatiza la construcción y el cableado de objetos, pero DI es un principio de diseño independiente de cualquier contenedor específico.

DI + IoC son fundamentales para frameworks PHP modernos y clave para codebases mantenibles y escalables.

</details>

<details>
<summary>27. ¿Qué son los service containers y cómo funcionan?</summary>

#### PHP

Un service container (contenedor DI) es un componente que gestiona la creación de objetos, el cableado de dependencias y el ciclo de vida en una aplicación.

1. **Qué hace un contenedor**

- Almacena definiciones/bindings de servicios.
- Resuelve dependencias automáticamente (a menudo mediante reflection y type hints).
- Construye grafos de objetos (servicio + todas las dependencias anidadas).
- Gestiona tiempos de vida (singleton/scoped/transient según framework).

2. **Por qué es útil**

- Centraliza la configuración de dependencias.
- Elimina wiring manual repetitivo con `new ...`.
- Simplifica el intercambio de implementaciones (interface -> clase concreta).
- Mejora la mantenibilidad en aplicaciones grandes.

3. **Flujo típico**

- Registras bindings:
  `LoggerInterface` -> `MonologLogger`
- Pides al contenedor un servicio:
  `OrderService`
- El contenedor construye `OrderService`, resolviendo recursivamente los argumentos requeridos del constructor.

4. **Ejemplo conceptual**

```php
$container->set(LoggerInterface::class, MonologLogger::class);
$container->set(OrderService::class, fn($c) => new OrderService($c->get(LoggerInterface::class)));

$service = $container->get(OrderService::class);
```

5. **Conceptos de lifetime de servicios**

- **Singleton/shared:** se reutiliza una instancia.
- **Transient/factory:** nueva instancia en cada resolución.
- **Scoped/request:** una instancia por alcance de solicitud (depende del framework).

6. **Buenas prácticas**

- Registra abstracciones (interfaces), no clases concretas, cuando sea posible.
- Mantén el código de negocio/dominio agnóstico al contenedor.
- Usa inyección por constructor por defecto.
- Evita llamar al contenedor directamente en profundidad dentro de la lógica de dominio (anti-patrón Service Locator).

Los service containers son herramientas de infraestructura que automatizan la gestión de dependencias y mantienen las aplicaciones PHP modernas modulares y componibles.

</details>

<details>
<summary>28. ¿Qué es middleware y el request lifecycle en frameworks?</summary>

#### PHP

En frameworks PHP modernos, el middleware son capas que procesan solicitudes y respuestas HTTP alrededor de la lógica principal de ruta/controlador. El request lifecycle es todo el recorrido desde la solicitud entrante hasta la respuesta final.

1. **Qué es middleware**

- Un componente de pipeline que puede:
  inspeccionar/modificar la solicitud, detener el procesamiento con su propia respuesta o pasar el control a la siguiente capa.
- A menudo se implementa con contratos estilo PSR-15 en ecosistemas modernos.

2. **Responsabilidades típicas de middleware**

- Autenticación y autorización
- CORS
- Rate limiting
- Normalización/validación de entrada
- Logging, tracing, métricas
- Manejo de excepciones y modelado de respuesta

3. **Request lifecycle típico**

1. La solicitud HTTP llega al servidor web (Nginx/Apache) y al runtime de PHP.
2. El bootstrap del framework carga configuración, servicios y rutas.
3. Comienza el pipeline de middleware global.
4. Se hace match de la ruta y se ejecuta middleware específico de ruta.
5. El controlador/handler ejecuta la lógica de negocio.
6. La respuesta vuelve a través del stack de middleware (post-procesamiento).
7. La respuesta final se envía al cliente.

4. **Por qué este modelo es útil**

- Separa preocupaciones transversales de los controladores.
- Mantiene handlers de ruta enfocados en lógica de negocio.
- Hace el comportamiento componible y reutilizable.
- Proporciona puntos de extensión consistentes para políticas a nivel plataforma.

5. **Guía práctica**

- Mantén cada middleware enfocado en una responsabilidad.
- Ordena middleware intencionalmente (por ejemplo, manejo de errores en la capa más externa).
- Evita lógica de negocio pesada en middleware.
- Prefiere middleware sin estado cuando sea posible.

Middleware + request lifecycle son conceptos arquitectónicos centrales detrás de un procesamiento HTTP limpio y predecible en frameworks PHP.

</details>

<details>
<summary>29. ¿Qué es MVC y cómo se implementa en frameworks PHP?</summary>

#### PHP

MVC (Model-View-Controller) es un patrón de arquitectura que separa las responsabilidades de la aplicación en capa de datos/negocio, renderizado de UI y orquestación de solicitudes.

1. **Componentes MVC**

- **Model** - lógica de dominio/datos, reglas e interacción con persistencia.
- **View** - capa de presentación (formato de templates/HTML/JSON).
- **Controller** - recibe la solicitud, coordina casos de uso y devuelve la respuesta.

2. **Cómo funciona en frameworks PHP**

Flujo típico:
1. El router hace match de la URL con una acción de controlador.
2. El controlador valida la entrada y llama a la capa de dominio/servicio/modelo.
3. El modelo/servicio recupera o muta datos.
4. El controlador pasa el resultado a la vista/template o devuelve respuesta API.
5. El framework emite la respuesta HTTP final.

3. **Ejemplo de responsabilidades**

- Controlador: `UserController@show($id)`
- Modelo/Servicio: obtener usuario, aplicar reglas de negocio
- Vista: renderizar `user/show.blade.php` (o recurso JSON)

4. **Por qué MVC es útil**

- Separación clara de responsabilidades.
- Mantenimiento y testing más simples.
- Mejor colaboración de equipo (separación de responsabilidades frontend/backend).
- Estructura de proyecto predecible.

5. **Errores comunes**

- Controladores gordos con lógica de negocio.
- Modelos gordos mezclando demasiadas responsabilidades.
- Acoplamiento fuerte entre controladores y detalles de persistencia.

6. **Práctica moderna en PHP**

Muchos proyectos usan MVC como base, pero mueven la lógica de negocio a capas de servicio/caso de uso, manteniendo controladores delgados y vistas simples.

MVC sigue siendo una base práctica en frameworks como Laravel y aplicaciones estilo Symfony, especialmente cuando se combina con principios de capas limpias.

</details>

<details>
<summary>30. ¿Qué es arquitectura hexagonal / clean architecture en PHP?</summary>

#### PHP

Hexagonal (Ports and Adapters) y Clean Architecture son enfoques que mantienen la lógica de negocio independiente de frameworks, bases de datos y servicios externos.

1. **Idea principal**

- Las reglas de negocio se colocan en el centro (dominio/casos de uso).
- Los sistemas externos se tratan como adaptadores reemplazables.
- Las dependencias apuntan hacia adentro: infraestructura depende del dominio, no al revés.

2. **Bloques principales**

- **Capa de dominio**: entidades, value objects, reglas de dominio.
- **Capa de aplicación/casos de uso**: orquesta escenarios de negocio.
- **Puertos (interfaces)**: contratos para capacidades necesarias (repositorios, gateways, buses).
- **Adaptadores**: implementaciones concretas (repositorio MySQL, cliente HTTP, publicador de colas).
- **Capa de entrega**: controladores HTTP/CLI/consumidores que llaman casos de uso.

3. **Por qué importa**

- El framework o la BD pueden cambiar con impacto mínimo en la lógica de negocio central.
- Los casos de uso son más fáciles de testear en aislamiento.
- Límites claros reducen acoplamiento y riesgo de mantenimiento a largo plazo.

4. **Ejemplo orientado a PHP**

- `CreateOrderUseCase` depende de `OrderRepositoryInterface` y `PaymentGatewayInterface`.
- Un controlador Laravel/Symfony invoca el caso de uso.
- Un repositorio MySQL y un adaptador Stripe implementan interfaces en la capa de infraestructura.

5. **Estructura de carpetas (conceptual)**

- `src/Domain/...`
- `src/Application/...`
- `src/Infrastructure/...`
- `src/Interface/Http/...` (o `Presentation/...`)

6. **Guía práctica**

- Mantén clases de framework fuera de la capa de dominio.
- Expresa límites mediante interfaces en el borde aplicación/dominio.
- Mapea DTOs de request/response del framework en los límites, no dentro del dominio.
- Empieza simple e introduce capas cuando la complejidad lo justifique.

La arquitectura Hexagonal/Clean ayuda a que sistemas PHP se mantengan adaptables, testeables y estables mientras evolucionan producto e infraestructura.

</details>

<details>
<summary>31. ¿Qué es el patrón Repository?</summary>

#### PHP

Repository es un patrón que abstrae el acceso a datos detrás de una interfaz orientada al dominio, para que la lógica de negocio trabaje con colecciones/agregados en lugar de detalles SQL/ORM directamente.

1. **Idea principal**

- Las capas de dominio/aplicación dependen de interfaces de repositorio.
- La capa de infraestructura proporciona implementaciones concretas (PDO/Doctrine/Eloquent/API).
- Las preocupaciones de persistencia quedan fuera de la lógica de casos de uso.

2. **Qué suele proporcionar Repository**

- Recuperar entidades/agregados (`findById`, `findByCriteria`).
- Persistir cambios (`save`, `remove`).
- Operaciones de consulta expresadas en términos del dominio.

3. **Interfaz de ejemplo**

```php
interface OrderRepositoryInterface
{
    public function getById(string $id): ?Order;
    public function save(Order $order): void;
}
```

4. **Por qué es útil**

- Desacopla la lógica de negocio de la tecnología de almacenamiento.
- Mejora la testabilidad (implementaciones in-memory/mock sencillas).
- Soporta límites de arquitectura (hexagonal/clean).
- Hace migraciones/refactors más seguros cuando cambia la persistencia.

5. **Errores comunes**

- Convertir el repositorio en un dump CRUD genérico sin intención de dominio.
- Duplicar innecesariamente todos los métodos del ORM uno a uno.
- Poner lógica de negocio en la implementación del repositorio.

6. **Guía práctica**

- Mantén interfaces de repositorio en el borde dominio/aplicación.
- Expón métodos con sentido para los casos de uso, no para internos de BD.
- Usa specifications/query objects para filtrado complejo cuando haga falta.
- Deja que repositorios manejen persistencia; conserva la orquestación en servicios/casos de uso.

El patrón Repository es más valioso en sistemas PHP medianos/grandes donde la longevidad de la lógica de dominio importa más que la velocidad CRUD de corto plazo.

</details>

<details>
<summary>32. ¿Qué son DTOs y Value Objects?</summary>

#### PHP

DTOs y Value Objects son patrones diferentes que a menudo se usan juntos en arquitectura PHP moderna.

1. **DTO (Data Transfer Object)**

- Un objeto simple usado para transferir datos estructurados entre capas/procesos.
- Normalmente contiene campos y lógica de negocio mínima o nula.
- Ayuda a evitar pasar arrays crudos entre límites.

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

- Un objeto de dominio definido por su valor, no por identidad.
- Normalmente inmutable y auto-validado.
- Encapsula reglas de dominio para un concepto específico (Email, Money, Currency, etc.).

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

3. **Diferencias clave**

- **Propósito**: DTO transporta datos; VO modela significado de dominio.
- **Lógica**: DTO mínima; VO puede imponer invariantes.
- **Identidad**: DTO suele ser incidental; VO se compara por valor.
- **Mutabilidad**: DTO puede ser mutable/inmutable; VO en general debe ser inmutable.

4. **Cuándo usar cada uno**

- Usa DTOs en límites (HTTP request/response, mensajería, entrada/salida de capa de aplicación).
- Usa Value Objects dentro del modelo de dominio para expresar conceptos validados de forma segura.

Los DTOs mejoran la claridad del flujo de datos, mientras que los Value Objects mejoran la corrección del dominio y previenen estados inválidos.

</details>

<details>
<summary>33. ¿Qué es OOP en PHP?</summary>

#### PHP

OOP (Object-Oriented Programming) en PHP es un paradigma de programación donde el código se organiza alrededor de objetos que combinan datos (estado) y comportamiento (métodos).

1. **Conceptos centrales de OOP**

- **Class**: plantilla que define propiedades y métodos.
- **Object**: instancia de una clase.
- **Encapsulation**: controla acceso a internals (`public/protected/private`).
- **Inheritance**: clases hijas reutilizan/extienden comportamiento de la clase padre.
- **Polymorphism**: interfaces comunes con implementaciones intercambiables.
- **Abstraction**: expone contratos esenciales y oculta detalles de implementación.

2. **Por qué se usa OOP en PHP**

- Modela conceptos de dominio con claridad.
- Fomenta código modular y reutilizable.
- Mejora la mantenibilidad en codebases medianos/grandes.
- Funciona de forma natural con DI, interfaces y arquitectura de frameworks.

3. **Ejemplo básico**

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

4. **Features modernas de OOP en PHP**

- Typed properties y strict types
- Interfaces y abstract classes
- Traits para reutilización horizontal de código
- Attributes, enums, readonly properties/classes
- Constructor property promotion

5. **Buenas prácticas**

- Prefiere composición sobre herencia cuando sea posible.
- Programa contra interfaces, no contra clases concretas.
- Mantén clases enfocadas (responsabilidad única).
- Evita “god objects” con demasiadas responsabilidades.

OOP en PHP es la base para la mayoría de los diseños modernos de aplicaciones con frameworks y orientadas al dominio.

</details>

<details>
<summary>34. ¿Cuál es la diferencia entre interface y abstract class?</summary>

#### PHP

Tanto las interfaces como las clases abstractas definen contratos, pero sirven para propósitos de diseño diferentes.

1. **Interface**

- Define solo firmas de métodos (contrato) y constantes.
- Sin estado de instancia (sin propiedades con estado en runtime).
- Una clase puede implementar múltiples interfaces.
- Enfoque: contrato de capacidades y polimorfismo.

```php
interface PaymentGatewayInterface
{
    public function charge(int $amount): bool;
}
```

2. **Abstract class**

- Puede contener tanto métodos abstractos como métodos implementados.
- Puede tener estado/comportamiento compartido (propiedades, helpers protegidos, lógica de constructor).
- Una clase puede extender solo una abstract/base class.
- Enfoque: implementación parcial + comportamiento base común.

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

3. **Diferencias clave**

- **Herencia múltiple de tipo**: muchas interfaces, solo una clase padre.
- **Código compartido**: abstract class sí, interface no.
- **Acoplamiento**: la interface suele ser más flexible; la abstract class introduce acoplamiento por herencia.

4. **Cuándo elegir**

- Usa **interface** cuando necesites implementaciones intercambiables y contratos claros.
- Usa **abstract class** cuando las implementaciones compartan lógica/estado base con sentido.

5. **Regla práctica**

Prefiere interfaces para límites públicos de arquitectura; usa clases abstractas como herramientas internas de reutilización cuando la herencia esté justificada.

Interface = “qué puede hacer”, abstract class = “cómo está implementado en parte”.

</details>

<details>
<summary>35. ¿Qué son los traits y cuándo deberían usarse?</summary>

#### PHP

Los traits en PHP son un mecanismo de reutilización horizontal de código: permiten que clases reutilicen métodos (y miembros relacionados) sin herencia.

1. **Qué es un trait**

- Una unidad de código reutilizable declarada con `trait`.
- Se incluye en clases mediante `use`.
- Ayuda a compartir comportamiento entre jerarquías de clases no relacionadas.

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

2. **Cuándo son útiles los traits**

- Comportamiento transversal compartido (helpers de logging, timestamps, pequeños comportamientos utilitarios).
- Reutilización entre clases que no pueden compartir una misma clase padre.
- Reducir duplicación cuando la composición sería demasiado verbosa para bloques pequeños de comportamiento.

3. **Resolución de conflictos entre traits**

Si dos traits definen el mismo método, PHP ofrece resolución de conflictos:
- `insteadof` para elegir una implementación.
- `as` para alias/renombrar métodos.

4. **Limitaciones y riesgos**

- Los traits pueden ocultar acoplamiento y difuminar responsabilidades de clase si se abusa de ellos.
- “God traits” grandes se vuelven difíciles de testear y mantener.
- Son inclusión de código, no contratos polimórficos reales.

5. **Buenas prácticas**

- Mantén traits pequeños y enfocados.
- Usa traits para reutilización de comportamiento, no para modelado de dominio.
- Prefiere interfaces + composición para límites arquitectónicos centrales.
- Evita almacenar estado compartido mutable complejo dentro de traits.

Los traits son una herramienta práctica de PHP para reutilización dirigida, pero funcionan mejor como complemento ligero a un buen diseño de objetos, no como reemplazo.

</details>

<details>
<summary>36. ¿Qué son los métodos mágicos y cuándo se activan?</summary>

#### PHP

Los métodos mágicos son métodos especiales de PHP (con prefijo `__`) que el motor activa automáticamente en eventos específicos del ciclo de vida del objeto o de interacción.

1. **Métodos mágicos del ciclo de vida del objeto**

- `__construct()` - se llama cuando se crea el objeto.
- `__destruct()` - se llama cuando se destruye el objeto (o termina el script).
- `__clone()` - se llama después de clonar el objeto.

2. **Métodos mágicos de acceso a propiedades**

- `__get($name)` - lectura de propiedad inaccesible/no definida.
- `__set($name, $value)` - escritura de propiedad inaccesible/no definida.
- `__isset($name)` - `isset()`/`empty()` sobre propiedad inaccesible/no definida.
- `__unset($name)` - `unset()` sobre propiedad inaccesible/no definida.

3. **Intercepción de llamadas a métodos**

- `__call($name, $arguments)` - llamada a método de instancia inaccesible/no definido.
- `__callStatic($name, $arguments)` - llamada a método estático inaccesible/no definido.

4. **String/invocación/serialización**

- `__toString()` - objeto usado como string.
- `__invoke(...$args)` - objeto usado como función.
- `__serialize()` / `__unserialize()` - lógica personalizada de serialización.

5. **Helpers de exportación de estado/debug**

- `__set_state(array $properties)` - llamado por recreación con `var_export()`.
- `__debugInfo()` - salida personalizada para `var_dump()`.

6. **Ejemplo simple**

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

7. **Buenas prácticas**

- Usa métodos mágicos de forma intencional, no como arquitectura por defecto.
- Mantén el comportamiento explícito y predecible.
- Evita ocultar errores con `__get/__set` demasiado permisivos.
- Prefiere propiedades/métodos tipados cuando sea posible.

Los métodos mágicos son puntos de extensión potentes, pero deben usarse con cuidado porque pueden reducir la claridad si se abusa de ellos.

</details>

<details>
<summary>37. ¿Qué es late static binding?</summary>

#### PHP

Late Static Binding (LSB) en PHP permite resolver métodos/propiedades estáticas según la clase que se llama en runtime, no solo según la clase donde se definió el método.

1. **`self::` vs `static::`**

- `self::` queda vinculado a la clase donde se declara el método (early binding).
- `static::` se resuelve a la clase llamada en runtime (late static binding).

2. **Por qué importa**

- Habilita comportamiento polimórfico en contexto estático.
- Es útil en jerarquías de herencia donde las clases hijas deben controlar clase/valores retornados.
- Es común en patrones factory y APIs estilo Active Record.

3. **Ejemplo**

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

Si se usara `self::TABLE`, el comportamiento quedaría fijo al contexto de declaración de la clase base.

4. **Keyword relacionado**

- El tipo de retorno `static` (`public static function make(): static`) también usa semántica de late static y devuelve el tipo de la clase llamada.

5. **Guía práctica**

- Usa `static::` cuando las subclases deban personalizar comportamiento estático.
- Usa `self::` cuando el comportamiento deba permanecer intencionalmente fijo a la implementación de la clase base.

Late static binding es una feature OOP importante para jerarquías de clases extensibles en PHP.

</details>

<details>
<summary>38. ¿Cómo se manejan los objetos en memoria en PHP?</summary>

#### PHP

En PHP, los objetos son gestionados por el Zend Engine como estructuras asignadas en heap referenciadas por object handles, con gestión automática de memoria mediante conteo de referencias y recolección de basura.

1. **Modelo de almacenamiento de objetos**

- Las instancias de objeto se asignan en memoria gestionada por el engine (heap).
- Las variables contienen referencias (handles) a entradas de objeto, no copias completas del objeto.
- Asignar una variable de objeto a otra copia el handle, no el estado del objeto.

```php
$a = new stdClass();
$a->x = 1;

$b = $a;      // same object reference
$b->x = 2;

echo $a->x;   // 2
```

2. **Conteo de referencias**

- El engine rastrea cuántos zvals referencian un valor/objeto.
- Cuando el conteo baja a cero, la memoria puede liberarse.
- Para objetos, esto normalmente implica invocación del destructor y limpieza del objeto.

3. **Recolector de basura (GC)**

- El conteo de referencias por sí solo no puede recolectar referencias cíclicas.
- El GC de PHP detecta y limpia basura cíclica (por ejemplo, grafos de objetos que se referencian entre sí).

4. **Comportamiento de clonación**

- `clone` crea una nueva instancia de objeto (identidad separada).
- `__clone()` puede personalizar la lógica de estado posterior al clonado.

5. **Matiz de paso por referencia**

- Pasar objetos a funciones es efectivamente por handle (cambios en el objeto son visibles fuera).
- Normalmente no necesitas `&` para mutar el estado del objeto entre límites de función.

6. **Implicaciones de rendimiento/memoria**

- Grafos de objetos grandes incrementan presión de memoria.
- Referencias de larga vida (cachés estáticas, closures, contenedores globales) pueden retrasar la limpieza.
- Referencias circulares en workers de larga ejecución deben monitorearse para evitar crecimiento tipo leak.

7. **Guía práctica**

- Mantén los grafos de objetos intencionales y acotados.
- Haz `unset` explícito de estructuras temporales grandes en procesos de larga ejecución cuando haga falta.
- Usa herramientas de profiling para inspeccionar hotspots de memoria.
- Ten cuidado con singletons estáticos/estado global en workers/daemons.

El manejo de memoria de objetos en PHP es eficiente para ciclos de solicitud típicos, pero los procesos de larga ejecución requieren disciplina deliberada de memoria.

</details>

<details>
<summary>39. ¿Qué es PDO y por qué se prefiere?</summary>

#### PHP

PDO (PHP Data Objects) es una capa de abstracción de acceso a bases de datos en PHP que proporciona una API consistente para trabajar con múltiples motores de BD.

1. **Qué proporciona PDO**

- Interfaz unificada para operaciones de BD (`MySQL`, `PostgreSQL`, `SQLite`, etc.).
- Prepared statements y parameter binding.
- Soporte de transacciones.
- Modos de fetch y manejo de errores configurables.

2. **Por qué se prefiere PDO**

- **Portabilidad:** mismo estilo de código entre distintas bases de datos.
- **Seguridad:** prepared statements reducen riesgo de SQL injection.
- **Mantenibilidad:** código de acceso a BD más limpio y estandarizado.
- **Control:** comportamiento explícito de transacciones/errores.

3. **Ejemplo básico**

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

4. **PDO vs APIs directas específicas del driver**

- PDO ofrece una abstracción común y límites de arquitectura más limpios.
- APIs específicas del driver pueden exponer features de nicho, pero reducen portabilidad.

5. **Buenas prácticas**

- Activa siempre modo de excepciones (`PDO::ERRMODE_EXCEPTION`).
- Usa prepared statements para toda entrada externa.
- Configura charset explícito en DSN (por ejemplo, `utf8mb4`).
- Maneja transacciones explícitamente en escrituras de múltiples pasos.

PDO se prefiere en PHP moderno porque combina seguridad, portabilidad y patrones claros de acceso a base de datos.

</details>

<details>
<summary>40. ¿Qué son prepared statements y parameter binding?</summary>

#### PHP

Los prepared statements son consultas SQL compiladas como plantillas con placeholders, donde los valores se suministran por separado mediante parameter binding.

1. **Cómo funcionan**

- Paso 1: preparar SQL con placeholders (`:email`, `?`).
- Paso 2: bind/execute de valores por separado.
- La base de datos trata los valores vinculados estrictamente como datos, no como sintaxis SQL.

2. **Por qué son importantes**

- Defensa principal contra SQL injection.
- Código de consultas más limpio y seguro.
- Mejor manejo de tipos de datos y escaping por el driver.
- Puede mejorar rendimiento en ejecución repetida de consultas (depende de BD/driver).

3. **Ejemplo con placeholder nombrado (PDO)**

```php
$stmt = $pdo->prepare(
    'SELECT id, email FROM users WHERE email = :email AND status = :status'
);

$stmt->execute([
    'email' => $email,
    'status' => $status,
]);
```

4. **Ejemplo con placeholder posicional**

```php
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = ?');
$stmt->execute([$id]);
```

5. **Binding con tipos explícitos**

```php
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = :id');
$stmt->bindValue(':id', $id, PDO::PARAM_INT);
$stmt->execute();
```

6. **Matiz importante**

- Los prepared statements protegen valores, no identificadores SQL (nombres de tabla/columna).
- Identificadores dinámicos deben controlarse con allowlists estrictas.

7. **Buenas prácticas**

- Usa prepared statements en toda consulta que incluya entrada externa.
- Evita concatenación de strings para condiciones SQL.
- Mantén plantillas SQL legibles y explícitas.
- Combina esto con usuarios de BD de mínimo privilegio y límites de transacciones.

Prepared statements + parameter binding son la base estándar y no opcional para acceso seguro a BD en PHP.

</details>

<details>
<summary>41. ¿Cómo funcionan las transacciones en PHP?</summary>

#### PHP

Las transacciones en PHP (vía PDO/MySQLi) agrupan múltiples operaciones de base de datos en una sola unidad atómica: o todos los cambios se confirman, o todos se revierten.

1. **Operaciones principales de transacción**

- `beginTransaction()` - inicia la transacción.
- `commit()` - guarda permanentemente todos los cambios.
- `rollBack()` - cancela todos los cambios no confirmados.

2. **Por qué se necesitan transacciones**

- Aseguran consistencia de datos en escrituras de múltiples pasos.
- Previenen actualizaciones parciales cuando ocurre un error.
- Preservan invariantes de negocio (por ejemplo, débito y crédito deben ambos completarse).

3. **Ejemplo básico con PDO**

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

4. **Aislamiento y concurrencia**

- El nivel de aislamiento de BD controla visibilidad/comportamiento de locks entre transacciones concurrentes.
- Anomalías comunes: dirty reads, non-repeatable reads, phantom reads.
- Elige nivel de aislamiento según trade-offs de consistencia/rendimiento.

5. **Pitfalls prácticos**

- Transacciones largas mantienen locks y perjudican la concurrencia.
- Llamadas a APIs externas/red dentro de transacción BD aumentan ventana de fallo.
- Olvidar rollback en excepciones puede dejar el flujo inconsistente.

6. **Buenas prácticas**

- Mantén transacciones tan cortas como sea posible.
- Incluye solo operaciones de BD que deban ser atómicas.
- Usa manejo de errores explícito y garantías de rollback.
- Diseña lógica de reintentos para deadlocks/conflictos de serialización cuando haga falta.

Las transacciones son un mecanismo central de fiabilidad para flujos críticos de integridad en sistemas PHP (finanzas, inventario, etc.).

</details>

<details>
<summary>42. ¿Qué es ORM (Eloquent / Doctrine) y cuáles son los trade-offs?</summary>

#### PHP

ORM (Object-Relational Mapping) es una técnica que mapea tablas/filas de base de datos a objetos PHP, permitiéndote trabajar con entidades de dominio en lugar de SQL crudo en la mayor parte del código de aplicación.

1. **Qué te da un ORM**

- Clases de entidad/modelo mapeadas a esquemas de BD.
- APIs/builders de consulta en lugar de SQL manual para operaciones comunes.
- Manejo de relaciones (`hasMany`, `belongsTo`, etc.).
- Unit-of-work/change tracking (especialmente en Doctrine).
- Migraciones y tooling del ecosistema en muchos frameworks.

2. **ORMs comunes en PHP**

- **Eloquent (Laravel)**:
  estilo Active Record, productividad rápida, sintaxis expresiva.
- **Doctrine ORM**:
  estilo Data Mapper, modelado de dominio rico, separación de responsabilidades más fuerte.

3. **Beneficios**

- Desarrollo más rápido para features con mucho CRUD.
- Código de persistencia más limpio y legible para escenarios comunes.
- Recorrido de relaciones más sencillo y flujos centrados en modelos.
- Scaffolding por convención e integraciones de ecosistema.

4. **Trade-offs / desventajas**

- Overhead de abstracción y potencial costo de rendimiento.
- Consultas ocultas/implícitas (problema N+1).
- SQL/reporting complejo a menudo sigue requiriendo SQL manual.
- Patrones específicos del ORM pueden aumentar curva de aprendizaje y lock-in.

5. **Cuándo ORM funciona mejor**

- Aplicaciones de negocio con operaciones frecuentes de ciclo de vida de entidades.
- Equipos que valoran productividad y código mantenible centrado en modelos.

6. **Cuándo preferir SQL crudo/query builders**

- Hot paths críticos de rendimiento.
- Consultas analíticas/reportes complejos.
- Features específicas de proveedor de BD y control SQL fino.

7. **Estrategia práctica**

- Usa ORM por defecto para operaciones de dominio comunes.
- Perfila y optimiza cuellos de botella.
- Mezcla ORM con SQL optimizado cuando sea necesario (enfoque híbrido).
- Sé explícito con eager/lazy loading para evitar explosión de consultas.

ORM es un multiplicador de productividad en PHP, pero una buena ingeniería requiere entender dónde la abstracción ayuda y dónde es mejor un control SQL de bajo nivel.

</details>

<details>
<summary>43. ¿Qué es connection pooling y por qué es importante?</summary>

#### PHP

Connection pooling es una técnica en la que las conexiones de base de datos se reutilizan desde un pool gestionado en lugar de crearse y cerrarse en cada operación.

1. **Por qué las conexiones son costosas**

- Abrir conexiones de BD implica handshake de red, autenticación y asignación de recursos del servidor.
- Reconexiones frecuentes aumentan latencia y carga de CPU tanto en la app como en la BD.

2. **Qué hace el pooling**

- Mantiene un conjunto reutilizable de conexiones abiertas.
- Asigna una conexión existente al trabajo entrante.
- La devuelve al pool después del uso para reutilizarla en las siguientes solicitudes/jobs.

3. **Por qué es importante**

- Reduce latencia de solicitudes.
- Mejora throughput bajo carga.
- Disminuye churn y overhead de conexiones en la BD.
- Estabiliza el comportamiento en sistemas de alta concurrencia.

4. **Matiz del contexto PHP**

- En el modelo clásico de solicitudes PHP-FPM, cada proceso worker tiene ciclo de vida aislado, por lo que el pooling es menos directo que en runtimes de larga vida.
- Enfoques prácticos comunes:
  conexiones persistentes (`PDO::ATTR_PERSISTENT` con cautela),
  poolers/proxies externos (por ejemplo, PgBouncer para PostgreSQL),
  workers de larga ejecución (RoadRunner/Swoole/consumidores de cola) donde la reutilización es más directa.

5. **Trade-offs / riesgos**

- Conexiones stale/rotas deben detectarse y reciclarse.
- Un tamaño de pool deficiente puede causar contención o sobrecarga de BD.
- Conexiones persistentes pueden retener recursos del servidor más tiempo del esperado.

6. **Buenas prácticas**

- Configura límites sensatos de pool/conexiones alineados con la capacidad de la BD.
- Usa health checks/timeouts de conexión.
- Monitorea cantidad de conexiones, tiempo de espera y tasas de error.
- Mantén consultas eficientes; pooling no corrige SQL lento.

Connection pooling es una técnica clave de escalabilidad para sistemas PHP intensivos en base de datos, especialmente bajo tráfico concurrente sostenido.

</details>

<details>
<summary>44. ¿Cómo estructuras una aplicación PHP escalable?</summary>

#### PHP

Una aplicación PHP escalable se estructura alrededor de límites claros, arquitectura predecible y preparación operativa para crecer en tráfico, tamaño de equipo y complejidad de features.

1. **Usa límites por capas/módulos**

- Divide por responsabilidades y dominios de negocio, no solo por carpetas técnicas.
- Capas típicas:
  `Domain`, `Application/UseCases`, `Infrastructure`, `Interface/HTTP`.

2. **Mantén la lógica de negocio agnóstica al framework**

- Coloca reglas centrales en la capa de dominio/casos de uso.
- Mantén controladores delgados.
- Depende de interfaces; deja adaptadores de BD/framework en infraestructura.

3. **Diseña para escalado horizontal stateless**

- Evita estado mutable local en instancias de la app.
- Guarda estado compartido en sistemas externos:
  BD, Redis, object storage, colas.
- Haz que sesiones/caché estén listas para despliegues multi-nodo.

4. **Estrategia de datos y persistencia**

- Usa repositorios/servicios para límites de persistencia.
- Aplica indexación y optimización de consultas desde temprano.
- Introduce caché (aplicación/consulta/HTTP) donde esté justificado.
- Usa separación lectura/escritura y particionado solo cuando haga falta.

5. **Procesamiento asíncrono y en background**

- Mueve tareas no críticas/lentas a colas (emails, exports, notificaciones, webhooks).
- Mantén el path de request rápido y determinista.

6. **Escalabilidad operativa**

- Containeriza workloads (Docker/K8s/plataformas gestionadas).
- Usa health checks, logging estructurado, métricas, tracing.
- Agrega rate limiting, timeouts, retries, circuit breakers.
- Construye CI/CD con estrategia segura de rollout y rollback.

7. **Escalabilidad del codebase para equipos**

- Aplica coding standards y análisis estático.
- Mantén límites modulares de paquetes.
- Usa tests de integración y de contrato alrededor de paths críticos.
- Documenta decisiones de arquitectura (ADRs) y contratos de servicios.

8. **Ruta práctica de evolución**

- Empieza con un monolito modular y límites fuertes.
- Extrae servicios solo cuando restricciones claras de escala/equipo lo justifiquen.

La escalabilidad en PHP es principalmente una disciplina de arquitectura + operaciones, no una sola elección de framework.

</details>

<details>
<summary>45. ¿Cómo manejas la configuración (variables de entorno)?</summary>

#### PHP

En aplicaciones PHP modernas, la configuración debe externalizarse del código y proveerse mediante variables de entorno, siguiendo principios de 12-factor.

1. **Principio central**

- Mantén la configuración fuera del código fuente.
- Trata el entorno como fuente de settings específicos de despliegue:
  credenciales BD, URLs de API, hosts de caché, feature flags, etc.

2. **Setup típico**

- Desarrollo: archivo `.env` (cargado por framework/bootstrap).
- Producción: variables de entorno reales desde plataforma/orquestador (no `.env` en el repo).

3. **Cómo se consumen los valores**

- Lee env una vez en el bootstrap de configuración.
- Mapea a estructura/objeto de config tipado.
- Inyecta config en servicios vía DI.

4. **Buenas prácticas**

- Separa config por entorno (`dev`, `staging`, `prod`) usando valores env.
- Proporciona defaults solo para valores locales no sensibles de desarrollo.
- Valida configuración requerida al arranque y falla rápido si falta/es inválida.
- Mantén claves de config consistentes y documentadas.

5. **Qué no hacer**

- No hardcodees credenciales en el código.
- No hagas commit de secretos de producción al repositorio.
- No llames `getenv()` aleatoriamente por toda la lógica de dominio.
- No mezcles lógica de negocio con lógica de carga de configuración.

6. **Patrón práctico**

Usa archivos centrales de config que leen desde env, por ejemplo:
- `config/database.php`
- `config/cache.php`
- `config/app.php`

Luego inyecta la configuración resuelta en servicios dependientes.

7. **Nota de seguridad**

Las variables de entorno son mejores que secretos hardcodeados, pero siguen siendo sensibles:
limita el acceso, evita loguear valores completos y combínalas con gestores de secretos dedicados para credenciales críticas.

Manejar configuración vía variables de entorno mantiene apps PHP portables, seguras y consistentes entre entornos.

</details>

<details>
<summary>46. ¿Cómo gestionas secretos (Vault, AWS Secrets Manager)?</summary>

#### PHP

La gestión de secretos es la práctica de almacenar, rotar y acceder de forma segura a valores sensibles (API keys, contraseñas de BD, tokens, certificados) fuera del código de aplicación.

1. **Por qué se necesitan gestores de secretos dedicados**

- Evitan que secretos se filtren al repositorio/historial.
- Centralizan control de acceso y auditoría.
- Permiten rotación segura sin redeploy del código.
- Reducen riesgo operativo frente a archivos `.env` planos.

2. **Herramientas comunes**

- **HashiCorp Vault**: secretos dinámicos, leases, acceso basado en políticas, capacidades fuertes de auditoría.
- **AWS Secrets Manager**: almacenamiento/rotación gestionados de secretos integrados con IAM y servicios AWS.
- (También comunes: parameter stores nativos de cloud o soluciones respaldadas por KMS.)

3. **Flujo recomendado de secretos**

1. Se establece la identidad de la app (rol IAM, workload identity, método de auth de Vault).
2. La app obtiene secretos requeridos al arranque (o bajo demanda con caché).
3. Los secretos se mantienen en memoria solo cuando se necesitan.
4. Los eventos de rotación se manejan sin valores hardcodeados.

4. **Buenas prácticas**

- Nunca hagas commit de secretos en git (incluyendo archivos de ejemplo con valores reales).
- Usa políticas de mínimo privilegio por servicio/entorno.
- Rota secretos regularmente y ante triggers de incidentes.
- Registra metadatos de acceso, nunca valores de secretos.
- Separa secretos por entorno (`dev/staging/prod`) y alcance de servicio.
- Usa credenciales de corta vida cuando sea posible (credenciales dinámicas de BD/tokens).

5. **Patrón de integración en PHP**

- Obtén secretos en la capa bootstrap/infraestructura.
- Mapéalos a objetos de configuración tipados.
- Inyecta config/secretos en servicios dependientes vía DI.
- Agrega estrategia de fallback y retry para caídas del gestor de secretos.

6. **Consideraciones operativas**

- Cachea secretos con TTL para reducir latencia y límites de API.
- Planifica comportamiento de arranque cuando el backend de secretos no esté disponible temporalmente.
- Prueba el procedimiento de rotación en staging antes del rollout en producción.

Usar Vault/AWS Secrets Manager convierte el manejo de secretos de variables de entorno ad-hoc en un proceso de seguridad controlado y apto para sistemas PHP en producción.

</details>

<details>
<summary>47. ¿Qué es una app 12-factor en el contexto de PHP?</summary>

#### PHP

12-factor app es un conjunto de principios de ingeniería cloud-native para construir servicios portables, escalables y mantenibles. En PHP, estos principios ayudan a pasar de “apps acopladas al servidor” a servicios modernos desplegables.

1. **Codebase**

- Un codebase rastreado en control de versiones.
- Muchos despliegues (`dev/staging/prod`) desde el mismo codebase.

2. **Dependencias**

- Declara dependencias explícitamente en `composer.json`.
- Evita depender de paquetes del sistema instalados globalmente.

3. **Config**

- Guarda configuración en variables de entorno, no en código.
- Mantén secretos y valores específicos de entorno fuera del repositorio.

4. **Backing services**

- Trata BD, caché, cola, object storage como recursos adjuntos.
- Accede a ellos vía config/URLs, para poder intercambiarlos por entorno.

5. **Separación build, release, run**

- Construye el artefacto una sola vez.
- Promueve el mismo artefacto entre entornos.
- Mantén configuración de runtime separada del build.

6. **Procesos**

- Ejecuta la app como procesos stateless.
- Guarda estado persistente en servicios externos (BD/Redis/S3/etc.).

7. **Port binding y concurrencia**

- Expón servicios mediante entrypoints HTTP/runtime.
- Escala con replicación de procesos/contenedores, no solo con ajuste vertical.

8. **Disposability y paridad**

- Inicio/apagado rápido para despliegues seguros y autoscaling.
- Mantén entornos `dev/staging/prod` lo más similares posible.

9. **Logs y tareas admin**

- Trata logs como streams de eventos (stdout/agregadores).
- Ejecuta tareas admin/migraciones como procesos one-off usando el mismo codebase.

10. **Implicaciones prácticas específicas de PHP**

- Usa Composer + config por env + estado externalizado.
- Runtime amigable con contenedores (PHP-FPM/workers CLI).
- Workers de cola para tareas en background.
- Pipeline CI/CD con artefactos inmutables.

Aplicar principios 12-factor en PHP mejora fiabilidad de despliegue, escalabilidad operativa y mantenibilidad a largo plazo.

</details>

<details>
<summary>48. ¿Qué es la containerización (Docker) en aplicaciones PHP?</summary>

#### PHP

La containerización empaqueta una aplicación PHP con sus dependencias de runtime en una imagen portable, para que se ejecute de forma consistente en local, CI, staging y producción.

1. **Qué aporta Docker a apps PHP**

- Runtime reproducible (versión de PHP, extensiones, librerías del sistema).
- Paridad de entorno entre máquinas de desarrollo y producción.
- Despliegue, rollback y escalado más simples.
- Aislamiento entre servicios (app, BD, caché, cola, worker).

2. **Stack típico de PHP containerizado**

- Contenedor PHP-FPM (runtime de aplicación)
- Contenedor Nginx/Apache (servidor web)
- Contenedores separados para BD/Redis/workers de cola/cron jobs

3. **Patrón básico de Dockerfile**

```dockerfile
FROM php:8.4-fpm-alpine

RUN docker-php-ext-install pdo pdo_mysql opcache
WORKDIR /var/www/html

COPY . .
RUN php -v
```

4. **Por qué importa para escalabilidad**

- El escalado horizontal se vuelve más simple (replicar contenedores).
- Despliegues inmutables basados en imagen reducen drift/desajuste de configuración.
- Funciona naturalmente con plataformas de orquestación (Kubernetes, ECS, Nomad).

5. **Buenas prácticas**

- Usa imágenes base pequeñas y builds multi-stage.
- Fija versiones de imagen/tag para reproducibilidad.
- Mantén imágenes stateless; guarda datos persistentes externamente.
- Inyecta config/secretos vía env/gestores de secretos, no embebidos en la imagen.
- Ejecuta health checks y expón logs estructurados a stdout/stderr.

6. **Pitfalls comunes**

- Ejecutar todo en un solo contenedor (web + BD + cola) en producción.
- Escribir datos persistentes de app en filesystem del contenedor.
- Imágenes grandes con herramientas de build innecesarias en la capa runtime.

La containerización es una práctica central para operaciones PHP modernas porque estandariza el comportamiento del runtime y mejora la capacidad de despliegue a escala.

</details>

<details>
<summary>49. ¿Qué es OPcache y cómo mejora el rendimiento?</summary>

#### PHP

OPcache es un caché de bytecode integrado en PHP que almacena bytecode compilado de scripts en memoria compartida, para que PHP no tenga que parsear y compilar los mismos archivos en cada solicitud.

1. **Qué problema resuelve OPcache**

- Sin OPcache, cada solicitud repite:
  leer archivo PHP -> parsear -> compilar a opcodes -> ejecutar.
- Esta compilación repetida agrega overhead de CPU y latencia.

2. **Cómo mejora OPcache el rendimiento**

- Los opcodes compilados se cachean en memoria y se reutilizan entre solicitudes.
- Reduce uso de CPU y tiempo de solicitud.
- Incrementa throughput bajo carga.
- Mejora rendimiento de arranque en frameworks con muchos archivos.

3. **Setup típico de producción**

- Habilita OPcache en runtime de PHP (`opcache.enable=1`).
- Ajusta límites de memoria y cantidad de archivos:
  `opcache.memory_consumption`, `opcache.max_accelerated_files`.
- Desactiva validación por timestamp para artefactos de release inmutables:
  `opcache.validate_timestamps=0` (con reset de caché disparado por despliegue).

4. **Settings útiles comunes**

- `opcache.enable`
- `opcache.memory_consumption`
- `opcache.max_accelerated_files`
- `opcache.interned_strings_buffer`
- `opcache.validate_timestamps`
- `opcache.revalidate_freq`

5. **Consideraciones de despliegue**

- Cuando cambia el código, el bytecode cacheado debe refrescarse.
- En despliegues inmutables/contenedores, reiniciar workers PHP suele ser suficiente.
- En despliegues mutables, usa estrategia controlada de invalidación/reinicio.

6. **Buenas prácticas**

- Usa siempre OPcache en producción.
- Monitorea cache hit rate, uso de memoria y reinicios.
- Dimensiona la caché según crecimiento del codebase.
- Combina OPcache con caché de aplicación/base de datos para ganancias completas de rendimiento.

OPcache es una de las features de rendimiento de mayor impacto y menor esfuerzo para entornos PHP de producción.

</details>

<details>
<summary>50. ¿Qué es JIT en PHP y cuándo es útil?</summary>

#### PHP

JIT (Just-In-Time compilation) en PHP es una optimización del motor que compila opcodes seleccionados de Zend a código máquina nativo en runtime.

1. **Qué hace JIT**

- Flujo normal de PHP: script -> opcodes -> ejecución por intérprete.
- Con JIT: rutas de código calientes pueden compilarse a código nativo y ejecutarse más rápido.

2. **Dónde JIT puede ayudar**

- Workloads intensivos de CPU:
  matemáticas pesadas, loops, procesamiento de datos, algoritmos computacionales.
- Workers CLI de larga ejecución y tareas de cómputo especializadas.

3. **Dónde JIT suele dar poco beneficio**

- Apps web típicas dominadas por I/O:
  consultas de base de datos, llamadas de red, acceso a caché, renderizado de templates.
- En muchos workloads CRUD/API, OPcache y optimización de consultas importan más que JIT.

4. **Relación con OPcache**

- JIT está construido sobre la infraestructura de OPcache.
- OPcache generalmente da la mayor ganancia base para la mayoría de apps.
- JIT es una capa adicional de optimización para código CPU-bound.

5. **Guía práctica**

- Habilita y benchmarkea antes/después en tu workload real.
- No asumas mejoras globales de velocidad para todos los tipos de request.
- Prioriza primero corrección de cuellos de botella:
  SQL lento, consultas N+1, llamadas de red excesivas, caché ineficiente.

6. **Regla general**

- Para backends web clásicos: el impacto de JIT suele ser moderado.
- Para workloads PHP intensivos en cómputo: JIT puede aportar mejoras significativas.

JIT es una herramienta de optimización útil, pero su valor depende mucho del perfil de carga.

</details>

<details>
<summary>51. ¿Qué es lazy loading y dónde se usa?</summary>

#### PHP

Lazy loading es una técnica en la que datos u objetos se cargan solo cuando realmente se necesitan, en lugar de cargar todo por adelantado.

1. **Idea principal**

- Retrasa inicialización costosa hasta el primer acceso.
- Reduce uso inicial de memoria y tiempo de arranque.
- Pagas el costo solo en rutas que realmente se usan.

2. **Dónde se usa lazy loading en PHP**

- Relaciones ORM (proxies de relaciones en Doctrine/Eloquent).
- Inicialización de servicios en contenedores DI (servicios diferidos).
- Configuración/recursos grandes cargados bajo demanda.
- Procesamiento de streams/archivos donde los chunks se cargan progresivamente.

3. **Ejemplo típico en ORM**

- Se carga la entidad `User`.
- `User->orders` no se obtiene inmediatamente.
- El primer acceso a orders dispara la consulta SQL.

4. **Beneficios**

- Respuesta inicial más rápida en muchos casos de uso.
- Menor huella de memoria cuando no se requieren todos los datos.
- Mejor escalabilidad para grafos de objetos complejos.

5. **Trade-offs y riesgos**

- Consultas ocultas pueden causar problemas de rendimiento N+1.
- Los patrones de acceso se vuelven menos explícitos.
- Lazy loading en loops ajustados puede disparar demasiados round-trips a BD.

6. **Buenas prácticas**

- Usa eager loading cuando sabes que se necesitarán datos relacionados.
- Perfila cantidad de consultas y latencia.
- Mantén límites de lazy loading explícitos en capa de repositorio/consulta.
- Evita lazy-loading dentro de loops de serialización/salida.

7. **Regla general**

- Usa lazy loading para dependencias/datos opcionales o poco usados.
- Usa eager loading para datos relacionados predecibles y accedidos con frecuencia.

Lazy loading es potente para optimización de rendimiento, pero solo cuando se combina con visibilidad del comportamiento de consultas y una estrategia de carga deliberada.

</details>

<details>
<summary>52. ¿Cuáles son los cuellos de botella de rendimiento comunes en PHP?</summary>

#### PHP

La mayoría de problemas de rendimiento en PHP no los causa el lenguaje en sí, sino I/O ineficiente, patrones de consulta y decisiones de arquitectura.

1. **Cuellos de botella de base de datos (los más comunes)**

- Consultas N+1 en uso de ORM.
- Índices faltantes o planes de consulta deficientes.
- Over-fetching de datos (`SELECT *` cuando no hace falta).
- Transacciones largas y contención de locks.

2. **Red e I/O externo**

- APIs de terceros lentas sin timeouts/retries.
- Demasiadas llamadas salientes síncronas en el path de request.
- Falta de circuit breakers/fallbacks.

3. **Ineficiencias a nivel aplicación**

- Lógica de negocio pesada ejecutada en cada solicitud.
- Recalcular resultados costosos en lugar de usar caché.
- Serialización/deserialización excesiva o procesamiento de payloads grandes.

4. **Overhead de autoload/bootstrap**

- Bootstraps de framework grandes para endpoints triviales.
- Demasiadas clases/config providers cargados.
- OPcache mal configurado.

5. **Overhead de filesystem y logging**

- Escrituras frecuentes a disco en el path de request.
- Logging bloqueante/verboso sin procesamiento asíncrono.
- Volúmenes de almacenamiento lentos en contenedores/VMs.

6. **Presión de memoria**

- Colecciones en memoria grandes y arrays sin límites.
- Loops ineficientes sobre datasets enormes.
- Workers de larga vida reteniendo referencias sin querer.

7. **Caché ausente/ineficaz**

- Sin caché para datos con muchas lecturas.
- Estrategia de invalidación incorrecta que causa datos stale/fallos frecuentes.
- Cache stampede bajo carga.

8. **Cómo abordarlo sistemáticamente**

- Perfila antes de optimizar.
- Prioriza primero endpoints/consultas más calientes.
- Agrega optimización de consultas + caché + offloading asíncrono.
- Monitorea latencia p95/p99, tiempo de BD, cache hit ratio y tasas de error.

En sistemas PHP, las ganancias más rápidas suelen venir de tuning de consultas, estrategia de caché y reducción de I/O síncrono en el path de request.

</details>

<details>
<summary>53. ¿Cómo perfiles una aplicación PHP?</summary>

#### PHP

Profiling es el proceso de medir dónde se gasta realmente tiempo de ejecución, CPU, memoria e I/O, para que la optimización se base en evidencia y no en suposiciones.

1. **Qué medir primero**

- Latencia de solicitud (p50/p95/p99)
- Tiempo de base de datos y cantidad de consultas
- Duración de llamadas a APIs externas
- Uso de memoria y pico de uso
- Funciones/rutas de código calientes

2. **Herramientas comunes de profiling en PHP**

- **Blackfire** - profiling apto para producción y recomendaciones de rendimiento.
- **Xdebug (modo profiler)** - trazas detalladas/callgrind para análisis local.
- **Tideways/familia XHProf** - profiling a nivel de función con opciones de bajo overhead.
- **Herramientas APM** (Datadog/New Relic/etc.) para visibilidad distribuida de requests.

3. **Flujo práctico de profiling**

1. Reproduce endpoint/job lento con datos realistas.
2. Captura trace de profiling.
3. Identifica mayores contribuidores (BD, I/O externo, funciones CPU-intensivas).
4. Optimiza un cuello de botella a la vez.
5. Vuelve a perfilar y compara métricas.

4. **Qué suele aparecer como hotspot**

- Consultas ORM N+1
- Índices faltantes / scans SQL costosos
- Serialización repetida y procesamiento de payloads grandes
- Llamadas de red síncronas en el path de request
- Overhead excesivo de framework/bootstrap

5. **Foco de profiling de memoria**

- Arrays/colecciones grandes cargados de una vez
- Referencias de larga vida en workers
- Grafos de objetos innecesarios y datos duplicados

6. **Buenas prácticas**

- Perfila en entornos cercanos al comportamiento de producción.
- Benchmarkea antes y después de cada optimización.
- Rastrea regresiones en CI/CD con presupuestos de rendimiento para endpoints críticos.
- Combina profiling de código con profiling de BD (`EXPLAIN`, logs de consultas lentas).

Profiling convierte el tuning de rendimiento en un proceso de ingeniería medible y es la forma más fiable de mejorar velocidad de aplicaciones PHP de forma segura.

</details>

<details>
<summary>54. ¿Cómo funciona el caching (Redis, Memcached)?</summary>

#### PHP

Caching almacena datos precalculados o frecuentemente solicitados en almacenamiento rápido (normalmente memoria) para evitar operaciones costosas repetidas como consultas BD o cómputos pesados.

1. **Cómo funciona el caching (flujo básico)**

1. La app recibe una solicitud de datos.
2. Verifica caché por clave.
3. Si hay hit: devuelve valor cacheado rápidamente.
4. Si hay miss: carga de origen (BD/API), guarda en caché con TTL y devuelve valor.

2. **Backends de caché comunes**

- **Redis**:
  almacén en memoria con estructuras de datos ricas, opciones de persistencia, pub/sub, features distribuidas.
- **Memcached**:
  caché distribuido simple en memoria clave-valor, enfocado en caching efímero de alta velocidad.

3. **Casos típicos de uso de caché en PHP**

- Caché de resultados de consultas
- Almacenamiento de sesiones
- Caché de respuestas/fragmentos
- Contadores de rate limiting
- Locks y claves de idempotencia
- Datos de referencia calculados/de configuración

4. **Conceptos importantes de diseño de caché**

- **Estrategia de claves**: namespacing y versionado predecibles (`user:42:v2`).
- **TTL**: elige expiración según volatilidad de datos.
- **Invalidación**: invalidación explícita en escrituras cuando importa la frescura.
- **Modelo de consistencia**: acepta consistencia eventual donde corresponda.

5. **Pitfalls comunes**

- Cache stampede (muchos misses concurrentes).
- Datos stale por estrategia de invalidación débil.
- Valores sobredimensionados y diseño pobre de claves.
- Tratar la caché como fuente de verdad.

6. **Buenas prácticas**

- Cachea solo lecturas costosas/de alta frecuencia.
- Usa TTLs cortos y sensatos, con jitter para reducir expiración sincronizada.
- Agrega protección contra stampede (locks, request coalescing, stale-while-revalidate).
- Monitorea hit rate, latencia, evicción y uso de memoria.
- Mantén BD como fuente de verdad; la caché es capa de aceleración.

El caching con Redis/Memcached es una de las formas más efectivas de reducir latencia y carga de base de datos en sistemas PHP de producción.

</details>

<details>
<summary>55. ¿Qué es el procesamiento asíncrono en PHP?</summary>

#### PHP

El procesamiento asíncrono significa mover tareas lentas o no críticas fuera del flujo HTTP síncrono de request, para que los usuarios reciban respuestas rápidas mientras el trabajo en background se ejecuta por separado.

1. **Por qué se necesita async**

- Los ciclos request-response deben mantenerse cortos.
- Algunas operaciones son costosas:
  emails, procesamiento de archivos, generación de reportes, llamadas a APIs externas.
- Hacer todo inline aumenta latencia e impacto de fallos.

2. **Cómo funciona en sistemas PHP**

1. La app principal recibe la solicitud.
2. El estado crítico se guarda rápidamente.
3. Se envía un job/evento en background a la cola.
4. Un proceso worker consume y ejecuta la tarea de forma asíncrona.

3. **Workloads async típicos**

- Notificaciones email/SMS/push
- Procesamiento de media (imágenes/video/PDF)
- Importaciones/exportaciones de datos
- Entrega/reintentos de webhooks
- Actualizaciones de índice de búsqueda
- Procesamiento de analytics/eventos

4. **Beneficios**

- Menor latencia visible para usuario.
- Mejor resiliencia (reintentos, dead-letter queues).
- Mayor throughput al desacoplar jobs pesados.
- Separación más limpia entre trabajo online y offline.

5. **Trade-offs**

- Complejidad operativa adicional (colas/workers/monitoring).
- Consistencia eventual entre escritura y efectos secundarios.
- Necesidad de idempotencia y handlers seguros para reintentos.

6. **Buenas prácticas**

- Mantén payloads de jobs mínimos (IDs, no objetos completos).
- Haz handlers idempotentes.
- Configura retry/backoff y manejo de dead-letter.
- Monitorea profundidad de cola, lag de workers y tasa de fallos.
- Define qué tareas son críticas síncronas vs diferidas asíncronamente.

En arquitectura PHP, el procesamiento asíncrono es una técnica clave para escalar experiencia de usuario y fiabilidad bajo carga real de producción.

</details>

<details>
<summary>56. ¿Qué son las colas (RabbitMQ, Kafka, colas Redis)?</summary>

#### PHP

Las colas son mecanismos de mensajería usados para desacoplar productores y consumidores, habilitando procesamiento asíncrono, buffering y ejecución fiable en background.

1. **Concepto central de cola**

- El productor publica un mensaje/job.
- El broker lo almacena temporalmente.
- El consumidor/worker lo procesa después.
- Esto quita trabajo pesado del flujo síncrono de request.

2. **Por qué las colas son importantes**

- Suavizan picos de tráfico (buffering).
- Mejoran tiempo de respuesta (offload de tareas en background).
- Aumentan fiabilidad con reintentos y manejo de dead-letter.
- Desacoplan servicios y componentes.

3. **Tecnologías de colas comunes en PHP**

- **RabbitMQ**:
  broker de mensajes tradicional, patrones de routing fuertes, acknowledgements, reintentos.
- **Kafka**:
  log de eventos distribuido, procesamiento de streams de alto throughput, mensajes re-reproducibles.
- **Colas basadas en Redis** (por ejemplo, colas de Laravel):
  simples y rápidas para muchos jobs de background a nivel aplicación.

4. **Casos típicos de uso de colas en PHP**

- Envío de email/SMS/push
- Entrega de webhooks
- Procesamiento de archivos/imágenes/video
- Indexación de búsqueda
- Generación de reportes
- Fan-out de integración/eventos

5. **Conceptos de fiabilidad**

- **Ack/Nack**: confirmar éxito o solicitar reintento.
- **Política de reintentos**: backoff exponencial, máximo de intentos.
- **Dead-letter queue (DLQ)**: aislar mensajes problemáticos/fallidos.
- **Idempotencia**: reprocesamiento seguro sin efectos secundarios duplicados.

6. **Buenas prácticas**

- Mantén payloads de mensajes pequeños (prefiere IDs sobre objetos grandes).
- Versiona esquemas de mensajes.
- Haz consumidores idempotentes y observables (logs/métricas/tracing).
- Monitorea profundidad de cola, lag de procesamiento, tasa de fallos y tasa de reintentos.
- Define SLAs claros para latencia de procesamiento.

Las colas son un bloque fundamental para sistemas PHP escalables y resilientes con workloads asíncronos.

</details>

<details>
<summary>57. ¿Qué es la arquitectura orientada a eventos en PHP?</summary>

#### PHP

La arquitectura orientada a eventos (EDA) es un estilo donde los componentes del sistema se comunican publicando y reaccionando a eventos en lugar de llamadas síncronas directas.

1. **Concepto central**

- Un productor emite un evento (por ejemplo, `OrderPlaced`).
- Los consumidores interesados se suscriben y lo manejan de forma independiente.
- El publicador no necesita saber qué consumidores existen.

2. **Por qué EDA es útil**

- Desacopla módulos/servicios.
- Mejora extensibilidad (nuevos consumidores pueden agregarse sin cambiar el publicador).
- Soporta procesamiento asíncrono y mejor escalabilidad.
- Hace explícitos los efectos secundarios como eventos de dominio/integración.

3. **Casos típicos de uso en PHP**

- Pedido creado -> enviar email, reservar stock, publicar analytics.
- Usuario registrado -> secuencia de bienvenida, sync con CRM, log de auditoría.
- Pago exitoso -> generación de factura, notificaciones, fulfillment.

4. **Tipos de eventos**

- **Eventos de dominio**: hechos significativos de negocio dentro del límite de dominio.
- **Eventos de integración**: eventos publicados para otros servicios/sistemas.

5. **Opciones de entrega en ecosistema PHP**

- Event bus/dispatcher en proceso (eventos a nivel framework).
- Entrega respaldada por cola/broker (RabbitMQ/Kafka/Redis streams/queues) para distribución async y entre servicios.

6. **Preocupaciones clave de diseño**

- Handlers idempotentes (un evento puede entregarse más de una vez).
- Garantías de orden (dependen de estrategia de transporte/tópico/partición).
- Política de reintentos y dead-letter ante fallos.
- Evolución de esquema/versión para payloads de eventos.

7. **Buenas prácticas**

- Usa payloads de eventos inmutables y versionados.
- Mantén handlers enfocados e independientes.
- Trata eventos como hechos (nombres en pasado: `UserRegistered`).
- Agrega observabilidad: correlation IDs, tracing, métricas de lag de procesamiento.

EDA en PHP ayuda a construir sistemas modulares y escalables donde los flujos pueden evolucionar sin acoplamiento fuerte entre componentes.

</details>

<details>
<summary>58. ¿Qué son WebSockets y cuándo usarlos?</summary>

#### PHP

WebSockets son un protocolo que crea una conexión persistente y bidireccional entre cliente y servidor, permitiendo intercambio de datos en tiempo real sin polling HTTP repetido.

1. **En qué se diferencian WebSockets de HTTP**

- HTTP: request/response, normalmente de corta vida e iniciado por el cliente.
- WebSocket: una conexión de larga vida donde ambos lados pueden enviar mensajes en cualquier momento.

2. **Cuándo WebSockets son útiles**

- Chat y mensajería en tiempo real.
- Dashboards/actualizaciones de monitoreo en vivo.
- Edición colaborativa e indicadores de presencia.
- Feeds de trading/mercado, eventos de gaming, notificaciones.

3. **Por qué no usar WebSockets en todas partes**

- Agrega complejidad operativa (estado de conexión, escalado, routing).
- No es necesario para páginas CRUD simples con actualizaciones poco frecuentes.
- En algunos casos, SSE o short polling pueden ser más simples y suficientes.

4. **Consideraciones de arquitectura en PHP**

- El modelo tradicional de requests PHP-FPM no es ideal para conexiones de larga vida.
- Enfoques comunes:
  servidores WebSocket dedicados (Ratchet/Swoole/RoadRunner),
  servicio realtime separado + integración con backend PHP vía Redis/message broker.

5. **Preocupaciones de escalado**

- Eficiencia de fan-out y broadcast de conexiones.
- Sticky sessions vs backplane pub/sub compartido.
- Escalado horizontal con capas de mensajería tipo Redis/Kafka/NATS.

6. **Seguridad y fiabilidad**

- Autentica handshake/sesión WebSocket.
- Valida esquema de mensajes y aplica autorización por canal/tópico.
- Aplica rate limits y protección contra abuso.
- Maneja reconexiones, heartbeats y backpressure.

7. **Regla general**

- Usa WebSockets cuando server push de baja latencia sea un requisito central del producto.
- Prefiere enfoques HTTP más simples cuando near-real-time sea suficiente.

WebSockets son una herramienta realtime potente en ecosistemas PHP cuando se combinan con el runtime y modelo de escalado adecuados.

</details>

<details>
<summary>59. ¿Cómo construyes APIs REST en PHP?</summary>

#### PHP

Construir APIs REST en PHP significa exponer recursos por HTTP usando rutas claras, métodos estándar, códigos de estado predecibles y contratos JSON consistentes.

1. **Principios REST centrales**

- Endpoints orientados a recursos (`/users`, `/orders/{id}`).
- Métodos HTTP correctos:
  `GET`, `POST`, `PUT/PATCH`, `DELETE`.
- Solicitudes stateless.
- Formato de representación consistente (normalmente JSON).

2. **Capas típicas de API en PHP**

- Capa de ruta/controlador (entrada/salida HTTP).
- Capa de validación/auth/middleware.
- Capa de servicio/caso de uso (lógica de negocio).
- Capa de repositorio/datos (persistencia).

3. **Esenciales de diseño**

- Estrategia de versionado (`/api/v1/...` o basada en headers).
- Envelope de respuesta estándar y formato de errores.
- Convenciones de paginación/filtrado/ordenación.
- Idempotencia para operaciones de escritura relevantes.

4. **Corrección HTTP**

- Devuelve códigos de estado significativos (`200`, `201`, `204`, `400`, `401`, `403`, `404`, `422`, `500`).
- Configura `Content-Type: application/json`.
- Usa headers de caché cuando corresponda.

5. **Base de seguridad**

- Autenticación (token/JWT/sesión según contexto).
- Checks de autorización por recurso/acción.
- Validación de entrada y codificación de salida.
- Rate limiting y protección contra abuso.
- Protección CSRF para APIs basadas en cookies.

6. **Calidad operativa**

- Logging estructurado + correlation IDs de request.
- Manejo centralizado de excepciones.
- Documentación OpenAPI/Swagger.
- Tests de contrato/integración para endpoints críticos.

7. **Forma típica de endpoint**

- `POST /api/v1/orders`
- Validar payload -> ejecutar caso de uso -> devolver `201 Created` con body/location del recurso.

8. **Guía práctica**

- Mantén controladores delgados.
- Mantén la lógica de negocio fuera de la capa HTTP.
- Haz contratos API explícitos y estables.

Una buena API REST en PHP no trata solo de rutas, sino de contratos consistentes, comportamiento seguro y fiabilidad operativa.

</details>

<details>
<summary>60. ¿Qué es GraphQL y cómo se usa en PHP?</summary>

#### PHP

GraphQL es un lenguaje de consultas de API y runtime donde los clientes solicitan exactamente los campos que necesitan desde un esquema tipado, en lugar de consumir payloads REST fijos.

1. **Conceptos centrales de GraphQL**

- **Schema**: contrato fuertemente tipado (types, fields, arguments).
- **Queries**: operaciones de lectura.
- **Mutations**: operaciones de escritura.
- **Resolvers**: funciones/métodos PHP que obtienen/calculan datos de campos.

2. **Por qué los equipos usan GraphQL**

- Evita over-fetching/under-fetching común en REST.
- Un único endpoint para recuperación flexible de datos.
- Mejor velocidad de frontend para necesidades complejas de datos en UI.
- Soporte fuerte de introspección y tooling.

3. **Cómo se usa en PHP**

- Define schema GraphQL en código/SDL.
- Implementa resolvers que llamen servicios/repositorios.
- Ejecuta la consulta contra el schema y devuelve respuesta JSON.
- Integra auth, validación, límites de complejidad y caché en la capa de ejecución.

4. **Opciones típicas de stack PHP**

- `webonyx/graphql-php` (implementación core de GraphQL)
- Integraciones/adaptadores de framework para ecosistemas Laravel/Symfony

5. **Trade-offs**

- Más complejidad que REST básico para APIs simples.
- Requiere controles estrictos de profundidad/complejidad de consulta para evitar consultas costosas.
- La estrategia de caché puede ser más difícil que el caché por endpoint REST.
- La disciplina de gobernanza/versionado del schema es esencial.

6. **Buenas prácticas**

- Mantén resolvers delgados; delega en servicios de aplicación.
- Usa patrón DataLoader para evitar llamadas backend N+1.
- Aplica auth por campo/recurso cuando sea necesario.
- Limita profundidad/complejidad de consultas y monitorea operaciones pesadas.
- Publica documentación del schema y trata cambios de schema como contratos.

GraphQL en PHP es más efectivo para productos ricos en datos con necesidades complejas de cliente, siempre que el equipo gestione cuidadosamente complejidad de consultas y gobernanza del schema.

</details>

<details>
<summary>61. ¿Qué es la autenticación de API (JWT, OAuth)?</summary>

#### PHP

La autenticación de API verifica quién llama a tu API y bajo qué permisos. Dos enfoques comunes son autenticación basada en token JWT y flujos OAuth 2.0 / OpenID Connect.

1. **Autenticación basada en JWT**

- Tras login exitoso, el servidor emite un token firmado (JWT).
- El cliente envía el token en cada solicitud (normalmente `Authorization: Bearer ...`).
- La API valida firma, expiración y claims.

Claims típicos de JWT:
- `sub` (subject/user id)
- `exp` (expiration)
- `iss`/`aud` (issuer/audience)
- roles/scopes opcionales

2. **OAuth 2.0 (framework de autorización)**

- Diseñado para acceso delegado y autorización de terceros.
- El acceso se concede mediante scopes y tiempos de vida de token.
- Flujos comunes: Authorization Code (+ PKCE), Client Credentials.

3. **OpenID Connect (OIDC)**

- Capa de identidad sobre OAuth 2.0.
- Añade ID token y claims estandarizados de identidad de usuario.

4. **JWT vs OAuth (distinción práctica)**

- JWT es formato/mecanismo de token.
- OAuth es protocolo de autorización.
- Los tokens OAuth pueden ser JWT u opacos.

5. **Buenas prácticas de seguridad**

- Usa solo HTTPS.
- Mantén access tokens de corta vida; rota refresh tokens de forma segura.
- Valida firma, issuer, audience, expiry en cada solicitud.
- Almacena tokens de forma segura del lado cliente (evita patrones inseguros de almacenamiento).
- Implementa estrategia de revocación/introspección cuando haga falta.

6. **Guía de implementación en PHP**

- Usa librerías probadas para validación JWT/OAuth/OIDC.
- Centraliza middleware de autenticación.
- Separa autenticación (quién) de autorización (qué está permitido).
- Representa permisos como roles/scopes/policies verificados a nivel de recurso.

Una autenticación de API sólida en PHP depende de corrección de protocolo, higiene de ciclo de vida de tokens y validación estricta en cada endpoint protegido.

</details>

<details>
<summary>62. ¿Qué es rate limiting y seguridad de API?</summary>

#### PHP

Rate limiting es un mecanismo de control que restringe cuántas solicitudes puede hacer un cliente en una ventana de tiempo dada. Es una parte central de una seguridad de API más amplia.

1. **Por qué se necesita rate limiting**

- Previene abuso y ataques de fuerza bruta.
- Protege recursos backend contra sobrecarga.
- Asegura uso justo entre clientes/tenants.
- Reduce impacto de integraciones con fallos o maliciosas.

2. **Estrategias comunes de rate limiting**

- Ventana fija (contadores simples por intervalo).
- Ventana deslizante (distribución más precisa).
- Token bucket / leaky bucket (amigable con ráfagas y límites sostenidos).

3. **Dónde se aplican límites**

- Por dirección IP
- Por API key/client id
- Por usuario/cuenta/tenant
- Por sensibilidad de endpoint (más estricto para endpoints de auth)

4. **Implementación típica en stacks PHP**

- Checks a nivel middleware usando contadores en Redis/memoria.
- Enforcement en reverse proxy/API gateway (Nginx, cloud API gateway).
- Devolver `429 Too Many Requests` con headers de reintento.

5. **Base de seguridad de API (más allá de rate limits)**

- Autenticación fuerte (JWT/OAuth/OIDC).
- Checks de autorización por recurso/acción.
- Validación de entrada y codificación de salida.
- HTTPS en todas partes + headers seguros.
- Límites de tamaño/tiempo de request y control de timeouts.
- Audit logging, detección de anomalías y alerting.

6. **Buenas prácticas**

- Usa controles por capas: gateway + middleware de app.
- Aplica cuotas diferentes según plan/nivel de confianza.
- Agrega manejo de ráfagas y degradación elegante.
- Protege endpoints de login/token con reglas más estrictas y bloqueos.
- Monitorea hits de límites, solicitudes bloqueadas y patrones de ataque.

Rate limiting es un pilar de la seguridad de API; la protección real viene de combinarlo con autenticación, autorización, validación y observabilidad.

</details>

<details>
<summary>63. ¿Qué es la pirámide de testing en PHP?</summary>

#### PHP

La pirámide de testing es un modelo de estrategia de pruebas que recomienda muchas pruebas rápidas de bajo nivel y menos pruebas lentas de alto nivel, para equilibrar confianza, velocidad y costo de mantenimiento.

1. **Capas de la pirámide**

- **Base (la más grande): tests unitarios**
  pruebas rápidas y aisladas para funciones/clases/reglas de negocio.
- **Medio: tests de integración**
  verifican colaboración entre módulos (BD, caché, cola, adaptadores externos).
- **Cima (la más pequeña): tests end-to-end/API/UI**
  validan flujos completos de usuario en todo el sistema.

2. **Por qué este modelo funciona**

- Los tests unitarios son baratos y se ejecutan rápido en grandes cantidades.
- Los tests de integración detectan problemas de límites y wiring.
- Los tests E2E dan confianza realista, pero son más lentos y frágiles.

3. **Mapeo específico para PHP**

- Unit: PHPUnit/Pest con mocks/stubs.
- Integración: contenedores de BD reales, repositorios, clientes HTTP en entorno controlado.
- E2E/API: tests a nivel request contra app/servicio en ejecución.

4. **Anti-patrones comunes**

- “Cono de helado”: demasiados tests UI/E2E y muy pocos unitarios.
- Mockear todo en exceso, perdiendo confianza de integración.
- Sin tests de contrato para integraciones externas críticas.

5. **Recomendaciones prácticas**

- Mantén la mayoría de pruebas en nivel unitario.
- Agrega tests de integración enfocados alrededor de límites críticos.
- Mantén la suite E2E pequeña, estable y centrada en procesos críticos de negocio.
- Ejecuta suites rápidas en cada commit; suites más pesadas en gates de main/pre-release.

6. **Resultado**

Una pirámide saludable da feedback rápido a desarrolladores y alta confianza de release sin tiempo excesivo de CI ni mantenimiento de pruebas inestables.

</details>

<details>
<summary>64. ¿Qué es unit testing (PHPUnit / Pest)?</summary>

#### PHP

Unit testing verifica el comportamiento de las piezas de código más pequeñas que se pueden probar (funciones, métodos, clases) en aislamiento de sistemas externos.

1. **Qué deben cubrir los tests unitarios**

- Reglas de negocio y cálculos.
- Casos límite y validación de entrada.
- Comportamiento de errores/excepciones.
- Ramas de lógica determinista.

2. **Principio de aislamiento**

- Los tests unitarios no deben depender de BD real, red, filesystem o servicios de cola.
- Las dependencias externas se reemplazan con test doubles (mocks/stubs/fakes).

3. **Herramientas PHP**

- **PHPUnit**: framework de testing clásico y ampliamente adoptado.
- **Pest**: sintaxis expresiva construida sobre el ecosistema de PHPUnit.

4. **Ejemplo simple (estilo PHPUnit)**

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

5. **Por qué importan los tests unitarios**

- Feedback rápido durante desarrollo.
- Refactorización más segura.
- Mejor documentación del comportamiento esperado.
- Detección temprana de regresiones.

6. **Buenas prácticas**

- Mantén tests pequeños, enfocados y deterministas.
- Usa estructura clara arrange-act-assert.
- Nombra tests por comportamiento esperado.
- Evita over-mocking de lógica interna.
- Ejecuta tests unitarios en cada commit en CI.

Unit testing con PHPUnit/Pest es la base de una entrega PHP fiable porque proporciona confianza rápida y precisa en la lógica central.

</details>

<details>
<summary>65. ¿Qué es integration testing?</summary>

#### PHP

Integration testing verifica que múltiples componentes funcionen correctamente juntos (por ejemplo, lógica de aplicación + base de datos + caché + adaptadores externos), manteniéndose más acotado que tests end-to-end completos.

1. **En qué se enfocan los tests de integración**

- Límites de módulos y colaboración.
- Correctitud de persistencia/lectura de datos.
- Comportamiento de adaptadores de infraestructura.
- Correctitud de configuración y wiring.

2. **Cómo se diferencia de tests unitarios**

- Tests unitarios aíslan un componente y mockean dependencias.
- Tests de integración usan dependencias reales o casi reales para validar interacciones.

3. **Escenarios típicos de integración en PHP**

- Repositorio con BD de prueba/contenedor real.
- Adaptador de cliente HTTP contra sandbox/mock server.
- Flujo de publicación/consumo de cola en entorno controlado.
- Interacción de ruta + middleware + controlador + servicio del framework.

4. **Por qué importan los tests de integración**

- Detectan problemas que los mocks no revelan (mismatch de schema SQL, bugs de serialización, errores de config).
- Aumentan confianza en límites críticos.
- Reducen sorpresas en producción por acoplamiento de infraestructura.

5. **Buenas prácticas**

- Ejecuta contra infraestructura de test dedicada (BD/caché aisladas).
- Controla setup/teardown de datos de forma determinista.
- Mantén alcance enfocado: una preocupación de integración por test.
- Evita dependencia de red innecesaria cuando bastan stubs de contrato.
- Incluye suite de integración en CI para paths críticos.

6. **Trade-off**

- Son más lentos y pesados que tests unitarios, por eso deben ser menos y bien dirigidos.

Los tests de integración son el puente entre confianza rápida de unit tests y confianza del sistema completo en pipelines de entrega PHP.

</details>

<details>
<summary>66. ¿Qué es mocking y por qué se necesita?</summary>

#### PHP

Mocking es una técnica de testing donde dependencias reales se reemplazan por test doubles controlados para aislar la unidad bajo prueba y verificar interacciones.

1. **Por qué se necesita mocking**

- Aislar lógica de negocio de sistemas externos (BD, HTTP, cola, filesystem).
- Hacer tests rápidos y deterministas.
- Simular escenarios raros/de error difíciles de reproducir con servicios reales.
- Verificar contratos de colaboración (método llamado con argumentos esperados).

2. **Tipos comunes de test doubles**

- **Stub**: devuelve valores predefinidos.
- **Mock**: verifica interacciones/llamadas esperadas.
- **Fake**: implementación funcional ligera (por ejemplo, repositorio en memoria).
- **Spy**: registra llamadas para aserciones posteriores.

3. **Concepto de ejemplo en PHP**

Probar `OrderService` mockeando `PaymentGatewayInterface` y `OrderRepositoryInterface`, y luego afirmar:
- el servicio devuelve resultado esperado
- gateway llamado una vez con monto correcto
- repository save llamado con estado esperado de entidad

4. **Dónde mocking es apropiado**

- Tests unitarios de servicios de dominio/aplicación.
- Testing de rutas de error para dependencias externas.
- Verificación de contratos en límites de módulo.

5. **Dónde mocking no es suficiente**

- Comportamiento de integración con protocolos reales de BD/red.
- Problemas de wiring/configuración de framework.
- Características de rendimiento y semántica de transacciones.

6. **Buenas prácticas**

- Mockea solo límites externos, no lógica pura interna.
- Mantén expectativas enfocadas en comportamiento observable.
- Prefiere interfaces para dependencias mockeables.
- Combina tests unitarios + de integración (mocking no es estrategia completa por sí sola).

Mocking es esencial para tests unitarios PHP rápidos y aislados, pero debe equilibrarse con tests de integración para confianza en el sistema real.

</details>

<details>
<summary>67. ¿Qué es code coverage?</summary>

#### PHP

Code coverage es una métrica que muestra qué partes del código fuente fueron ejecutadas por pruebas automatizadas.

1. **Qué mide coverage**

- **Line coverage**: líneas ejecutadas.
- **Branch/condition coverage**: ramas de decisión ejecutadas.
- **Function/method coverage**: unidades invocables ejecutadas.

2. **Por qué es útil**

- Señala áreas sin tests.
- Ayuda a priorizar dónde faltan pruebas.
- Soporta evaluación de riesgo de regresión durante refactorización.

3. **Lo que coverage NO garantiza**

- Coverage alto no significa automáticamente alta calidad de tests.
- Los tests pueden ejecutar código sin validar comportamiento correcto.
- Casos límite críticos pueden seguir faltando pese a buenos porcentajes.

4. **Tooling en PHP**

- PHPUnit/Pest pueden generar reportes de coverage.
- Normalmente depende de drivers Xdebug o PCOV.
- Reportes pueden producirse en texto, HTML o formatos CI.

5. **Uso práctico en equipos**

- Rastrea tendencias en el tiempo en lugar de perseguir un único número absoluto.
- Define umbrales mínimos sensatos para módulos críticos.
- Usa deltas de coverage en checks de PR para prevenir regresiones de pruebas.

6. **Buenas prácticas**

- Enfócate primero en probar lógica de negocio crítica y rutas riesgosas.
- Combina coverage con mutation testing/análisis estático cuando sea posible.
- Revisa calidad de aserciones, no solo líneas ejecutadas.
- Evita tests flaky o de bajo valor para no “jugar” con coverage.

Code coverage es una señal útil de completitud de pruebas, pero debe interpretarse junto con calidad de tests y contexto de riesgo, no como objetivo aislado.

</details>

<details>
<summary>68. ¿Qué es análisis estático (PHPStan, Psalm)?</summary>

#### PHP

El análisis estático revisa código PHP sin ejecutarlo para detectar temprano problemas de tipos, bugs potenciales, código muerto y violaciones de arquitectura.

1. **Qué encuentra el análisis estático**

- Incompatibilidades de tipos y tipos imposibles.
- Problemas de nullability y acceso a variable/propiedad/método no definido.
- Tipos de retorno incorrectos y casts inseguros.
- Código inalcanzable/muerto y algunos patrones de mal uso de API.

2. **Herramientas principales**

- **PHPStan**: ampliamente adoptada, niveles de strictness, fuerte integración con ecosistema.
- **Psalm**: sistema de tipos avanzado, inferencia potente, opciones de taint analysis.

3. **Por qué es valioso**

- Encuentra defectos antes de runtime y antes de que los tests puedan cubrirlos.
- Mejora seguridad de refactorización en codebases grandes.
- Fomenta tipado más fuerte y contratos más claros.
- Reduce incidentes en producción causados por errores básicos de tipo/flujo.

4. **Cómo lo usan los equipos**

- Ejecutarlo en CI en cada PR.
- Empezar con strictness moderado y aumentarlo gradualmente.
- Mantener baseline para issues legacy mientras se previenen nuevos.

5. **Buenas prácticas**

- Agrega type hints/return types de forma consistente.
- Usa anotaciones genéricas donde haga falta (colecciones, repositorios).
- Corrige problemas de tipado de raíz en lugar de suprimir warnings.
- Mantén config de análisis versionada y revisada como código.

6. **Análisis estático vs tests**

- El análisis estático no reemplaza tests.
- Complementa tests unitarios/de integración demostrando correctitud estructural/de tipos en rutas que los tests pueden no cubrir.

El análisis estático con PHPStan/Psalm es un quality gate de alto impacto para proyectos PHP modernos, especialmente durante refactorización continua.

</details>

<details>
<summary>69. ¿Qué es Rector y cómo se usa para refactorización?</summary>

#### PHP

Rector es una herramienta de refactorización automatizada para PHP que transforma código fuente usando reglas predefinidas y personalizadas, ayudando a actualizar y modernizar codebases de forma segura a escala.

1. **Qué hace Rector**

- Aplica transformaciones de código basadas en AST.
- Actualiza sintaxis/features entre versiones de PHP.
- Refactoriza patrones de uso de framework/librería.
- Automatiza cambios mecánicos repetitivos.

2. **Casos típicos de uso**

- Upgrade desde versiones antiguas de PHP a estándares más nuevos.
- Migrar APIs deprecated a alternativas actuales.
- Aplicar constructos modernos del lenguaje (typed properties, constructor promotion, etc.).
- Limpieza de codebase a gran escala antes de adoptar análisis estático estricto.

3. **Cómo se usa en la práctica**

1. Configurar `rector.php` con sets de reglas.
2. Ejecutar Rector sobre rutas seleccionadas.
3. Revisar diff generado.
4. Ejecutar tests/análisis estático.
5. Hacer commit de lotes incrementales y seguros.

4. **Por qué los equipos usan Rector**

- Acelera drásticamente el trabajo de modernización.
- Reduce error humano en refactors repetitivos.
- Mantiene la refactorización consistente entre módulos.

5. **Buenas prácticas**

- Ejecuta Rector en alcances enfocados, no en todo el codebase legacy de una vez.
- Mantén cambios pequeños y revisables.
- Valida siempre con tests + PHPStan/Psalm tras la transformación.
- Fija versión de Rector en tooling para reproducibilidad.
- Combina refactorización automatizada con revisión arquitectónica manual.

6. **Limitación importante**

- Rector maneja bien transformaciones mecánicas, pero no reemplaza criterio arquitectónico ni decisiones de rediseño específicas de dominio.

Rector es más efectivo como parte de un pipeline de refactorización con análisis estático y tests, no como herramienta aislada de “migración con un clic”.

</details>

<details>
<summary>70. ¿Qué es la aplicación de estándares de código (PHP-CS-Fixer)?</summary>

#### PHP

La aplicación de estándares de código es la práctica de verificar y corregir automáticamente reglas de estilo para que el codebase se mantenga consistente, legible y fácil de revisar.

1. **Por qué importan los estándares de código**

- Mejora legibilidad entre equipos.
- Reduce ruido de estilo en pull requests.
- Hace que code reviews se enfoquen en lógica, no en formato.
- Mantiene coherencia en codebases de larga vida.

2. **Qué hace PHP-CS-Fixer**

- Escanea archivos PHP según reglas de estilo configuradas.
- Reescribe automáticamente problemas de formato/estilo.
- Soporta rule sets estándar (por ejemplo, PSR-12) y reglas personalizadas.

3. **Flujo típico**

- Configurar reglas en `.php-cs-fixer.php`.
- Ejecutar checker en CI para prevenir drift.
- Ejecutar fixer en local/pre-commit para autoformatear archivos modificados.

4. **Categorías comunes de reglas**

- Orden de imports y eliminación de imports no usados.
- Estilo de espacios/indentación/llaves.
- Normalización de sintaxis de arrays/funciones.
- Reglas de tipado estricto y preferencia por sintaxis moderna.

5. **Buenas prácticas**

- Acordar temprano un único estándar para todo el proyecto.
- Auto-fix dentro del flujo de desarrollo (pre-commit/hooks/integración de editor).
- Mantener CI como gate de enforcement (modo `--dry-run`).
- Aplicar reformateos grandes por separado de cambios de feature para mantener diffs claros.

6. **Herramientas relacionadas**

- PHP-CS-Fixer (auto-fix de formato/estilo).
- PHP_CodeSniffer (verificación de reglas y análisis de estándares de código).
- Combina herramientas de estilo con PHPStan/Psalm para calidad más allá del formato.

La aplicación de estándares con herramientas como PHP-CS-Fixer es una forma de bajo costo para mejorar mantenibilidad y velocidad de equipo en proyectos PHP.

</details>

<details>
<summary>71. ¿Qué es un pipeline CI/CD para aplicaciones PHP?</summary>

#### PHP

Un pipeline CI/CD es un flujo automatizado que construye, prueba, verifica y despliega aplicaciones PHP de forma consistente desde el commit hasta producción.

1. **Objetivos de CI (Continuous Integration)**

- Validar cada cambio rápidamente.
- Detectar bugs temprano mediante checks automatizados.
- Mantener la rama principal siempre liberable.

2. **Etapas típicas de CI para PHP**

1. Instalar dependencias (`composer install`).
2. Checks estáticos (PHPStan/Psalm, estándares de código).
3. Tests unitarios/de integración (PHPUnit/Pest).
4. Build/package de artefactos (imagen Docker o bundle de despliegue).

3. **Objetivos de CD (Continuous Delivery/Deployment)**

- Entregar artefactos validados de forma segura a entornos.
- Automatizar pasos de rollout y minimizar errores manuales.
- Soportar rollback rápido ante incidentes.

4. **Etapas típicas de CD**

- Despliegue a staging.
- Ejecutar smoke/health checks.
- Promover el mismo artefacto a producción.
- Monitorear métricas y logs post-despliegue.

5. **Buenas prácticas específicas de PHP**

- Usa instalaciones reproducibles basadas en lockfile.
- Construye artefactos inmutables una vez y reutilízalos entre entornos.
- Ejecuta migraciones de BD con estrategia controlada.
- Mantén secretos/config fuera del artefacto.
- Usa patrones de rollout sin downtime (blue-green/canary/rolling).

6. **Quality gates**

- Estado requerido de tests en verde.
- Umbral de análisis estático.
- Checks de seguridad (dependency audit/SAST).
- Checks opcionales de performance smoke para endpoints críticos.

7. **Resultado**

Un pipeline CI/CD sólido mejora frecuencia de releases, fiabilidad y confianza del equipo, reduciendo riesgo de producción en la entrega PHP.

</details>

<details>
<summary>72. ¿Cómo despliegas aplicaciones PHP?</summary>

#### PHP

Desplegar aplicaciones PHP significa entregar un artefacto probado a producción con configuración de runtime predecible, downtime mínimo y seguridad de rollback.

1. **Destinos comunes de despliegue**

- VM/bare metal tradicional con Nginx/Apache + PHP-FPM.
- Plataformas de contenedores (Docker, Kubernetes, ECS).
- Servicios de plataforma (variantes PaaS/serverless).

2. **Flujo recomendado de despliegue**

1. Construir artefacto inmutable (imagen/paquete) en CI.
2. Ejecutar tests/checks estáticos/scans de seguridad.
3. Desplegar artefacto en staging.
4. Ejecutar smoke checks y health checks.
5. Promover el mismo artefacto a producción.

3. **Esenciales de runtime**

- Configuración y secretos por entorno (no hardcodeados).
- Extensiones PHP correctas y settings de OPcache.
- Conectividad a BD/caché/cola verificada al arranque.
- Logging estructurado y monitoreo habilitados.

4. **Estrategia de migraciones de base de datos**

- Aplica migraciones compatibles hacia atrás antes de cambiar tráfico.
- Usa enfoque expand-and-contract para cambios de schema riesgosos.
- Mantén scripts de migración versionados y repetibles.

5. **Técnicas de cero/bajo downtime**

- Despliegues blue-green, rolling o canary.
- Reloads elegantes de workers (PHP-FPM/process manager).
- Cambio de tráfico basado en health checks vía load balancer.

6. **Estrategia de rollback**

- Rollback rápido al artefacto/versión anterior.
- Plan controlado de rollback de BD o forward-fix.
- Ventana de monitoreo post-deploy con alerting.

7. **Buenas prácticas**

- Nunca desplegar directamente desde máquina local.
- Mantener proceso de despliegue automatizado y auditable.
- Usar infraestructura como código cuando sea posible.
- Separar claramente preocupaciones de build-time y runtime.

Un buen despliegue PHP es un sistema de ingeniería: artefactos reproducibles, mecánica de rollout segura, observabilidad y rollback fiable.

</details>

<details>
<summary>73. ¿Qué es blue-green deployment?</summary>

#### PHP

Blue-green deployment es una estrategia de release donde se mantienen dos entornos de producción idénticos: uno activo (sirviendo tráfico) y otro inactivo (candidato para la próxima versión).

1. **Cómo funciona**

- **Blue**: entorno live actual.
- **Green**: nueva versión desplegada y validada en paralelo.
- Tras pasar checks, el tráfico se cambia de Blue a Green.
- El entorno antiguo permanece disponible para rollback rápido.

2. **Por qué los equipos lo usan**

- Minimiza downtime de despliegue.
- Reduce riesgo de release con rollback casi instantáneo.
- Permite verificación realista antes del switch en un stack parecido a producción.

3. **Flujo típico de rollout**

1. Desplegar nuevo release PHP en entorno inactivo.
2. Ejecutar health checks/smoke tests/estrategia de migraciones.
3. Cambiar load balancer/router al nuevo entorno.
4. Monitorear tasas de error/latencia.
5. Mantener temporalmente el entorno previo para rollback.

4. **Consideraciones clave para apps PHP**

- La estrategia de sesión debe soportar cambio de entorno (Redis/session store compartido).
- Assets estáticos/versionado deben ser compatibles entre ambos entornos.
- Cambios de BD deben ser backward-compatible durante la ventana de transición.
- Workers de cola y cron jobs deben evitar efectos secundarios duplicados.

5. **Ventajas**

- Ruta rápida de rollback.
- Despliegues más seguros para sistemas de alto tráfico.
- Separación clara de release “actual” vs “candidato”.

6. **Trade-offs**

- Mayor costo de infraestructura (dos entornos).
- Más complejidad operativa alrededor de compatibilidad de datos/schema.

Blue-green es un patrón de despliegue sólido para sistemas PHP en producción donde uptime y velocidad de rollback son críticos.

</details>

<details>
<summary>74. ¿Qué es una estrategia de rollback?</summary>

#### PHP

Una estrategia de rollback es un plan predefinido para restaurar rápidamente una versión estable anterior cuando un despliegue causa incidentes (errores, regresiones, caídas de rendimiento, problemas de datos).

1. **Por qué una estrategia de rollback es crítica**

- Reduce duración de incidentes e impacto en clientes.
- Evita acciones de emergencia ad-hoc durante caídas.
- Aumenta confianza en releases frecuentes.

2. **Qué debe estar listo para rollback**

- Versión de artefacto/imagen de aplicación.
- Versión de infraestructura/configuración.
- Estado de feature flags/toggles.
- Plan de compatibilidad de migraciones de base de datos.

3. **Enfoques comunes de rollback**

- **Artifact rollback**: redeploy del build anterior conocido como estable.
- **Traffic rollback**: volver tráfico al entorno anterior (reversión blue-green/canary).
- **Feature rollback**: desactivar feature flag problemático sin redeploy completo.

4. **Realidad del rollback de base de datos**

- El rollback de BD suele ser la parte más difícil.
- Prefiere migraciones backward-compatible:
  primero expandir, luego contraer.
- Usa forward-fix cuando un rollback real de schema sea riesgoso.

5. **Checklist operativo**

- Define umbrales disparadores de rollback (tasa de error, latencia, checks fallidos).
- Mantén el release previo inmediatamente desplegable.
- Automatiza pasos de rollback en pipeline/runbooks.
- Verifica salud tras rollback y continúa monitoreo.

6. **Buenas prácticas**

- Ensaya rollback en staging regularmente.
- Mantén releases pequeños para reducir blast radius.
- Acopla rollout y rollback con observabilidad (logs/métricas/traces).
- Documenta ownership y flujo de decisiones de incidentes.

Una estrategia de rollback sólida es un mecanismo central de fiabilidad para la entrega PHP en producción, especialmente en entornos de despliegue de alta frecuencia.

</details>

<details>
<summary>75. ¿Qué es serverless PHP (Laravel Vapor, Bref)?</summary>

#### PHP

Serverless PHP es un modelo de ejecución donde tu código PHP corre en funciones/plataformas cloud gestionadas sin administrar directamente servidores tradicionales.

1. **Idea central**

- Despliegas código/funciones, no fleets de VMs.
- El proveedor cloud gestiona provisioning, scaling y gran parte de operaciones.
- El cobro normalmente se basa en tiempo de ejecución y solicitudes.

2. **Opciones comunes de serverless PHP**

- **Laravel Vapor**:
  plataforma enfocada en Laravel sobre AWS (Lambda, integraciones gestionadas).
- **Bref**:
  runtime/tooling open-source para ejecutar PHP en AWS Lambda (soporte agnóstico al framework).

3. **Por qué los equipos usan serverless PHP**

- Auto-escalado horizontal rápido.
- Menor carga operativa (menos patching/provisioning).
- Eficiencia de costos para tráfico con picos o baseline bajo.
- Menor time-to-production para workloads de API/backoffice.

4. **Implicaciones de arquitectura**

- Ejecución de funciones stateless.
- Estado externalizado (BD, Redis, object storage, colas).
- Triggers orientados a eventos (HTTP, colas, cron, eventos de objetos).
- Deben considerarse cold starts y límites de ejecución.

5. **Mejores casos de uso**

- APIs con tráfico variable.
- Jobs/eventos en background.
- Tareas programadas y automatización ligera.
- MVPs y equipos optimizando velocidad de entrega.

6. **Trade-offs**

- Restricciones de plataforma/runtime y timeouts.
- Riesgo de vendor lock-in.
- Impacto de latencia por cold-start en algunos endpoints.
- Debugging/observabilidad pueden requerir configuración extra.

7. **Buenas prácticas**

- Mantén funciones pequeñas y enfocadas.
- Optimiza tiempo de bootstrap y huella de dependencias.
- Usa colas asíncronas para trabajo de larga duración.
- Configura logging/métricas/tracing robustos desde el día uno.
- Diseña handlers idempotentes y flujos seguros para reintentos.

Serverless PHP con Vapor/Bref es una opción sólida para arquitecturas escalables de baja operación cuando las características de carga encajan con el modelo serverless.

</details>

<details>
<summary>76. ¿Qué son microservices vs monolith en PHP?</summary>

#### PHP

Monolith y microservices son estilos de arquitectura para estructurar sistemas. En PHP, ambos pueden funcionar bien si se eligen según tamaño del equipo, complejidad del dominio y madurez operativa.

1. **Monolith (una sola app desplegable)**

- Un codebase/una unidad desplegable que contiene múltiples capacidades de negocio.
- Runtime compartido y normalmente base de datos compartida.

**Pros**
- Desarrollo, testing y despliegue más simples.
- Menor overhead operativo.
- Debug local más sencillo y transacciones entre módulos.

**Contras**
- Puede volverse difícil de evolucionar si los límites son débiles.
- Despliegues grandes pueden aumentar riesgo de release.
- El escalado suele ser de grano grueso (toda la app).

2. **Microservices (múltiples servicios desplegables de forma independiente)**

- Sistema dividido en servicios pequeños alineados a dominios de negocio.
- Cada servicio posee su lógica y a menudo su datastore.

**Pros**
- Escalado/despliegue independiente por servicio.
- Límites claros de ownership.
- Flexibilidad tecnológica/runtime por servicio.

**Contras**
- Mayor complejidad (red, observabilidad, auth, reintentos, consistencia de datos).
- Desarrollo local y debug cross-service más difíciles.
- Requiere madurez significativa de DevOps/plataforma.

3. **Realidad práctica específica de PHP**

- Muchos equipos tienen éxito empezando con un monolito modular.
- Microservices valen la pena cuando bounded contexts claros y escalado de equipos justifican el costo operativo.

4. **Guía de decisión**

- Elige **monolith/monolito modular** cuando:
  el producto está en fase temprana, el equipo es pequeño/mediano y la velocidad importa más.
- Elige **microservices** cuando:
  los dominios son claramente separables, las necesidades de escalado difieren mucho y las capacidades de plataforma son maduras.

5. **Error común**

- Empezar con microservices demasiado pronto crea complejidad accidental sin retorno de negocio.

En ecosistemas PHP, el camino pragmático suele ser: monolito bien estructurado primero y luego extracción selectiva a servicios cuando restricciones objetivas lo exijan.

</details>

<details>
<summary>77. ¿Qué es la arquitectura de monolito modular?</summary>

#### PHP

Un monolito modular es una única aplicación desplegable estructurada como módulos internos claramente separados, con límites y contratos explícitos.

1. **Idea central**

- Una sola aplicación/runtime/unidad de despliegue.
- Múltiples módulos de negocio (bounded contexts) dentro de ella.
- Límites internos fuertes para reducir acoplamiento.

2. **En qué se diferencia**

- Vs monolito clásico:
  el monolito modular impone límites de módulos estrictos y reglas de dependencias.
- Vs microservices:
  mantiene una sola unidad desplegable y evita complejidad de sistemas distribuidos.

3. **Estructura típica de módulos en PHP**

- `Modules/Orders/...`
- `Modules/Billing/...`
- `Modules/Users/...`

Cada módulo contiene su propia:
- lógica de dominio
- servicios de aplicación/casos de uso
- adaptadores de infraestructura
- handlers HTTP/API (o interfaces mapeadas)

4. **Por qué los equipos lo eligen**

- Desarrollo más rápido que microservices.
- Debug local y transacciones más sencillos.
- Menor overhead operativo.
- Buen camino para organización orientada al dominio y futura extracción a servicios.

5. **Prácticas para aplicar límites**

- Comunicar entre módulos vía interfaces/eventos, no por internos directos.
- Evitar utilidades “god” mutables compartidas entre módulos.
- Usar análisis estático/tests para aplicar dirección de dependencias.
- Mantener ownership de base de datos claro (aunque esté físicamente compartida).

6. **Cuándo encaja bien**

- El producto y el equipo crecen, pero la complejidad de microservices aún es prematura.
- Se necesita separación de dominio fuerte con modelo de despliegue simple.

7. **Ruta de evolución**

- Empezar con monolito modular.
- Extraer módulos seleccionados a servicios solo cuando presión de escala/equipo/ownership sea real y medible.

El monolito modular suele ser la arquitectura más pragmática para equipos PHP que quieren límites limpios hoy, sin overhead prematuro de sistemas distribuidos.

</details>

<details>
<summary>78. ¿Cuáles son las vulnerabilidades PHP comunes en proyectos reales?</summary>

#### PHP

La mayoría de incidentes reales de seguridad en PHP no vienen del lenguaje en sí, sino de manejo inseguro de entrada, controles débiles de auth/sesión y problemas de dependencias/configuración.

1. **Vulnerabilidades de inyección**

- SQL Injection por construcción insegura de consultas.
- Command Injection al pasar entrada no confiable a llamadas shell/system.
- Inyecciones tipo Header/LDAP/NoSQL en capas de integración.

2. **Vulnerabilidades cross-site**

- XSS (stored/reflected/DOM) por falta de escape contextual de salida.
- CSRF en flujos con auth por cookies sin token y protecciones SameSite.

3. **Fallos de autenticación y autorización**

- Manejo débil de contraseñas o falta de MFA para roles críticos.
- Control de acceso roto (IDOR/BOLA): un usuario accede a recursos de otros cambiando IDs.
- Falta de checks de autorización server-side en endpoints sensibles.

4. **Problemas de sesión y tokens**

- Flags de cookie inseguras (falta de `Secure`, `HttpOnly`, `SameSite`).
- Session fixation/hijacking por mala rotación de ID.
- Tokens API filtrados o de larga vida sin estrategia de revocación.

5. **Riesgos de manejo de archivos**

- Uploads inseguros (sin validación de tipo/contenido, uploads ejecutables).
- Path traversal (`../`) por rutas de archivo sin validación.
- Deserialización insegura o parseo inseguro de archivos no confiables.

6. **Riesgos de configuración y dependencias**

- Modo debug habilitado en producción.
- Secretos expuestos en repo/logs/dumps de entorno.
- Dependencias desactualizadas con CVEs conocidos.
- CORS/CSP/headers de seguridad mal configurados.

7. **Cómo mitigarlo de forma sistemática**

- Validación estricta de entrada + codificación de salida según contexto.
- Prepared statements y capas de consulta seguras.
- Políticas de authz centralizadas y checks deny-by-default.
- Gestión segura del ciclo de vida de sesiones/tokens.
- Escaneo/parcheo de dependencias y config de producción endurecida.
- Testing de seguridad regular (SAST/DAST), logging y playbooks de incidentes.

La seguridad en proyectos PHP es principalmente una disciplina de diseño seguro, defaults seguros y verificación continua en código, runtime y operaciones.

</details>

<details>
<summary>79. ¿Cómo detectas memory leaks en PHP?</summary>

#### PHP

En PHP, los “memory leaks” a menudo no son fugas permanentes clásicas de código a nivel script, sino crecimiento de memoria causado por procesos de larga ejecución, referencias retenidas, buffers grandes en memoria, fugas a nivel de extensiones o fragmentación del asignador.

1. **Primero identifica dónde aparece el comportamiento tipo fuga**

- Modelo FPM/request: la memoria debería liberarse al terminar la request; el crecimiento suele indicar problemas a nivel worker o requests sobredimensionadas.
- Workers de larga ejecución (consumidores de cola, daemons, Swoole/RoadRunner): retener estado entre jobs es una fuente común.
- Scripts batch CLI: arrays/cachés sin límites pueden simular fugas.

2. **Instrumenta memoria dentro del código**

- Usa `memory_get_usage(true)` y `memory_get_peak_usage(true)` alrededor de etapas importantes del pipeline.
- Loguea memoria por iteración/job para detectar tendencia de crecimiento monótono.
- Agrega contadores de items procesados para correlacionar memoria con tamaño de carga.

3. **Usa diagnósticos a nivel runtime/proceso**

- Observa RSS de workers en el tiempo con `ps`, `top`, métricas de contenedor o APM.
- Compara uso de memoria a nivel PHP vs nivel SO para detectar comportamiento de asignador/fragmentación.
- En FPM, monitorea memoria de workers del pool y patrones de reinicio.

4. **Usa profilers y herramientas especializadas**

- Xdebug/Blackfire/Tideways para hotspots de asignación y rutas de llamada pesadas.
- Valgrind/ASan para fugas en extensiones C o a nivel nativo (builds debug, más lentos pero precisos).
- Toolbars/profilers de framework para snapshots de memoria por request.

5. **Causas raíz comunes a revisar**

- Arrays estáticos/globales acumulando datos entre jobs.
- Event listeners/closures capturando objetos grandes sin querer.
- Identity maps ORM o resultados de consulta retenidos demasiado tiempo.
- Copias de strings/payloads JSON grandes durante transformaciones.
- Referencias circulares + GC retrasado en loops largos.

6. **Patrones de mitigación tras detectar**

- Procesa datos en chunks/streams en vez de colecciones completas en memoria.
- Haz `unset()` explícito de variables grandes y llama ocasionalmente `gc_collect_cycles()` en loops largos.
- Recrea proceso worker tras N jobs/tiempo (`--max-jobs`, reinicios del supervisor).
- Configura memory limits sensatos y comportamiento fail-fast.
- Mantén dependencias/extensiones actualizadas cuando se corrigen fugas nativas upstream.

El enfoque práctico es: medir tendencia, aislar hotspot, confirmar con profiling y aplicar límites de ciclo de vida para procesos de larga ejecución.

</details>

<details>
<summary>80. ¿Cómo optimizas el uso de memoria?</summary>

#### PHP

La optimización de memoria en PHP consiste principalmente en controlar el ciclo de vida de datos, reducir copias innecesarias y usar procesamiento por streaming/chunks en lugar de cargar todo de una vez.

1. **Procesa datos de forma incremental**

- Prefiere generators (`yield`) para datasets grandes en lugar de construir arrays enormes.
- Lee archivos/streams línea por línea o en chunks.
- Pagina lecturas de BD (`LIMIT/OFFSET` o APIs cursor/chunk) para jobs batch.

2. **Evita copias innecesarias**

- Minimiza concatenación de strings en loops ajustados; usa estrategias de buffering.
- Evita `array_merge` repetido sobre arrays grandes dentro de loops.
- Ten cuidado con transformaciones que duplican estructuras grandes.

3. **Libera memoria temprano en scripts de larga ejecución**

- Haz `unset()` de variables temporales grandes tras usarlas.
- Divide trabajo en iteraciones acotadas; limpia estado por iteración.
- Para referencias cíclicas en loops largos, llama ocasionalmente `gc_collect_cycles()`.

4. **Elige patrones eficientes de acceso a datos**

- Selecciona solo columnas necesarias en SQL, no `SELECT *`.
- Hidrata DTOs/arrays ligeros cuando modelos ORM completos no sean necesarios.
- Usa lazy-loading con cuidado; evita consultas N+1 y grafos de objetos excesivos.

5. **Usa límites de runtime y controles de ciclo de vida de workers**

- Configura `memory_limit` razonable para fallar rápido en lugar de degradar el host.
- Para workers de cola, reinicia tras N jobs/tiempo para evitar deriva de memoria a largo plazo.
- Monitorea tendencia de memoria con `memory_get_usage(true)` y métricas del SO.

6. **Cachea con criterio, no a ciegas**

- Cachea solo cómputos costosos y de alto valor.
- Guarda payloads de caché compactos; comprime cuando sea útil.
- Usa TTLs/invalidación para prevenir crecimiento ilimitado de caché.

7. **Perfila antes y después**

- Usa Xdebug/Blackfire/Tideways/APM para encontrar hotspots reales.
- Optimiza primero cuellos de botella medidos; evita micro-optimizaciones prematuras.

En la práctica, las mayores ganancias vienen de streaming/chunking, control de ciclo de vida de objetos y prevención de asignaciones transitorias grandes.

</details>

<details>
<summary>81. ¿Cómo invertirías una cadena sin funciones built-in?</summary>

#### PHP

La idea central es iterar desde el final de la cadena hasta el inicio y construir una nueva cadena carácter por carácter.

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

La complejidad temporal es `O(n)`, y el espacio extra es `O(n)` para la salida invertida.

Notas para entrevistas:

- Esta versión basada en bytes funciona para ASCII.
- Para cadenas UTF-8/multibyte, indexar por byte puede romper caracteres, por lo que se necesita un enfoque seguro para multibyte.

</details>

<details>
<summary>82. ¿Cómo eliminarías duplicados de un array?</summary>

#### PHP

El enfoque estándar es rastrear valores vistos en un hash map y conservar solo la primera ocurrencia.

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

Por qué esta versión funciona bien para entrevistas:

- Mantiene el orden de inserción.
- Funciona en tiempo lineal en promedio: `O(n)`.
- Maneja escalares, `null` y valores complejos vía `serialize`.

Si la pregunta permite built-ins, `array_unique()` es más corto, pero la lógica manual de hash-set demuestra mejor los fundamentos.

</details>

<details>
<summary>83. ¿Cómo encontrarías el segundo número más grande?</summary>

#### PHP

Una solución robusta en una sola pasada mantiene el valor máximo y el segundo máximo distintos mientras recorre el array.

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

Comportamiento:

- Devuelve `null` si no existe un segundo máximo distinto (por ejemplo, `[5]`, `[7, 7]`).
- Complejidad temporal: `O(n)`.
- Complejidad espacial: `O(1)`.

</details>

<details>
<summary>84. ¿Cómo comprobarías si una cadena es un palíndromo?</summary>

#### PHP

Un palíndromo se lee igual de izquierda a derecha y de derecha a izquierda. De forma eficiente, se comparan caracteres desde ambos extremos moviéndose hacia el centro.

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

Complejidad:

- Tiempo: `O(n)`
- Espacio: `O(1)`

Notas para entrevistas:

- Esta versión trabaja por bytes y está bien para ASCII.
- Para UTF-8, usa un enfoque seguro para multibyte antes de indexar caracteres.
- Aclara si deben ignorarse espacios, puntuación y mayúsculas/minúsculas; si sí, normaliza la entrada primero.

</details>

<details>
<summary>85. ¿Cómo comprobarías si un número es primo?</summary>

#### PHP

Un número `n` es primo si tiene exactamente dos divisores positivos: `1` y `n`.  
Comprobación eficiente: probar divisibilidad solo hasta `sqrt(n)`.

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

Complejidad:

- Tiempo: `O(sqrt(n))`
- Espacio: `O(1)`

Esta es la solución estándar de entrevista: correcta, suficientemente rápida y fácil de razonar.

</details>

<details>
<summary>86. ¿Cómo implementarías factorial usando recursión?</summary>

#### PHP

El factorial recursivo usa la definición `n! = n * (n - 1)!` con caso base `0! = 1` (y `1! = 1`).

```php
<?php
function factorial(int $n): int
{
    if ($n < 0) {
        throw new InvalidArgumentException('Factorial is undefined for negative numbers.');
    }

    if ($n === 0 || $n === 1) {
        return 1;
    }

    return $n * factorial($n - 1);
}
```

Complejidad:

- Tiempo: `O(n)`
- Espacio: `O(n)` por el stack de recursión.

Nota de entrevista: la versión iterativa usa stack `O(1)` y es más segura para valores muy grandes de `n`.

</details>

<details>
<summary>87. ¿Cómo implementarías sorting manualmente?</summary>

#### PHP

Para entrevistas, un ejemplo manual claro es Bubble Sort: intercambiar repetidamente elementos adyacentes si están en orden incorrecto.

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

Complejidad:

- Tiempo peor/promedio: `O(n^2)`
- Mejor caso (ya ordenado con corte temprano): `O(n)`
- Espacio: `O(1)` extra (ignorando semántica de copia de salida)

Si te piden un algoritmo más eficiente, explica Merge Sort (`O(n log n)`) o Quick Sort en promedio (`O(n log n)`).

</details>

<details>
<summary>88. ¿Cómo generarías la secuencia de Fibonacci?</summary>

#### PHP

El enfoque más práctico es iterativo: empezar con `0, 1` y seguir agregando la suma de los dos números anteriores.

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

Complejidad:

- Tiempo: `O(n)`
- Espacio: `O(n)` para almacenar la secuencia

Nota de entrevista:

- Fibonacci recursivo sin memoización es exponencial y normalmente no es aceptable para respuestas sensibles al rendimiento.
- Si solo necesitas el valor n-ésimo, el espacio puede reducirse a `O(1)` guardando solo los dos valores previos.

</details>

<details>
<summary>89. ¿Cómo encontrarías el elemento más frecuente?</summary>

#### PHP

Usa un mapa de frecuencias (hash table): cuenta ocurrencias de cada valor y luego devuelve la clave con el conteo máximo.

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

Complejidad:

- Tiempo: `O(n)`
- Espacio: `O(k)`, donde `k` es el número de elementos distintos

Comportamiento en empate: esta implementación devuelve el primer elemento que alcanza la frecuencia más alta.

</details>

<details>
<summary>90. ¿Cómo diseñarías un sistema PHP de alta carga?</summary>

#### PHP

Para sistemas PHP de alta carga, el principio central es hacer la aplicación stateless, sacar trabajo pesado fuera del path de request y escalar horizontalmente detrás de infraestructura confiable.

1. **Base de arquitectura**

- Instancias PHP stateless detrás de un load balancer.
- Nginx/Envoy + PHP-FPM (o RoadRunner/Swoole cuando esté justificado).
- Capas separadas de datos, caché, cola y object storage.

2. **Estrategia de datos**

- BD primaria + réplicas de lectura; separar rutas de lectura/escritura.
- Indexación correcta, optimización de consultas y monitoreo de consultas lentas.
- Particionado/sharding solo cuando se agote el escalado en un solo nodo.

3. **Capas de caché**

- Caché CDN/edge para respuestas estáticas y dinámicas cacheables.
- Redis/Memcached para datos de aplicación y resultados de consultas calientes.
- Política clara de invalidación de caché (TTL + invalidación basada en eventos).

4. **Procesamiento asíncrono**

- Mover tareas costosas a colas (emails, reportes, procesamiento de media).
- Usar workers idempotentes con reintentos y dead-letter queues.
- Mantener requests HTTP cortas y predecibles.

5. **Fiabilidad y resiliencia**

- Timeouts, circuit breakers, bulkheads para dependencias externas.
- Degradación elegante cuando fallan servicios no críticos.
- Health checks, auto-restarts y despliegues rolling.

6. **Observabilidad**

- Logs centralizados con correlation IDs.
- Métricas: latencia p95/p99, tasa de error, queue lag, saturación de BD/caché.
- Tracing para rutas de request multi-servicio.

7. **Prácticas operativas**

- Capacity planning y load testing antes de eventos pico.
- Releases blue-green/canary para reducir riesgo.
- Endurecimiento de seguridad y rate limiting en edge y capa app.

Un diseño PHP escalable es sobre todo una disciplina de infraestructura y arquitectura: capa de app stateless, acceso eficiente a datos, caché agresiva y ejecución asíncrona en background.

</details>

<details>
<summary>91. ¿Cómo escalarías PHP horizontalmente?</summary>

#### PHP

Escalado horizontal en PHP significa agregar más nodos de aplicación idénticos y asegurar que cualquier request pueda ser atendida por cualquier nodo sin depender de estado local.

1. **Haz la capa de aplicación stateless**

- Guarda sesiones en Redis/BD, no en disco local.
- Mueve archivos subidos a almacenamiento compartido/de objetos (p. ej., compatible con S3).
- Mantén cachés locales del nodo como opcionales, no como fuente de verdad.

2. **Coloca nodos detrás de un load balancer**

- Usa load balancer L4/L7 (Nginx, HAProxy, cloud LB).
- Habilita health checks y remoción automática de nodos no saludables.
- Sticky sessions son workaround temporal; prefiere diseño realmente stateless.

3. **Escala dependencias de mucha lectura**

- Agrega réplicas de lectura de BD y enruta tráfico de lectura adecuadamente.
- Agrega caché distribuida (Redis/Memcached) para descargar BD primaria.
- Usa CDN para assets estáticos y respuestas cacheables.

4. **Controla workloads en background**

- Usa workers basados en cola para jobs pesados.
- Escala workers de forma independiente de nodos HTTP.
- Haz jobs idempotentes y seguros para reintentos.

5. **Estandariza runtime con contenedores/imágenes**

- Imágenes inmutables para despliegues consistentes.
- Políticas de autoescalado basadas en señales de CPU, memoria y latencia.
- Gestión centralizada de config/secretos.

6. **Observabilidad y señales de escalado**

- Rastrea latencia p95/p99, saturación, tasa de error, queue lag.
- Monitorea presión del pool de conexiones BD y cache hit ratio.
- Usa estas métricas para disparar autoescalado y capacity planning.

En la práctica, el escalado horizontal de PHP es directo cuando el estado está externalizado y la infraestructura maneja distribución, salud y elasticidad.

</details>

<details>
<summary>92. ¿Cómo manejarías millones de usuarios?</summary>

#### PHP

Manejar millones de usuarios es una tarea de diseño de sistemas, no un truco puntual de PHP. La solución es escalar por capas en edge, aplicación, datos y operaciones.

1. **Distribución de tráfico y edge**

- CDN global para assets estáticos y respuestas API cacheables.
- Load balancers con nodos PHP stateless autoescalados.
- Rate limiting y protección contra bots en edge.

2. **Arquitectura de aplicación**

- Divide cuellos de botella del monolito en servicios acotados cuando haga falta.
- Mantén mínimo el path síncrono de request; mueve tareas pesadas a colas.
- Usa idempotency keys para operaciones críticas de escritura.

3. **Capa de datos a escala**

- BD primaria para escrituras, múltiples réplicas de lectura para tráfico de lectura.
- Indexación agresiva y tuning de consultas; evita anti-patrones ORM.
- Particionado/sharding para datasets muy grandes y tenants calientes.

4. **Estrategia de caché**

- Caché multicapa: CDN -> Redis/Memcached -> BD.
- Cachea objetos calientes, vistas calculadas y consultas costosas.
- Reglas fuertes de invalidación para evitar datos críticos stale.

5. **Procesamiento asíncrono y orientado a eventos**

- Workers de cola para emails, notificaciones, media, pipelines de analytics.
- Reintentos con backoff, dead-letter queues y handlers idempotentes.
- Publica eventos para consumidores downstream en lugar de bloquear requests.

6. **Fiabilidad y resiliencia**

- Degradación elegante de features no esenciales bajo presión.
- Presupuestos de timeout y circuit breakers para dependencias.
- Despliegue multi-AZ y procedimientos de failover probados.

7. **Observabilidad y disciplina de capacidad**

- SLOs de latencia/error; rastrear p95/p99 y saturación.
- Load/stress testing continuo antes de lanzamientos importantes.
- Forecast de capacidad basado en patrones reales de uso.

En escala de “millones”, el éxito viene de arquitectura predecible, crecimiento de datos controlado y prácticas operativas sólidas más que de optimizaciones a nivel de lenguaje.

</details>

<details>
<summary>93. ¿Cómo diseñarías una estrategia de caché?</summary>

#### PHP

Una buena estrategia de caché empieza por los patrones de acceso y los requisitos de consistencia, no solo por la elección de tecnología.

1. **Definir qué cachear**

- Resultados de consultas DB costosas.
- Respuestas API agregadas/calculadas.
- Contexto de sesión y autorización (cuando sea seguro).
- Datos estáticos/de configuración/de referencia con baja frecuencia de cambios.

2. **Usar caché en múltiples capas**

- Caché de edge/CDN para assets estáticos y respuestas HTTP cacheables.
- Caché de aplicación (Redis/Memcached) para objetos calientes y resultados de consultas.
- Optimizaciones in-process/opcache para código y configuración inmutable.

3. **Elegir patrones de caché adecuados**

- Cache-aside para datos con muchas lecturas (el más común).
- Write-through/write-behind para casos específicos de consistencia/rendimiento.
- Read-through si el proveedor de caché soporta carga transparente.

4. **Diseñar bien claves y TTL**

- Claves con namespace: `entity:{id}:v{version}`.
- TTL distintos según volatilidad de datos y criticidad de negocio.
- Añadir jitter al TTL para reducir el thundering herd.

5. **Gestionar la invalidación explícitamente**

- Invalidación dirigida por eventos después de escrituras.
- Claves versionadas para invalidación lógica sencilla.
- Invalidación por etiquetas cuando esté soportada.

6. **Protegerse ante fallos de caché**

- Ruta de fallback si la caché cae (degradado, pero funcional).
- Request coalescing/locking para evitar stampede.
- Warm-up para claves críticas tras deploy/restart.

7. **Medir y ajustar continuamente**

- Monitorear hit ratio, latencia, tasa de evicción, presión de memoria.
- Rastrear incidentes de lecturas obsoletas y coste de cache-miss.
- Optimizar basándose en trazas reales de producción.

Una estrategia de caché sólida es equilibrio: maximizar hit rate y mejoras de latencia manteniendo corrección y comportamiento de invalidación predecible.

</details>

<details>
<summary>94. ¿En qué se diferencian internamente los frameworks PHP modernos (Laravel, Symfony)?</summary>

#### PHP

Laravel y Symfony comparten muchas bases (ciclo de vida de petición HTTP, DI, conceptos de middleware/eventos), pero difieren en filosofía arquitectónica, valores por defecto y modelo de extensión.

1. **Filosofía central**

- Symfony: enfoque component-first, configuración explícita, alta composabilidad.
- Laravel: experiencia de desarrollo integrada, convenciones marcadas, entrega más rápida “out of the box”.

2. **Inyección de dependencias y contenedor**

- Symfony tiene un contenedor DI compilado con fuerte validación y optimización en tiempo de compilación.
- Laravel usa un contenedor de servicios muy dinámico con resolución en runtime y patrones de auto-wiring orientados a ergonomía del desarrollador.

3. **Modelo de configuración**

- Symfony: centrado en configuración (`yaml/xml/php`), bundles por entorno, wiring explícito.
- Laravel: convención + service providers + facades; muchas funcionalidades se habilitan con configuración mínima.

4. **Internals del pipeline HTTP**

- El flujo de request en Symfony se centra en `HttpKernel` y listeners del event dispatcher.
- El flujo de request en Laravel está orientado al pipeline de middleware con integración expresiva de rutas/controladores.

5. **Valores por defecto del ORM/capa de datos**

- Symfony suele usar Doctrine ORM (patrón Data Mapper, comportamiento de unit-of-work explícito).
- Laravel incluye Eloquent (patrón Active Record, ergonomía rápida para CRUD).

6. **Estructura del ecosistema**

- Los componentes de Symfony se reutilizan ampliamente de forma standalone en el ecosistema PHP.
- El ecosistema Laravel está estrechamente integrado (queues, jobs, scheduler, Horizon, patrones de tooling tipo Nova).

7. **Rendimiento y perfil en producción**

- Ambos pueden ser de nivel producción a gran escala.
- Symfony suele enfatizar previsibilidad y control explícito en sistemas enterprise grandes.
- Laravel enfatiza velocidad de implementación y flujo de trabajo cohesivo para desarrolladores.

En resumen: Symfony optimiza arquitectura explícita y composición de componentes; Laravel optimiza productividad integrada y entrega rápida de funcionalidades.

</details>

<details>
<summary>95. ¿Cómo funciona el enrutamiento en los frameworks?</summary>

#### PHP

El enrutamiento mapea una petición HTTP entrante a un handler específico (controller/action/closure) usando método, patrón de ruta, host y restricciones opcionales.

1. **Fase de definición de rutas**

- El framework carga la tabla de rutas al iniciar (desde archivos/atributos/anotaciones).
- Cada ruta guarda método(s), patrón de ruta, handler, middleware y metadatos.
- Muchos frameworks precompilan/cachean definiciones de rutas para búsquedas más rápidas.

2. **Fase de coincidencia de petición**

- El router recibe ruta normalizada + método.
- Intenta emparejar primero rutas estáticas y luego rutas dinámicas parametrizadas.
- Se validan restricciones (regex, host, scheme, locale).

3. **Extracción de parámetros**

- Segmentos dinámicos como `/users/{id}` se extraen de la ruta.
- Los valores se convierten/validan (explícitamente o vía reglas de binding del framework).
- Se aplican valores por defecto opcionales para parámetros faltantes.

4. **Middleware y guards**

- Antes de ejecutar el handler, corre la cadena de middleware de ruta/grupo/global.
- Checks típicos: auth, rate limiting, CSRF, permisos, resolución de tenant.
- El middleware puede hacer short-circuit y devolver respuesta temprana.

5. **Dispatch del controlador**

- El contenedor resuelve dependencias del controlador.
- Parámetros de ruta + servicios inyectados se pasan al método action.
- La action devuelve objeto/datos de respuesta para serialización.

6. **Reverse routing**

- El framework puede generar URLs desde nombres de rutas + parámetros.
- Esto evita URLs hardcodeadas y mejora la seguridad al refactorizar.

7. **Consideraciones de rendimiento**

- Route cache/precompilación en producción.
- Preferir rutas específicas/estáticas sobre patrones wildcard demasiado amplios.
- Mantener mínima la cadena de middleware en endpoints calientes.

Internamente, el routing es esencialmente un pipeline indexado de coincidencia de patrones y dispatch, envuelto con middleware e inyección de dependencias.

</details>

<details>
<summary>96. ¿Cómo funciona internamente el pipeline de middleware?</summary>

#### PHP

El pipeline de middleware es una cadena de responsabilidad: cada middleware recibe la petición y un callable "next", luego pasa el control hacia adelante o devuelve una respuesta de inmediato.

1. **Construcción del pipeline**

- El framework recopila middleware global, de grupo y específico de ruta.
- Se resuelve el orden del middleware (pueden aplicar reglas de prioridad).
- Se define un handler final de destino (controller/action) como último paso.

2. **Modelo de ejecución**

- La firma conceptual del middleware es: `handle(Request $request, Closure $next): Response`.
- El middleware puede hacer preprocesamiento y luego llamar a `$next($request)`.
- Después de que `next` devuelve, el middleware puede hacer postprocesamiento sobre la respuesta.

3. **Comportamiento short-circuit**

- El middleware puede devolver una respuesta sin llamar a `$next`.
- Casos típicos: fallo de auth, fallo CSRF, rate-limit excedido, modo mantenimiento.
- Esto evita la ejecución de middleware/controladores posteriores.

4. **Pila de llamadas anidada**

- La cadena suele construirse envolviendo closures desde el último hacia el primero.
- La ejecución “baja” por la ruta de la petición y luego “desenrolla” la ruta de respuesta.
- Esto habilita preocupaciones transversales como logging, timing e inyección de headers.

5. **Manejo de errores y excepciones**

- Un middleware/handler de excepciones puede capturar y normalizar errores.
- Algunos frameworks colocan el manejo de errores fuera de la pila de middleware, como lógica de kernel de nivel superior.
- Un mapeo consistente de errores mantiene predecibles las respuestas API.

6. **Responsabilidades comunes del middleware**

- Checks de autenticación/autorización.
- Validación/sanitización de requests.
- Rate limiting y controles antiabuso.
- Trazas, logging, métricas, correlation IDs.
- Headers CORS/seguridad y transformación de respuestas.

7. **Consideraciones de rendimiento**

- Mantener la cadena mínima en rutas calientes.
- Colocar temprano checks baratos de rechazo rápido.
- Evitar I/O síncrono pesado en middleware genérico.

Internamente, el middleware es una composición ordenada de callables que centraliza preocupaciones transversales alrededor del flujo request/response.

</details>

<details>
<summary>97. ¿Cómo funciona la resolución de dependencias por debajo?</summary>

#### PHP

La resolución de dependencias en frameworks PHP modernos la realiza un contenedor DI que construye objetos basándose en bindings y metadatos del constructor, normalmente vía reflexión y definiciones cacheadas.

1. **Bindings del contenedor**

- Interfaces/abstracts se mapean a implementaciones concretas.
- Los bindings pueden ser singleton, scoped o transient.
- Factories/closures pueden definir lógica de construcción personalizada.

2. **Solicitud de resolución**

- El framework pide al contenedor un tipo (controller, service, middleware, etc.).
- El contenedor verifica si la instancia ya existe (para ciclos de vida singleton/scoped).
- Si no existe, empieza a construir el grafo de objetos.

3. **Introspección del constructor**

- El contenedor inspecciona parámetros del constructor (reflexión o metadatos compilados).
- Para parámetros tipados como clase, resuelve dependencias recursivamente.
- Para valores scalar/config, usa parámetros explícitos, bindings env/config o valores por defecto.

4. **Construcción recursiva del grafo de objetos**

- Las dependencias se resuelven en profundidad (depth-first).
- La detección de dependencias circulares evita recursión infinita.
- Dependencias opcionales pueden ser nullable/default si no están enlazadas.

5. **Ciclo de vida y caché**

- Los singletons se cachean tras la primera creación.
- Las instancias scoped se cachean por alcance de request/job.
- Algunos contenedores compilan metadatos para acelerar resolución en producción.

6. **Inyección en métodos/actions**

- Además de constructores, los frameworks pueden inyectar dependencias en actions de controladores, command handlers y métodos middleware.
- Parámetros de ruta y servicios del contenedor se combinan durante el dispatch.

7. **Modos de fallo**

- Interface/abstract no enlazado.
- Cadena de dependencias ambigua o no instanciable.
- Parámetros scalar en constructor sin defaults/bindings.
- Dependencias circulares entre servicios.

Por debajo, la resolución DI es una construcción determinista de grafos con reglas de ciclo de vida, reflexión/metadatos y caché para rendimiento.

</details>

<details>
<summary>98. ¿Cuáles son las mejores prácticas para el desarrollo PHP moderno en 2026?</summary>

#### PHP

Las mejores prácticas de PHP moderno en 2026 se enfocan en disciplina de ingeniería estricta: tipado fuerte, puertas automáticas de calidad, seguridad por defecto y sistemas de producción observables.

1. **Usar intencionalmente las features actuales del lenguaje**

- `declare(strict_types=1);` en el código de aplicación.
- Propiedades tipadas, tipos de retorno, enums, patrones readonly/value-object.
- Preferir contratos explícitos sobre magia dinámica siempre que sea posible.

2. **Arquitectura y organización del código**

- Límites modulares (dominio/aplicación/infraestructura o equivalente).
- Separación clara entre lógica de negocio y código de integración con framework.
- Inversión de dependencias con interfaces para testabilidad.

3. **Automatización de calidad**

- CI con análisis estático (PHPStan/Psalm) con alta exigencia.
- Estilo de código consistente vía PHP-CS-Fixer/Pint.
- Pruebas unitarias + integración + contrato con fixtures realistas.

4. **Rendimiento y eficiencia de runtime**

- PHP 8.3/8.4+ con OPcache y ajustes afinados de FPM/process manager.
- Perfilar primero (Blackfire/XHProf/APM), luego optimizar hotspots.
- Usar caché/colas para mantener liviano el camino síncrono de request.

5. **Seguridad por defecto**

- Prepared statements, escape contextual de salida, protección CSRF.
- Gestión de secretos fuera del repo; rotación de claves y mínimo privilegio.
- Escaneo de vulnerabilidades de dependencias en CI.

6. **Madurez operativa**

- Logs estructurados, métricas, trazas, correlation IDs.
- Monitoreo guiado por SLO con control de fatiga de alertas.
- Releases seguras: canary/blue-green y procedimientos de rollback.

7. **Higiene de dependencias y ecosistema**

- Mantener dependencias Composer actualizadas con cadencia de upgrades controlada.
- Fijar y auditar paquetes críticos.
- Evitar acoplamiento innecesario al framework en código core de dominio.

8. **Convenciones de equipo**

- ADRs para decisiones importantes y estándares claros de code review.
- Reglas de compatibilidad hacia atrás para APIs públicas/internas.
- Documentación cercana al código para onboarding y respuesta a incidentes.

Los equipos PHP más fuertes en 2026 tratan la salud del codebase como un producto: tipado, probado, observable y en mejora continua.

</details>

<details>
<summary>99. ¿Qué herramientas son esenciales para un desarrollador PHP moderno?</summary>

#### PHP

Un toolkit PHP moderno y efectivo cubre codificación, calidad, depuración, entrega y operaciones.

1. **Lenguaje base y gestión de paquetes**

- Runtime PHP 8.3/8.4+.
- Composer para dependencias y autoloading.
- Herramientas de entorno local: Docker/DDEV/Lando o setup nativo reproducible.

2. **Calidad de código y análisis estático**

- PHPStan o Psalm para análisis estático.
- PHP-CS-Fixer o Pint para estándares de código.
- PHP_CodeSniffer cuando se requieren estándares personalizados.

3. **Stack de testing**

- PHPUnit o Pest para pruebas unitarias/de integración.
- Librerías de mocking/test doubles según necesidad.
- Reportes de cobertura integrados en CI.

4. **Depuración y profiling**

- Xdebug para depuración paso a paso.
- Profilers Blackfire/Tideways/XHProf/APM para cuellos de botella de rendimiento.
- Herramientas de logging estructurado y visor centralizado de logs.

5. **Herramientas de framework y DX**

- Laravel Artisan o Symfony Console.
- Utilidades de debug/profiler específicas del framework.
- Herramientas API: Postman/Insomnia + validación OpenAPI.

6. **Herramientas de datos e infraestructura**

- Redis y herramientas CLI de BD (`redis-cli`, `psql`, `mysql`) para diagnóstico.
- Dashboards de monitoreo de colas/workers.
- Herramientas de migraciones y gestión de esquemas.

7. **CI/CD y automatización**

- GitHub Actions/GitLab CI o equivalente.
- Gates automatizados de lint, análisis estático, tests y security scans.
- Automatización de despliegue con capacidad de rollback.

8. **Seguridad e higiene de dependencias**

- `composer audit` y/o escáneres SCA.
- Secret scanning y hooks pre-commit.
- SAST/DAST donde el perfil de riesgo lo requiera.

9. **Observabilidad y operaciones**

- Stack de métricas, trazas y alertas (Prometheus/Grafana/APM).
- Seguimiento de errores (Sentry/Bugsnag).
- Correlación de logs con request IDs.

El conjunto esencial es el que fuerza loops de feedback rápidos: checks de calidad de código, pruebas confiables, entrega segura y visibilidad en producción.

</details>

<details>
<summary>100. ¿Cómo mantienes un codebase PHP mantenible a largo plazo?</summary>

#### PHP

La mantenibilidad a largo plazo se logra combinando estándares técnicos, disciplina arquitectónica y feedback operativo continuo.

1. **Mantener la arquitectura explícita**

- Aplicar límites claros de módulos y ownership.
- Separar la lógica de dominio de detalles de framework/infraestructura.
- Minimizar acoplamiento oculto y estado global.

2. **Priorizar legibilidad sobre “ingenio”**

- Clases/funciones pequeñas y enfocadas, con nombres claros.
- Convenciones consistentes en todo el codebase.
- Preferir comportamiento explícito sobre abstracciones “mágicas”.

3. **Tomar en serio la seguridad de tipos**

- `strict_types=1` cuando sea viable.
- Tipado fuerte en params/returns/properties.
- Análisis estático (PHPStan/Psalm) como gate obligatorio de CI.

4. **Construir un portfolio de tests resiliente**

- Tests unitarios rápidos para lógica core.
- Tests de integración para límites con BD/sistemas externos.
- Tests de contrato para APIs/eventos compartidos con otros servicios.

5. **Controlar dependencias y upgrades**

- Cadencia regular de actualización de dependencias, en lugar de upgrades masivos esporádicos.
- Seguimiento de changelogs y deprecations en cambios de framework/runtime.
- Eliminar proactivamente paquetes sin uso y abstracciones muertas.

6. **Diseñar para cambio seguro**

- Reglas de compatibilidad hacia atrás para APIs públicas.
- Feature flags para despliegues riesgosos.
- Migraciones y cambios de datos con planes de rollback/repair.

7. **Institucionalizar el proceso de calidad de código**

- Checklist de code review (correctitud, seguridad, rendimiento, legibilidad).
- Formateo/linting automatizados para reducir ruido en revisión.
- ADRs para decisiones importantes y preservar contexto en el tiempo.

8. **Loop de feedback operativo**

- Observabilidad en producción: logs, métricas, trazas, error tracking.
- Revisiones post-incidente que alimenten mejoras concretas de código/proceso.
- Priorización basada en SLO para mantener visible la confiabilidad.

9. **Proteger la continuidad del equipo**

- Documentación actualizada para setup, arquitectura y runbooks.
- Guías de onboarding y estándares de ingeniería compartidos.
- Reducir riesgo de “experto único” mediante compartición de conocimiento y rotación.

Un codebase PHP mantenible no es estático; se cura continuamente mediante estándares, automatización y simplificación deliberada.

</details>
