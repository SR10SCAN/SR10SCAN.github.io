# 👨‍💻 Portafolio de Ciberseguridad – SR10SCAN

¡Bienvenido a mi sitio! Aprende conmigo ciberseguridad ofensiva y defensiva. Aquí documento todo lo que voy aprendiendo, resolviendo y creando.

---

## Overthewire
# 🚩 OverTheWire: Bandit Writeups (30-31)

Soluciones detalladas para los niveles de Git y escapes de Shell en Bandit.

---

## 🚩 Bandit Level 31 → 32
**Concepto Clave:** Bypass de `.gitignore` y Validación mediante Git Hooks.

### 📝 Objetivo del Nivel
El servidor requiere que enviemos un archivo específico al repositorio remoto para validar nuestra identidad y entregarnos la siguiente credencial.


* **Archivo:** key.txt
* **Contenido:** May I come in?
* **Rama:** master

---

### 🛠️ Paso a Paso para la Resolución

#### 1. Clonar el repositorio
Primero, descargamos el repositorio a nuestra máquina local:
como buen practica creamos una carpeta en el cual clonaremos 'repo'.
>>git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
cd repo

#### 2. Creación del archivo de acceso
Creamos el archivo key.txt con el contenido exacto requerido por el reto:
echo "May I come in?" > key.txt

#### 3. Forzar el seguimiento del archivo (Bypass de .gitignore)
Al intentar añadir el archivo con git add, el sistema lo rechazará porque existe una regla en el archivo .gitignore que ignora todos los archivos .txt. Para saltarnos esta restricción, usamos el parámetro force (-f):
git add -f key.txt

### 4. Confirmación y envío (Push)
Realizamos el commit local y subimos los cambios al servidor.
Nota: La contraseña para el comando push es la misma que usamos para clonar: f***2xb7bRyFmAvQYQGEqsbhVy*****y

git commit -m "Añadiendo la llave de acceso"
git push origin master
---
### finalmente tendremos la contraseña:'3****hqyAlVBEZpVb6LYStshZoq****K'
Aunque el comando git push devuelva un error al final, la contraseña aparecerá en los mensajes del terminal. Esto se debe a la configuración del servidor
---
## 📓 Blog Técnico

> Reflexiones, artículos técnicos, consejos y aprendizaje continuo.

- [Cómo estructurar tu portafolio de ciberseguridad](blog/estructura_portafolio.md)
- [Errores comunes en principiantes de hacking ético](blog/errores_principiantes.md)
- [¿Qué son los IOC? Indicadores de compromiso](blog/que_son_iocs.md)

---

## 📬 Contacto

Puedes comunicarte conmigo dejando un mensaje en la pestaña de [Discussions](https://github.com/SR10SCAN/SR10SCAN.github.io/discussions) de este repositorio.

---

© 2025 SR10SCAN – Todos los derechos reservados
