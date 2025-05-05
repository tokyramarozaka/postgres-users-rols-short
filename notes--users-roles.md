# Resumé sur les users et les rôles 

Ce document resume le cours rapide sur les users dans postgresql. 

## Comment créer un nouvel utilisateur ? 

Pour créer un nouvel utilisateur nommé `etudiant1` on doit executer la __commande__ suivante.

```sql
CREATE USER etudiant1 WITH PASSWORD 'password'; 
```

Pour se connecter avec cet utilisateur il faut tout simplement taper la commande suivante 

```sql
\c votre_base etudiant1 
```
Par défaut, le nouvel utilisateur n'a aucune permission.

## Comment donner une permission à un utilisateur 

Avant toute chose, veuillez vous assurez que vous êtes connecté en tant qu'admin (postgres).

Puis executez la commande suivante.

```sql
    GRANT (UPDATE | SELECT ...) ON (table_name | database_name) TO user_name
```

Si vous voulez donner toutes les permissions sur une table, ecrivez plutôt ceci. 

```sql 
    GRANT ALL [PRIVILEGES] ON table_name TO user_name
```

Pour revoke il s'agit tout simplement de retirer des permissions accordées actuellement. 

Si vous voulez obtenir la liste des users il suffit de lancer la commande `\du`