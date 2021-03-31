# Keycloak Cheat Sheet
Keycloak Cheat Sheet with the most needed stuff..









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


# Realm and a user
- When you log in to the admin console, you work in a realm, which is a space where you manage objects. Two types of realms exist:

  - Master realm - This realm was created for you when you first started Keycloak. It contains the admin account you created at the first login. You use this realm only to create other realms.

  - Other realms - These realms are created by the admin in the master realm. In these realms, administrators create users and applications. The applications are owned by the users.

![Test Image 4](https://www.keycloak.org/docs/latest/getting_started/images/master_realm.png)




<br><br>



## Creating a realm
- Go to http://localhost:8080/auth/admin/ and log in to the Keycloak admin console using the admin account.

  - From the Master menu, click Add Realm. When you are logged in to the master realm, this menu lists all other realms.

    - Type demo in the Name field.

    ![Test Image 4](https://www.keycloak.org/docs/latest/getting_started/images/add-demo-realm.png)

      - Click Create.

    ![Test Image 4](https://www.keycloak.org/docs/latest/getting_started/images/demo-realm.png)

      - Switch between managing the master realm and the realm you just created by clicking entries in the Select realm drop-down list.

