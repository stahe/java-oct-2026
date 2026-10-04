# Apprentissage du langage Java 25

📖 **Lire le tutoriel : [https://stahe.github.io/java-oct-2026/](https://stahe.github.io/java-oct-2026/)**

Ce cours apprend le langage [Java](https://dev.java/) 25 **par l'exemple** : plus de deux cents programmes (320 fichiers Java), commentés ligne par ligne, dont les résultats d'exécution sont reproduits. Il part des bases du langage et va jusqu'à l'accès aux bases de données avec JDBC et Hibernate, la programmation réseau et les services web avec Spring Boot.

C'est le portage en Java du cours [Apprentissage du langage C# 14 avec .NET 10](https://stahe.github.io/csharp-oct-2026/) (octobre 2026), lui-même réécriture d'un cours C# de 2008 : même plan, mêmes exemples, même fil rouge, mais écrits dans le Java d'aujourd'hui. Tous les programmes compilent **sans erreur ni avertissement** avec le JDK 25 (`javac -Xlint:all`) et ont été exécutés ; les résultats reproduits dans le cours sont ceux de ces exécutions.

| Cours C# 14 (2026) | Cours Java 25 (2026) |
|---|---|
| C# 14, .NET 10 (LTS) | Java 25 (LTS), JDK 25 |
| applications fichier unique (`dotnet run prog.cs`) | fichiers source compacts (`java Prog.java`) |
| projets `.csproj`, solutions `.slnx`, NuGet | projets Maven (`pom.xml`), Maven Central |
| propriétés, structures, surcharge des opérateurs | accesseurs, records, classes scellées, filtrage par motif |
| LINQ | API Stream |
| délégués et événements | interfaces fonctionnelles, lambdas, écouteurs |
| `Task`, `async` / `await` | `CompletableFuture`, threads virtuels |
| MSTest, Microsoft.Extensions.DependencyInjection | JUnit 6, Spring Framework 7 |
| System.Text.Json | Jackson 3 |
| ADO.NET, MySqlConnector | JDBC, MySQL Connector/J, HikariCP |
| Entity Framework Core | **Hibernate 7** (Jakarta Persistence 3.2) |
| `HttpClient`, `TcpClient` / `TcpListener` | `java.net.http.HttpClient`, `Socket` / `ServerSocket` |
| ASP.NET Core Minimal API | Spring Boot 4 |

## Le plan du cours

| Chapitre | Contenu |
|---|---|
| Installation | JDK 25, IntelliJ IDEA / VS Code, les commandes `java` et `javac`, fichiers source compacts, Maven, projets multi-modules |
| Les bases du langage | types, `var`, blocs de texte, conversions, tableaux, opérateurs, expressions `switch` et filtrage par motif, exceptions contrôlées et non contrôlées, `try` avec ressources, énumérations, passage de paramètres |
| Classes, records, interfaces | classes, héritage, polymorphisme, classes scellées, `equals` / `hashCode` / `compareTo`, interfaces, classes abstraites, génériques, paquetages et modules, records, filtrage par motif sur les objets, `Optional` |
| Classes Java d'usage courant | chaînes, tableaux, collections (dont les collections séquencées), **API Stream** et `Gatherers`, fichiers texte et binaires (`java.nio.file`), JSON avec Jackson 3, expressions régulières |
| Architectures en couches | couches [dao] / [metier] / [ui], projet Maven multi-modules, tests unitaires **JUnit 6**, **injection de dépendances** avec Spring |
| Interfaces fonctionnelles, lambdas et événements | `java.util.function`, lambdas, références de méthodes, fermetures, composition, écouteurs d'événements, `PropertyChangeSupport` |
| Les threads d'exécution | `Thread`, **threads virtuels**, `synchronized`, `ReentrantLock`, `Condition`, atomiques, `Semaphore`, `CountDownLatch`, collections concurrentes, `ExecutorService`, fork/join, `ThreadLocal`, `ScopedValue` |
| La programmation asynchrone | `CompletableFuture` et threads virtuels, composition, exceptions, annulation et délais, progression, E/S asynchrones, `Flow`, concurrence structurée (aperçu) |
| L'accès aux bases de données avec JDBC | MySQL, MySQL Connector/J, `DataSource` et HikariCP, requêtes paramétrées et injection SQL, transactions, lots, `CachedRowSet` |
| **Hibernate** | entités, `SessionFactory` / `Session`, CRUD, contexte de persistance, HQL et API Criteria, relations et chargement paresseux, migrations, concurrence optimiste, SQL natif, `StatelessSession`, Spring ORM et `@Transactional` |
| Programmation Internet | TCP/IP, IPv6, `InetAddress`, clients et serveurs TCP (un thread virtuel par client), HTTP, `HttpClient`, SMTP |
| Services web | REST / JSON avec **Spring Boot 4**, clients console Java, client web JavaScript, client Node.js |

## Le fil rouge : un calcul d'impôt en 9 versions

Tout le cours construit, version après version, une application de **calcul de l'impôt sur le revenu** :

- **version 1** : un programme unique ; **version 2** : des classes et des interfaces ; **version 3** : les données lues dans un fichier texte ou JSON ;
- **versions 4 et 5** : une architecture en couches, en modules Maven, testée avec JUnit et intégrée par injection de dépendances avec Spring ;
- **versions 6 et 7** : les données dans une base MySQL, lues avec JDBC puis avec Hibernate ;
- **version 8** : un serveur TCP de calcul de l'impôt et son client ;
- **version 9** : un service web REST Spring Boot, son client console et son client web.

## Technologies

Java 25 · JDK 25 · Maven 3.9 · IntelliJ IDEA · VS Code · JUnit 6 · Spring Framework 7 · Jackson 3 · MySQL 8 · MySQL Connector/J 9 · HikariCP · Hibernate ORM 7.4 · Jakarta Persistence 3.2 · Spring Boot 4.1 · Laragon

## Prérequis

- Avoir déjà programmé dans un langage quelconque.
- Un [JDK 25](https://adoptium.net) (Eclipse Temurin ou autre distribution), [Maven](https://maven.apache.org) et un éditeur ([IntelliJ IDEA](https://www.jetbrains.com/idea/) ou [VS Code](https://code.visualstudio.com) avec l'Extension Pack for Java) ; [Laragon](https://laragon.org) pour MySQL (chapitres sur les bases de données). Les instructions d'installation sont données dans le cours.

## Auteur

Ce cours et ses codes ont été rédigés par **Claude**, l'IA d'[Anthropic](https://www.anthropic.com) (octobre 2026), à la demande de Serge Tahé, à partir de son cours C# 14.

Réviseur : [Serge Tahé](https://stahe.github.io)
