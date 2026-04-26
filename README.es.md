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
