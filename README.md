# Configuracion nativa de la computadora
## Displays
- DPI en "More Space"
- Brillo al maximo sin brillo automatico
- TrueTone activado
- Advanced > Slim dim the display on battery desactivado
- Night Shift como al 10% de intensidad en modo "Sunset to Sunrise"

## Dock
- Size al 20%
- Magnification al 40%
- Dock auto hide

## Uso
- Generalmente tener las ventanas principales del momento (VSCode, Chrome, Discord, etc) en fullscreen en escritorios separados
- En el escritorio principal con Stage Manager las demas aplicaciones que van rotando (DBeaver, Warp, Ajustes, Mail, etc)
- Ventanas no maximizadas seteadas en Almost Maximaze (Swish/Raycast -> Ver mas adelante)

## Control Center en MenuBar
De derecha a izquierda partiendo desde el Control Center
- Spotlite
- Battery > Show Percentage
- Wi-fi
- Bluetooth
- Sound
- Raycast con calendar (Ver mas adelante)

Todos en show allways

## Touchpad
- Tap to click activado
- Speed en 5/10

# Aplicaciones principales

## Chrome
Principalmente Chrome con las siguientes extensiones:
- React DevTools
- Video Speed Controller
- Volume Master
- Duplicate Tab
- 1Password
- AdblockPlus
- Youtube Auto HD + FPS
- Wappalizer
- JSON Viewer

## VSCode
Configuracion automatica (futura commit)

## Brew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
```bash
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/lucasalda/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
```

## Warp
- Theme: Base16 Solarflare
    Copiarlo en una carpeta llamada ~/.warp/themes
- Font: MesloLGS NF Regular.tff
    Instalar la font en MacOS
- Feature > Sessions > Honor user's custom propmt Activado
- Feature > Sessions > Working directory for new sessions: Advanced
    - New Window: ~/Documents
    - New Tab: previous
    - New split: previous

#### Launch config:
Mover a ~/.warp/launch_configurations/ el archivo nexus.yaml

### Powerlevel10k 
Instalation
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```
```bash
p10k configure
```

### Bat (cat on steroids)
```bash
brew install bat
```
Para reemplazar a cat
```bash
nano ~/.zshrc
```
y agregar al final del archivo
```bash
alias ocat="/bin/cat"
alias cat="bat"
alias ll="ls -l"
```
## Linear 
Instalar desde la web

## Raycast
Instalar desde la web

Para reemplazar el cmd+space se tiene que:
System Preferences > Keyboard > Shortcuts > Spotlight y deshabilitar el shortcut

### Extensiones 
- Calendar: dar permiso y activar show events in menu bar: Allways
- VS Code
- Google Translate
- Kill process
- Color Picker
- Warp -> Se crea un quicklink para ejecutar las launch configs
- System Monitor
- MyIp
- Linear -> Testeando si dejarla en el menubar

### Commandos
- Comando para abrirlo: cmd + space
- clipboard history: cmd + shift + v
- Floating note: opt + n
- Color picker: ctrl + p


## SSH

### Activar
ir a Settings > Privacy & Securiry > Full Access Disk y darselo a VS Code y Warp

```bash
sudo systemsetup -setremoteLogin on
```

Iniciar el agente ssh-agent
```bash
eval "$(ssh-agent -s)"
```

```bash
ssh-keygen
```

### Conectar a github
```bash
touch ~/.ssh/config
nano ~/.ssh/config
```

```bash
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
```

```bash
ssh-add --apple-use-keychain ~/.ssh/id_rsa
```

```bash
pbcopy < ~/.ssh/id_rsa.pub
```

Agregar lo que se copio al clipboard al github

## Nodejs

Manejo de versiones via nvm:

```bash
curl -sL https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.0/install.sh -o install_nvm.sh
```

```bash
chmod +x ./install_nvm.sh && ./install_nvm.sh
```
Reiniciar la consola

```bash
nvm install --lts
```

## Swish (gestos touchpad)

Configuracion pendiente (ver en icloud las fotos)




