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
