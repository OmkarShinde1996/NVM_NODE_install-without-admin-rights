# NVM_NODE_install-without-admin-rights
This file demonstrates how to install nvm (node version manager) and node js latest version on windows without admin rights

## 1. Open Powershell and Execute following command
```
cd $Env:USERPROFILE;
```
```
Invoke-WebRequest https://raw.githubusercontent.com/jchip/nvm/refs/heads/master/install.ps1 -OutFile install.ps1;
```
```
.\install.ps1 -nvmhome $Env:USERPROFILE\nvm;
```
```
del install.ps1
```
## 2. If you encounter following error
```
.\install.ps1 : File C:\Users\node\install.ps1 cannot be loaded because running scripts is disabled on this system.
For more information, see about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170.
At line:3 char:1
+ .\install.ps1 -nvmhome $Env:USERPROFILE\nvm;
+ ~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```
## 3. Execute following command to override #2 error
```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```
  - ### Provide answer as "Y"
    ```
    Execution Policy Change
    The execution policy helps protect you from scripts that you do not trust. Changing the execution policy might expose
    you to the security risks described in the about_Execution_Policies help topic at
    https:/go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): 
    ```

## 4. Execute following command
```
cd $Env:USERPROFILE;
Invoke-WebRequest https://raw.githubusercontent.com/jchip/nvm/refs/heads/master/install.ps1 -OutFile install.ps1;
.\install.ps1 -nvmhome $Env:USERPROFILE\nvm;
del install.ps1
```
  - ### _NVM should be installed_

    ```

    Got NVM_HOME C:\Users\node\nvm from command line
    Default NVM_LINK to C:\Users\node\nvm\nodejs\bin
    Retrieving https://nodejs.org/dist/v18.12.1/node-v18.12.1-win-x64.zip
    Retrieving https://registry.npmjs.org/@jchip/nvm/-/nvm-1.5.4.tgz
    Installing Node v18.12.1...
    Node.js v18.12.1 installed.
    The operation completed successfully.
    NVM installed, Node.js version v18.12.1 activated.
    ```
## 5. Execute to Verify NVM installation

```
nvm ls
```
   - ### Installed NVM

      ```
      PS C:\Users\node> nvm ls
      v12.22.12
      * v18.12.1 (linked)
      ```
---
## 6. At last use below command to point to the latest version of node
```
nvm use <version number provided by `nmv ls` command>
```
Ref: https://github.com/jchip/nvm
