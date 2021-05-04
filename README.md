# Keycloak Cheat Sheet
Keycloak Cheat Sheet with the most needed stuff..




<br><br>

# Docs
- keycloak.org/docs



































<br><br>
____________________________________________
____________________________________________
<br><br>



# Download
- https://www.keycloak.org/downloads.html
```bash
tar -xvzf keycloak-12.0.4.tar.gz
```

































<br><br>
____________________________________________
____________________________________________
<br><br>


# Starting server
```bash
cd bin
./standalone.sh
```

<br><br>


# Creating the admin account
- Before you can use Keycloak, you need to create an admin account which you use to log in to the Keycloak admin console.

  - Open http://localhost:8080/auth in your web browser.
  
    - Enter a username and password to create an initial admin user


<br><br>


# Login to Admin Area
- http://localhost:8080/auth/admin/

























<br><br>
____________________________________________
____________________________________________
<br><br>


# Realm
- Realms will handle multiple clients. It is a parent section of clients

<br><br>

- When you log in to the admin console, you work in a realm, which is a space where you manage objects. Two types of realms exist:

  - Master realm - This realm was created for you when you first started Keycloak. It contains the admin account you created at the first login. You use this realm only to create other realms.

  - Other realms - These realms are created by the admin in the master realm. In these realms, administrators create users and applications. The applications are owned by the users.

![Test Image 4](https://www.keycloak.org/docs/latest/getting_started/images/master_realm.png)




<br><br><br><br>



## Creating a realm
- Go to http://localhost:8080/auth/admin/ and log in to the Keycloak admin console using the admin account.

  - From the Master menu, click Add Realm. When you are logged in to the master realm, this menu lists all other realms.

    - Type demo in the Name field.

    ![Test Image 4](https://www.keycloak.org/docs/latest/getting_started/images/add-demo-realm.png)

      - Click Create.



<br><br>


![Test Image 4](https://www.keycloak.org/docs/latest/getting_started/images/demo-realm.png)

- Switch between managing the master realm and the realm you just created by clicking entries in the Select realm drop-down list.







<br><br><br><br>

## Tokens
- Settings for your Tokens

















































<br><br>
____________________________________________
____________________________________________
<br><br>


# User

- Will be only created inside of a realm

<br><br>



## Creating a user
- From the menu, click Users to open the user list page.

  - On the right side of the empty user list, click Add User to open the Add user page.

    - Enter a name in the Username field.



<br><br>
-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
<br><br>


- This is the only required field.

  - Add user page

    - Creating a user

    ![Test Image 4](https://www.keycloak.org/docs/latest/getting_started/images/add-user.png)

      - Flip the Email Verified switch to On and click Save.

        - The management page for the new user opens.

          - Click the Credentials tab to set a temporary password for the new user.

            - Type a new password and confirm it.

              - Click Set Password to set the user password to the new one you specified.

              ![Test Image 4](https://www.keycloak.org/docs/latest/getting_started/images/user-credentials.png)






          





<br><br><br><br>

## Logging into the Account Console

- Every user in a realm has access to the account console. You use this console to update your profile information and change your credentials. You can now test logging in with that user in the realm that you created.

  - Log out of the admin console by opening the user menu and selecting Sign Out.

    - Go to http://localhost:8080/auth/realms/demo/account and log in to your demo realm as the user that you just created.

      - When you are asked to supply a new password, enter a password that you can remember.

      ![Test Image 4](https://www.keycloak.org/docs/latest/getting_started/images/update-password.png)

























































































<br><br>
____________________________________________
____________________________________________
<br><br>


# Clients

- Will handle your applications with domains

- You can use /auth on each application to sign-in

<br><br>









































































<br><br>
____________________________________________
____________________________________________
<br><br>



# Roles
- Roles identify a type or category of user. Admin, user, manager, and employee are all typical roles that may exist in an organization. Applications often assign access and permissions to specific roles rather than individual users as dealing with users can be too fine grained and hard to manage. For example, the Admin Console has specific roles which give permission to users to access parts of the Admin Console UI and perform certain actions. There is a global namespace for roles and each client also has its own dedicated namespace where roles can be defined.


<br><br>

## Realm Roles
- Realm-level roles are a global namespace to define your roles. You can see the list of built-in and created roles by clicking the Roles left menu item.

![Test Image 4](https://www.keycloak.org/docs/latest/server_admin/keycloak-images/roles.png)

  <br><br>
  - To create a role, click Add Role on this page, enter in the name and description of the role, and click Save.
  
  ![Test Image 4](https://www.keycloak.org/docs/latest/server_admin/keycloak-images/role.png)








<br><br><br><br>

## Client Roles
- Client roles are basically a namespace dedicated to a client. Each client gets its own namespace. Client roles are managed under the Roles tab under each individual client. You interact with this UI the same way you do for realm-level roles.







<br><br><br><br>

## Composite Roles (https://www.keycloak.org/docs/6.0/server_admin/#_composite-roles)
- Any realm or client level role can be turned into a composite role. A composite role is a role that has one or more additional roles associated with it. When a composite role is mapped to the user, the user also gains the roles associated with that composite. This inheritance is recursive so any composite of composites also gets inherited.

<br><br>

To turn a regular role into a composite role, go to the role detail page and flip the Composite Role switch on.

![Test Image 4](https://www.keycloak.org/docs/latest/server_admin/keycloak-images/composite-role.png)

















































<br><br>
____________________________________________
____________________________________________
<br><br>


# Authentication (https://www.keycloak.org/docs/6.0/server_admin/#authentication)
- There are a few features you should be aware of when configuring authentication for your realm. Many organizations have strict password and OTP policies that you can enforce via settings in the Admin Console. You may or may not want to require different credential types for authentication. You may want to give users the option to login via Kerberos or disable or enable various built-in credential types. This chapter covers all of these topics.







































<br><br>
____________________________________________
____________________________________________
<br><br>


# Securing a sample application (https://www.keycloak.org/docs/latest/getting_started/index.html#securing-a-sample-application)
- Now that you have an admin account, a realm, and a user, you can use Keycloak to secure a sample WildFly servlet application. You install a WildFly client adapter, register the application in the admin console, modify the WildFly instance to work with Keycloak, and use Keycloak with some sample code to secure the application.

  <br><br>
  - Prerequisites
    - You need to adjust the port used by Keycloak to avoid port conflicts with WildFly.

















































<br><br>
____________________________________________
____________________________________________
<br><br>

# Gatekeeper (https://github.com/oneconcern/keycloak-gatekeeper)
- Dynamic adapter thats work together with Keycloak. Or in other words a middleware

<br><br>


## DOCS
- https://www.keycloak.org/docs/latest/securing_apps/#_keycloak_generic_adapter




<br><br>


## Params
```yml
# require-any-role - All listed roles will gain access.
- uri: /api/v1/data/*
  methods: [ POST ]
  roles: [ editCcs, deleteCcs ]
  require-any-role: true
  groups: [ /$(group.name) ]
```





