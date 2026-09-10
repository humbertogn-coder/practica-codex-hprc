# Practica Codex HPRC

Este repositorio es una practica reusable para aprender un flujo basico de trabajo con:

- Conda, para crear un ambiente de Python reproducible.
- Git y GitHub, para guardar cambios y compartir el proyecto.
- Codex, para revisar, explicar y mejorar codigo.
- HPRC, para correr el mismo proyecto en un cluster.

El programa actual esta en `main.py`. Por ahora imprime una tabla pequena con `pandas`.

## 1. Requisitos

Antes de empezar, instala o confirma que tienes:

- Anaconda o Miniconda.
- Git.
- Una cuenta de GitHub.
- Acceso a HPRC, si quieres practicar la parte del cluster.

## 2. Descargar el proyecto

Si el proyecto ya esta en GitHub, clonalo:

```bash
git clone URL_DEL_REPOSITORIO
cd PracticaCodex
```

Si ya tienes la carpeta en tu computadora, entra a ella:

```bash
cd PracticaCodex
```

## 3. Crear el ambiente con Conda

Opcion recomendada para practicar desde cero:

```bash
conda create -n codex-practica python=3.11
conda activate codex-practica
pip install -r requirements.txt
```

Opcion alternativa si quieres recrear el ambiente exportado:

```bash
conda env create -f environment.yml
conda activate codex-practica
```

Nota: `environment.yml` puede incluir detalles especificos de la computadora donde se exporto. Para compartir el proyecto con otras personas, `requirements.txt` suele ser mas simple.

## 4. Ejecutar localmente

Con el ambiente activado:

```bash
python main.py
```

Deberias ver un mensaje y una tabla con el estado de tres partes del flujo: computadora, GitHub y HPRC.

## 5. Practicar con Git

Revisa el estado del repositorio:

```bash
git status
```

Despues de editar archivos, guarda una version:

```bash
git add README.md
git commit -m "Mejora instrucciones del proyecto"
```

Para ver el historial:

```bash
git log --oneline
```

## 6. Subir a GitHub

Crea un repositorio vacio en GitHub. Luego conecta esta carpeta local con ese repositorio:

```bash
git remote add origin URL_DEL_REPOSITORIO
git branch -M main
git push -u origin main
```

Si el remoto ya existe, puedes verificarlo con:

```bash
git remote -v
```

## 7. Practicar con Codex

Ideas de tareas pequenas para pedirle a Codex:

- "Explicame que hace `main.py` linea por linea."
- "Revisa el proyecto y dime que archivos son importantes."
- "Propon una mejora, pero no cambies el codigo todavia."
- "Agrega una columna nueva a la tabla de `main.py`."
- "Crea una funcion para construir el DataFrame."

Buena practica: haz cambios pequenos, ejecuta `python main.py`, revisa `git status` y crea un commit cuando el resultado funcione.

## 8. Correr en HPRC

Entra al cluster:

```bash
ssh TU_USUARIO@DIRECCION_HPRC
```

Clona el repositorio:

```bash
git clone URL_DEL_REPOSITORIO
cd PracticaCodex
```

Carga Conda o Miniconda segun las instrucciones de HPRC. Un ejemplo comun es:

```bash
module load Anaconda3
```

Crea y activa el ambiente:

```bash
conda create -n codex-practica python=3.11
conda activate codex-practica
pip install -r requirements.txt
```

Ejecuta el programa:

```bash
python main.py
```

## 9. Ejemplo de trabajo reusable

Usa este ciclo cada vez que practiques:

```bash
conda activate codex-practica
git pull
python main.py
git status
```

Despues de hacer cambios:

```bash
python main.py
git add .
git commit -m "Describe el cambio"
git push
```

## 10. Archivos del proyecto

- `main.py`: codigo principal de la practica.
- `requirements.txt`: dependencias simples para instalar con `pip`.
- `environment.yml`: ambiente Conda exportado.
- `README.md`: instrucciones del proyecto.

## Problemas comunes

Si Conda no reconoce el ambiente:

```bash
conda env list
conda activate codex-practica
```

Si falta una dependencia:

```bash
pip install -r requirements.txt
```

Si Git no sabe a que repositorio subir:

```bash
git remote -v
```
