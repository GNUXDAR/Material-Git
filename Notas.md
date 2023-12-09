# Notas
# 01 Introduccion
## Tipos Control de versiones
* Locales (RCS)
* Centralizados (CVS, SVN)
* Distribuidos (mercurial, bazaar, GIT)
* rcs es un sistema de control de versiones locales
Evoluciones: RCS -> CVS->Subversion(SVN)->GIT

## Sistemas de control de versione git
github  
gitlab  
bitbucket  
surceforge (permite tipo, mercurias y svn)  

# 02 Instalacion
Se puede instalar en windows, Mac Os y en nuestros queridos GNU/Linux  
en GNU/Linux: sudo apt install git  
se puede instalar en server propio gitlab ó gitea  

# 03 Repositorio Local I
hay 3 configuraciones en git
 * A nivel de sistema operativo (--system)
   * git config --list --system
     * cat /etc/gitconfig
 * Global (--global a todos los repositorios de mi usuario)
    * git config --list --global
      * cat ~/.gitconfig
 * local (--local a mi repositorio actual)
   * git config --list --local
     * cat .git/config

## git init --bare nombre_repo_aplicacion  
esto es mas que todo para trabajar en una intranet, una especie de repositorio compartido en la misma maquina o en el misma red

## git tag 
git tag                             (lista los tag)
git tag 1.0.0 -m "version 1.0.0"
git push origin 1.0.0               (hacer push al tag)