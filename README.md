***Tutorial : How to deploy your online website with Github when you use FTP server.***
![]()


**1** - *Create the Repository* 

**2** - *Clone your repository*

**3** - *Click to the Action Button* 

![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/Action-0.png)




**4** - *Create a "main.yml" file*


![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/create-the-main-yml-2.png)

                     
              on: push
              name: Publish Website
              jobs:
                FTP-Deploy-Action:
                  name: FTP-Deploy-Action
                  runs-on: ubuntu-latest
                  steps:
                  - uses: actions/checkout@master
                  - name: FTP-Deploy-Action
                    uses: SamKirkland/FTP-Deploy-Action@master
                    with:
                      server: ${{ secrets.FTP_SERVER }}
                      username: ${{ secrets.FTP_USERNAME }}  
                      password: ${{ secrets.FTP_PASSWORD }}
                      server-dir: /wp-content/themes/NomDeVotreTheme/


**5** - *Commit the main.yml file*


![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/commit-the-main-3.png)





**6** - *Create the secrets (Environnement variables)* 

![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/settings-4.png)

![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/settings-secret-5.png)

![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/new-repository-secret-6.png)

   **6.1** - *Create The Secrets Password*

![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/create-password-variable-7.png)

   **6.2** - *Create The Secrets Server*
        

![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/create-the-server-variable-8.png)

   **6.3** - *Create The Secrets Username*
        

![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/create-the-username-variable-9.png)

   **6.4** -*See Your different variables*

**7** - *rerun the jobs* 

![](https://raw.githubusercontent.com/EmiliePieront/FTP-deploy-action-Watch/main/images/rerun-the-jobs-11.png)



**Last Step** - *Push your folders and files in the repository* 

![](https://github.com/EmiliePieront/FTP-deploy-action-Watch/blob/main/images/screenshot-filezilla-12.png?raw=true)

And that's it :D Congratulation ! 

**Source** 
[Le lien de la source ici](https://github.com/marketplace/actions/ftp-deploy)
