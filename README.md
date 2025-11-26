# TD .NET - Débogage et Exploration (BoutiqueDiayma 2025)
**Étudiant :** Zeynabou BA  
**Date :** 20 novembre 2025  
**Repo :** https://github.com/TonUsername/BoutiqueDiayma-TD-MonNom

# Boutique Diayma
## Réponses aux Questions

### 1. Récupération et Exécution
Cloné via `git clone`. Exécuté avec `dotnet run`.
Port : https://localhost:62929. Avertissements fermés.

### 2. Projets de la Solution
- Diayma (Diayma.csproj, avec un seul fichier ".sln")

### 3. Version SDK .NET
Version : .NET 2.0. Vérifié dans tous les .csproj.

### 4. Installation SDK
.NET 2.0 installé via site officiel.

### 5. Dépôt GitHub Personnel
https://github.com/ZeynabouBaSchool/BoutiqueDiayma-TD-ZBa.git

### 6. Exploration et Bugs 
Bug 1 : La langue espagnole du francais
Bug 2 :  Le calcule du totale du panier n’est pas correcte

### 7. Points d'Arrêt
- a) CartSummaryViewComponent.cs L12 : OK  
- b) ProductController.cs L15 : OK  
- c) OrderController L17 : OK
- d) CartController L15 : OK
- e) Startup L20 : OK


### 8. Namespaces/Classes/Méthodes (Accueil Produits)
| Ordre | Namespace                                 | Classe                     | Méthode                              | Commentaire |
|-------|-------------------------------------------|----------------------------|--------------------------------------|-------------|
| 1     | P2FixAnAppDotNetCode                      | Program                    | Main()                               | Point d’entrée |
| 2     | Microsoft.AspNetCore.Hosting              | GenericWebHostBuilder      | Build()                              | Construction du host |
| 3     | P2FixAnAppDotNetCode                      | Startup                    | ConfigureServices(IServiceCollection) | Injection de dépendances (Cart, ProductService, etc.) |
| 4     | P2FixAnAppDotNetCode                      | Startup                    | Configure(IApplicationBuilder, IHostingEnvironment) | Configuration du pipeline HTTP |
| 5     | P2FixAnAppDotNetCode.Startup             | Configure()                | app.UseStaticFiles()                 | F10 → passe à la ligne suivante |
| 6     | P2FixAnAppDotNetCode.Startup             | Configure()                | app.UseRequestLocalization()        | F10 |
| 7     | P2FixAnAppDotNetCode.Startup             | Configure()                | app.UseSession()                    | F10 |
| 8     | P2FixAnAppDotNetCode.Startup             | Configure()                | app.UseMvc(routes => ...)            | F10 → ici le routeur est configuré |
| 9     | Microsoft.AspNetCore.Mvc                  | MvcRouteHandler           | RouteAsync()                         | Le framework trouve la route par défaut |
| 10    | P2FixAnAppDotNetCode.Controllers         | ProductController          | Index()                              | Méthode exécutée pour l’URL /** |
| 11    | P2FixAnAppDotNetCode.Controllers.ProductController | Index()       | return View(products);               | Retourne la liste des produits |
| 12    | Microsoft.AspNetCore.Mvc.ViewFeatures     | ViewResultExecutor         | ExecuteAsync()                       | Rend la vue |
| 13    | Views/Product/Index.cshtml                | -                          | -                                    | Affichage final dans le navigateur |

### 9. Déploiement
`dotnet publish -c Release -r win-x64 --self-contained`. 
Déployé en self-contained pour Windows x64
Exe dans bin/Release.

### 10. Lien Exécutable
https://drive.google.com/drive/u/0/folders/1PoqAH4sbgK0zGDEuisetKW1jkwWvzwO4
