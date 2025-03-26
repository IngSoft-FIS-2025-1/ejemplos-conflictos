# Ejemplo de resolución de conflictos en Git

## 1. Inicializar el Repositorio

**1. Creación de nuevo directorio:**
```
   mkdir mi_proyecto
   cd mi_proyecto
```

**2. Inicialización del repositorio en el directorio creado:**
```
   git init
```

**3. Configuración de nombre de usuario y correo electrónico:**
```
   git config user.name "Nombre"
   git config user.email "mail@ejemplo.com"
```


**4. Opcional: vinculación con un repositorio remoto:**

```
   git remote add origin {url_github}
```


## 2. Creación de archivos

**1. Crear un archivo inicial y agregar contenido:**
```
   echo "Esto es una prueba" > archivo.txt
```


**2. Añadir el archivo al área de preparación (staging area):**
```
   git add archivo.txt
```


**3. Verificar el estado del repositorio:**
```
   git status
```

 
**4. Realizar un commit inicial:**
```
   git commit -m "Commit inicial: agrega archivo.txt"
```


## 3. Creación y trabajo con ramas

**1. Crear y moverse a una nueva rama llamada nueva_rama:**
```
   git checkout -b nueva_rama
```


**2. Modificar archivo.txt en nueva_rama:**
```
   echo "Texto en nueva_rama" >> archivo.txt
```

   
**3. Añadir y realizar un commit en nueva_rama:**
```
   git add archivo.txt
   git commit -m "Actualiza archivo.txt en nueva_rama"
```


**4. Moverse a la rama principal (main o master):**
```
   git checkout master
   Nota: chequear si la rama se llama main o master en el repositorio para usarla en el comando.
```
   
**5. Modificar archivo.txt en la rama principal:**
```
   echo "Texto en main" >> archivo.txt
```

**6. Añadir y realizar un commit en la rama principal:**
```
   git add archivo.txt
   git commit -m "Actualiza archivo.txt en main"
```

## 4. Hacer merge

**1. Fusionar nueva_rama en main:**
```
   git merge nueva_rama
```

Nota: Ambos commits han modificado el mismo archivo archivo.txt en diferentes ramas, por lo tanto, se espera que haya un conflicto.
   
## 5. Resolver el Conflicto

**1. Verificar el estado del conflicto:**

```
   git status
```


**2. Editar archivo.txt para resolver el conflicto.**

Buscar las marcas de conflicto <<<<<<<, =======, y >>>>>>> en el archivo y elegir/combinar los cambios necesarios. El archivo se verá algo así:

```
Esto es una prueba
<<<<<<< HEAD
Texto en main
=======
Texto en nueva_rama
>>>>>>> nueva_rama
```

**3. Después de resolver el conflicto, añadir el archivo resuelto al área de preparación:**

```
   git add archivo.txt
```

**4. Finalizar el merge con un commit:**

```
   git commit -m "Se resuelve conflicto entre main y nueva_rama"
```

## 6. Visualizar el log de commits

```
   git log --oneline --graph
```

