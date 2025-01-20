

---
# Git Cheatsheet

### **Comandos básicos de Git**

- **Configurar Git (primer uso):**
  ```bash
  git config --global user.name "Tu Nombre"
  git config --global user.email "tu.email@dominio.com"
  ```

- **Iniciar un repositorio nuevo:**
  ```bash
  git init
  ```

- **Clonar un repositorio remoto:**
  ```bash
  git clone https://github.com/usuario/repositorio.git
  ```

- **Ver el estado de los archivos:**
  ```bash
  git status
  ```

- **Añadir cambios al área de preparación (staging area):**
  - Para agregar un archivo específico:
    ```bash
    git add archivo.txt
    ```
  - Para agregar todos los archivos modificados:
    ```bash
    git add .
    ```

- **Hacer un commit con un mensaje:**
  ```bash
  git commit -m "Mensaje del commit"
  ```

- **Ver el historial de commits:**
  ```bash
  git log
  ```

- **Subir cambios al repositorio remoto:**
  ```bash
  git push origin main
  ```

- **Actualizar tu repositorio local con los cambios remotos:**
  ```bash
  git pull origin main
  ```

---

### **Comandos para gestionar archivos**

- **Eliminar un archivo del índice de Git (pero mantenerlo en tu sistema):**
  ```bash
  git rm --cached archivo.txt
  ```

- **Eliminar un archivo de Git y también del sistema de archivos:**
  ```bash
  git rm archivo.txt
  ```

- **Ver qué archivos están siendo ignorados por `.gitignore`:**
  ```bash
  git check-ignore -v archivo.txt
  ```

- **Deshacer un cambio en el área de preparación (staging area):**
  ```bash
  git reset archivo.txt
  ```

- **Deshacer un commit (mover los cambios a staging):**
  ```bash
  git reset --soft HEAD^
  ```

---

### **Trabajar con ramas**

- **Ver las ramas disponibles:**
  ```bash
  git branch
  ```

- **Crear una nueva rama:**
  ```bash
  git branch nombre-rama
  ```

- **Cambiar a una rama existente:**
  ```bash
  git checkout nombre-rama
  ```

- **Crear y cambiar a una nueva rama:**
  ```bash
  git checkout -b nombre-nueva-rama
  ```

- **Fusionar una rama en la rama actual:**
  ```bash
  git merge nombre-rama
  ```

---

### **Gestionar el `.gitignore`**

- **Añadir un archivo o patrón al `.gitignore`:**
  - Abre el archivo `.gitignore` y agrega:
    ```txt
    archivo_o_patron
    ```

- **Ver si un archivo está siendo ignorado correctamente:**
  ```bash
  git check-ignore -v archivo.txt
  ```

- **Ver qué archivos están siendo ignorados por Git:**
  ```bash
  git ls-files --ignored --exclude-standard --others
  ```

---

### **Gestionar tu repositorio en GitHub**

- **Crear un repositorio en GitHub**: Lo haces en la página de GitHub, no en la terminal, pero una vez creado, puedes conectarlo a tu repositorio local con:
  ```bash
  git remote add origin https://github.com/usuario/repositorio.git
  ```

- **Configurar el repositorio remoto (si aún no lo has hecho):**
  ```bash
  git remote add origin https://github.com/usuario/repositorio.git
  ```

- **Ver las URL de los repositorios remotos:**
  ```bash
  git remote -v
  ```

- **Eliminar un archivo de GitHub completamente del historial** (requiere reescribir el historial):
  - Usando `BFG Repo-Cleaner`:
    ```bash
    bfg --delete-files 'tempCodeRunnerFile.py'
    ```
  - O con `git filter-branch` (más complejo, no recomendado para principiantes):
    ```bash
    git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch tempCodeRunnerFile.py' --prune-empty --tag-name-filter cat -- --all
    ```

---

### **Comandos para limpiar y optimizar el repositorio**

- **Limpiar archivos no rastreados (archivos no añadidos, temporales, etc.):**
  ```bash
  git clean -fd
  ```

- **Limpiar los archivos del repositorio que están en caché pero ya no están en el índice:**
  ```bash
  git rm -r --cached .
  ```

---

### **Autenticación con GitHub (con token personal)**

- **Configurar token personal de acceso como método de autenticación** (para evitar usar contraseñas):

  Cuando Git te pida tu contraseña, utiliza el token en lugar de tu contraseña de GitHub.

  - Si ya tienes configurado el token, la primera vez que te autenticas (después de escribir tu usuario), puedes escribir el token cuando te pida la contraseña.

---

### **Errores comunes y soluciones**

- **"fatal: Authentication failed"**: Este error ocurre porque las contraseñas han sido deshabilitadas para operaciones de Git en GitHub. Usa un **token personal de acceso** (PAT) en su lugar.

- **"fatal: No such file or directory"**: Asegúrate de estar en la carpeta correcta del repositorio y que el archivo exista.

---

Este cheatsheet cubre los comandos básicos más importantes y los problemas comunes que puedas encontrar en tu trabajo con Git y GitHub. Te recomiendo que sigas practicando y te familiarices con ellos para facilitarte la gestión de tus repositorios.

Si alguna vez tienes dudas adicionales, ¡no dudes en preguntarme!

--- 

Este formato está listo para pegar directamente en un archivo `.md` para que lo puedas subir como parte de la documentación de tu repositorio de GitHub.
