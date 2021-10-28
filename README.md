# Sobre este Template

![ULL](images/ull.gif)
En este template se ha dejado un fichero de configuración para gitpod [.gitpod.yml](.gitpod.yml) con algunos alias para `git`

```yml
# List the start up tasks. Learn more https://www.gitpod.io/docs/config-start-tasks/
tasks:
  - init: |
      git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --"
      git config --global alias.co checkout
      git config --global alias.br branch
      git config --global alias.ci commit
      git config --global alias.st status
    command: echo 'Bienvenido a esta tarea de Aprendizaje y Enseñanza de la Tecnología'

image:
  file: .gitpod.Dockerfile

# List the ports to expose. Learn more https://www.gitpod.io/docs/config-ports/
ports:
  - port: 3000
    onOpen: open-browser
```

También se ha añadido un Dockerfile <.gitpod.Dockerfile> que extiende el contenedor `gitpod/workspace-full` instalando GitHub Cli y `markdownlint-cli`:

```dockerfile
FROM gitpod/workspace-full

# Install custom tools, runtime, etc.
# RUN brew install fzf
RUN npm install -g markdownlint-cli # runs during prebuild
RUN brew install gh
```

## Editar en Mi Máquina con Visual Studio Code 

[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-f059dc9a6f8d3a56e377f745f24479a46679e63a5d9fe6f495e02850cd0d8118.svg)](https://classroom.github.com/online_ide?assignment_repo_id=6123381&assignment_repo_type=AssignmentRepo)
