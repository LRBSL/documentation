# Backend Application

## Database Entities

For the development, we used MariaDB/MySql as the database of LRBSL project. However, by using the TypeORM which is an object relation mapping tool, the database-backend development could be able to complete independently from database type. The database entities which are based on TypeORM can be found at "/blockchain/packages/server/src/entities" location.

- **user.entity :** _parent class for main 3 user entities_
- **user.auth.entity :** _contains authentication user information_
- **user.notary.entity :** _contains notary related user information_
- **user.surveyor.entity :** _contains surveyor related user information_
- **user.rlr.entity :** _contains regional land registry related user information_
- **nic.entity :** _contains national identity card information_
- **land.entity :** _contains land information which are not in blockchain_
- **land.deed.entity :** _contains deed information for each land_
- **land.plan.entity :** _contains plan information for each land_

## Database Entity Related Services

The services for database entities can be found at "/blockchain/packages/server/src/services" location.

- **user.service :**
    - _Auth User related services_
        - getAuthUserById(id: string)
        - getAuthUserByCredentials(email: string, password: string)
        - createAuthUser(email: string, password: string, type: string)
        - updateAuthUser(user: AuthUser)
        - updateAuthUserPassword(id: string, password: string)
        - deleteAuthUserById(id: string)