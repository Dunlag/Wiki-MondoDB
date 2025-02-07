# Instalación de MongoDB en Windows, Linux y macOS

MongoDB es una base de datos NoSQL orientada a documentos. A continuación, se describen los pasos para instalarlo en diferentes sistemas operativos.

## 📌 Instalación en Windows

1. **Descargar el instalador**
   - Ve a la página oficial: [MongoDB Community Server](https://www.mongodb.com/try/download/community)
   - Descarga el instalador `.msi` para Windows.
   
2. **Ejecutar el instalador**
   - Ejecuta el archivo `.msi` y sigue las instrucciones.
   - Selecciona "Complete Installation".
   - Habilita la opción "Run MongoDB as a Windows Service".

3. **Configurar variables de entorno** (Opcional pero recomendado)
   - Agrega `C:\Program Files\MongoDB\Server\<versión>\bin` a la variable de entorno `PATH`.

4. **Verificar la instalación**
   ```powershell
   mongosh --version
   ```

## 🐧 Instalación en Linux

### Ubuntu y Debian

1. **Importar la clave GPG y agregar el repositorio**
   ```bash
   curl -fsSL https://pgp.mongodb.com/server-7.0.asc | sudo gpg --dearmor -o /usr/share/keyrings/mongodb-server-7.0.gpg
   echo "deb [signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
   sudo apt update
   ```

2. **Instalar MongoDB**
   ```bash
   sudo apt install -y mongodb-org
   ```

3. **Iniciar el servicio**
   ```bash
   sudo systemctl start mongod
   sudo systemctl enable mongod
   ```

4. **Verificar la instalación**
   ```bash
   mongosh --version
   ```

### Arch Linux

1. **Instalar MongoDB desde los repositorios oficiales**
   ```bash
   sudo pacman -S mongodb
   ```
2. **Iniciar el servicio**
   ```bash
   sudo systemctl start mongodb
   sudo systemctl enable mongodb
   ```

## 🍏 Instalación en macOS

### Instalación con Homebrew

1. **Actualizar Homebrew y añadir MongoDB**
   ```bash
   brew tap mongodb/brew
   ```
2. **Instalar MongoDB Community Edition**
   ```bash
   brew install mongodb-community@7.0
   ```
3. **Iniciar el servicio**
   ```bash
   brew services start mongodb-community@7.0
   ```

4. **Verificar la instalación**
   ```bash
   mongosh --version
   ```

---
## 🔥 Comprobar que MongoDB está funcionando

Independientemente del sistema operativo, puedes probar la conexión ejecutando:
```bash
mongosh
```
Si ves un prompt interactivo, ¡MongoDB está listo para usarse! 🎉

---

## 🖥️ Instalación y Uso de MongoDB Compass

MongoDB Compass es una interfaz gráfica que permite visualizar y administrar bases de datos MongoDB de forma intuitiva.

### 📥 Instalación de MongoDB Compass

1. **Descargar Compass**
   - Ve a la página oficial: [MongoDB Compass](https://www.mongodb.com/try/download/compass)
   - Descarga el instalador según tu sistema operativo.

2. **Instalar MongoDB Compass**
   - En Windows y macOS, ejecuta el instalador y sigue las instrucciones.
   - En Linux, descomprime el archivo `.tgz` y ejecuta `mongodb-compass`.

### 🚀 Conectarse a una base de datos

1. **Abrir MongoDB Compass**
2. **Introducir la URI de conexión**, por ejemplo:
   ```
   mongodb://localhost:27017
   ```
3. **Hacer clic en "Connect"**

### 📊 Funcionalidades Principales
- **Explorar bases de datos y colecciones**
- **Ejecutar consultas visualmente**
- **Visualizar estadísticas de rendimiento**
- **Importar y exportar datos**

MongoDB Compass es una excelente herramienta para facilitar el trabajo con MongoDB sin necesidad de escribir comandos en la terminal.
