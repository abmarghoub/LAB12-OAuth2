# TP 12 : Intégration OAuth2 (Google ou Keycloak)

## 1. Objectif du TP
Ce TP a pour objectif de mettre en place un système d'authentification via **Google OAuth2** dans une application **Spring Boot**.  
L'utilisateur peut se connecter avec son compte Google, accéder à une page protégée affichant ses informations personnelles (nom, email, photo) et se déconnecter proprement.

---

## 2. Architecture du TP

### 2.1 Stack technologique

| Technologie        | Rôle dans le projet                                 |
|------------------|----------------------------------------------------|
| **Java 21**        | Langage de programmation principal                |
| **Spring Boot 3**  | Framework pour créer l'application Web            |
| **Spring Security**| Gestion de la sécurité et OAuth2                  |
| **Thymeleaf**      | Moteur de templates pour les vues HTML            |
| **Lombok**         | Réduction du code boilerplate (getters, setters…) |
| **Maven**          | Gestion des dépendances et compilation            |

---

### 2.2 Structure du projet

<img width="430" height="878" alt="image" src="https://github.com/user-attachments/assets/ab366bed-166e-4bdd-bf92-229a5fbd61f8" />


- `SecurityConfig.java` → configure la sécurité, les routes protégées, OAuth2 login et logout.  
- `HomeController.java` → gère les pages `/profile` et `/` (accueil).  
- `application.yml` → configuration OAuth2 Google (client-id, client-secret, scopes, issuer-uri).  
- `templates/` → contient les vues Thymeleaf (`profile.html`).  

---

## 3. Résultat attendu
 
1. Accéder à une page protégée ` http://localhost:8080/profile` :
   
2. **Redirection automatique vers Google** pour l’authentification.
   
   <img width="914" height="277" alt="image" src="https://github.com/user-attachments/assets/2fd9fdef-0e70-4d82-a131-25e40de90b43" />


5. Après connexion :

* La page `/profile` affiche les informations de l’utilisateur :

<img width="566" height="483" alt="image" src="https://github.com/user-attachments/assets/5d7e20df-5898-4ec7-8a06-5a4e7ee65ed8" />


* Le bouton **Se déconnecter** fonctionne correctement et redirige vers la page souhaitée.

<img width="750" height="339" alt="image" src="https://github.com/user-attachments/assets/a23e883b-1388-4f24-8581-320f68ca6032" />
<img width="670" height="256" alt="image" src="https://github.com/user-attachments/assets/1f8b910d-3c91-4a86-ae19-cf590a3245c5" />


