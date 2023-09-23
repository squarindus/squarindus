# Power cookie
* Go to the web site
* Rightclick and select inspect then go to application
* Select cookies change the cookie value
* Flag will be displayed on the screen after reloading
* Flag :picoCTF{gr4d3_A_c00k13_65fd1e1a}

# Sql Direct
* Connect to this PostgreSQL server and find the flag!
  Additional details will be available after launching your challenge instance.
* Execute the following syntaxes in linux interface
  * psql -h saturn.picoctf.net -p 50750 -U postgres pico               
  * password:postgre
  * \c pico                                        
  * \dt                                              
  * select * from flags                           
* flag:picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
# Irish-Name-Repo

> Repo 1
 * Used sql injection inorder to get the flag
 * Used admin as the user name and password as ' OR '1'=1
 * Got the flag
> Repo 2
 * This site looks a lot like the one from Irish-Name-Repo 1, yet once we try this same SQL Injection of ' OR 1=1-- here, we get nothing but a page that says SQLi detected.
 * But we use injection command in different way we get the flag username=admin' and 1=1-- password='  >
 * Flag :picoCTF{m0R3_SQL_plz_c34df170}
> Repo 3
 * By using linux interface i got the flag
# Java Code Analysis!?!
 * Download the attachment and read the java file and get the secret code.
 * After log into the web site inspect it go to local storage and copy the json token and use an online json decoder in order to change the user preferences to admin ,username as Admin and email as admin ,user=2
 * Paste it to the token in local storage change the credintials in the dictonary.
 * Reload
 * Flag:picoCTF{w34k_jwt_n0t_g00d_6e5d7df5}
