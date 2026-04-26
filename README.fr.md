**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  PHP <img src="./assets/php.svg" width="40" height="40" alt="PHP logo"/>
</h1>

<h2>Questions et réponses d’entretien PHP les plus populaires</h2>

<details>
<summary>1. Qu’est-ce que PHP et quels problèmes résout-il dans le développement backend moderne ?</summary>

#### PHP

PHP est un langage de programmation côté serveur conçu principalement pour le développement web. Dans le développement backend moderne, PHP résout plusieurs problèmes pratiques :

1. **Développement rapide de backends HTTP :** PHP permet de créer rapidement des API, des applications web et des pages rendues côté serveur.

2. **Traitement des requêtes et logique métier :** Il traite les requêtes HTTP entrantes, valide les données, exécute les règles métier et renvoie des réponses.

3. **Intégration base de données :** PHP dispose d’outils matures pour travailler avec les bases de données (MySQL, PostgreSQL, SQLite) via PDO et les ORM.

4. **Sessions et authentification :** Il prend en charge les sessions utilisateur, les systèmes de connexion, la gestion des cookies et le contrôle d’accès.

5. **Écosystème pour applications de production :** Des frameworks comme Laravel et Symfony fournissent le routage, l’injection de dépendances, les files de tâches, les événements et l’infrastructure de tests.

6. **Traitements en arrière-plan :** PHP peut exécuter des tâches asynchrones via des files (emails, rapports, notifications, imports) en dehors du flux requête-réponse.

7. **Scalabilité dans des systèmes réels :** Avec OPcache, des couches de cache (Redis), des conteneurs et le scaling horizontal, PHP alimente des systèmes à forte charge.

8. **Intégration avec des services externes :** PHP est largement utilisé pour les passerelles de paiement, les brokers de messages, les API tierces et les services cloud.

En bref, PHP couvre tout le cycle backend : réception des requêtes, traitement des données, interaction avec le stockage et livraison de services web sécurisés et maintenables.

</details>

<details>
<summary>2. Quelles sont les différences clés entre PHP et JavaScript (runtime, modèle d’exécution) ?</summary>

#### PHP

PHP et JavaScript sont tous deux largement utilisés dans le développement web, mais ils diffèrent fortement par le modèle d’exécution, le flux de traitement et le comportement backend typique.

1. **Environnement d’exécution principal :**
   PHP s’exécute sur le serveur (PHP-FPM, CLI, Swoole/RoadRunner), tandis que JavaScript s’exécute dans le navigateur et sur le serveur via Node.js/Deno/Bun.

2. **Modèle d’exécution (classique) :**
   Le PHP traditionnel suit un modèle requête-par-processus/requête-par-worker : chaque requête HTTP démarre, s’exécute et se termine avec un état isolé.
   JavaScript (Node.js) s’exécute généralement comme un processus long vivant avec un état mémoire partagé.

3. **Modèle de concurrence :**
   La concurrence en PHP est généralement obtenue via plusieurs workers/processus traitant les requêtes en parallèle.
   Les runtimes serveur JavaScript utilisent une boucle d’événements avec I/O asynchrones et opérations non bloquantes dans un processus unique (avec threads/processus workers si nécessaire).

4. **Cycle de vie de l’état :**
   En PHP classique, l’état en mémoire n’est pas persistant entre les requêtes ; l’état durable vit donc en général dans Redis/DB/cache.
   En Node.js, la mémoire du processus peut persister entre les requêtes, ce qui est pratique mais demande une gestion d’état rigoureuse.

5. **Rôle web typique :**
   PHP est traditionnellement orienté backend (SSR, API, logique métier).
   JavaScript est naturellement full-stack : langage d’UI frontend + option backend.

6. **Orientation de l’écosystème :**
   L’écosystème PHP met l’accent sur les frameworks backend (Laravel, Symfony), le templating serveur et les backends web d’entreprise.
   L’écosystème JavaScript met fortement l’accent sur les frameworks frontend et l’outillage universel/full-stack.

7. **Profil opérationnel :**
   PHP est souvent déployé derrière Nginx/Apache avec des pools PHP-FPM.
   Les backends JavaScript sont couramment déployés comme des processus applicatifs longue durée derrière des reverse proxies.

En pratique, PHP est souvent choisi pour son isolation prédictible des requêtes et ses frameworks backend matures, tandis que JavaScript est souvent choisi quand les équipes veulent un seul langage sur le frontend et le backend avec un développement serveur asynchrone par défaut.

</details>

<details>
<summary>3. Quelles sont les principales fonctionnalités introduites dans PHP 8.x (8.1–8.5) ?</summary>

#### PHP

PHP 8.1–8.5 a introduit des améliorations majeures du langage et du runtime. Les points les plus importants par version :

1. **PHP 8.1 (sortie le 25 novembre 2021) :**
   Enums, propriétés readonly, fibers, syntaxe callable de première classe, types d’intersection et type de retour `never`.

2. **PHP 8.2 (sortie le 8 décembre 2022) :**
   Classes readonly, types DNF, types autonomes `null`/`false`/`true`, nouvelle extension `Random`, et dépréciation des propriétés dynamiques.

3. **PHP 8.3 (sortie le 23 novembre 2023) :**
   Constantes de classe typées, attribut `#[\Override]`, récupération dynamique de constantes de classe (`Class::{$name}`), et améliorations readonly/clonage.

4. **PHP 8.4 (sortie le 21 novembre 2024) :**
   Property hooks, visibilité asymétrique (style `public private(set)`), attribut `#[\Deprecated]`, API DOM mise à jour et prise en charge des objets paresseux.

5. **PHP 8.5 (sortie le 20 novembre 2025) :**
   Opérateur pipe (`|>`), extension URI, mises à jour clone-with via `clone(...)`, `#[\NoDiscard]`, closures dans les expressions constantes, et améliorations supplémentaires API/runtime.

#### Pourquoi c’est important

- **Meilleure sûreté de type :** typage renforcé, contrats plus sûrs, moins de surprises à l’exécution.
- **Modélisation métier plus propre :** enums, constructions readonly, et sémantique moderne des propriétés.
- **Code plus expressif :** opérateur pipe, attributs, et meilleur support des callables.
- **Performance et maintenabilité :** évolution continue du moteur, de l’outillage et de la bibliothèque standard.

En bref, PHP 8.x a modernisé le langage de manière significative et a facilité la construction et la maintenance d’architectures backend modernes.

</details>

<details>
<summary>4. Que sont les enums, les attributs et les propriétés readonly en PHP ?</summary>

#### PHP

Les enums, les attributs et les propriétés readonly sont des fonctionnalités modernes de PHP qui améliorent la justesse, la lisibilité et la maintenabilité.

1. **Enums**

- Les enums définissent un ensemble fixe de valeurs autorisées en tant que vrai type.
- Elles empêchent les états invalides en string/int et rendent la modélisation métier plus sûre.
- PHP prend en charge :
  les enums backed (`enum Status: string { ... }`) et les enums unit (`enum Role { ... }`).

```php
enum OrderStatus: string
{
    case Draft = 'draft';
    case Paid = 'paid';
    case Shipped = 'shipped';
}
```

2. **Attributs**

- Les attributs sont des métadonnées natives (`#[...]`) attachées aux classes, méthodes, propriétés, paramètres, etc.
- Ils remplacent de nombreux usages d’annotations docblock par des métadonnées structurées et lisibles par machine.
- Cas d’usage courants : routage, validation, injection de dépendances, règles de sérialisation, marqueurs de dépréciation.

```php
#[Deprecated(reason: 'Use NewService instead')]
class LegacyService {}
```

3. **Propriétés readonly**

- Une propriété `readonly` ne peut être écrite qu’une seule fois (généralement dans le constructeur).
- Après initialisation, toute mutation est interdite.
- C’est utile pour des DTO immuables, des value objects et une conception d’objet plus sûre.

```php
final class UserDto
{
    public function __construct(
        public readonly int $id,
        public readonly string $email,
    ) {}
}
```

#### Pourquoi elles sont importantes ensemble

- **Les enums** protègent les états autorisés.
- **Les attributs** fournissent des métadonnées explicites pour les frameworks et les outils.
- **Les propriétés readonly** imposent l’immuabilité des données critiques.

Ensemble, ces fonctionnalités réduisent les bugs, rendent les API plus claires et améliorent la qualité de l’analyse statique dans les codebases PHP modernes.

</details>

<details>
<summary>5. Qu’est-ce que le typage strict en PHP et pourquoi est-il important ?</summary>

#### PHP

Le typage strict en PHP s’active par fichier avec :

```php
declare(strict_types=1);
```

Quand le typage strict est activé, les déclarations de types scalaires sont appliquées plus strictement pour les arguments de fonctions et les valeurs de retour.

1. **Sans types stricts (`strict_types=0`, par défaut) :**
   PHP peut convertir implicitement les valeurs scalaires (par exemple, `'10'` en `10`) quand c’est possible.

2. **Avec types stricts (`strict_types=1`) :**
   PHP lève une `TypeError` au lieu de convertir silencieusement des valeurs scalaires incompatibles.

```php
declare(strict_types=1);

function add(int $a, int $b): int
{
    return $a + $b;
}

add('2', 3); // TypeError en mode strict
```

#### Pourquoi c’est important

- **Détection précoce des erreurs :** les incompatibilités de types échouent immédiatement.
- **Refactorisation plus sûre :** des contrats plus clairs réduisent les régressions cachées.
- **Comportement plus prévisible :** moins de magie de conversion implicite.
- **Meilleure analyse statique :** des outils comme PHPStan/Psalm deviennent plus efficaces.
- **Frontières d’API plus nettes :** les signatures de fonctions sont traitées comme des contrats stricts.

#### Recommandation pratique

Utilise `declare(strict_types=1);` dans tous les nouveaux fichiers PHP et combine-le avec des type hints explicites, des DTO/value objects et de l’analyse statique pour une fiabilité de niveau production.

</details>

<details>
<summary>6. Que sont les types union et intersection ?</summary>

#### PHP

Les types union et intersection en PHP sont des outils pour exprimer des contrats de types plus stricts et plus explicites.

1. **Types union (`A|B`)**

- Une valeur peut être de **l’un des types autorisés**.
- Utile quand un argument ou une valeur de retour peut légitimement varier.

```php
function formatId(int|string $id): string
{
    return (string) $id;
}
```

2. **Types intersection (`A&B`)**

- Une valeur doit satisfaire **tous les types listés en même temps**.
- Souvent utilisé avec des interfaces pour exiger plusieurs capacités.

```php
interface Cacheable {}
interface Jsonable { public function toJson(): string; }

function store(Cacheable&Jsonable $entity): void
{
    // $entity doit implémenter les deux interfaces
}
```

3. **Différence clé**

- `A|B` signifie **soit A, soit B**.
- `A&B` signifie **A et B ensemble**.

4. **Pourquoi c’est important**

- Meilleurs contrats d’API et code auto-documenté.
- Moins d’erreurs à l’exécution dues à des formes d’objets/valeurs invalides.
- Analyse statique plus forte et refactorisation plus sûre.

5. **Conseils pratiques**

- Utilise les types union pour des frontières d’entrée flexibles.
- Utilise les types intersection pour une conception orientée capacités (surtout avec des interfaces).
- Préfère des types spécifiques à `mixed` quand c’est possible.

</details>

<details>
<summary>7. Qu’est-ce que l’opérateur nullsafe et quand l’utiliser ?</summary>

#### PHP

L’opérateur nullsafe en PHP est `?->`. Il permet un accès sûr aux méthodes/propriétés d’objets pouvant être `null`.

1. **Ce qu’il fait**

- Si la partie gauche est un objet, l’accès continue normalement.
- Si la partie gauche est `null`, l’évaluation s’arrête et renvoie `null` au lieu de lancer une erreur.

```php
$country = $user?->getProfile()?->getAddress()?->country;
```

2. **Pourquoi c’est utile**

- Évite des vérifications `null` imbriquées et verbeuses.
- Réduit le boilerplate dans les chaînes d’objets optionnelles.
- Rend l’intention plus claire lorsque les valeurs peuvent légitimement être nullables.

3. **Cas d’usage typiques**

- Structures API/DTO avec des champs imbriqués optionnels.
- Relations ORM potentiellement absentes.
- Objets de contexte de requête dont certaines parties sont optionnelles.

4. **Équivalent sans nullsafe (plus verbeux)**

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

5. **Notes importantes**

- `?->` fonctionne uniquement pour l’accès objet (méthodes/propriétés), pas pour les index de tableau.
- Il applique un court-circuit de gauche à droite.
- Si la chaîne se résout en `null`, le résultat final est `null`.

Utilise l’opérateur nullsafe lorsque `null` est un état attendu et que tu veux une traversée concise et sûre des graphes d’objets.

</details>

<details>
<summary>8. Que sont les property hooks (PHP 8.4+) ?</summary>

#### PHP

Les property hooks (introduits en PHP 8.4) permettent d’attacher une logique directement aux opérations de lecture/écriture de propriétés via des hooks `get` et `set`.

1. **Quel problème ils résolvent**

- Réduire le boilerplate des méthodes getter/setter.
- Garder la validation/transformation proche de la définition de la propriété.
- Permettre des propriétés calculées (virtuelles) avec une syntaxe plus claire.

2. **Idée de base**

```php
class User
{
    public string $name {
        set => trim($value);
    }
}
```

Toute affectation à `$user->name` passe par le hook `set`.

3. **Exemple de propriété calculée**

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

`$fullName` est dérivée d’autres champs et ne nécessite pas de méthodes getter manuelles.

4. **Exemple de validation/transformation**

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

5. **Quand les utiliser**

- Entités métier avec des invariants stricts.
- Objets DTO/value-like qui nécessitent des écritures contrôlées.
- Cas où les méthodes get/set classiques étaient surtout du boilerplate.

Les property hooks rendent les modèles objets plus expressifs et réduisent le code répétitif d’accès, tout en conservant une validation forte et une bonne encapsulation.

</details>

<details>
<summary>9. Qu’est-ce que l’opérateur pipe (PHP 8.5) et quand est-il utile ?</summary>

#### PHP

L’opérateur pipe en PHP 8.5 est `|>`. Il transmet le résultat de l’expression de gauche au callable de droite, ce qui permet une transformation des données lisible de gauche à droite.

1. **Idée centrale**

Au lieu d’appels profondément imbriqués, tu peux construire un pipeline de traitement linéaire.

```php
$result = " Hello World "
    |> trim(...)
    |> strtolower(...)
    |> (fn(string $s) => str_replace(' ', '-', $s));
```

2. **Pourquoi c’est utile**

- Améliore la lisibilité des transformations en plusieurs étapes.
- Réduit les variables temporaires.
- Évite les appels imbriqués “de l’intérieur vers l’extérieur”.
- Facilite la refactorisation des chaînes de transformation.

3. **Avant vs après**

Sans pipe :

```php
$slug = strtolower(str_replace(' ', '-', trim($title)));
```

Avec pipe :

```php
$slug = $title
    |> trim(...)
    |> (fn(string $s) => str_replace(' ', '-', $s))
    |> strtolower(...);
```

4. **Bons cas d’usage**

- Pipelines de normalisation de chaînes/données.
- Flux de mapping/transformation de DTO.
- Traitement de données en style fonctionnel dans les services.

5. **Note pratique**

Utilise l’opérateur pipe pour des transformations séquentielles claires. Pour une logique conditionnelle complexe, des variables intermédiaires classiques peuvent rester plus faciles à comprendre.

</details>

<details>
<summary>10. Que sont les superglobales en PHP et comment les utiliser ?</summary>

#### PHP

Les superglobales en PHP sont des tableaux associatifs intégrés, disponibles dans toutes les portées (fonctions, méthodes, portée globale) sans utiliser `global`.

1. **Superglobales principales**

- `$_GET` - paramètres de query string depuis l’URL.
- `$_POST` - paramètres de formulaire/corps pour les requêtes POST.
- `$_REQUEST` - données de requête fusionnées (dépend de `request_order`/`variables_order`).
- `$_SERVER` - métadonnées serveur et requête (headers, méthode, URI, hôte, etc.).
- `$_COOKIE` - cookies client envoyés avec la requête.
- `$_SESSION` - données de session conservées entre les requêtes.
- `$_FILES` - métadonnées des fichiers uploadés.
- `$_ENV` - variables d’environnement.
- `$GLOBALS` - référence vers toutes les variables globales.

2. **Exemples d’usage typiques**

```php
$page = $_GET['page'] ?? 'home';
$method = $_SERVER['REQUEST_METHOD'] ?? 'GET';
$token = $_COOKIE['csrf_token'] ?? null;
```

3. **Pourquoi elles sont importantes**

- Elles sont l’interface principale entre le code PHP et l’environnement HTTP/runtime.
- Elles fournissent les entrées de requête, le contexte et l’état utilisateur/session persistant.

4. **Pratiques de sécurité et de fiabilité**

- Ne fais jamais confiance directement aux entrées des superglobales.
- Valide et assainis toujours les données externes.
- Utilise des vérifications strictes et des valeurs par défaut (`??`, `filter_input`, validateurs).
- Évite de t’appuyer sur `$_REQUEST` dans le code critique car la priorité des sources peut varier.
- Échappe la sortie pour prévenir XSS et utilise des requêtes préparées pour prévenir l’injection SQL.

Les superglobales sont fondamentales en développement web PHP, mais elles doivent être traitées comme des frontières d’entrée non fiables.

</details>

<details>
<summary>11. Quelle est la différence entre les requêtes GET et POST ?</summary>

#### PHP

GET et POST sont des méthodes HTTP avec des sémantiques et des usages différents.

1. **Objectif**

- **GET** sert à récupérer des données (opérations en lecture seule).
- **POST** sert à envoyer des données pouvant modifier l’état du serveur (actions de création/traitement).

2. **Où les données sont envoyées**

- **GET** envoie les paramètres dans la query string de l’URL (`/users?page=2`).
- **POST** envoie les données dans le corps de la requête.

3. **Visibilité et journalisation**

- Les paramètres **GET** sont visibles dans l’URL, l’historique du navigateur, les logs et les referrers.
- Le corps **POST** n’apparaît pas dans l’URL, mais doit quand même être traité comme une entrée non fiable.

4. **Cache et favoris**

- Les requêtes **GET** sont adaptées au cache et bookmarkables.
- Les requêtes **POST** ne sont généralement pas cacheables par défaut et ne sont pas bookmarkables avec leur payload.

5. **Idempotence et sécurité (sémantique HTTP)**

- **GET** doit être sûr et ne pas changer l’état du serveur.
- **POST** n’est pas garanti idempotent et produit généralement des effets de bord.

6. **Accès en PHP**

```php
$search = $_GET['q'] ?? null;      // depuis la query string
$email  = $_POST['email'] ?? null; // depuis le corps de la requête
```

7. **Quand les utiliser**

- Utilise **GET** pour filtrer, rechercher, paginer et lire des ressources.
- Utilise **POST** pour les soumissions de formulaires, les actions d’authentification et la création/mise à jour de données côté serveur (ou PUT/PATCH si approprié pour les API).

Règle clé : GET pour les opérations de lecture et POST pour les opérations qui changent l’état, en validant toutes les entrées dans les deux cas.

</details>

<details>
<summary>12. Comment PHP gère-t-il les requêtes et réponses HTTP ?</summary>

#### PHP

Dans une architecture web typique, PHP gère HTTP via un cycle requête-réponse coordonné par un serveur web (Nginx/Apache) et un runtime PHP (le plus souvent PHP-FPM).

1. **Arrivée de la requête**

- Le client envoie une requête HTTP (méthode, URI, headers, corps).
- Le serveur web la reçoit et route les requêtes dynamiques vers PHP.

2. **Le runtime PHP exécute le script**

- PHP initialise le contexte de requête et remplit les superglobales (`$_SERVER`, `$_GET`, `$_POST`, `$_COOKIE`, `$_FILES`).
- Le bootstrap de l’application s’exécute (autoload, config, conteneur DI, kernel framework).

3. **L’application exécute la logique métier**

- Le routeur résout le contrôleur/handler.
- Middleware/guards/validation s’exécutent.
- Les services/repositories accèdent à la base, au cache ou à des API externes.

4. **La réponse est construite**

- L’app définit le code de statut, les headers et le corps (HTML/JSON/fichier/flux).
- En PHP natif, cela se fait typiquement via `header()`, `http_response_code()` et la sortie.
- Dans les frameworks, un objet Response est renvoyé puis émis.

```php
http_response_code(200);
header('Content-Type: application/json; charset=utf-8');
echo json_encode(['ok' => true], JSON_THROW_ON_ERROR);
```

5. **La réponse est envoyée**

- PHP envoie la sortie au serveur web.
- Le serveur web envoie la réponse HTTP finale au client.
- En PHP-FPM classique, l’état de requête prend fin après la réponse (le stockage externe partagé sert pour la persistance).

6. **Gestion des erreurs**

- Les exceptions sont converties en réponses d’erreur HTTP (par exemple `404`, `422`, `500`) par les handlers framework/globaux.
- Les logs/monitoring capturent les échecs pour le diagnostic.

Le modèle PHP est direct : recevoir le contexte de requête, exécuter le code applicatif, produire une réponse HTTP et terminer proprement la requête.

</details>

<details>
<summary>13. Comment fonctionnent les sessions et quelles sont les pratiques de session sécurisées ?</summary>

#### PHP

Les sessions PHP permettent de conserver un état spécifique à l’utilisateur entre des requêtes HTTP stateless en stockant les données côté serveur et en les liant à un identifiant de session.

1. **Comment fonctionnent les sessions**

- Le client envoie une première requête.
- Le serveur crée un identifiant de session (SID).
- Le SID est envoyé au client, généralement via un cookie (souvent `PHPSESSID`).
- Aux requêtes suivantes, le client renvoie le SID.
- PHP charge les données de session côté serveur correspondantes dans `$_SESSION`.

2. **Utilisation de base**

```php
session_start();

$_SESSION['user_id'] = 42;
$userId = $_SESSION['user_id'] ?? null;
```

3. **Où les données sont stockées**

- Par défaut : stockage de session sur le système de fichiers.
- En production : souvent Redis/base de données/memcached via des handlers personnalisés pour la scalabilité.

4. **Pratiques de session sécurisées**

- Régénérer l’identifiant de session après connexion/changement de privilèges :
  `session_regenerate_id(true);`
- Utiliser les flags cookie :
  `HttpOnly`, `Secure`, `SameSite` (`Lax` ou `Strict` quand possible).
- Imposer HTTPS pour les applications authentifiées.
- Définir un timeout de session et une expiration par inactivité.
- Invalider la session à la déconnexion (unset des données + destruction session + expiration cookie).
- Lier prudemment les sessions à des signaux de contexte (par exemple vérifications partielles IP/UA) pour réduire le risque de détournement.
- Stocker un minimum de données sensibles en session ; préférer des IDs/références plutôt que des secrets complets.

5. **Menaces courantes**

- **Session fixation :** l’attaquant force un SID connu avant l’authentification.
- **Session hijacking :** un SID volé est réutilisé par l’attaquant.
- **Vol assisté par XSS :** des scripts malveillants peuvent exploiter une gestion de session non sécurisée.

6. **Checklist de durcissement**

- `session.use_strict_mode=1`
- `session.cookie_httponly=1`
- `session.cookie_secure=1` (en HTTPS)
- `session.cookie_samesite` correctement défini
- Régénération régulière du SID pour les flux authentifiés

Les sessions sont sûres et efficaces lorsque les identifiants sont protégés, rotés correctement et transportés uniquement sur des canaux de confiance.

</details>

<details>
<summary>14. Comment les cookies sont-ils définis et sécurisés dans les applications modernes ?</summary>

#### PHP

Les cookies sont de petites paires clé-valeur stockées par le navigateur et envoyées avec les requêtes correspondantes. Dans les applications modernes, ils servent aux sessions, aux préférences et aux flux d’authentification sécurisés.

1. **Comment définir des cookies en PHP**

Utiliser `setcookie()` (ou les helpers de réponse du framework) avant tout envoi de sortie :

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

2. **Comment lire les cookies**

```php
$token = $_COOKIE['session_token'] ?? null;
```

3. **Attributs de sécurité (critiques)**

- **`Secure`** : cookie envoyé uniquement en HTTPS.
- **`HttpOnly`** : non accessible depuis JavaScript (`document.cookie`), réduit le risque de vol via XSS.
- **`SameSite`** :
  `Strict` (forte protection CSRF), `Lax` (équilibré), `None` (nécessite `Secure`, pour les cas cross-site).
- **`Expires/Max-Age`** : limite la durée de vie.
- **`Path/Domain`** : limiter la portée du cookie au maximum.

4. **Bonnes pratiques**

- Utiliser HTTPS partout et toujours activer `Secure` pour les cookies sensibles.
- Activer `HttpOnly` pour les cookies de session/auth.
- Préférer `SameSite=Lax` ou `Strict` sauf si un comportement cross-site est explicitement requis.
- Faire tourner les tokens de session/auth et définir des expirations adaptées.
- Ne pas stocker de données sensibles en clair dans les cookies.
- Envisager de signer ou chiffrer la charge utile du cookie si l’état est stocké côté client.

5. **Erreurs courantes**

- Oublier `HttpOnly` ou `Secure`.
- `domain`/`path` trop larges.
- Expiration trop longue pour les cookies d’auth.
- Faire confiance aux valeurs de cookie sans vérification côté serveur.

La sécurité moderne des cookies repose sur une portée stricte, un transport sûr, des réglages par défaut sûrs et une validation côté serveur de toutes les valeurs fournies par le client.

</details>

<details>
<summary>15. Qu’est-ce que le CSRF et comment le prévenir ?</summary>

#### PHP

Le CSRF (Cross-Site Request Forgery) est une attaque où le navigateur d’une victime est trompé pour envoyer une requête authentifiée vers votre application sans l’intention de l’utilisateur.

1. **Comment fonctionne le CSRF**

- L’utilisateur est connecté à `your-app.com`.
- L’attaquant attire l’utilisateur vers une page malveillante.
- Cette page déclenche une requête vers `your-app.com` (par exemple, changer l’email, transférer des fonds).
- Le navigateur inclut automatiquement les cookies/session, donc la requête peut être acceptée.

2. **Pourquoi c’est dangereux**

- Le serveur voit une session authentifiée valide.
- Des actions qui modifient l’état peuvent être exécutées au nom de la victime.

3. **Défense principale : token CSRF**

- Générer un token aléatoire par session/requête.
- Intégrer le token dans les formulaires ou headers de requête.
- Vérifier le token côté serveur avant de traiter les actions qui changent l’état.

```php
session_start();

// Générer le token une seule fois
$_SESSION['csrf_token'] ??= bin2hex(random_bytes(32));

// Valider sur POST
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $token = $_POST['_csrf'] ?? '';
    if (!hash_equals($_SESSION['csrf_token'], $token)) {
        http_response_code(419);
        exit('Invalid CSRF token');
    }
}
```

4. **Protections supplémentaires**

- Utiliser des cookies `SameSite` (`Lax`/`Strict`) pour réduire l’envoi cross-site des cookies.
- Valider les headers `Origin`/`Referer` pour les endpoints sensibles (défense en profondeur).
- Exiger une ré-authentification ou une confirmation renforcée pour les opérations critiques.
- Ne pas utiliser GET pour les actions qui changent l’état.

5. **Bonne pratique en framework**

- Utiliser le middleware CSRF intégré (Laravel/Symfony/etc.) plutôt qu’une logique maison quand c’est possible.
- S’assurer que les tokens sont inclus dans toutes les requêtes mutantes (POST/PUT/PATCH/DELETE), y compris les appels AJAX.

La protection CSRF est obligatoire pour les flux d’authentification basés sur cookies et doit faire partie du middleware de sécurité par défaut.

</details>

<details>
<summary>16. Qu’est-ce que le XSS et comment le prévenir correctement ?</summary>

#### PHP

Le XSS (Cross-Site Scripting) est une vulnérabilité où des données contrôlées par un attaquant sont interprétées par le navigateur comme du script exécutable dans les pages de votre application.

1. **Principaux types de XSS**

- **Stored XSS** : la charge malveillante est stockée (DB/commentaire/profil) puis servie plus tard aux utilisateurs.
- **Reflected XSS** : la charge vient de l’entrée de requête et est immédiatement reflétée dans la réponse.
- **DOM-based XSS** : le JavaScript côté client écrit des données non sûres dans le DOM.

2. **Cause racine**

- Une entrée non fiable atteint les contextes HTML/JS/URL/CSS sans encodage de sortie correct.

3. **Défense principale : échappement contextuel en sortie**

- Échapper les données **au moment de la sortie**, selon le contexte de rendu.
- Pour le contexte texte HTML en PHP :

```php
echo htmlspecialchars($userInput, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
```

4. **Règles spécifiques au contexte**

- Corps HTML : `htmlspecialchars(...)`.
- Attributs HTML : échapper aussi les guillemets (`ENT_QUOTES`).
- Contexte JavaScript : encoder en JSON, éviter la concaténation directe de chaînes.
- Contexte URL : `rawurlencode()` pour les valeurs de paramètres.
- Éviter d’injecter directement du HTML non fiable.

5. **Protections supplémentaires**

- Utiliser les fonctionnalités d’auto-échappement des moteurs de templates/frameworks.
- Assainir le HTML riche avec des sanitizers à allowlist (si l’entrée HTML est nécessaire).
- Définir une Content Security Policy (CSP) forte comme défense en profondeur.
- Éviter les scripts inline quand c’est possible.
- Valider l’entrée, mais ne pas considérer la validation comme un remplacement de l’encodage de sortie.

6. **Erreurs courantes**

- Échapper l’entrée une fois puis la réutiliser dans plusieurs contextes.
- Désactiver globalement l’auto-échappement du moteur de templates.
- Rendre du contenu utilisateur brut dans les panneaux admin/outils internes.

La prévention XSS repose surtout sur un encodage contextuel strict au point de sortie, plus CSP et des patterns de rendu sûrs.

</details>

<details>
<summary>17. Qu’est-ce que l’injection SQL et comment les requêtes préparées la préviennent-elles ?</summary>

#### PHP

L’injection SQL est une vulnérabilité où l’entrée d’un attaquant modifie la structure des requêtes SQL, permettant un accès ou une manipulation non autorisés des données.

1. **Comment l’injection SQL se produit**

Elle survient lorsque des entrées non fiables sont concaténées directement dans des chaînes SQL.

```php
// Exemple non sûr
$sql = "SELECT * FROM users WHERE email = '" . $_POST['email'] . "'";
```

Un attaquant peut injecter des fragments SQL et altérer la logique de la requête.

2. **Impact**

- Contournement de l’authentification
- Fuite/modification/suppression de données
- Élévation de privilèges
- Dans les cas graves, compromission complète de la base

3. **Comment les requêtes préparées la préviennent**

Les requêtes préparées séparent :
- **La structure SQL** (template de requête)
- **Les valeurs de données** (paramètres liés)

La base de données traite les valeurs liées comme des données, pas comme du code SQL exécutable.

```php
$pdo = new PDO($dsn, $user, $pass, [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
]);

$stmt = $pdo->prepare('SELECT * FROM users WHERE email = :email');
$stmt->execute(['email' => $_POST['email']]);
$user = $stmt->fetch(PDO::FETCH_ASSOC);
```

4. **Nuance importante**

- Les requêtes préparées protègent les valeurs, mais pas les identifiants SQL dynamiques (noms de table/colonne).
- Si les identifiants doivent être dynamiques, utiliser des allowlists strictes.

5. **Bonnes pratiques**

- Utiliser partout des requêtes préparées PDO/MySQLi pour les entrées externes.
- Ne jamais construire du SQL par concaténation de chaînes avec des valeurs utilisateur.
- Appliquer le principe de moindre privilège aux comptes DB.
- Valider les entrées et journaliser l’activité suspecte.
- Maintenir le moteur DB et les drivers à jour.

Les requêtes préparées sont la défense principale et obligatoire contre l’injection SQL dans les applications PHP modernes.

</details>

<details>
<summary>18. Qu’est-ce que la Content Security Policy (CSP) ?</summary>

#### PHP

La Content Security Policy (CSP) est un mécanisme de sécurité du navigateur qui limite quelles ressources (scripts, styles, images, frames, etc.) sont autorisées à se charger et à s’exécuter sur une page.

1. **Ce que la CSP protège**

- Réduit principalement l’impact du XSS en bloquant les scripts inline/externes non autorisés.
- Aide à limiter l’exfiltration de données via des chargements de ressources malveillants.
- Restreint les capacités navigateur risquées aux origines de confiance.

2. **Comment la CSP est livrée**

- Généralement via un header de réponse HTTP :
  `Content-Security-Policy: ...`
- Peut aussi être envoyée d’abord en mode report-only :
  `Content-Security-Policy-Report-Only: ...`

3. **Exemple de base**

```php
header("Content-Security-Policy: default-src 'self'; script-src 'self'; object-src 'none'; base-uri 'self'; frame-ancestors 'none'");
```

4. **Directives importantes**

- `default-src` - politique source de repli.
- `script-src` - contrôle les sources JavaScript.
- `style-src` - contrôle les sources CSS.
- `img-src` - contrôle les sources d’images.
- `connect-src` - contrôle les cibles XHR/fetch/WebSocket.
- `frame-ancestors` - prévient le clickjacking en contrôlant l’intégration.
- `object-src 'none'` - désactive les contenus legacy de plugins.
- `base-uri` - restreint l’injection de balise `<base>`.

5. **Bonnes pratiques**

- Commencer en `Report-Only`, collecter les violations, puis appliquer en mode enforce.
- Préférer des nonces/hashes pour les scripts inline au lieu de `'unsafe-inline'`.
- Garder une policy stricte et explicite par environnement.
- Combiner la CSP avec l’échappement de sortie, la protection CSRF et des cookies sécurisés.

6. **La CSP n’est pas une solution miracle**

- C’est une défense en profondeur, pas un remplacement du code sécurisé.
- Il faut toujours assainir/échapper les sorties non fiables et éviter les patterns DOM non sûrs.

La CSP renforce fortement la posture de sécurité frontend lorsqu’elle est configurée avec soin et surveillée en continu.

</details>

<details>
<summary>19. Qu’est-ce que l’autoloading et comment fonctionne PSR-4 ?</summary>

#### PHP

L’autoloading est un mécanisme qui charge automatiquement les fichiers de classes/interfaces/traits PHP lors de leur première utilisation, au lieu d’écrire manuellement de nombreux `require`/`include`.

1. **Pourquoi l’autoloading est nécessaire**

- Supprime les inclusions de fichiers manuelles.
- Garde la structure du projet scalable.
- Facilite la gestion des dépendances et des modules.

2. **PSR-4 en bref**

PSR-4 est le standard moderne pour mapper les namespaces vers des chemins de système de fichiers.

- Le préfixe de namespace est mappé à un répertoire de base.
- Les parties restantes du namespace sont mappées aux sous-répertoires.
- Le nom de classe est mappé au nom de fichier (`ClassName.php`).

3. **Exemple de mapping**

Si la config Composer contient :

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

Alors :
- `App\Services\UserService` -> `src/Services/UserService.php`
- `App\Http\Controllers\HomeController` -> `src/Http/Controllers/HomeController.php`

4. **Comment Composer l’active**

- Définir `autoload.psr-4` dans `composer.json`.
- Exécuter :

```bash
composer dump-autoload
```

- Inclure l’autoloader Composer une seule fois (généralement dans le bootstrap de l’app) :

```php
require __DIR__ . '/vendor/autoload.php';
```

5. **Bonnes pratiques**

- Respecter une classe par fichier.
- Garder alignés noms de namespace et de répertoires.
- Utiliser un namespace racine explicite (`App\\`, `Domain\\`, `Company\\Project\\`).
- Régénérer les fichiers d’autoload après des changements de namespace/chemin.

L’autoloading avec PSR-4 est la base par défaut de la structure des applications PHP modernes et du chargement des dépendances.

</details>

<details>
<summary>20. Qu’est-ce que Composer et comment fonctionne la gestion des dépendances ?</summary>

#### PHP

Composer est le gestionnaire de dépendances standard pour PHP. Il installe, met à jour et autoload les bibliothèques du projet de manière reproductible.

1. **Fichiers principaux**

- `composer.json` - déclare les métadonnées du projet, les packages requis, les règles d’autoload et les scripts.
- `composer.lock` - verrouille les versions exactes des packages résolues pour le projet.
- `vendor/` - dépendances installées et autoloader Composer.

2. **Comment fonctionne la gestion des dépendances**

- Tu déclares des contraintes dans `composer.json` (par exemple `^11.0`).
- Composer résout un graphe de dépendances compatible.
- Les versions exactes résolues sont écrites dans `composer.lock`.
- L’équipe/CI installe les versions verrouillées exactes pour des builds déterministes.

3. **Workflow de base**

```bash
# Ajouter une dépendance
composer require monolog/monolog

# Installer depuis le lock file
composer install

# Mettre à jour les dépendances (re-résolution des contraintes)
composer update
```

4. **Contraintes de version**

- `^1.2` - autorise des mises à jour non cassantes jusqu’à `<2.0.0`.
- `~1.2.3` - autorise les patch/minor dans cette branche.
- Les versions exactes sont possibles mais souvent trop rigides pour les bibliothèques.

5. **Intégration autoload**

Composer génère `vendor/autoload.php` et prend en charge le mapping PSR-4 depuis `composer.json`.

```php
require __DIR__ . '/vendor/autoload.php';
```

6. **Bonnes pratiques**

- Commit `composer.lock` pour les applications.
- Utiliser `composer install` en CI/production.
- Utiliser `composer update` intentionnellement et relire les changements du lock file.
- Préférer des versions de packages stables.
- Auditer régulièrement les dépendances (`composer audit`).

Composer est essentiel en PHP moderne car il standardise la gestion des packages, l’autoloading et les builds reproductibles entre environnements.

</details>

<details>
<summary>21. Que sont les standards PSR et pourquoi sont-ils importants ?</summary>

#### PHP

Les PSR (PHP Standards Recommendations) sont des standards communautaires publiés par le PHP-FIG (PHP Framework Interop Group) pour améliorer l’interopérabilité et la cohérence entre bibliothèques et frameworks PHP.

1. **Ce que définissent les PSR**

- Des conventions de style de code (par exemple, PSR-12).
- Des conventions d’autoloading (PSR-4).
- Des interfaces communes pour les messages HTTP, middleware, conteneurs, logging, cache, etc.

2. **Pourquoi ils sont importants**

- **Interopérabilité :** des bibliothèques de fournisseurs différents fonctionnent plus facilement ensemble.
- **Prévisibilité :** interfaces et structure familières entre projets.
- **Maintenabilité :** les codebases d’équipe sont plus cohérentes et plus faciles à relire.
- **Portabilité framework :** moins de vendor lock-in quand l’architecture utilise des contrats standards.

3. **PSR couramment utilisés**

- **PSR-1 / PSR-12** - style de code de base et style étendu.
- **PSR-3** - interface de logger (`LoggerInterface`).
- **PSR-4** - standard d’autoloading.
- **PSR-6 / PSR-16** - interfaces de cache.
- **PSR-7** - interfaces des messages HTTP (Request/Response/Stream).
- **PSR-11** - interface de conteneur.
- **PSR-15** - request handlers HTTP serveur et middleware.
- **PSR-18** - interface de client HTTP.

4. **Effet pratique dans les projets réels**

- Tu peux échanger des implémentations (par exemple logger/client/conteneur) sans réécrire la logique métier.
- Les frameworks et packages s’intègrent plus vite via des interfaces partagées.
- L’outillage (linters/analyseurs statiques/adapters framework) devient plus simple à adopter.

Les PSR ne sont pas seulement des guides de style ; ce sont des contrats d’architecture qui rendent les écosystèmes PHP modernes composables et durables.

</details>

<details>
<summary>22. Qu’est-ce que PSR-7 (messages HTTP) ?</summary>

#### PHP

PSR-7 est un standard qui définit des interfaces pour les messages HTTP en PHP : requêtes, réponses, flux et fichiers uploadés.

1. **Ce que PSR-7 standardise**

- `ServerRequestInterface` - requête HTTP entrante depuis le contexte client/serveur.
- `RequestInterface` - requête sortante générique.
- `ResponseInterface` - réponse HTTP (statut, headers, corps).
- `StreamInterface` - abstraction du corps du message.
- `UploadedFileInterface` - abstraction de fichier uploadé.
- `UriInterface` - représentation d’URI.

2. **Pourquoi c’est important**

- Fournit un contrat commun entre frameworks et bibliothèques.
- Permet des pipelines middleware et des composants HTTP réutilisables.
- Réduit le vendor lock-in en codant contre des interfaces, pas des classes framework concrètes.

3. **Principe d’immutabilité**

Les messages PSR-7 sont immuables. Des méthodes comme `withHeader()` renvoient une nouvelle instance au lieu de modifier l’objet d’origine.

```php
$newResponse = $response
    ->withStatus(201)
    ->withHeader('Content-Type', 'application/json');
```

4. **Usage typique**

- Dans les middleware et handlers (souvent avec PSR-15).
- Dans les frameworks API pour le parsing de requête et la génération de réponse.
- Dans les clients/serveurs HTTP qui échangent des objets de message standardisés.

5. **Bénéfice pratique**

Un composant écrit pour PSR-7 peut généralement être réutilisé dans différents écosystèmes (Slim, Laminas, Symfony bridges, Mezzio, etc.) avec une adaptation minimale.

PSR-7 est la couche d’interopérabilité centrale pour la gestion des messages HTTP dans les applications PHP modernes.

</details>

<details>
<summary>23. Qu’est-ce que PSR-11 (conteneur de dépendances) ?</summary>

#### PHP

PSR-11 est l’interface standard pour les conteneurs d’injection de dépendances en PHP. Elle définit comment le code applicatif peut récupérer des services depuis un conteneur de manière agnostique vis-à-vis du framework.

1. **Interfaces PSR-11 principales**

- `Psr\Container\ContainerInterface`
- `Psr\Container\ContainerExceptionInterface`
- `Psr\Container\NotFoundExceptionInterface`

Méthodes principales :
- `get(string $id): mixed`
- `has(string $id): bool`

2. **Ce que cela résout**

- Standardise l’accès au conteneur entre bibliothèques/frameworks.
- Permet aux composants de dépendre d’un contrat commun plutôt que d’implémentations de conteneur spécifiques.
- Améliore l’interopérabilité et la portabilité.

3. **Exemple d’usage simple**

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

4. **Note de conception importante**

PSR-11 définit **comment lire des services**, pas comment les enregistrer/construire. Les API d’enregistrement sont spécifiques à chaque conteneur.

5. **Bonnes pratiques**

- Préférer l’injection par constructeur dans le code applicatif.
- Utiliser la lecture directe du conteneur surtout dans les couches infrastructure/bootstrap.
- Éviter l’anti-pattern Service Locator dans la logique domaine/métier.
- Type-hinter des interfaces plutôt que des implémentations concrètes dès que possible.

PSR-11 est un standard minimal mais important qui rend l’usage des conteneurs de dépendances cohérent dans l’écosystème PHP.

</details>

<details>
<summary>24. Qu’est-ce que PSR-15 (middleware) ?</summary>

#### PHP

PSR-15 est le standard qui définit le middleware HTTP côté serveur et les request handlers en PHP. Il fonctionne avec les interfaces de messages requête/réponse de PSR-7.

1. **Interfaces PSR-15 principales**

- `Psr\Http\Server\MiddlewareInterface`
- `Psr\Http\Server\RequestHandlerInterface`

Contrats de méthode :
- Middleware : `process(ServerRequestInterface $request, RequestHandlerInterface $handler): ResponseInterface`
- Handler : `handle(ServerRequestInterface $request): ResponseInterface`

2. **Comment fonctionne le pipeline middleware**

- La requête entre dans la chaîne middleware.
- Chaque middleware peut :
  valider/modifier la requête, court-circuiter avec une réponse, ou passer la requête à l’étape suivante.
- Le handler final génère la réponse.
- La réponse peut être modifiée au retour à travers la pile middleware.

3. **Responsabilités typiques du middleware**

- Authentification/autorisation
- CORS
- Logging/tracing
- Rate limiting
- Validation de requête
- Conversion exception-vers-réponse

4. **Exemple simple de middleware**

```php
use Psr\Http\Message\ResponseInterface;
use Psr\Http\Message\ServerRequestInterface;
use Psr\Http\Server\MiddlewareInterface;
use Psr\Http\Server\RequestHandlerInterface;

final class AuthMiddleware implements MiddlewareInterface
{
    public function process(ServerRequestInterface $request, RequestHandlerInterface $handler): ResponseInterface
    {
        // vérifier l’auth, puis continuer
        return $handler->handle($request);
    }
}
```

5. **Pourquoi PSR-15 est important**

- Rend le middleware réutilisable entre frameworks/écosystèmes.
- Standardise les points d’extension du cycle de vie des requêtes.
- Encourage une séparation propre des préoccupations transversales.

PSR-15 fournit le contrat d’interopérabilité pour les pipelines HTTP basés middleware dans les applications PHP modernes.

</details>

<details>
<summary>25. Qu’est-ce que PSR-18 (client HTTP) ?</summary>

#### PHP

PSR-18 est l’interface standard pour les clients HTTP en PHP. Elle définit comment le code applicatif envoie des requêtes HTTP sortantes de manière agnostique vis-à-vis de l’implémentation.

1. **Contrat PSR-18 principal**

- Interface principale : `Psr\Http\Client\ClientInterface`
- Méthode principale : `sendRequest(RequestInterface $request): ResponseInterface`
- Fonctionne avec les objets requête/réponse PSR-7.

2. **Quel problème cela résout**

- Découple la logique métier des bibliothèques client HTTP spécifiques.
- Rend les intégrations portables et plus faciles à tester.
- Permet de changer d’implémentation client sans réécrire le code service.

3. **Usage de base**

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

PSR-18 définit des interfaces d’exception standard pour les échecs client (erreurs de requête, erreurs réseau/transport), ce qui permet une gestion d’erreurs cohérente entre implémentations.

5. **Bonnes pratiques**

- Type-hinter `ClientInterface` dans les services.
- Construire les requêtes via les factories PSR-17.
- Configurer timeouts/retries/circuit-breakers dans la couche infrastructure.
- Mocker l’interface client dans les tests pour un comportement déterministe.

PSR-18 standardise la communication HTTP sortante et constitue un élément clé d’un code d’intégration interopérable et maintenable dans les applications PHP modernes.

</details>

<details>
<summary>26. Qu’est-ce que l’injection de dépendances et l’inversion de contrôle ?</summary>

#### PHP

L’injection de dépendances (DI) et l’inversion de contrôle (IoC) sont des principes d’architecture pour construire un code faiblement couplé et testable.

1. **Inversion de contrôle (IoC)**

IoC signifie qu’une classe ne crée pas et ne contrôle pas directement ses dépendances ; ce contrôle est déplacé à l’extérieur (vers la couche framework/conteneur/bootstrap).

2. **Injection de dépendances (DI)**

DI est une manière concrète d’implémenter IoC : les dépendances sont fournies (injectées) depuis l’extérieur au lieu d’être créées avec `new` à l’intérieur de la classe.

3. **Pourquoi c’est important**

- Réduit le couplage entre composants.
- Améliore la testabilité (mocking/stubbing facile).
- Rend le code plus simple à étendre et refactoriser.
- Soutient des frontières d’architecture propres.

4. **Sans DI (fortement couplé)**

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

5. **Avec DI (faiblement couplé)**

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

6. **Styles DI courants**

- Injection par constructeur (préférée).
- Injection par méthode.
- Injection par setter/propriété (moins préférée pour les dépendances requises).

7. **Relation avec les conteneurs**

Un conteneur DI automatise la construction et le câblage des objets, mais la DI reste un principe de conception indépendant de tout conteneur spécifique.

DI + IoC sont fondamentaux dans les frameworks PHP modernes et essentiels pour des codebases maintenables et scalables.

</details>

<details>
<summary>27. Que sont les conteneurs de services et comment fonctionnent-ils ?</summary>

#### PHP

Un conteneur de services (conteneur DI) est un composant qui gère la création d’objets, le câblage des dépendances et le cycle de vie dans une application.

1. **Ce que fait un conteneur**

- Stocke les définitions/bindings de services.
- Résout automatiquement les dépendances (souvent via réflexion et type hints).
- Construit des graphes d’objets (service + toutes les dépendances imbriquées).
- Gère les durées de vie (singleton/scoped/transient selon le framework).

2. **Pourquoi c’est utile**

- Centralise la configuration des dépendances.
- Supprime le câblage manuel répétitif avec `new ...`.
- Simplifie le remplacement d’implémentations (interface -> classe concrète).
- Améliore la maintenabilité dans les grandes applications.

3. **Flux typique**

- Tu enregistres des bindings :
  `LoggerInterface` -> `MonologLogger`
- Tu demandes au conteneur un service :
  `OrderService`
- Le conteneur construit `OrderService` en résolvant récursivement les arguments requis du constructeur.

4. **Exemple conceptuel**

```php
$container->set(LoggerInterface::class, MonologLogger::class);
$container->set(OrderService::class, fn($c) => new OrderService($c->get(LoggerInterface::class)));

$service = $container->get(OrderService::class);
```

5. **Concepts de durée de vie des services**

- **Singleton/shared :** une seule instance réutilisée.
- **Transient/factory :** nouvelle instance à chaque résolution.
- **Scoped/request :** une instance par scope de requête (dépend du framework).

6. **Bonnes pratiques**

- Enregistrer des abstractions (interfaces), pas des classes concrètes, quand c’est possible.
- Garder le code métier/domaine agnostique du conteneur.
- Utiliser l’injection par constructeur par défaut.
- Éviter d’appeler le conteneur directement en profondeur dans la logique domaine (anti-pattern Service Locator).

Les conteneurs de services sont des outils d’infrastructure qui automatisent la gestion des dépendances et gardent les applications PHP modernes modulaires et composables.

</details>

<details>
<summary>28. Qu’est-ce que le middleware et le cycle de vie des requêtes dans les frameworks ?</summary>

#### PHP

Dans les frameworks PHP modernes, les middleware sont des couches qui traitent les requêtes et réponses HTTP autour de votre logique centrale de route/contrôleur. Le cycle de vie de la requête est le chemin complet entre la requête entrante et la réponse finale.

1. **Ce qu’est le middleware**

- Un composant de pipeline qui peut :
  inspecter/modifier la requête, arrêter le traitement avec sa propre réponse, ou passer le contrôle à la couche suivante.
- Souvent implémenté via des contrats de style PSR-15 dans les écosystèmes modernes.

2. **Responsabilités typiques du middleware**

- Authentification et autorisation
- CORS
- Rate limiting
- Normalisation/validation des entrées
- Logging, tracing, métriques
- Gestion des exceptions et formatage des réponses

3. **Cycle de vie typique d’une requête**

1. La requête HTTP atteint le serveur web (Nginx/Apache) et le runtime PHP.
2. Le bootstrap du framework charge la configuration, les services et les routes.
3. Le pipeline middleware global démarre.
4. La route est résolue et les middleware spécifiques à la route s’exécutent.
5. Le contrôleur/handler exécute la logique métier.
6. La réponse remonte à travers la pile middleware (post-processing).
7. La réponse finale est envoyée au client.

4. **Pourquoi ce modèle est utile**

- Sépare les préoccupations transversales des contrôleurs.
- Garde les handlers de routes focalisés sur la logique métier.
- Rend le comportement composable et réutilisable.
- Fournit des points d’extension cohérents pour les politiques de plateforme.

5. **Conseils pratiques**

- Garder chaque middleware centré sur une seule responsabilité.
- Ordonner les middleware intentionnellement (par exemple, gestion d’erreurs à l’extérieur).
- Éviter la logique métier lourde dans le middleware.
- Préférer des middleware stateless quand c’est possible.

Middleware + cycle de vie des requêtes sont des concepts architecturaux centraux derrière un traitement HTTP propre et prévisible dans les frameworks PHP.

</details>

<details>
<summary>29. Qu’est-ce que MVC et comment est-il implémenté dans les frameworks PHP ?</summary>

#### PHP

MVC (Model-View-Controller) est un pattern d’architecture qui sépare les préoccupations de l’application en couche données/métier, rendu UI et orchestration des requêtes.

1. **Composants MVC**

- **Model** - logique domaine/données, règles et interaction de persistance.
- **View** - couche de présentation (templates/HTML/formatage JSON).
- **Controller** - reçoit la requête, coordonne les cas d’usage, renvoie la réponse.

2. **Comment cela fonctionne dans les frameworks PHP**

Flux typique :
1. Le routeur associe l’URL à une action de contrôleur.
2. Le contrôleur valide l’entrée et appelle la couche domaine/service/model.
3. Le model/service récupère ou modifie les données.
4. Le contrôleur passe le résultat à la vue/template ou renvoie une réponse API.
5. Le framework émet la réponse HTTP finale.

3. **Exemples de responsabilités**

- Contrôleur : `UserController@show($id)`
- Model/Service : récupérer l’utilisateur, appliquer les règles métier
- Vue : rendre `user/show.blade.php` (ou ressource JSON)

4. **Pourquoi MVC est utile**

- Séparation claire des responsabilités.
- Maintenance et tests plus simples.
- Meilleure collaboration d’équipe (préoccupations frontend/backend séparées).
- Structure de projet prévisible.

5. **Pièges courants**

- Contrôleurs trop lourds avec logique métier.
- Models trop lourds mélangeant trop de responsabilités.
- Couplage fort entre contrôleurs et détails de persistance.

6. **Pratique moderne en PHP**

De nombreux projets utilisent MVC comme base mais déplacent la logique métier vers des couches service/use-case, en gardant des contrôleurs fins et des vues simples.

MVC reste une base pratique dans des frameworks comme Laravel et les applications de style Symfony, surtout lorsqu’il est combiné avec des principes de couches propres.

</details>

<details>
<summary>30. Qu’est-ce que l’architecture hexagonale / clean en PHP ?</summary>

#### PHP

L’architecture hexagonale (Ports and Adapters) et la Clean Architecture sont des approches qui gardent la logique métier indépendante des frameworks, des bases de données et des services externes.

1. **Idée centrale**

- Les règles métier sont placées au centre (domaine/use cases).
- Les systèmes externes sont traités comme des adaptateurs remplaçables.
- Les dépendances pointent vers l’intérieur : l’infrastructure dépend du domaine, et non l’inverse.

2. **Blocs principaux**

- **Couche Domaine** : entités, value objects, règles de domaine.
- **Couche Application/use-case** : orchestre les scénarios métier.
- **Ports (interfaces)** : contrats pour les capacités nécessaires (repositories, gateways, bus).
- **Adaptateurs** : implémentations concrètes (repository MySQL, client HTTP, publisher de queue).
- **Couche Delivery** : contrôleurs HTTP/CLI/consumers qui appellent les use cases.

3. **Pourquoi c’est important**

- Le framework ou la DB peuvent changer avec un impact minimal sur la logique métier centrale.
- Les use cases sont plus faciles à tester en isolation.
- Des frontières claires réduisent le couplage et le risque de maintenance à long terme.

4. **Exemple orienté PHP**

- `CreateOrderUseCase` dépend de `OrderRepositoryInterface` et `PaymentGatewayInterface`.
- Un contrôleur Laravel/Symfony invoque le use case.
- Le repository MySQL et l’adaptateur Stripe implémentent les interfaces dans la couche infrastructure.

5. **Structure de dossiers (conceptuelle)**

- `src/Domain/...`
- `src/Application/...`
- `src/Infrastructure/...`
- `src/Interface/Http/...` (ou `Presentation/...`)

6. **Lignes directrices pratiques**

- Garder les classes framework hors de la couche domaine.
- Exprimer les frontières via des interfaces à la limite application/domaine.
- Mapper les DTO request/response du framework aux frontières, pas dans le domaine.
- Commencer simple et introduire des couches quand la complexité le justifie.

L’architecture hexagonale/clean aide les systèmes PHP à rester adaptables, testables et stables à mesure que le produit et l’infrastructure évoluent.

</details>

<details>
<summary>31. Qu’est-ce que le pattern Repository ?</summary>

#### PHP

Repository est un pattern qui abstrait l’accès aux données derrière une interface orientée domaine, afin que la logique métier travaille avec des collections/agrégats plutôt qu’avec les détails SQL/ORM directement.

1. **Idée centrale**

- Les couches domaine/application dépendent d’interfaces de repository.
- La couche infrastructure fournit des implémentations concrètes (PDO/Doctrine/Eloquent/API).
- Les préoccupations de persistance restent en dehors de la logique des use cases.

2. **Ce que fournit typiquement un Repository**

- Récupérer des entités/agrégats (`findById`, `findByCriteria`).
- Persister des changements (`save`, `remove`).
- Exposer des opérations de requête exprimées en termes métier.

3. **Exemple d’interface**

```php
interface OrderRepositoryInterface
{
    public function getById(string $id): ?Order;
    public function save(Order $order): void;
}
```

4. **Pourquoi c’est utile**

- Découple la logique métier de la technologie de stockage.
- Améliore la testabilité (implémentations en mémoire/mock faciles).
- Soutient les frontières d’architecture (hexagonale/clean).
- Rend les migrations/refactors plus sûrs quand la persistance change.

5. **Erreurs courantes**

- Transformer le repository en CRUD générique sans intention métier.
- Dupliquer inutilement toutes les méthodes ORM à l’identique.
- Mettre la logique métier dans l’implémentation du repository.

6. **Conseils pratiques**

- Garder les interfaces de repository à la frontière domaine/application.
- Exposer des méthodes significatives pour les use cases, pas pour les internals DB.
- Utiliser des specifications/query objects pour les filtres complexes si nécessaire.
- Laisser les repositories gérer la persistance ; garder l’orchestration dans les services/use cases.

Le pattern Repository est surtout précieux dans les systèmes PHP moyens/grands où la longévité de la logique domaine compte plus que la vitesse CRUD à court terme.

</details>

<details>
<summary>32. Que sont les DTO et les Value Objects ?</summary>

#### PHP

Les DTO et les Value Objects sont des patterns différents, souvent utilisés ensemble dans l’architecture PHP moderne.

1. **DTO (Data Transfer Object)**

- Un objet simple utilisé pour transférer des données structurées entre couches/processus.
- Contient généralement des champs et peu/pas de logique métier.
- Aide à éviter le passage de tableaux bruts entre frontières.

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

- Un objet domaine défini par sa valeur, pas par son identité.
- Généralement immuable et auto-validant.
- Encapsule des règles métier pour un concept précis (Email, Money, Currency, etc.).

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

3. **Différences clés**

- **But** : le DTO transporte des données ; le VO modélise une signification métier.
- **Logique** : DTO minimal ; VO peut faire respecter des invariants.
- **Identité** : DTO souvent incidente ; VO comparé par valeur.
- **Mutabilité** : DTO peut être mutable/immuable ; VO devrait généralement être immuable.

4. **Quand utiliser chacun**

- Utiliser les DTO aux frontières (requête/réponse HTTP, messaging, entrées/sorties de couche application).
- Utiliser les Value Objects dans le modèle domaine pour exprimer des concepts validés de manière sûre.

Les DTO améliorent la clarté du flux de données, tandis que les Value Objects améliorent la justesse du domaine et empêchent les états invalides.

</details>

<details>
<summary>33. Qu’est-ce que la POO en PHP ?</summary>

#### PHP

La POO (Programmation Orientée Objet) en PHP est un paradigme où le code est organisé autour d’objets qui combinent des données (état) et des comportements (méthodes).

1. **Concepts POO de base**

- **Classe** : modèle définissant propriétés et méthodes.
- **Objet** : instance d’une classe.
- **Encapsulation** : contrôle l’accès aux internes (`public/protected/private`).
- **Héritage** : les classes enfants réutilisent/étendent le comportement parent.
- **Polymorphisme** : interfaces communes avec implémentations interchangeables.
- **Abstraction** : exposer les contrats essentiels, cacher les détails d’implémentation.

2. **Pourquoi la POO est utilisée en PHP**

- Modélise clairement les concepts métier.
- Encourage un code modulaire et réutilisable.
- Améliore la maintenabilité dans les codebases moyennes/grandes.
- S’intègre naturellement avec DI, interfaces et architecture framework.

3. **Exemple de base**

```php
interface NotifierInterface
{
    public function send(string $message): void;
}

final class EmailNotifier implements NotifierInterface
{
    public function send(string $message): void
    {
        // envoyer un email
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

4. **Fonctionnalités POO modernes en PHP**

- Propriétés typées et strict types
- Interfaces et classes abstraites
- Traits pour la réutilisation horizontale de code
- Attributs, enums, propriétés/classes readonly
- Constructor property promotion

5. **Bonnes pratiques**

- Préférer la composition à l’héritage quand c’est possible.
- Coder contre des interfaces, pas des classes concrètes.
- Garder des classes focalisées (responsabilité unique).
- Éviter les “god objects” avec trop de responsabilités.

La POO en PHP est la base de la plupart des frameworks modernes et de la conception orientée domaine.

</details>

<details>
<summary>34. Quelle est la différence entre une interface et une classe abstraite ?</summary>

#### PHP

Les interfaces et les classes abstraites définissent toutes deux des contrats, mais elles servent des objectifs de conception différents.

1. **Interface**

- Définit uniquement des signatures de méthodes (contrat) et des constantes.
- Pas d’état d’instance (pas de propriétés avec état runtime).
- Une classe peut implémenter plusieurs interfaces.
- Focus : contrat de capacité et polymorphisme.

```php
interface PaymentGatewayInterface
{
    public function charge(int $amount): bool;
}
```

2. **Classe abstraite**

- Peut contenir à la fois des méthodes abstraites et des méthodes implémentées.
- Peut avoir un état/comportement partagé (propriétés, helpers protégés, logique constructeur).
- Une classe ne peut étendre qu’une seule classe abstraite/de base.
- Focus : implémentation partielle + comportement de base commun.

```php
abstract class BaseGateway
{
    public function __construct(protected string $apiKey) {}

    abstract public function charge(int $amount): bool;

    protected function log(string $message): void
    {
        // logique partagée
    }
}
```

3. **Différences clés**

- **Héritage multiple de type** : plusieurs interfaces, une seule classe parente.
- **Code partagé** : classe abstraite oui, interface non.
- **Couplage** : l’interface est en général plus souple ; la classe abstraite introduit un couplage d’héritage.

4. **Quand choisir**

- Utiliser une **interface** quand tu as besoin d’implémentations interchangeables et de contrats clairs.
- Utiliser une **classe abstraite** quand les implémentations partagent une logique/état de base significatifs.

5. **Règle pratique**

Préfère les interfaces aux frontières publiques d’architecture ; utilise les classes abstraites comme outils de réutilisation interne quand l’héritage est justifié.

Interface = « ce qu’il peut faire », classe abstraite = « ce qu’il est partiellement implémenté pour être ».

</details>

<details>
<summary>35. Que sont les traits et quand faut-il les utiliser ?</summary>

#### PHP

Les traits en PHP sont un mécanisme de réutilisation horizontale de code : ils permettent aux classes de réutiliser des méthodes (et membres associés) sans héritage.

1. **Ce qu’est un trait**

- Une unité de code réutilisable déclarée avec `trait`.
- Incluse dans des classes via `use`.
- Aide à partager un comportement entre des hiérarchies de classes non liées.

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

2. **Quand les traits sont utiles**

- Comportements transversaux partagés (helpers de logging, timestamps, petits comportements utilitaires).
- Réutilisation entre classes qui ne peuvent pas partager une classe parente commune.
- Réduction de duplication quand la composition serait trop verbeuse pour de petits blocs de comportement.

3. **Résolution de conflits entre traits**

Si deux traits définissent la même méthode, PHP fournit une résolution de conflit :
- `insteadof` pour choisir une implémentation.
- `as` pour aliaser/renommer des méthodes.

4. **Limites et risques**

- Les traits peuvent masquer le couplage et brouiller les responsabilités de classe s’ils sont surutilisés.
- Les gros “god traits” deviennent difficiles à tester et maintenir.
- Ce sont des inclusions de code, pas de vrais contrats polymorphes.

5. **Bonnes pratiques**

- Garder les traits petits et focalisés.
- Utiliser les traits pour la réutilisation de comportement, pas pour la modélisation métier.
- Préférer interfaces + composition pour les frontières d’architecture principales.
- Éviter de stocker un état partagé mutable complexe dans les traits.

Les traits sont un outil PHP pratique pour une réutilisation ciblée, mais ils fonctionnent mieux comme complément léger d’une bonne conception objet, pas comme remplacement.

</details>

<details>
<summary>36. Que sont les méthodes magiques et quand sont-elles déclenchées ?</summary>

#### PHP

Les méthodes magiques sont des méthodes PHP spéciales (préfixées par `__`) qui sont déclenchées automatiquement par le moteur lors d’événements spécifiques du cycle de vie des objets ou d’interactions.

1. **Méthodes magiques du cycle de vie de l’objet**

- `__construct()` - appelée lors de la création de l’objet.
- `__destruct()` - appelée lors de la destruction de l’objet (ou fin de script).
- `__clone()` - appelée après le clonage de l’objet.

2. **Méthodes magiques d’accès aux propriétés**

- `__get($name)` - lecture d’une propriété inaccessible/non définie.
- `__set($name, $value)` - écriture d’une propriété inaccessible/non définie.
- `__isset($name)` - `isset()`/`empty()` sur une propriété inaccessible/non définie.
- `__unset($name)` - `unset()` sur une propriété inaccessible/non définie.

3. **Interception d’appels de méthodes**

- `__call($name, $arguments)` - appel d’une méthode d’instance inaccessible/non définie.
- `__callStatic($name, $arguments)` - appel d’une méthode statique inaccessible/non définie.

4. **Chaîne/invocation/sérialisation**

- `__toString()` - objet utilisé comme chaîne.
- `__invoke(...$args)` - objet utilisé comme fonction.
- `__serialize()` / `__unserialize()` - logique de sérialisation personnalisée.

5. **Helpers d’export d’état/debug**

- `__set_state(array $properties)` - appelée par la recréation `var_export()`.
- `__debugInfo()` - sortie personnalisée pour `var_dump()`.

6. **Exemple simple**

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

7. **Bonnes pratiques**

- Utiliser les méthodes magiques intentionnellement, pas comme architecture par défaut.
- Garder le comportement explicite et prévisible.
- Éviter de masquer des erreurs avec des `__get/__set` trop permissifs.
- Préférer des propriétés/méthodes typées quand c’est possible.

Les méthodes magiques sont de puissants points d’extension, mais elles doivent être utilisées avec prudence car elles peuvent réduire la clarté en cas de surutilisation.

</details>

<details>
<summary>37. Qu’est-ce que le late static binding ?</summary>

#### PHP

Le Late Static Binding (LSB) en PHP permet la résolution des méthodes/propriétés statiques selon la classe appelée à l’exécution, et pas seulement selon la classe où la méthode est définie.

1. **`self::` vs `static::`**

- `self::` est lié à la classe où la méthode est déclarée (early binding).
- `static::` est résolu vers la classe appelée à l’exécution (late static binding).

2. **Pourquoi c’est important**

- Permet un comportement polymorphe en contexte statique.
- Utile dans les hiérarchies d’héritage où les classes enfants doivent contrôler la classe/valeur retournée.
- Courant dans les patterns factory et les API de style Active Record.

3. **Exemple**

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

Si `self::TABLE` était utilisé, le comportement resterait figé au contexte de déclaration de la classe de base.

4. **Mot-clé lié**

- Le type de retour `static` (`public static function make(): static`) utilise aussi la sémantique du late static et renvoie le type de la classe appelée.

5. **Conseils pratiques**

- Utiliser `static::` quand les sous-classes doivent personnaliser le comportement statique.
- Utiliser `self::` quand le comportement doit volontairement rester fixé à l’implémentation de la classe de base.

Le late static binding est une fonctionnalité POO importante pour des hiérarchies de classes extensibles en PHP.

</details>

<details>
<summary>38. Comment les objets sont-ils gérés en mémoire en PHP ?</summary>

#### PHP

En PHP, les objets sont gérés par le Zend Engine comme des structures allouées sur le tas (heap), référencées par des handles d’objet, avec gestion mémoire automatique via comptage de références et garbage collection.

1. **Modèle de stockage des objets**

- Les instances d’objet sont allouées dans la mémoire gérée par le moteur (heap).
- Les variables contiennent des références (handles) vers les entrées d’objet, pas des copies complètes de l’objet.
- Affecter une variable objet à une autre copie le handle, pas l’état de l’objet.

```php
$a = new stdClass();
$a->x = 1;

$b = $a;      // même référence d’objet
$b->x = 2;

echo $a->x;   // 2
```

2. **Comptage de références**

- Le moteur suit combien de zvals référencent une valeur/un objet.
- Quand ce compteur tombe à zéro, la mémoire peut être libérée.
- Pour les objets, cela implique généralement l’appel du destructeur et le nettoyage.

3. **Garbage collector (GC)**

- Le comptage de références seul ne peut pas collecter les références cycliques.
- Le GC PHP détecte et nettoie les déchets cycliques (par exemple, des graphes d’objets qui se référencent mutuellement).

4. **Comportement du clonage**

- `clone` crée une nouvelle instance d’objet (identité séparée).
- `__clone()` peut personnaliser la logique d’état après clonage.

5. **Nuance pass-by-reference**

- Passer des objets aux fonctions se fait effectivement par handle (les changements d’objet sont visibles à l’extérieur).
- Tu n’as généralement pas besoin de `&` pour modifier l’état d’un objet à travers les frontières de fonctions.

6. **Implications perf/mémoire**

- Les grands graphes d’objets augmentent la pression mémoire.
- Les références longue durée (caches statiques, closures, conteneurs globaux) peuvent retarder le nettoyage.
- Les références circulaires dans des workers longue durée doivent être surveillées pour éviter une croissance type fuite.

7. **Conseils pratiques**

- Garder des graphes d’objets intentionnels et bornés.
- Faire explicitement `unset` sur de grandes structures temporaires dans les processus longue durée quand nécessaire.
- Utiliser des outils de profiling pour inspecter les hotspots mémoire.
- Faire attention aux singletons statiques/état global dans les workers/daemons.

La gestion mémoire des objets PHP est efficace pour les cycles de vie de requête classiques, mais les processus longue durée exigent une discipline mémoire délibérée.

</details>

<details>
<summary>39. Qu’est-ce que PDO et pourquoi est-il préféré ?</summary>

#### PHP

PDO (PHP Data Objects) est une couche d’abstraction d’accès aux bases de données en PHP qui fournit une API cohérente pour travailler avec plusieurs moteurs de base.

1. **Ce que PDO fournit**

- Interface unifiée pour les opérations DB (`MySQL`, `PostgreSQL`, `SQLite`, etc.).
- Requêtes préparées et binding de paramètres.
- Support des transactions.
- Modes de fetch et gestion des erreurs configurables.

2. **Pourquoi PDO est préféré**

- **Portabilité :** même style de code entre différentes bases.
- **Sécurité :** les requêtes préparées réduisent le risque d’injection SQL.
- **Maintenabilité :** code d’accès DB plus propre et standardisé.
- **Contrôle :** comportement explicite des transactions/erreurs.

3. **Exemple de base**

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

4. **PDO vs APIs spécifiques au driver**

- PDO offre une abstraction commune et des frontières d’architecture plus propres.
- Les APIs spécifiques au driver peuvent exposer des fonctionnalités de niche, mais réduisent la portabilité.

5. **Bonnes pratiques**

- Toujours activer le mode exception (`PDO::ERRMODE_EXCEPTION`).
- Utiliser des requêtes préparées pour toute entrée externe.
- Définir explicitement le charset dans le DSN (par exemple `utf8mb4`).
- Gérer explicitement les transactions pour les écritures multi-étapes.

PDO est préféré en PHP moderne car il combine sécurité, portabilité et patterns d’accès base clairs.

</details>

<details>
<summary>40. Que sont les requêtes préparées et le binding de paramètres ?</summary>

#### PHP

Les requêtes préparées sont des requêtes SQL compilées comme des templates avec des placeholders, où les valeurs sont fournies séparément via le binding de paramètres.

1. **Comment elles fonctionnent**

- Étape 1 : préparer le SQL avec des placeholders (`:email`, `?`).
- Étape 2 : binder/exécuter les valeurs séparément.
- La base traite les valeurs liées strictement comme des données, pas comme une syntaxe SQL.

2. **Pourquoi c’est important**

- Défense principale contre l’injection SQL.
- Code de requête plus propre et plus sûr.
- Meilleure gestion des types de données et de l’échappement par le driver.
- Peut améliorer les performances pour l’exécution répétée de requêtes (selon DB/driver).

3. **Exemple de placeholder nommé (PDO)**

```php
$stmt = $pdo->prepare(
    'SELECT id, email FROM users WHERE email = :email AND status = :status'
);

$stmt->execute([
    'email' => $email,
    'status' => $status,
]);
```

4. **Exemple de placeholder positionnel**

```php
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = ?');
$stmt->execute([$id]);
```

5. **Binding avec types explicites**

```php
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = :id');
$stmt->bindValue(':id', $id, PDO::PARAM_INT);
$stmt->execute();
```

6. **Nuance importante**

- Les requêtes préparées protègent les valeurs, pas les identifiants SQL (noms de table/colonne).
- Les identifiants dynamiques doivent être contrôlés par des allowlists strictes.

7. **Bonnes pratiques**

- Utiliser des requêtes préparées pour chaque requête incluant une entrée externe.
- Éviter la concaténation de chaînes pour les conditions SQL.
- Garder les templates SQL lisibles et explicites.
- Combiner avec des utilisateurs DB à moindre privilège et des frontières transactionnelles.

Requêtes préparées + binding de paramètres constituent la base standard, non optionnelle, pour un accès DB sécurisé en PHP.

</details>

<details>
<summary>41. Comment fonctionnent les transactions en PHP ?</summary>

#### PHP

Les transactions en PHP (via PDO/MySQLi) regroupent plusieurs opérations base de données en une seule unité atomique : soit tous les changements sont validés, soit tous sont annulés.

1. **Opérations transactionnelles de base**

- `beginTransaction()` - démarre une transaction.
- `commit()` - enregistre définitivement tous les changements.
- `rollBack()` - annule tous les changements non validés.

2. **Pourquoi les transactions sont nécessaires**

- Garantir la cohérence des données sur des écritures multi-étapes.
- Éviter des mises à jour partielles en cas d’erreur.
- Préserver les invariants métier (par exemple, débit et crédit doivent réussir tous les deux).

3. **Exemple PDO de base**

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

4. **Isolation et concurrence**

- Le niveau d’isolation DB contrôle la visibilité/le verrouillage entre transactions concurrentes.
- Anomalies courantes : dirty reads, non-repeatable reads, phantom reads.
- Choisir le niveau d’isolation selon les compromis cohérence/performance.

5. **Pièges pratiques**

- Les transactions longues maintiennent des verrous et nuisent à la concurrence.
- Les appels API/réseau externes dans une transaction DB augmentent la fenêtre d’échec.
- Oublier le rollback sur exception peut laisser le workflow incohérent.

6. **Bonnes pratiques**

- Garder les transactions aussi courtes que possible.
- Inclure uniquement les opérations DB qui doivent être atomiques.
- Utiliser une gestion d’erreurs explicite et des garanties de rollback.
- Concevoir une logique de retry pour les deadlocks/conflits de sérialisation si nécessaire.

Les transactions sont un mécanisme central de fiabilité pour les workflows critiques d’intégrité (finance, inventaire, etc.) dans les systèmes PHP.

</details>

<details>
<summary>42. Qu’est-ce qu’un ORM (Eloquent / Doctrine) et quels sont les compromis ?</summary>

#### PHP

ORM (Object-Relational Mapping) est une technique qui mappe les tables/lignes de base de données vers des objets PHP, ce qui permet de travailler avec des entités domaine au lieu de SQL brut dans la majorité du code applicatif.

1. **Ce que l’ORM apporte**

- Classes entité/modèle mappées aux schémas DB.
- APIs/builders de requêtes au lieu de SQL manuel pour les opérations courantes.
- Gestion des relations (`hasMany`, `belongsTo`, etc.).
- Unit-of-work/suivi des changements (surtout avec Doctrine).
- Outils de migration/écosystème dans de nombreux frameworks.

2. **ORM PHP courants**

- **Eloquent (Laravel)** :
  style Active Record, productivité rapide, syntaxe expressive.
- **Doctrine ORM** :
  style Data Mapper, modélisation domaine riche, séparation des responsabilités plus forte.

3. **Avantages**

- Développement plus rapide pour les fonctionnalités orientées CRUD.
- Code de persistance plus propre et lisible pour les scénarios courants.
- Parcours des relations plus simple et workflows centrés modèle.
- Scaffoldings basés conventions et intégrations écosystème.

4. **Compromis / inconvénients**

- Surcharge d’abstraction et coût potentiel en performance.
- Requêtes cachées/implicites (problème N+1).
- SQL/reporting complexes nécessitent souvent encore du SQL manuel.
- Les patterns spécifiques ORM peuvent augmenter la courbe d’apprentissage et le lock-in.

5. **Quand l’ORM fonctionne le mieux**

- Applications métier avec opérations fréquentes sur le cycle de vie des entités.
- Équipes qui valorisent productivité et code maintenable centré modèle.

6. **Quand préférer SQL brut/query builders**

- Hot paths critiques en performance.
- Requêtes analytiques/reporting complexes.
- Fonctionnalités spécifiques au vendor DB et contrôle SQL fin.

7. **Stratégie pratique**

- Utiliser l’ORM par défaut pour les opérations domaine courantes.
- Profiler et optimiser les goulots d’étranglement.
- Mixer ORM et SQL optimisé si nécessaire (approche hybride).
- Être explicite sur eager/lazy loading pour éviter les explosions de requêtes.

L’ORM est un multiplicateur de productivité en PHP, mais une bonne ingénierie exige de comprendre où l’abstraction aide et où un contrôle SQL plus bas niveau est préférable.

</details>

<details>
<summary>43. Qu’est-ce que le connection pooling et pourquoi est-ce important ?</summary>

#### PHP

Le connection pooling est une technique où les connexions base de données sont réutilisées depuis un pool géré, au lieu d’être créées et fermées pour chaque opération.

1. **Pourquoi les connexions sont coûteuses**

- Ouvrir des connexions DB implique handshake réseau, authentification et allocation de ressources serveur.
- Les reconnexions fréquentes augmentent la latence et la charge CPU côté application et DB.

2. **Ce que fait le pooling**

- Maintient un ensemble réutilisable de connexions ouvertes.
- Assigne une connexion existante au travail entrant.
- La remet dans le pool après usage pour réutilisation par les requêtes/jobs suivants.

3. **Pourquoi c’est important**

- Réduit la latence des requêtes.
- Améliore le débit sous charge.
- Réduit le churn et l’overhead des connexions DB.
- Stabilise le comportement pour les systèmes à forte concurrence.

4. **Nuance dans le contexte PHP**

- Dans le modèle de requête PHP-FPM classique, chaque processus worker a un cycle de vie isolé ; le pooling est donc moins direct que dans les runtimes longue durée.
- Approches pratiques courantes :
  connexions persistantes (`PDO::ATTR_PERSISTENT` avec prudence),
  poolers/proxys externes (par exemple PgBouncer pour PostgreSQL),
  workers longue durée (RoadRunner/Swoole/consommateurs de queue) où la réutilisation est plus directe.

5. **Compromis / risques**

- Les connexions obsolètes/cassées doivent être détectées et recyclées.
- Un mauvais dimensionnement du pool peut causer contention ou surcharge DB.
- Les connexions persistantes peuvent retenir des ressources serveur plus longtemps qu’attendu.

6. **Bonnes pratiques**

- Définir des limites de pool/connexion cohérentes avec la capacité DB.
- Utiliser des health checks/timeouts de connexion.
- Surveiller le nombre de connexions, le temps d’attente et les taux d’erreur.
- Garder des requêtes efficaces ; le pooling ne corrige pas un SQL lent.

Le connection pooling est une technique clé de scalabilité pour les systèmes PHP intensifs en base de données, surtout sous trafic concurrent soutenu.

</details>

<details>
<summary>44. Comment structurer une application PHP scalable ?</summary>

#### PHP

Une application PHP scalable est structurée autour de frontières claires, d’une architecture prévisible et d’une préparation opérationnelle à la croissance du trafic, de la taille d’équipe et de la complexité fonctionnelle.

1. **Utiliser des frontières en couches/modules**

- Découper par responsabilités et domaines métier, pas seulement par dossiers techniques.
- Couches typiques :
  `Domain`, `Application/UseCases`, `Infrastructure`, `Interface/HTTP`.

2. **Garder la logique métier agnostique du framework**

- Mettre les règles cœur dans la couche domaine/use-case.
- Garder les contrôleurs fins.
- Dépendre d’interfaces ; garder les adaptateurs DB/framework en couche infrastructure.

3. **Concevoir pour une scalabilité horizontale stateless**

- Éviter l’état mutable local dans les instances applicatives.
- Stocker l’état partagé dans des systèmes externes :
  DB, Redis, object storage, queues.
- Rendre sessions/cache prêts pour des déploiements multi-nœuds.

4. **Stratégie données et persistance**

- Utiliser repositories/services pour les frontières de persistance.
- Appliquer indexation et optimisation de requêtes tôt.
- Introduire du cache (application/requête/HTTP) quand justifié.
- Utiliser séparation lecture/écriture et partitionnement seulement si nécessaire.

5. **Traitement asynchrone et en arrière-plan**

- Déplacer les tâches non critiques/lentes vers des queues (emails, exports, notifications, webhooks).
- Garder le chemin de requête rapide et déterministe.

6. **Scalabilité opérationnelle**

- Containeriser les workloads (Docker/K8s/plateformes managées).
- Utiliser health checks, logs structurés, métriques, tracing.
- Ajouter rate limiting, timeouts, retries, circuit breakers.
- Construire un CI/CD avec stratégie de rollout et rollback sûrs.

7. **Scalabilité du codebase pour les équipes**

- Appliquer standards de code et analyse statique.
- Maintenir des frontières modulaires entre packages.
- Utiliser des tests d’intégration et de contrat autour des chemins critiques.
- Documenter les décisions d’architecture (ADR) et contrats de service.

8. **Trajectoire d’évolution pratique**

- Commencer par un monolithe modulaire avec frontières fortes.
- Extraire des services seulement quand des contraintes claires de scale/équipe le justifient.

La scalabilité en PHP est d’abord une discipline d’architecture + opérations, pas un simple choix de framework.

</details>

<details>
<summary>45. Comment gérer la configuration (variables d’environnement) ?</summary>

#### PHP

Dans les applications PHP modernes, la configuration doit être externalisée hors du code et fournie via des variables d’environnement, selon les principes 12-factor.

1. **Principe de base**

- Garder la config hors du code source.
- Traiter l’environnement comme la source des paramètres spécifiques au déploiement :
  credentials DB, URLs API, hôtes cache, feature flags, etc.

2. **Setup typique**

- Développement : fichier `.env` (chargé par framework/bootstrap).
- Production : vraies variables d’environnement depuis la plateforme/l’orchestrateur (pas de `.env` dans le repo).

3. **Comment les valeurs sont consommées**

- Lire l’env une seule fois dans le bootstrap de configuration.
- Mapper vers une structure/objet de config typé.
- Injecter la config dans les services via DI.

4. **Bonnes pratiques**

- Séparer la config par environnement (`dev`, `staging`, `prod`) via des valeurs env.
- Fournir des valeurs par défaut uniquement pour des valeurs locales non sensibles.
- Valider la config requise au démarrage et échouer vite si elle manque/est invalide.
- Garder des clés de config cohérentes et documentées.

5. **Ce qu’il ne faut pas faire**

- Ne pas hardcoder des credentials dans le code.
- Ne pas commit des secrets de production dans le repository.
- Ne pas appeler `getenv()` de façon aléatoire dans la logique domaine.
- Ne pas mélanger logique métier et logique de chargement de config.

6. **Pattern pratique**

Utiliser des fichiers de config centraux qui tirent depuis l’env, par exemple :
- `config/database.php`
- `config/cache.php`
- `config/app.php`

Puis injecter la config résolue dans les services dépendants.

7. **Note sécurité**

Les variables d’environnement sont meilleures que les secrets hardcodés, mais restent sensibles :
limiter l’accès, éviter de logger les valeurs complètes, et combiner avec des secret managers dédiés pour les credentials critiques.

La gestion de configuration via variables d’environnement garde les apps PHP portables, sécurisées et cohérentes entre environnements.

</details>

<details>
<summary>46. Comment gérez-vous les secrets (Vault, AWS Secrets Manager) ?</summary>

#### PHP

La gestion des secrets est la pratique consistant à stocker, faire tourner et accéder de manière sécurisée à des valeurs sensibles (clés API, mots de passe DB, tokens, certificats) en dehors du code applicatif.

1. **Pourquoi des secret managers dédiés sont nécessaires**

- Empêcher les fuites de secrets dans le repository/l’historique.
- Centraliser le contrôle d’accès et l’audit.
- Permettre une rotation sûre sans redéployer le code.
- Réduire le risque opérationnel par rapport aux fichiers `.env` simples.

2. **Outils courants**

- **HashiCorp Vault** : secrets dynamiques, leases, accès basé politiques, fortes capacités d’audit.
- **AWS Secrets Manager** : stockage/rotation managés intégrés à IAM et aux services AWS.
- (Également courant : parameter stores cloud-native ou solutions adossées KMS.)

3. **Flux secret recommandé**

1. L’identité de l’app est établie (rôle IAM, workload identity, méthode d’auth Vault).
2. L’app récupère les secrets requis au démarrage (ou à la demande avec cache).
3. Les secrets sont gardés en mémoire uniquement quand nécessaire.
4. Les événements de rotation sont gérés sans valeurs hardcodées.

4. **Bonnes pratiques**

- Ne jamais commit des secrets dans git (y compris fichiers d’exemple avec valeurs réelles).
- Utiliser des politiques d’accès à moindre privilège par service/environnement.
- Faire tourner les secrets régulièrement et lors d’incidents.
- Logger les métadonnées d’accès, jamais les valeurs des secrets.
- Séparer les secrets par environnement (`dev/staging/prod`) et par scope de service.
- Utiliser des credentials à courte durée de vie quand possible (identifiants DB dynamiques/tokens).

5. **Pattern d’intégration PHP**

- Récupérer les secrets dans la couche bootstrap/infrastructure.
- Les mapper dans des objets de config typés.
- Injecter config/secrets dans les services dépendants via DI.
- Ajouter une stratégie de fallback et retry en cas d’indisponibilité du secret manager.

6. **Considérations opérationnelles**

- Mettre en cache les secrets avec TTL pour réduire latence et limites API.
- Planifier le comportement de bootstrap si le backend de secrets est temporairement indisponible.
- Tester la procédure de rotation en staging avant rollout en production.

Utiliser Vault/AWS Secrets Manager transforme la gestion des secrets d’un simple env variable ad-hoc en un processus de sécurité contrôlé, adapté aux systèmes PHP de production.

</details>

<details>
<summary>47. Qu’est-ce que l’app 12-factor dans le contexte PHP ?</summary>

#### PHP

L’app 12-factor est un ensemble de principes d’ingénierie cloud-native pour construire des services portables, scalables et maintenables. En PHP, ces principes aident à passer d’applications “couplées au serveur” à des services modernes déployables.

1. **Codebase**

- Une seule codebase suivie dans le contrôle de version.
- Plusieurs déploiements (dev/staging/prod) depuis la même codebase.

2. **Dépendances**

- Déclarer explicitement les dépendances dans `composer.json`.
- Éviter de dépendre de packages système installés globalement.

3. **Config**

- Stocker la config dans des variables d’environnement, pas dans le code.
- Garder secrets et valeurs spécifiques à l’environnement hors du repository.

4. **Backing services**

- Traiter DB, cache, queue, object storage comme des ressources attachées.
- Y accéder via config/URLs pour pouvoir les remplacer selon l’environnement.

5. **Séparation build, release, run**

- Construire l’artifact une seule fois.
- Promouvoir le même artifact entre environnements.
- Garder la config runtime séparée du build.

6. **Processus**

- Exécuter l’app comme des processus stateless.
- Stocker l’état persistant dans des services externes (DB/Redis/S3/etc.).

7. **Port binding et concurrence**

- Exposer les services via des entrypoints HTTP/runtime.
- Scaler via réplication de processus/conteneurs, pas seulement via tuning vertical.

8. **Disposability et parité**

- Démarrage/arrêt rapides pour des déploiements sûrs et l’autoscaling.
- Garder les environnements dev/staging/prod aussi similaires que possible.

9. **Logs et tâches admin**

- Traiter les logs comme des flux d’événements (stdout/agrégateurs).
- Exécuter les tâches admin/migration comme des processus one-off utilisant la même codebase.

10. **Implications pratiques spécifiques PHP**

- Utiliser Composer + config env + état externalisé.
- Runtime compatible conteneurs (PHP-FPM/workers CLI).
- Queue workers pour les tâches en arrière-plan.
- Pipeline CI/CD avec artifacts immuables.

Appliquer les principes 12-factor en PHP améliore la fiabilité de déploiement, la scalabilité opérationnelle et la maintenabilité long terme.

</details>

<details>
<summary>48. Qu’est-ce que la conteneurisation (Docker) dans les applications PHP ?</summary>

#### PHP

La conteneurisation empaquette une application PHP avec ses dépendances d’exécution dans une image portable, afin qu’elle fonctionne de manière cohérente en local, en CI, en staging et en production.

1. **Ce que Docker apporte aux applications PHP**

- Environnement d’exécution reproductible (version de PHP, extensions, bibliothèques système).
- Parité des environnements entre les machines des développeurs et la production.
- Déploiement, rollback et mise à l’échelle facilités.
- Isolation entre les services (application, base de données, cache, file, worker).

2. **Stack PHP conteneurisée typique**

- Conteneur PHP-FPM (runtime applicatif)
- Conteneur Nginx/Apache (serveur web)
- Conteneurs séparés pour DB/Redis/workers de file/tâches cron

3. **Schéma de Dockerfile de base**

```dockerfile
FROM php:8.4-fpm-alpine

RUN docker-php-ext-install pdo pdo_mysql opcache
WORKDIR /var/www/html

COPY . .
RUN php -v
```

4. **Pourquoi c’est important pour la scalabilité**

- La mise à l’échelle horizontale devient plus simple (réplication des conteneurs).
- Les déploiements immuables basés sur image réduisent la dérive et les écarts de configuration.
- Fonctionne naturellement avec des plateformes d’orchestration (Kubernetes, ECS, Nomad).

5. **Bonnes pratiques**

- Utiliser de petites images de base et des builds multi-stage.
- Épingler les versions/tags d’image pour la reproductibilité.
- Garder les images stateless ; stocker les données persistantes à l’extérieur.
- Injecter la configuration/les secrets via variables d’environnement/gestionnaires de secrets, pas dans l’image.
- Exécuter des health checks et exposer des logs structurés vers stdout/stderr.

6. **Pièges fréquents**

- Exécuter tout dans un seul conteneur (web + DB + queue) en production.
- Écrire des données applicatives persistantes sur le système de fichiers du conteneur.
- Images volumineuses avec des outils de build inutiles dans la couche runtime.

La conteneurisation est une pratique clé des opérations PHP modernes, car elle standardise le comportement d’exécution et améliore la déployabilité à l’échelle.

</details>

<details>
<summary>49. Qu’est-ce qu’OPcache et comment améliore-t-il les performances ?</summary>

#### PHP

OPcache est un cache de bytecode PHP intégré qui stocke en mémoire partagée le bytecode compilé des scripts, afin que PHP n’ait pas besoin d’analyser et compiler les mêmes fichiers à chaque requête.

1. **Quel problème OPcache résout**

- Sans OPcache, chaque requête répète :
  lire le fichier PHP -> parser -> compiler en opcodes -> exécuter.
- Cette compilation répétée ajoute de la charge CPU et de la latence.

2. **Comment OPcache améliore les performances**

- Les opcodes compilés sont mis en cache en mémoire et réutilisés entre les requêtes.
- Réduit l’utilisation CPU et le temps de réponse.
- Augmente le débit sous charge.
- Améliore les performances de démarrage des frameworks avec beaucoup de fichiers.

3. **Configuration de production typique**

- Activer OPcache dans le runtime PHP (`opcache.enable=1`).
- Ajuster les limites mémoire et nombre de fichiers :
  `opcache.memory_consumption`, `opcache.max_accelerated_files`.
- Désactiver la validation des timestamps pour des artifacts de release immuables :
  `opcache.validate_timestamps=0` (avec reset du cache déclenché au déploiement).

4. **Paramètres courants utiles**

- `opcache.enable`
- `opcache.memory_consumption`
- `opcache.max_accelerated_files`
- `opcache.interned_strings_buffer`
- `opcache.validate_timestamps`
- `opcache.revalidate_freq`

5. **Considérations de déploiement**

- Quand le code change, le bytecode en cache doit être rafraîchi.
- Dans les déploiements immuables/conteneurisés, redémarrer les workers PHP suffit généralement.
- Dans les déploiements mutables, utiliser une stratégie contrôlée d’invalidation/redémarrage.

6. **Bonnes pratiques**

- Toujours utiliser OPcache en production.
- Surveiller le taux de hit du cache, l’usage mémoire et les redémarrages.
- Dimensionner le cache selon la croissance de la codebase.
- Combiner OPcache avec le cache applicatif/base de données pour des gains complets.

OPcache est l’une des fonctionnalités de performance les plus impactantes et les moins coûteuses en effort pour les environnements PHP de production.

</details>

<details>
<summary>50. Qu’est-ce que le JIT en PHP et quand est-il utile ?</summary>

#### PHP

Le JIT (compilation Just-In-Time) en PHP est une optimisation du moteur qui compile certains opcodes Zend en code machine natif à l’exécution.

1. **Ce que fait le JIT**

- Flux PHP normal : script -> opcodes -> exécution par l’interpréteur.
- Avec JIT : les chemins de code chauds peuvent être compilés en code natif et exécutés plus rapidement.

2. **Là où le JIT peut aider**

- Charges CPU-intensives :
  calculs lourds, boucles, traitement de données, algorithmes computationnels.
- Workers CLI de longue durée et tâches de calcul spécialisées.

3. **Là où le JIT apporte souvent peu**

- Applications web typiques dominées par l’I/O :
  requêtes base de données, appels réseau, accès cache, rendu de templates.
- Dans beaucoup de charges CRUD/API, OPcache et l’optimisation des requêtes comptent plus que le JIT.

4. **Relation avec OPcache**

- Le JIT est construit au-dessus de l’infrastructure OPcache.
- OPcache apporte généralement le plus grand gain de base pour la plupart des applications.
- Le JIT est une couche d’optimisation supplémentaire pour le code CPU-bound.

5. **Recommandations pratiques**

- Activer et benchmarker avant/après sur votre charge réelle.
- Ne pas supposer des accélérations globales pour tous les types de requêtes.
- Prioriser d’abord les corrections des goulots d’étranglement :
  SQL lent, requêtes N+1, appels réseau excessifs, cache inefficace.

6. **Règle pratique**

- Pour les backends web classiques : l’impact du JIT est souvent modeste.
- Pour les charges PHP fortement orientées calcul : le JIT peut apporter des gains significatifs.

Le JIT est un outil d’optimisation utile, mais sa valeur dépend fortement du profil de charge.

</details>

<details>
<summary>51. Qu’est-ce que le lazy loading et où est-il utilisé ?</summary>

#### PHP

Le lazy loading est une technique où les données ou objets sont chargés uniquement lorsqu’ils sont réellement nécessaires, au lieu de tout charger dès le départ.

1. **Idée principale**

- Retarder l’initialisation coûteuse jusqu’au premier accès.
- Réduire l’utilisation mémoire initiale et le temps de démarrage.
- Payer le coût seulement pour les chemins réellement utilisés.

2. **Où le lazy loading est utilisé en PHP**

- Relations ORM (proxies de relations Doctrine/Eloquent).
- Initialisation des services dans les conteneurs DI (services différés).
- Chargement à la demande de grosses configurations/ressources.
- Traitement de flux/fichiers où les chunks sont chargés progressivement.

3. **Exemple ORM typique**

- L’entité `User` est chargée.
- `User->orders` n’est pas récupéré immédiatement.
- Le premier accès aux commandes déclenche la requête SQL.

4. **Avantages**

- Réponse initiale plus rapide dans de nombreux cas.
- Empreinte mémoire plus faible quand toutes les données ne sont pas nécessaires.
- Meilleure scalabilité pour des graphes d’objets complexes.

5. **Compromis et risques**

- Les requêtes cachées peuvent provoquer des problèmes de performance N+1.
- Les schémas d’accès deviennent moins explicites.
- Le lazy loading dans des boucles serrées peut exploser les allers-retours DB.

6. **Bonnes pratiques**

- Utiliser l’eager loading quand vous savez que les données liées sont nécessaires.
- Profiler le nombre de requêtes et la latence.
- Garder les frontières lazy explicites dans la couche repository/query.
- Éviter le lazy loading dans les boucles de sérialisation/sortie.

7. **Règle pratique**

- Utiliser le lazy loading pour les dépendances/données optionnelles ou rarement utilisées.
- Utiliser l’eager loading pour les données liées prévisibles et fréquemment consultées.

Le lazy loading est puissant pour l’optimisation des performances, mais seulement avec une bonne visibilité du comportement des requêtes et une stratégie de chargement délibérée.

</details>

<details>
<summary>52. Quels sont les goulots d’étranglement de performance PHP les plus courants ?</summary>

#### PHP

La plupart des problèmes de performance PHP ne sont pas causés par le langage lui-même, mais par des I/O inefficaces, des schémas de requêtes et des choix d’architecture.

1. **Goulots d’étranglement base de données (les plus courants)**

- Requêtes N+1 dans l’usage ORM.
- Index manquants ou mauvais plans de requête.
- Sur-récupération de données (`SELECT *` quand ce n’est pas nécessaire).
- Transactions longues et contention de verrous.

2. **Réseau et I/O externes**

- APIs tierces lentes sans timeouts/retries.
- Trop d’appels sortants synchrones dans le chemin de requête.
- Absence de circuit breakers/fallbacks.

3. **Inefficacités au niveau applicatif**

- Logique métier lourde exécutée à chaque requête.
- Recalcul de résultats coûteux au lieu du caching.
- Sérialisation/désérialisation excessive ou traitement de payloads volumineux.

4. **Surcharge d’autoload/bootstrap**

- Bootstrap framework lourd pour des endpoints triviaux.
- Trop de classes/providers de configuration chargés.
- OPcache mal configuré.

5. **Surcharge du système de fichiers et des logs**

- Écritures disque fréquentes dans le chemin de requête.
- Logging bloquant/trop verbeux sans traitement asynchrone.
- Volumes de stockage lents en conteneurs/VM.

6. **Pression mémoire**

- Grosses collections en mémoire et tableaux non bornés.
- Boucles inefficaces sur de très grands jeux de données.
- Workers long-lived qui conservent des références involontairement.

7. **Caching absent/inefficace**

- Pas de cache pour les données à forte lecture.
- Mauvaise stratégie d’invalidation menant à des données périmées/misses fréquents.
- Cache stampede sous charge.

8. **Comment traiter cela de façon systématique**

- Profiler avant d’optimiser.
- Prioriser d’abord les endpoints/requêtes les plus chauds.
- Ajouter optimisation des requêtes + caching + offloading asynchrone.
- Surveiller la latence p95/p99, le temps DB, le ratio de hit cache et les taux d’erreur.

Dans les systèmes PHP, les gains les plus rapides viennent généralement de l’optimisation des requêtes, de la stratégie de cache et de la réduction des I/O synchrones dans le chemin de requête.

</details>

<details>
<summary>53. Comment profile-t-on une application PHP ?</summary>

#### PHP

Le profiling est le processus qui consiste à mesurer où sont réellement dépensés le temps d’exécution, le CPU, la mémoire et les I/O, afin d’optimiser sur la base de preuves plutôt que d’hypothèses.

1. **Ce qu’il faut mesurer en premier**

- Latence des requêtes (p50/p95/p99)
- Temps base de données et nombre de requêtes
- Durée des appels API externes
- Utilisation mémoire et pic mémoire
- Fonctions/chemins de code les plus chauds

2. **Outils de profiling PHP courants**

- **Blackfire** - profiling orienté production et recommandations de performance.
- **Xdebug (mode profiler)** - traces détaillées/callgrind pour analyse locale.
- **Famille Tideways/XHProf** - profiling au niveau des fonctions avec options à faible overhead.
- **Outils APM** (Datadog/New Relic/etc.) pour la visibilité distribuée des requêtes.

3. **Workflow de profiling pratique**

1. Reproduire l’endpoint/job lent avec des données réalistes.
2. Capturer une trace de profil.
3. Identifier les principaux contributeurs (DB, I/O externes, fonctions CPU-intensives).
4. Optimiser un goulot d’étranglement à la fois.
5. Reprofiler et comparer les métriques.

4. **Ce qui apparaît le plus souvent comme hotspot**

- Requêtes ORM N+1
- Index manquants / scans SQL coûteux
- Sérialisation répétée et traitement de payloads volumineux
- Appels réseau synchrones dans le chemin de requête
- Surcharge excessive du framework/bootstrap

5. **Focus profiling mémoire**

- Grandes listes/collections chargées d’un coup
- Références long-lived dans les workers
- Graphes d’objets inutiles et données dupliquées

6. **Bonnes pratiques**

- Profiler dans des environnements proches du comportement production.
- Benchmarker avant et après chaque optimisation.
- Suivre les régressions en CI/CD avec des budgets de performance pour les endpoints critiques.
- Combiner profiling code avec profiling DB (`EXPLAIN`, logs de requêtes lentes).

Le profiling transforme l’optimisation des performances en un processus d’ingénierie mesurable et c’est la méthode la plus fiable pour améliorer la vitesse d’une application PHP en toute sécurité.

</details>

<details>
<summary>54. Comment fonctionne le caching (Redis, Memcached) ?</summary>

#### PHP

Le caching stocke des données pré-calculées ou fréquemment demandées dans un stockage rapide (généralement en mémoire) pour éviter des opérations coûteuses répétées, comme les requêtes DB ou des calculs lourds.

1. **Comment le cache fonctionne (flux de base)**

1. L’application reçoit une requête pour des données.
2. Elle vérifie le cache par clé.
3. Si hit : elle retourne rapidement la valeur en cache.
4. Si miss : elle charge depuis la source (DB/API), stocke en cache avec TTL, puis retourne la valeur.

2. **Backends de cache courants**

- **Redis** :
  data store en mémoire avec structures riches, options de persistance, pub/sub, fonctionnalités distribuées.
- **Memcached** :
  cache clé-valeur distribué en mémoire, simple et orienté caching éphémère haute vitesse.

3. **Cas d’usage typiques du cache en PHP**

- Cache des résultats de requêtes
- Stockage de sessions
- Cache de réponse/fragment
- Compteurs de rate limiting
- Verrous et clés d’idempotence
- Données de référence calculées/de configuration

4. **Concepts importants de conception du cache**

- **Stratégie de clés** : namespacing et versioning prévisibles (`user:42:v2`).
- **TTL** : choisir l’expiration selon la volatilité des données.
- **Invalidation** : invalidation explicite à l’écriture quand la fraîcheur est critique.
- **Modèle de cohérence** : accepter la cohérence éventuelle quand c’est approprié.

5. **Pièges courants**

- Cache stampede (beaucoup de misses simultanés).
- Données périmées à cause d’une stratégie d’invalidation faible.
- Valeurs surdimensionnées et mauvaise conception des clés.
- Traiter le cache comme source de vérité.

6. **Bonnes pratiques**

- Mettre en cache seulement les lectures coûteuses/haute fréquence.
- Utiliser des TTL courts et raisonnables, avec jitter pour réduire les expirations synchronisées.
- Ajouter une protection anti-stampede (verrous, coalescence de requêtes, stale-while-revalidate).
- Surveiller hit rate, latence, évictions et usage mémoire.
- Garder la DB comme source de vérité ; le cache est une couche d’accélération.

Le caching Redis/Memcached est l’un des moyens les plus efficaces pour réduire la latence et la charge base de données dans les systèmes PHP en production.

</details>

<details>
<summary>55. Qu’est-ce que le traitement asynchrone en PHP ?</summary>

#### PHP

Le traitement asynchrone consiste à déplacer les tâches lentes ou non critiques hors du flux HTTP synchrone, afin que les utilisateurs obtiennent des réponses rapides pendant que le travail en arrière-plan est exécuté séparément.

1. **Pourquoi l’async est nécessaire**

- Les cycles requête-réponse doivent rester courts.
- Certaines opérations sont coûteuses :
  emails, traitement de fichiers, génération de rapports, appels API externes.
- Faire tout cela en ligne augmente la latence et l’impact des pannes.

2. **Comment cela fonctionne dans les systèmes PHP**

1. L’application principale reçoit la requête.
2. L’état critique est sauvegardé rapidement.
3. Un job/événement de fond est poussé dans une file.
4. Un processus worker consomme et exécute la tâche de manière asynchrone.

3. **Charges async typiques**

- Notifications email/SMS/push
- Traitement média (images/vidéo/PDF)
- Imports/exports de données
- Livraison/retry de webhooks
- Mises à jour d’index de recherche
- Traitement analytics/événements

4. **Bénéfices**

- Latence côté utilisateur plus faible.
- Meilleure résilience (retries, dead-letter queues).
- Débit amélioré grâce au découplage des jobs lourds.
- Séparation plus claire entre travail en ligne et hors ligne.

5. **Compromis**

- Complexité opérationnelle accrue (queues/workers/monitoring).
- Cohérence éventuelle entre l’écriture et les effets secondaires.
- Besoin d’idempotence et de handlers sûrs en retry.

6. **Bonnes pratiques**

- Garder les payloads de job minimaux (IDs, pas des objets complets).
- Rendre les handlers idempotents.
- Configurer retry/backoff et gestion des dead letters.
- Surveiller la profondeur de file, le retard des workers et le taux d’échec.
- Définir quelles tâches sont critiques en sync vs différées en async.

Dans l’architecture PHP, le traitement asynchrone est une technique clé pour faire monter l’expérience utilisateur et la fiabilité sous charge réelle de production.

</details>

<details>
<summary>56. Que sont les files (RabbitMQ, Kafka, files Redis) ?</summary>

#### PHP

Les files sont des mécanismes de messagerie utilisés pour découpler producteurs et consommateurs, ce qui permet le traitement asynchrone, le buffering et une exécution fiable en arrière-plan.

1. **Concept de base des files**

- Le producteur publie un message/job.
- Le broker le stocke temporairement.
- Le consommateur/worker le traite plus tard.
- Cela retire le travail lourd du flux de requête synchrone.

2. **Pourquoi les files sont importantes**

- Lisser les pics de trafic (buffering).
- Améliorer le temps de réponse (décharger les tâches de fond).
- Augmenter la fiabilité avec retries et dead-letter handling.
- Découpler services et composants.

3. **Technologies de files courantes en PHP**

- **RabbitMQ** :
  broker de messages traditionnel, routage puissant, acknowledgements, retries.
- **Kafka** :
  journal d’événements distribué, traitement de flux à haut débit, messages rejouables.
- **Files basées sur Redis** (par exemple, files Laravel) :
  simples et rapides pour de nombreux jobs applicatifs de fond.

4. **Cas d’usage typiques des files en PHP**

- Envoi email/SMS/push
- Livraison de webhooks
- Traitement de fichiers/images/vidéo
- Indexation de recherche
- Génération de rapports
- Fan-out d’intégration/événements

5. **Concepts de fiabilité**

- **Ack/Nack** : confirmer le succès ou demander un retry.
- **Politique de retry** : backoff exponentiel, nombre max de tentatives.
- **Dead-letter queue (DLQ)** : isoler les messages toxiques/en échec.
- **Idempotence** : retraitement sûr sans effets secondaires dupliqués.

6. **Bonnes pratiques**

- Garder des payloads de message petits (préférer les IDs aux gros objets).
- Versionner les schémas de messages.
- Rendre les consommateurs idempotents et observables (logs/métriques/tracing).
- Surveiller profondeur de file, lag de traitement, taux d’échec, taux de retry.
- Définir des SLA clairs pour la latence de traitement.

Les files sont un bloc fondamental pour construire des systèmes PHP scalables et résilients avec des charges asynchrones.

</details>

<details>
<summary>57. Qu’est-ce que l’architecture orientée événements en PHP ?</summary>

#### PHP

L’architecture orientée événements (EDA) est un style où les composants du système communiquent en publiant et en réagissant à des événements au lieu d’appels synchrones directs.

1. **Concept de base**

- Un producteur émet un événement (par exemple, `OrderPlaced`).
- Les consommateurs intéressés s’abonnent et le traitent indépendamment.
- L’émetteur n’a pas besoin de savoir quels consommateurs existent.

2. **Pourquoi l’EDA est utile**

- Découple les modules/services.
- Améliore l’extensibilité (de nouveaux consommateurs peuvent être ajoutés sans changer l’émetteur).
- Supporte le traitement asynchrone et une meilleure scalabilité.
- Rend les effets secondaires explicites sous forme d’événements de domaine/d’intégration.

3. **Cas d’usage PHP typiques**

- Commande créée -> envoyer un email, réserver le stock, publier des analytics.
- Utilisateur inscrit -> séquence de bienvenue, sync CRM, journal d’audit.
- Paiement réussi -> génération de facture, notifications, fulfillment.

4. **Types d’événements**

- **Événements de domaine** : faits métier significatifs à l’intérieur de la frontière du domaine.
- **Événements d’intégration** : événements publiés pour d’autres services/systèmes.

5. **Options de livraison dans l’écosystème PHP**

- Bus/dispatcher d’événements in-process (événements au niveau framework).
- Livraison adossée à une file/un broker (RabbitMQ/Kafka/Redis streams/files) pour l’async et la distribution inter-services.

6. **Points de conception clés**

- Handlers idempotents (les événements peuvent être livrés plus d’une fois).
- Garanties d’ordre (dépendent de la stratégie de transport/topic/partition).
- Politique de retry et de dead-letter en cas d’échec.
- Évolution de schéma/version des payloads d’événements.

7. **Bonnes pratiques**

- Utiliser des payloads d’événements immuables et versionnés.
- Garder les handlers ciblés et indépendants.
- Traiter les événements comme des faits (nommage au passé : `UserRegistered`).
- Ajouter de l’observabilité : IDs de corrélation, tracing, métriques de lag de traitement.

L’EDA en PHP aide à construire des systèmes modulaires et scalables où les workflows peuvent évoluer sans couplage fort entre composants.

</details>

<details>
<summary>58. Que sont les WebSockets et quand les utiliser ?</summary>

#### PHP

Les WebSockets sont un protocole qui crée une connexion persistante et bidirectionnelle entre client et serveur, permettant l’échange de données en temps réel sans polling HTTP répété.

1. **En quoi les WebSockets diffèrent de HTTP**

- HTTP : requête/réponse, généralement courte et initiée par le client.
- WebSocket : une connexion longue durée où les deux côtés peuvent pousser des messages à tout moment.

2. **Quand les WebSockets sont utiles**

- Chat et messagerie en temps réel.
- Tableaux de bord live/mises à jour de monitoring.
- Édition collaborative et indicateurs de présence.
- Flux trading/marché, événements de jeu, notifications.

3. **Pourquoi ne pas utiliser les WebSockets partout**

- Ajoute de la complexité opérationnelle (état de connexion, scalabilité, routage).
- Inutile pour des pages CRUD simples avec des mises à jour peu fréquentes.
- Dans certains cas, SSE ou short polling peut être plus simple et suffisant.

4. **Considérations d’architecture PHP**

- Le modèle de requête PHP-FPM traditionnel n’est pas idéal pour des connexions longues.
- Approches courantes :
  serveurs WebSocket dédiés (Ratchet/Swoole/RoadRunner),
  service temps réel séparé + intégration backend PHP via Redis/broker de messages.

5. **Enjeux de scalabilité**

- Fan-out de connexions et efficacité du broadcast.
- Sticky sessions vs backplane pub/sub partagé.
- Scalabilité horizontale avec couches de messagerie type Redis/Kafka/NATS.

6. **Sécurité et fiabilité**

- Authentifier le handshake/session WebSocket.
- Valider le schéma des messages et imposer l’autorisation par canal/topic.
- Appliquer rate limits et protection contre les abus.
- Gérer reconnexions, heartbeats et backpressure.

7. **Règle pratique**

- Utiliser les WebSockets quand le server push à faible latence est une exigence produit centrale.
- Préférer des approches HTTP plus simples quand le quasi-temps réel suffit.

Les WebSockets sont un outil temps réel puissant dans les écosystèmes PHP lorsqu’ils sont associés au bon runtime et au bon modèle de scalabilité.

</details>

<details>
<summary>59. Comment construire des API REST en PHP ?</summary>

#### PHP

Construire des API REST en PHP signifie exposer des ressources via HTTP avec des routes claires, des méthodes standard, des codes de statut prévisibles et des contrats JSON cohérents.

1. **Principes REST de base**

- Endpoints orientés ressources (`/users`, `/orders/{id}`).
- Méthodes HTTP appropriées :
  `GET`, `POST`, `PUT/PATCH`, `DELETE`.
- Requêtes stateless.
- Format de représentation cohérent (généralement JSON).

2. **Couches API typiques en PHP**

- Couche route/contrôleur (entrée/sortie HTTP).
- Couche validation/auth/middleware.
- Couche service/use-case (logique métier).
- Couche repository/données (persistance).

3. **Éléments essentiels de conception**

- Stratégie de versioning (`/api/v1/...` ou basée sur en-tête).
- Enveloppe de réponse standard et format d’erreur standard.
- Conventions de pagination/filtrage/tri.
- Idempotence pour les opérations d’écriture concernées.

4. **Correction HTTP**

- Retourner des codes de statut pertinents (`200`, `201`, `204`, `400`, `401`, `403`, `404`, `422`, `500`).
- Définir `Content-Type: application/json`.
- Utiliser des en-têtes de cache quand c’est approprié.

5. **Base de sécurité**

- Authentification (token/JWT/session selon le contexte).
- Contrôles d’autorisation par ressource/action.
- Validation des entrées et encodage des sorties.
- Rate limiting et protection contre les abus.
- Protection CSRF pour les API basées sur cookies.

6. **Qualité opérationnelle**

- Logging structuré + IDs de corrélation de requêtes.
- Gestion centralisée des exceptions.
- Documentation OpenAPI/Swagger.
- Tests de contrat/d’intégration pour les endpoints critiques.

7. **Exemple de forme d’endpoint**

- `POST /api/v1/orders`
- Valider le payload -> exécuter le use case -> retourner `201 Created` avec body/location de la ressource.

8. **Guide pratique**

- Garder les contrôleurs légers.
- Garder la logique métier hors de la couche HTTP.
- Rendre les contrats API explicites et stables.

Une bonne API REST PHP ne se limite pas aux routes : elle repose aussi sur des contrats cohérents, un comportement sécurisé et une fiabilité opérationnelle.

</details>

<details>
<summary>60. Qu’est-ce que GraphQL et comment est-il utilisé en PHP ?</summary>

#### PHP

GraphQL est un langage de requête API et un runtime où les clients demandent exactement les champs dont ils ont besoin à partir d’un schéma typé, au lieu de consommer des payloads REST fixes.

1. **Concepts de base de GraphQL**

- **Schema** : contrat fortement typé (types, champs, arguments).
- **Queries** : opérations de lecture.
- **Mutations** : opérations d’écriture.
- **Resolvers** : fonctions/méthodes PHP qui récupèrent/calculent les données des champs.

2. **Pourquoi les équipes utilisent GraphQL**

- Éviter l’over-fetching/under-fetching courant en REST.
- Endpoint unique pour une récupération de données flexible.
- Meilleure vélocité frontend pour des besoins UI complexes.
- Forte introspection et support outillage.

3. **Comment il est utilisé en PHP**

- Définir le schéma GraphQL en code/SDL.
- Implémenter les resolvers qui appellent services/repositories.
- Exécuter la requête sur le schéma et retourner une réponse JSON.
- Intégrer auth, validation, limites de complexité et cache dans la couche d’exécution.

4. **Options de stack PHP typiques**

- `webonyx/graphql-php` (implémentation GraphQL principale)
- Intégrations/adapters framework pour les écosystèmes Laravel/Symfony

5. **Compromis**

- Plus de complexité que REST basique pour des API simples.
- Nécessite des contrôles stricts de profondeur/complexité des requêtes pour éviter les requêtes coûteuses.
- La stratégie de cache peut être plus difficile qu’avec le cache d’endpoints REST.
- Une discipline de gouvernance/versioning du schéma est essentielle.

6. **Bonnes pratiques**

- Garder les resolvers légers ; déléguer aux services applicatifs.
- Utiliser le pattern DataLoader pour éviter les appels backend N+1.
- Appliquer l’auth par champ/ressource quand nécessaire.
- Limiter profondeur/complexité des requêtes et surveiller les opérations lourdes.
- Publier la documentation du schéma et traiter les changements de schéma comme des contrats.

GraphQL en PHP est surtout efficace pour des produits riches en données avec des besoins clients complexes, à condition que l’équipe gère soigneusement la complexité des requêtes et la gouvernance du schéma.

</details>

<details>
<summary>61. Qu’est-ce que l’authentification API (JWT, OAuth) ?</summary>

#### PHP

L’authentification API vérifie qui appelle votre API et avec quelles permissions. Deux approches courantes sont l’authentification par token JWT et les flux OAuth 2.0 / OpenID Connect.

1. **Authentification basée sur JWT**

- Après une connexion réussie, le serveur émet un token signé (JWT).
- Le client envoie le token à chaque requête (généralement `Authorization: Bearer ...`).
- L’API valide la signature, l’expiration et les claims.

Claims JWT typiques :
- `sub` (subject/user id)
- `exp` (expiration)
- `iss`/`aud` (issuer/audience)
- rôles/scopes optionnels

2. **OAuth 2.0 (framework d’autorisation)**

- Conçu pour l’accès délégué et l’autorisation tierce.
- L’accès est accordé via des scopes et des durées de vie de tokens.
- Flux courants : Authorization Code (+ PKCE), Client Credentials.

3. **OpenID Connect (OIDC)**

- Couche d’identité au-dessus d’OAuth 2.0.
- Ajoute un ID token et des claims d’identité utilisateur standardisés.

4. **JWT vs OAuth (distinction pratique)**

- JWT est un format/mécanisme de token.
- OAuth est un protocole d’autorisation.
- Les tokens OAuth peuvent être JWT ou opaques.

5. **Bonnes pratiques de sécurité**

- Utiliser HTTPS uniquement.
- Garder les access tokens de courte durée ; faire tourner les refresh tokens en toute sécurité.
- Valider signature, issuer, audience et expiration à chaque requête.
- Stocker les tokens de façon sûre côté client (éviter les patterns de stockage non sûrs).
- Implémenter une stratégie de révocation/introspection quand nécessaire.

6. **Guide d’implémentation PHP**

- Utiliser des bibliothèques éprouvées pour la validation JWT/OAuth/OIDC.
- Centraliser le middleware d’authentification.
- Séparer authentification (qui) et autorisation (quoi est permis).
- Représenter les permissions comme rôles/scopes/policies vérifiés au niveau ressource.

Une authentification API forte en PHP repose sur la justesse du protocole, une bonne hygiène du cycle de vie des tokens et une validation stricte sur chaque endpoint protégé.

</details>

<details>
<summary>62. Qu’est-ce que le rate limiting et la sécurité API ?</summary>

#### PHP

Le rate limiting est un mécanisme de contrôle qui limite le nombre de requêtes qu’un client peut faire dans une fenêtre de temps donnée. C’est une partie centrale de la sécurité API au sens large.

1. **Pourquoi le rate limiting est nécessaire**

- Prévenir les abus et les attaques par force brute.
- Protéger les ressources backend contre la surcharge.
- Assurer une utilisation équitable entre clients/tenants.
- Réduire l’impact d’intégrations boguées ou malveillantes.

2. **Stratégies courantes de rate limiting**

- Fenêtre fixe (compteurs simples par intervalle).
- Fenêtre glissante (distribution plus précise).
- Token bucket / leaky bucket (tolérant aux bursts avec limites soutenues).

3. **Où les limites sont appliquées**

- Par adresse IP
- Par clé API/client id
- Par utilisateur/compte/tenant
- Par sensibilité d’endpoint (plus strict pour endpoints d’auth)

4. **Implémentation typique dans les stacks PHP**

- Vérifications au niveau middleware avec compteurs Redis/en mémoire.
- Application au niveau reverse proxy/API gateway (Nginx, API gateway cloud).
- Retourner `429 Too Many Requests` avec en-têtes de retry.

5. **Base de sécurité API (au-delà des limites)**

- Authentification forte (JWT/OAuth/OIDC).
- Contrôles d’autorisation par ressource/action.
- Validation des entrées et encodage des sorties.
- HTTPS partout + en-têtes de sécurité.
- Limites de taille/temps de requête et contrôle des timeouts.
- Journalisation d’audit, détection d’anomalies et alerting.

6. **Bonnes pratiques**

- Utiliser des contrôles en couches : gateway + middleware applicatif.
- Appliquer des quotas différents selon le plan/niveau de confiance.
- Ajouter gestion des bursts et dégradation gracieuse.
- Protéger endpoints de login/token avec règles plus strictes et lockouts.
- Surveiller hits de limite, requêtes bloquées et patterns d’attaque.

Le rate limiting est un pilier de la sécurité API ; la protection réelle vient de sa combinaison avec l’authentification, l’autorisation, la validation et l’observabilité.

</details>

<details>
<summary>63. Qu’est-ce que la pyramide de tests en PHP ?</summary>

#### PHP

La pyramide de tests est un modèle de stratégie de test qui recommande beaucoup de tests rapides de bas niveau et moins de tests lents de haut niveau afin d’équilibrer confiance, vitesse et coût de maintenance.

1. **Couches de la pyramide**

- **Base (la plus large) : tests unitaires**
  tests rapides et isolés pour fonctions/classes/règles métier.
- **Milieu : tests d’intégration**
  vérifient la collaboration entre modules (DB, cache, queue, adaptateurs externes).
- **Sommet (le plus petit) : tests end-to-end/API/UI**
  valident les flux utilisateur complets à travers tout le système.

2. **Pourquoi ce modèle fonctionne**

- Les tests unitaires sont peu coûteux et s’exécutent rapidement en grand nombre.
- Les tests d’intégration détectent les problèmes de frontières et de câblage.
- Les tests E2E offrent une confiance réaliste mais sont plus lents et plus fragiles.

3. **Mapping spécifique PHP**

- Unitaire : PHPUnit/Pest avec mocks/stubs.
- Intégration : conteneurs DB réels, repositories, clients HTTP en environnement contrôlé.
- E2E/API : tests au niveau requête contre l’application/service en exécution.

4. **Anti-patterns courants**

- « Cône de glace » : trop de tests UI/E2E, trop peu de tests unitaires.
- Sur-mocking de tout, avec perte de confiance d’intégration.
- Pas de tests de contrat pour les intégrations externes critiques.

5. **Recommandations pratiques**

- Garder la majorité des tests au niveau unitaire.
- Ajouter des tests d’intégration ciblés autour des frontières critiques.
- Garder la suite E2E petite, stable et centrée sur le métier critique.
- Exécuter les suites rapides à chaque commit ; les suites plus lourdes sur les gates main/pré-release.

6. **Résultat**

Une pyramide saine fournit un feedback rapide aux développeurs et une forte confiance de release sans temps CI excessif ni maintenance de tests flaky.

</details>

<details>
<summary>64. Qu’est-ce que le unit testing (PHPUnit / Pest) ?</summary>

#### PHP

Le unit testing vérifie le comportement des plus petites unités testables du code (fonctions, méthodes, classes) en isolation des systèmes externes.

1. **Ce que les tests unitaires doivent couvrir**

- Règles métier et calculs.
- Cas limites et validation d’entrée.
- Comportement d’erreur/exception.
- Branches de logique déterministes.

2. **Principe d’isolation**

- Les tests unitaires ne doivent pas dépendre d’une DB réelle, du réseau, du système de fichiers ou de services de queue.
- Les dépendances externes sont remplacées par des doubles de test (mocks/stubs/fakes).

3. **Outils PHP**

- **PHPUnit** : framework de test classique et largement adopté.
- **Pest** : syntaxe expressive construite sur l’écosystème PHPUnit.

4. **Exemple simple (style PHPUnit)**

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

5. **Pourquoi les tests unitaires comptent**

- Feedback rapide pendant le développement.
- Refactoring plus sûr.
- Meilleure documentation du comportement attendu.
- Détection précoce des régressions.

6. **Bonnes pratiques**

- Garder les tests petits, ciblés et déterministes.
- Utiliser une structure claire arrange-act-assert.
- Nommer les tests selon le comportement attendu.
- Éviter le sur-mocking de la logique interne.
- Exécuter les tests unitaires à chaque commit en CI.

Le unit testing avec PHPUnit/Pest est la base d’une livraison PHP fiable, car il apporte une confiance rapide et précise dans la logique cœur.

</details>

<details>
<summary>65. Qu’est-ce que l’intégration testing ?</summary>

#### PHP

L’intégration testing vérifie que plusieurs composants fonctionnent correctement ensemble (par exemple, logique applicative + base de données + cache + adaptateurs externes), tout en restant plus ciblé que les tests end-to-end complets.

1. **Ce sur quoi les tests d’intégration se concentrent**

- Frontières de modules et collaboration.
- Correction de la persistance/récupération des données.
- Comportement des adaptateurs d’infrastructure.
- Correction de la configuration et du câblage.

2. **Différence avec les tests unitaires**

- Les tests unitaires isolent un composant et mockent les dépendances.
- Les tests d’intégration utilisent des dépendances réelles ou proches du réel pour valider les interactions.

3. **Scénarios d’intégration PHP typiques**

- Repository avec DB de test/conteneur réel.
- Adaptateur client HTTP contre serveur sandbox/mock.
- Flux publication/consommation de queue en environnement contrôlé.
- Interaction route framework + middleware + contrôleur + service.

4. **Pourquoi les tests d’intégration comptent**

- Détectent des problèmes que les mocks ne révèlent pas (mismatch de schéma SQL, bugs de sérialisation, erreurs de config).
- Augmentent la confiance sur les frontières critiques.
- Réduisent les surprises en production liées au couplage infrastructure.

5. **Bonnes pratiques**

- Exécuter sur une infrastructure de test dédiée (DB/cache isolés).
- Contrôler setup/teardown des données de façon déterministe.
- Garder une portée ciblée : une préoccupation d’intégration par test.
- Éviter les dépendances réseau inutiles quand des stubs de contrat suffisent.
- Inclure la suite d’intégration en CI pour les chemins critiques.

6. **Compromis**

- Plus lents et plus lourds que les tests unitaires, donc ils doivent être moins nombreux et ciblés.

Les tests d’intégration sont le pont entre la confiance rapide des tests unitaires et la confiance système complète dans les pipelines de livraison PHP.

</details>

<details>
<summary>66. Qu’est-ce que le mocking et pourquoi est-il nécessaire ?</summary>

#### PHP

Le mocking est une technique de test où les dépendances réelles sont remplacées par des doubles de test contrôlés afin d’isoler l’unité testée et de vérifier les interactions.

1. **Pourquoi le mocking est nécessaire**

- Isoler la logique métier des systèmes externes (DB, HTTP, queue, filesystem).
- Rendre les tests rapides et déterministes.
- Simuler des scénarios rares/d’erreur difficiles à reproduire avec de vrais services.
- Vérifier les contrats de collaboration (méthode appelée avec les arguments attendus).

2. **Types courants de doubles de test**

- **Stub** : retourne des valeurs prédéfinies.
- **Mock** : vérifie les interactions/appels attendus.
- **Fake** : implémentation légère fonctionnelle (par exemple, repository en mémoire).
- **Spy** : enregistre les appels pour assertions ultérieures.

3. **Concept d’exemple PHP**

Tester `OrderService` en mockant `PaymentGatewayInterface` et `OrderRepositoryInterface`, puis vérifier :
- le service retourne le résultat attendu
- le gateway est appelé une fois avec le bon montant
- `repository save` est appelé avec l’état d’entité attendu

4. **Où le mocking est approprié**

- Tests unitaires de services domaine/applicatifs.
- Tests de chemins d’erreur pour dépendances externes.
- Vérification de contrat aux frontières de modules.

5. **Où le mocking n’est pas suffisant**

- Comportement d’intégration avec DB réelle/protocoles réseau.
- Problèmes de câblage/configuration framework.
- Caractéristiques de performance et sémantique transactionnelle.

6. **Bonnes pratiques**

- Mocker uniquement les frontières externes, pas la logique interne pure.
- Garder les attentes centrées sur le comportement observable.
- Préférer des interfaces pour des dépendances mockables.
- Combiner tests unitaires + tests d’intégration (le mocking seul n’est pas une stratégie complète).

Le mocking est essentiel pour des tests unitaires PHP rapides et isolés, mais il doit être équilibré avec des tests d’intégration pour une confiance système réelle.

</details>

<details>
<summary>67. Qu’est-ce que la couverture de code ?</summary>

#### PHP

La couverture de code est une métrique qui montre quelles parties du code source ont été exécutées par les tests automatisés.

1. **Ce que la couverture mesure**

- **Couverture de lignes** : lignes exécutées.
- **Couverture de branches/conditions** : branches de décision exécutées.
- **Couverture de fonctions/méthodes** : unités appelables exécutées.

2. **Pourquoi c’est utile**

- Met en évidence les zones non testées.
- Aide à prioriser où des tests manquent.
- Soutient l’évaluation du risque de régression pendant le refactoring.

3. **Ce que la couverture ne garantit PAS**

- Une couverture élevée ne signifie pas automatiquement une haute qualité des tests.
- Les tests peuvent exécuter du code sans vérifier le comportement correct.
- Des cas limites critiques peuvent encore être manqués malgré de bons pourcentages.

4. **Outillage PHP**

- PHPUnit/Pest peuvent générer des rapports de couverture.
- Repose généralement sur les drivers Xdebug ou PCOV.
- Les rapports peuvent être produits en texte, HTML ou formats CI.

5. **Usage pratique en équipe**

- Suivre les tendances dans le temps plutôt que viser un seul chiffre absolu.
- Définir des seuils minimums raisonnables pour les modules critiques.
- Utiliser les deltas de couverture dans les checks de PR pour éviter les régressions de tests.

6. **Bonnes pratiques**

- Se concentrer d’abord sur la logique métier critique et les chemins risqués.
- Combiner la couverture avec mutation testing/analyse statique quand possible.
- Revoir la qualité des assertions, pas seulement les lignes exécutées.
- Éviter que des tests flaky ou de faible valeur biaisent la couverture.

La couverture de code est un signal utile de complétude des tests, mais elle doit être interprétée avec la qualité des tests et le contexte de risque, pas comme objectif autonome.

</details>

<details>
<summary>68. Qu’est-ce que l’analyse statique (PHPStan, Psalm) ?</summary>

#### PHP

L’analyse statique vérifie le code PHP sans l’exécuter afin de détecter tôt les problèmes de typage, bugs potentiels, code mort et violations d’architecture.

1. **Ce que l’analyse statique détecte**

- Incompatibilités de types et types impossibles.
- Problèmes de nullabilité et accès à variable/propriété/méthode non définis.
- Types de retour incorrects et casts non sûrs.
- Code inatteignable/mort et certains patterns de mauvaise utilisation d’API.

2. **Outils principaux**

- **PHPStan** : largement adopté, niveaux de sévérité, forte intégration écosystème.
- **Psalm** : système de types avancé, inférence puissante, options d’analyse taint.

3. **Pourquoi c’est précieux**

- Détecte les défauts avant l’exécution et avant que les tests ne les couvrent.
- Améliore la sécurité de refactoring dans les grandes codebases.
- Encourage un typage plus fort et des contrats plus clairs.
- Réduit les incidents en production causés par des erreurs de type/flux basiques.

4. **Comment les équipes l’utilisent**

- Exécution en CI sur chaque PR.
- Démarrer avec une sévérité modérée puis augmenter progressivement.
- Maintenir une baseline pour les problèmes legacy tout en empêchant les nouveaux.

5. **Bonnes pratiques**

- Ajouter de manière cohérente des type hints/types de retour.
- Utiliser des annotations génériques quand nécessaire (collections, repositories).
- Corriger les problèmes de typage à la racine plutôt que masquer les warnings.
- Garder la config d’analyse versionnée et revue comme du code.

6. **Analyse statique vs tests**

- L’analyse statique ne remplace pas les tests.
- Elle complète les tests unitaires/d’intégration en prouvant la correction structurelle/de type sur des chemins que les tests peuvent manquer.

L’analyse statique avec PHPStan/Psalm est une barrière qualité à fort levier pour les projets PHP modernes, surtout pendant le refactoring continu.

</details>

<details>
<summary>69. Qu’est-ce que Rector et comment est-il utilisé pour le refactoring ?</summary>

#### PHP

Rector est un outil de refactoring automatisé pour PHP qui transforme le code source avec des règles prédéfinies et personnalisées, afin d’aider à mettre à niveau et moderniser les codebases de manière sûre à grande échelle.

1. **Ce que fait Rector**

- Applique des transformations de code basées sur l’AST.
- Met à niveau la syntaxe/fonctionnalités entre versions PHP.
- Refactorise les patterns d’usage framework/librairie.
- Automatise les changements mécaniques répétitifs.

2. **Cas d’usage typiques**

- Mettre à niveau depuis des versions PHP anciennes vers des standards récents.
- Migrer des API dépréciées vers des alternatives actuelles.
- Appliquer des constructions modernes du langage (propriétés typées, promotion de constructeur, etc.).
- Nettoyage à grande échelle d’une codebase avant adoption d’une analyse statique stricte.

3. **Comment il est utilisé en pratique**

1. Configurer `rector.php` avec des jeux de règles.
2. Exécuter Rector sur des chemins sélectionnés.
3. Revoir le diff généré.
4. Exécuter tests/analyse statique.
5. Committer des lots incrémentaux et sûrs.

4. **Pourquoi les équipes utilisent Rector**

- Accélère fortement le travail de modernisation.
- Réduit les erreurs humaines dans les refactors répétitifs.
- Garde un refactoring cohérent entre modules.

5. **Bonnes pratiques**

- Exécuter Rector sur des périmètres ciblés, pas sur toute une codebase legacy d’un coup.
- Garder des changements petits et facilement revus.
- Toujours valider avec tests + PHPStan/Psalm après transformation.
- Épingler la version de Rector dans l’outillage pour la reproductibilité.
- Combiner refactoring automatisé et revue architecturale manuelle.

6. **Limitation importante**

- Rector gère bien les transformations mécaniques, mais ne remplace pas le jugement architectural ni les décisions de redesign spécifiques au domaine.

Rector est le plus efficace comme partie d’un pipeline de refactoring avec analyse statique et tests, et non comme outil autonome de « migration en un clic ».

</details>

<details>
<summary>70. Qu’est-ce que l’application des standards de code (PHP-CS-Fixer) ?</summary>

#### PHP

L’application des standards de code consiste à vérifier et corriger automatiquement les règles de style afin que la codebase reste cohérente, lisible et facile à reviewer.

1. **Pourquoi les standards de code comptent**

- Améliorent la lisibilité entre équipes.
- Réduisent le bruit de style dans les pull requests.
- Permettent aux code reviews de se concentrer sur la logique, pas le formatage.
- Gardent les codebases long-lived cohérentes.

2. **Ce que fait PHP-CS-Fixer**

- Analyse les fichiers PHP selon des règles de style configurées.
- Réécrit automatiquement les problèmes de formatage/style.
- Supporte des jeux de règles standard (par exemple, PSR-12) plus des règles personnalisées.

3. **Workflow typique**

- Configurer les règles dans `.php-cs-fixer.php`.
- Exécuter le checker en CI pour éviter la dérive.
- Exécuter le fixer en local/pre-commit pour auto-formater les fichiers modifiés.

4. **Catégories de règles courantes**

- Ordre des imports et suppression des imports inutilisés.
- Style des espaces/indentation/accolades.
- Normalisation de la syntaxe tableaux/fonctions.
- Règles de typage strict et préférence pour syntaxe moderne.

5. **Bonnes pratiques**

- S’accorder tôt sur un standard unique à l’échelle du projet.
- Auto-corriger dans le workflow développeur (pre-commit/hooks/intégration éditeur).
- Garder la CI comme barrière d’application (`--dry-run`).
- Appliquer les gros reformatages séparément des changements fonctionnels pour garder des diffs clairs.

6. **Outils liés**

- PHP-CS-Fixer (auto-correction formatage/style).
- PHP_CodeSniffer (vérification de règles et analyse de standards de code).
- Combiner les outils de style avec PHPStan/Psalm pour la qualité au-delà du formatage.

L’application de standards avec des outils comme PHP-CS-Fixer est un moyen peu coûteux d’améliorer la maintenabilité et la vélocité d’équipe dans les projets PHP.

</details>

<details>
<summary>71. Qu’est-ce qu’un pipeline CI/CD pour les applications PHP ?</summary>

#### PHP

Un pipeline CI/CD est un workflow automatisé qui build, teste, vérifie et déploie les applications PHP de manière cohérente, du commit jusqu’à la production.

1. **Objectifs CI (Continuous Integration)**

- Valider rapidement chaque changement.
- Détecter les bugs tôt via des checks automatisés.
- Garder la branche principale toujours livrable.

2. **Étapes CI typiques pour PHP**

1. Installer les dépendances (`composer install`).
2. Checks statiques (PHPStan/Psalm, standards de code).
3. Tests unitaires/d’intégration (PHPUnit/Pest).
4. Build/package des artifacts (image Docker ou bundle de déploiement).

3. **Objectifs CD (Continuous Delivery/Deployment)**

- Livrer des artifacts validés de façon sûre vers les environnements.
- Automatiser les étapes de rollout et minimiser les erreurs manuelles.
- Supporter un rollback rapide en cas d’incident.

4. **Étapes CD typiques**

- Déployer en staging.
- Exécuter smoke checks/health checks.
- Promouvoir le même artifact en production.
- Monitorer métriques et logs post-déploiement.

5. **Bonnes pratiques spécifiques PHP**

- Utiliser des installations reproductibles basées sur lockfile.
- Builder des artifacts immuables une seule fois et les réutiliser entre environnements.
- Exécuter les migrations DB avec une stratégie contrôlée.
- Garder secrets/config hors artifact.
- Utiliser des patterns de rollout zero-downtime (blue-green/canary/rolling).

6. **Gates qualité**

- Statut de passage des tests requis.
- Seuil d’analyse statique.
- Checks de sécurité (audit de dépendances/SAST).
- Smoke checks de performance optionnels pour endpoints critiques.

7. **Résultat**

Un pipeline CI/CD solide améliore la fréquence de release, la fiabilité et la confiance de l’équipe tout en réduisant le risque de production dans la livraison PHP.

</details>

<details>
<summary>72. Comment déployer des applications PHP ?</summary>

#### PHP

Déployer des applications PHP signifie livrer un artifact testé en production avec une configuration runtime prévisible, un downtime minimal et une sécurité de rollback.

1. **Cibles de déploiement courantes**

- VM/bare metal traditionnels avec Nginx/Apache + PHP-FPM.
- Plateformes de conteneurs (Docker, Kubernetes, ECS).
- Services plateforme (variantes PaaS/serverless).

2. **Flux de déploiement recommandé**

1. Builder un artifact immuable (image/package) en CI.
2. Exécuter tests/checks statiques/scans de sécurité.
3. Déployer l’artifact en staging.
4. Exécuter smoke checks et health checks.
5. Promouvoir le même artifact en production.

3. **Essentiels runtime**

- Config et secrets basés sur l’environnement (pas hardcodés).
- Extensions PHP correctes et réglages OPcache.
- Connectivité DB/cache/queue vérifiée au démarrage.
- Logging structuré et monitoring activés.

4. **Stratégie de migration base de données**

- Appliquer des migrations backward-compatible avant de basculer le trafic.
- Utiliser l’approche expand-and-contract pour les changements de schéma risqués.
- Garder les scripts de migration versionnés et répétables.

5. **Techniques zero/low-downtime**

- Déploiements blue-green, rolling ou canary.
- Reload gracieux des workers (PHP-FPM/process manager).
- Bascule de trafic basée sur health checks via load balancer.

6. **Stratégie de rollback**

- Rollback rapide vers artifact/version précédente.
- Rollback DB contrôlé ou plan de forward-fix.
- Fenêtre de monitoring post-déploiement avec alerting.

7. **Bonnes pratiques**

- Ne jamais déployer directement depuis la machine locale.
- Garder le process de déploiement automatisé et auditable.
- Utiliser l’infrastructure as code quand possible.
- Séparer clairement les préoccupations build-time et runtime.

Un bon déploiement PHP est un système d’ingénierie : artifacts reproductibles, mécanique de rollout sûre, observabilité et rollback fiable.

</details>

<details>
<summary>73. Qu’est-ce que le déploiement blue-green ?</summary>

#### PHP

Le déploiement blue-green est une stratégie de release où deux environnements de production identiques sont maintenus : un actif (qui sert le trafic) et un inactif (candidat pour la prochaine release).

1. **Comment cela fonctionne**

- **Blue** : environnement live actuel.
- **Green** : nouvelle version déployée et validée en parallèle.
- Après validation, le trafic est basculé de Blue vers Green.
- L’ancien environnement reste disponible pour un rollback rapide.

2. **Pourquoi les équipes l’utilisent**

- Minimise le downtime de déploiement.
- Réduit le risque de release avec rollback quasi instantané.
- Permet une vérification réaliste avant bascule sur une stack proche production.

3. **Flux de rollout typique**

1. Déployer la nouvelle release PHP dans l’environnement inactif.
2. Exécuter health checks/smoke tests/stratégie de migration.
3. Basculer le load balancer/router vers le nouvel environnement.
4. Surveiller taux d’erreur/latence.
5. Garder temporairement l’environnement précédent pour rollback.

4. **Points clés pour les apps PHP**

- La stratégie de session doit supporter le switch d’environnement (Redis/session store partagé).
- Les assets statiques/versioning doivent être compatibles entre les deux environnements.
- Les changements DB doivent rester backward-compatible pendant la fenêtre de transition.
- Les queue workers et cron jobs doivent éviter les effets secondaires dupliqués.

5. **Avantages**

- Chemin de rollback rapide.
- Déploiements plus sûrs pour systèmes à fort trafic.
- Séparation claire entre release « actuelle » et « candidate ».

6. **Compromis**

- Coût d’infrastructure plus élevé (deux environnements).
- Complexité opérationnelle accrue autour de la compatibilité données/schéma.

Le blue-green est un pattern de déploiement solide pour les systèmes PHP de production où l’uptime et la vitesse de rollback sont critiques.

</details>

<details>
<summary>74. Qu’est-ce qu’une stratégie de rollback ?</summary>

#### PHP

Une stratégie de rollback est un plan prédéfini pour restaurer rapidement une version stable précédente lorsqu’un déploiement provoque des incidents (erreurs, régressions, chutes de performance, problèmes de données).

1. **Pourquoi une stratégie de rollback est critique**

- Réduit la durée des incidents et l’impact client.
- Évite les actions d’urgence ad-hoc pendant les pannes.
- Augmente la confiance dans les releases fréquentes.

2. **Ce qui doit être prêt au rollback**

- Version de l’artifact/image applicatif.
- Version infrastructure/configuration.
- État des feature flags/toggles.
- Plan de compatibilité des migrations de base de données.

3. **Approches courantes de rollback**

- **Artifact rollback** : redéployer le build précédent connu comme sain.
- **Traffic rollback** : rebascule vers l’environnement précédent (revert blue-green/canary).
- **Feature rollback** : désactiver un feature flag problématique sans redéploiement complet.

4. **Réalité du rollback base de données**

- Le rollback DB est souvent la partie la plus difficile.
- Préférer des migrations backward-compatible :
  expand d’abord, contract ensuite.
- Utiliser un forward-fix quand un vrai rollback de schéma est risqué.

5. **Checklist opérationnelle**

- Définir des seuils déclencheurs de rollback (taux d’erreur, latence, checks échoués).
- Garder la release précédente immédiatement déployable.
- Automatiser les étapes de rollback dans le pipeline/runbooks.
- Vérifier la santé après rollback et continuer le monitoring.

6. **Bonnes pratiques**

- Répéter le rollback en staging régulièrement.
- Garder les releases petites pour réduire le blast radius.
- Coupler rollout et rollback avec observabilité (logs/métriques/traces).
- Documenter la responsabilité et le flux de décision incident.

Une stratégie de rollback solide est un mécanisme central de fiabilité pour la livraison PHP en production, surtout dans les environnements de déploiement à haute fréquence.

</details>

<details>
<summary>75. Qu’est-ce que le PHP serverless (Laravel Vapor, Bref) ?</summary>

#### PHP

Le PHP serverless est un modèle d’exécution où votre code PHP tourne sur des fonctions/plateformes cloud managées, sans gérer directement des serveurs traditionnels.

1. **Idée centrale**

- Vous déployez du code/des fonctions, pas des flottes de VM.
- Le fournisseur cloud gère le provisioning, la scalabilité et une grande partie des opérations.
- La facturation est généralement basée sur le temps d’exécution et le nombre de requêtes.

2. **Options serverless PHP courantes**

- **Laravel Vapor** :
  plateforme orientée Laravel sur AWS (Lambda, intégrations managées).
- **Bref** :
  runtime/outillage open source pour exécuter PHP sur AWS Lambda (support agnostique framework).

3. **Pourquoi les équipes utilisent le PHP serverless**

- Auto-scalabilité horizontale rapide.
- Charge ops réduite (moins de patching/provisioning).
- Efficacité des coûts pour trafic irrégulier ou faible charge de base.
- Time-to-production plus rapide pour workloads API/backoffice.

4. **Implications d’architecture**

- Exécution de fonctions stateless.
- État externalisé (DB, Redis, object storage, queues).
- Triggers orientés événements (HTTP, queues, cron, événements objets).
- Les cold starts et limites d’exécution doivent être pris en compte.

5. **Meilleurs cas d’usage**

- APIs à trafic variable.
- Jobs/événements en arrière-plan.
- Tâches planifiées et automatisation légère.
- MVPs et équipes optimisant la vitesse de livraison.

6. **Compromis**

- Contraintes de plateforme/runtime et timeouts.
- Risque de vendor lock-in.
- Impact de latence des cold starts sur certains endpoints.
- Debugging/observabilité peuvent nécessiter une configuration supplémentaire.

7. **Bonnes pratiques**

- Garder les fonctions petites et ciblées.
- Optimiser le temps de bootstrap et l’empreinte des dépendances.
- Utiliser des queues async pour les traitements longs.
- Configurer un logging/métriques/tracing robustes dès le premier jour.
- Concevoir des handlers idempotents et des workflows sûrs en retry.

Le PHP serverless avec Vapor/Bref est une option solide pour des architectures scalables à faible charge ops quand les caractéristiques de charge correspondent au modèle serverless.

</details>

<details>
<summary>76. Microservices vs monolithe en PHP : que choisir ?</summary>

#### PHP

Monolithe et microservices sont des styles d’architecture pour structurer les systèmes. En PHP, les deux peuvent bien fonctionner si le choix est fait selon la taille de l’équipe, la complexité du domaine et la maturité opérationnelle.

1. **Monolithe (application unique déployable)**

- Une codebase/unité déployable contenant plusieurs capacités métier.
- Runtime partagé et généralement base de données partagée.

**Avantages**
- Développement, tests et déploiement plus simples.
- Surcharge opérationnelle plus faible.
- Debug local et transactions inter-modules plus faciles.

**Inconvénients**
- Peut devenir difficile à faire évoluer si les frontières sont faibles.
- Les gros déploiements peuvent augmenter le risque de release.
- La scalabilité est souvent grossière (application entière).

2. **Microservices (plusieurs services déployables indépendamment)**

- Système découpé en petits services alignés sur les domaines métier.
- Chaque service possède sa logique et souvent son datastore.

**Avantages**
- Scalabilité/déploiement indépendants par service.
- Frontières de responsabilité claires.
- Flexibilité technologique/runtime par service.

**Inconvénients**
- Complexité plus élevée (réseau, observabilité, auth, retries, cohérence des données).
- Développement local et debug inter-services plus difficiles.
- Maturité DevOps/plateforme significative requise.

3. **Réalité pratique spécifique PHP**

- Beaucoup d’équipes réussissent d’abord avec un monolithe modulaire.
- Les microservices deviennent pertinents quand des bounded contexts clairs et la montée en équipe justifient le coût opérationnel.

4. **Guide de décision**

- Choisir **monolithe/monolithe modulaire** quand :
  produit en phase initiale, équipe petite/moyenne, vélocité prioritaire.
- Choisir **microservices** quand :
  domaines clairement séparables, besoins de scalabilité très différents, et capacités plateforme matures.

5. **Erreur fréquente**

- Démarrer trop tôt avec les microservices crée une complexité accidentelle sans bénéfice métier.

Dans les écosystèmes PHP, la voie pragmatique est souvent : monolithe bien structuré d’abord, puis extraction sélective vers des services lorsque des contraintes objectives l’exigent.

</details>

<details>
<summary>77. Qu’est-ce que l’architecture monolithe modulaire ?</summary>

#### PHP

Un monolithe modulaire est une application unique déployable structurée en modules internes clairement séparés avec des frontières et des contrats explicites.

1. **Idée centrale**

- Une seule application/runtime/unité de déploiement.
- Plusieurs modules métier (bounded contexts) à l’intérieur.
- Frontières internes fortes pour réduire le couplage.

2. **En quoi il diffère**

- Vs monolithe classique :
  le monolithe modulaire impose des frontières de module strictes et des règles de dépendance.
- Vs microservices :
  il garde une unité déployable unique et évite la complexité des systèmes distribués.

3. **Structure de module PHP typique**

- `Modules/Orders/...`
- `Modules/Billing/...`
- `Modules/Users/...`

Chaque module contient ses propres :
- logique de domaine
- services applicatifs/use-case
- adaptateurs d’infrastructure
- handlers HTTP/API (ou interfaces mappées)

4. **Pourquoi les équipes le choisissent**

- Développement plus rapide que les microservices.
- Debug local et transactions plus faciles.
- Surcharge opérationnelle plus faible.
- Bon chemin pour l’organisation domain-driven et l’extraction future de services.

5. **Pratiques d’application des frontières**

- Communiquer entre modules via interfaces/événements, pas via des internals directs.
- Éviter les utilitaires partagés mutables « god » entre modules.
- Utiliser analyse statique/tests pour imposer la direction des dépendances.
- Garder la propriété de base de données claire (même si physiquement partagée).

6. **Quand c’est un bon choix**

- Le produit et l’équipe grandissent, mais la complexité microservices est prématurée.
- Besoin d’une séparation forte du domaine avec un modèle de déploiement simple.

7. **Chemin d’évolution**

- Commencer par un monolithe modulaire.
- Extraire des modules sélectionnés en services seulement quand la pression de scalabilité/équipe/propriété est réelle et mesurable.

Le monolithe modulaire est souvent l’architecture la plus pragmatique pour les équipes PHP qui veulent des frontières propres aujourd’hui sans surcharge distribuée trop tôt.

</details>

<details>
<summary>78. Quelles sont les vulnérabilités PHP courantes dans les projets réels ?</summary>

#### PHP

La plupart des incidents de sécurité PHP réels viennent d’une gestion d’entrée non sûre, de contrôles auth/session faibles et de problèmes de dépendances/configuration, plutôt que du langage lui-même.

1. **Vulnérabilités d’injection**

- Injection SQL due à une construction de requêtes non sûre.
- Command Injection lors du passage d’entrées non fiables aux appels shell/system.
- Injections de type Header/LDAP/NoSQL dans les couches d’intégration.

2. **Vulnérabilités cross-site**

- XSS (stored/reflected/DOM) à cause d’un échappement contextuel de sortie manquant.
- CSRF dans les flux auth par cookie sans token ni protections SameSite.

3. **Failles d’authentification et d’autorisation**

- Gestion de mot de passe faible ou MFA absent pour les rôles critiques.
- Contrôle d’accès cassé (IDOR/BOLA) : l’utilisateur accède aux ressources d’autres utilisateurs en changeant les IDs.
- Vérifications d’autorisation server-side manquantes sur endpoints sensibles.

4. **Problèmes de session et de token**

- Flags cookie non sécurisés (`Secure`, `HttpOnly`, `SameSite` absents).
- Session fixation/hijacking dû à une mauvaise rotation d’ID.
- Tokens API exposés ou longue durée sans stratégie de révocation.

5. **Risques de gestion de fichiers**

- Uploads de fichiers non sûrs (pas de validation type/contenu, uploads exécutables).
- Path traversal (`../`) dû à des chemins de fichiers non vérifiés.
- Désérialisation non sûre ou parsing non sûr de fichiers non fiables.

6. **Risques de configuration et de dépendances**

- Mode debug activé en production.
- Secrets exposés dans repo/logs/dumps d’environnement.
- Dépendances obsolètes avec CVE connus.
- En-têtes CORS/CSP/sécurité mal configurés.

7. **Comment mitiger de façon systématique**

- Validation stricte des entrées + encodage de sortie selon le contexte.
- Prepared statements et couches de requête sûres.
- Politiques d’authz centralisées et checks deny-by-default.
- Gestion sécurisée du cycle de vie session/token.
- Scan/patch de dépendances et config production durcie.
- Tests de sécurité réguliers (SAST/DAST), logging et playbooks d’incident.

La sécurité des projets PHP est avant tout une discipline de conception sécurisée, de safe defaults et de vérification continue à travers le code, le runtime et les opérations.

</details>

<details>
<summary>79. Comment détecter les fuites mémoire en PHP ?</summary>

#### PHP

En PHP, les « fuites mémoire » ne sont souvent pas des fuites permanentes classiques au niveau script, mais une croissance mémoire causée par des processus long-running, des références retenues, de gros buffers en mémoire, des fuites au niveau extensions ou la fragmentation de l’allocateur.

1. **Identifier d’abord où apparaît le comportement de fuite**

- Modèle FPM/requête : la mémoire doit revenir après la fin de la requête ; une croissance indique généralement des problèmes au niveau worker ou des requêtes surdimensionnées.
- Workers long-running (consommateurs de queue, daemons, Swoole/RoadRunner) : état retenu entre jobs est une source fréquente.
- Scripts batch CLI : tableaux/caches non bornés peuvent simuler des fuites.

2. **Instrumenter la mémoire dans le code**

- Utiliser `memory_get_usage(true)` et `memory_get_peak_usage(true)` autour des grandes étapes du pipeline.
- Logger la mémoire par itération/job pour détecter une tendance de croissance monotone.
- Ajouter des compteurs d’items traités pour corréler la mémoire à la taille de charge.

3. **Utiliser des diagnostics runtime/niveau process**

- Surveiller le RSS des workers dans le temps via `ps`, `top`, métriques conteneur ou APM.
- Comparer usage niveau PHP vs mémoire niveau OS pour repérer fragmentation/comportement allocateur.
- En FPM, monitorer la mémoire des workers du pool et les patterns de redémarrage.

4. **Utiliser des profileurs et outils spécialisés**

- Xdebug/Blackfire/Tideways pour hotspots d’allocation et chemins d’appel lourds.
- Valgrind/ASan pour fuites au niveau extension C ou natif (builds debug, plus lents mais précis).
- Toolbars/profileurs framework pour snapshots mémoire par requête.

5. **Causes racines courantes à vérifier**

- Tableaux statiques/globaux qui accumulent des données entre jobs.
- Event listeners/closures capturant involontairement de gros objets.
- Identity maps ORM ou résultats de requête retenus trop longtemps.
- Copies de grosses chaînes/payloads JSON pendant les transformations.
- Références circulaires + GC retardé dans de longues boucles.

6. **Patterns de mitigation après détection**

- Traiter les données en chunks/streams au lieu de collections complètes en mémoire.
- Faire `unset()` explicite des grosses variables et appeler occasionnellement `gc_collect_cycles()` dans les longues boucles.
- Recréer le process worker après N jobs/temps (`--max-jobs`, redémarrages supervisor).
- Configurer des limites mémoire raisonnables et un comportement fail-fast.
- Garder dépendances/extensions à jour quand des fuites natives sont corrigées en amont.

L’approche pratique est : mesurer la tendance, isoler le hotspot, confirmer avec profiling, et imposer des frontières de cycle de vie pour les processus long-running.

</details>

<details>
<summary>80. Comment optimiser l’utilisation de la mémoire ?</summary>

#### PHP

L’optimisation mémoire en PHP consiste surtout à contrôler la durée de vie des données, réduire les copies inutiles et utiliser un traitement en streaming/chunks au lieu de tout charger d’un coup.

1. **Traiter les données de façon incrémentale**

- Préférer les générateurs (`yield`) pour les grands jeux de données au lieu de construire d’énormes tableaux.
- Lire les fichiers/streams ligne par ligne ou en chunks.
- Paginer les lectures DB (`LIMIT/OFFSET` ou APIs cursor/chunk) pour les jobs batch.

2. **Éviter les copies inutiles**

- Minimiser la concaténation de chaînes dans les boucles serrées ; utiliser des stratégies de buffering.
- Éviter les `array_merge` répétés sur de grands tableaux dans les boucles.
- Faire attention aux transformations qui dupliquent de grosses structures.

3. **Libérer la mémoire tôt dans les scripts long-running**

- Faire `unset()` des grosses variables temporaires après usage.
- Découper le travail en itérations bornées ; nettoyer l’état par itération.
- Pour les références cycliques dans les longues boucles, appeler occasionnellement `gc_collect_cycles()`.

4. **Choisir des patterns d’accès aux données efficaces**

- Sélectionner uniquement les colonnes nécessaires en SQL, pas `SELECT *`.
- Hydrater des DTO/tableaux légers quand les modèles ORM complets ne sont pas nécessaires.
- Utiliser le lazy-loading avec prudence ; éviter les requêtes N+1 et les graphes d’objets excessifs.

5. **Utiliser limites runtime et contrôles de cycle de vie des workers**

- Définir un `memory_limit` raisonnable pour fail-fast plutôt que dégrader l’hôte.
- Pour les queue workers, redémarrer après N jobs/temps pour éviter la dérive mémoire long terme.
- Surveiller la tendance mémoire avec `memory_get_usage(true)` et les métriques OS.

6. **Mettre en cache intelligemment, pas aveuglément**

- Mettre en cache uniquement les calculs coûteux à forte valeur.
- Stocker des payloads de cache compacts ; compresser si utile.
- Utiliser TTLs/invalidation pour éviter une croissance non bornée du cache.

7. **Profiler avant et après**

- Utiliser Xdebug/Blackfire/Tideways/APM pour trouver les vrais hotspots.
- Optimiser d’abord les goulots mesurés ; éviter les micro-optimisations prématurées.

En pratique, les plus grands gains viennent du streaming/chunking, du contrôle de la durée de vie des objets et de la prévention des grosses allocations transitoires.

</details>

<details>
<summary>81. Comment inverser une chaîne sans fonctions intégrées ?</summary>

#### PHP

L’idée de base est d’itérer de la fin de la chaîne vers le début et de construire une nouvelle chaîne caractère par caractère.

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

La complexité temporelle est `O(n)`, et l’espace supplémentaire est `O(n)` pour la sortie inversée.

Notes d’entretien :

- Cette version basée sur les octets fonctionne pour l’ASCII.
- Pour les chaînes UTF-8/multioctets, l’indexation par octet peut casser les caractères, donc une approche multioctet sûre est nécessaire.

</details>

<details>
<summary>82. Comment supprimer les doublons d’un tableau ?</summary>

#### PHP

L’approche standard consiste à suivre les valeurs déjà vues dans une table de hachage et à ne garder que la première occurrence.

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

Pourquoi cette version est adaptée à l’entretien :

- Conserve l’ordre d’insertion.
- Fonctionne en temps linéaire en moyenne : `O(n)`.
- Gère les scalaires, `null` et les valeurs complexes via `serialize`.

Si la question autorise les fonctions intégrées, `array_unique()` est plus court, mais la logique manuelle hash-set montre mieux les fondamentaux.

</details>

<details>
<summary>83. Comment trouver le deuxième plus grand nombre ?</summary>

#### PHP

Une solution robuste en un seul passage consiste à suivre la plus grande et la deuxième plus grande valeurs distinctes pendant le parcours du tableau.

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

Comportement :

- Retourne `null` s’il n’existe pas de deuxième maximum distinct (ex. `[5]`, `[7, 7]`).
- Complexité temporelle : `O(n)`.
- Complexité espace : `O(1)`.

</details>

<details>
<summary>84. Comment vérifier si une chaîne est un palindrome ?</summary>

#### PHP

Un palindrome se lit de la même manière à l’endroit et à l’envers. Efficacement, on compare les caractères depuis les deux extrémités en avançant vers le centre.

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

Complexité :

- Temps : `O(n)`
- Espace : `O(1)`

Notes d’entretien :

- Cette version est basée sur les octets et convient pour l’ASCII.
- Pour UTF-8, utiliser une approche multioctet sûre avant d’indexer les caractères.
- Clarifier si les espaces, la ponctuation et la casse doivent être ignorés ; si oui, normaliser l’entrée d’abord.

</details>
