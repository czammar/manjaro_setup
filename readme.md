# Post installacion de Manjaro

**Fecha:** 05/09/2020

Setup de manjaro tras instalación.

## R y Rstudio
```{bash}
# Install yay para binarios https://kumulonimb.us/post/instalar_rstudio_manjaro/
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si

# R installing
sudo pacman -S r
#r

## Rstudio & openblas-lapack
sudo pacman -S gcc-fortran
yay -S rstudio-desktop-bin
yay -S openblas-lapack # Elimina blas y lapack
```

## Anaconda
```{bash}
wget https://repo.anaconda.com/archive/Anaconda3-2020.07-Linux-x86_64.sh
sh Anaconda3-2019.10-Linux-x86_64.sh
# Habilitar comandos jupyter y jupyter lab
echo "## -- Seteamos el path para llamar anaconda# >>.zshrc
echo "export PATH="/home/cesar/anaconda3/bin:$PATH"" >>.zshrc
```

## Pyenv
```{bash}
sudo pacman -S base-devel openssl zlib xz
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bash_profile
exec "$SHELL"
man pyenv
pyenv install versions
pyenv install --list
```
## Docker
```{bash}
sudo pacman -S docker
```
## Gummi
```{bash}
sudo pacman -S gummi
```

## Fixing slow pacman mirros

```{bash}
sudo pacman-mirrors
#sudo pacman-mirrors --geoip && sudo pacman -Syyu # test on geographic ip, but takes a lot to run
sudo pacman-mirrors --continent && sudo pacman -Syyu # test on currenct continental location
cat /etc/pacman.d/mirrorlist
```

## Requrimiento de Java para Spark

```{bash}
which java
sudo pacman -sS java | grep jre\
sudo pacman -S jre-openjdk
java -version
```

## Editores de codigo

```{bash}
sudo pacman -S snapd
sudo systemctl enable --now snapd.socket
sudo ln -s /var/lib/snapd/snap /snap
sudo snap install sublime-text --classic
sudo pacman -S atomhhhhh
```

## Postgres
```{bash}
sudo pacman -S postgresql postgresql-docs postgis  
```

## Otros
```{bash}
sudo pacman -S youtube-dl htop tree
```


```
