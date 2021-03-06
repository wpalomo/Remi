# Remi
Aplicación para recuperar la información de comprobantes electrónicos del SRI Ecuador

## *Python 2.7*

* Instalación del conector de Oracle en Mac OSX.

    - Descargar Oracle Instant Client. http://www.oracle.com/technetwork/database/features/instant-client/index-097480.html
        + instantclient-basic-macos.x64-11.2.0.4.0.zip 
        + instantclient-sqlplus-macos.x64-11.2.0.4.0.zip 
        + instantclient-sdk-macos.x64-11.2.0.4.0.zip
    - Copiar en un directorio todos los archivos, por ejemplo: /Users/jorgequiguango/opt/instantclient_11_2.
        ```
        libocci.dylib.11.1
        libociei.dylib
        libocijdbc11.dylib
        libsqlplus.dylib
        libsqlplusic.dylib
        ojdbc5.jar
        ojdbc6.jar
        sdk
        sqlplus
        uidrvci
        xstreams.jar
        ```
    - Crear enlaces simbólicos en el terminal:
        ```
        ln -s libclntsh.dylib.11.1 libclntsh.dylib
        ln -s libocci.dylib.11.1 libocci.dylib
        ```
    - Añadir al archivo .bash_profile: 
        ```
        nano .bash_profile 
        ```
        ```
        #Oracle Instant Client
        export ORACLE_HOME=/Users/jorgequiguango/opt/instantclient_11_2
        export DYLD_LIBRARY_PATH=$ORACLE_HOME
        export LD_LIBRARY_PATH=$ORACLE_HOME
        export NLS_LANG=AMERICAN_AMERICA.UTF8
        export PATH=$PATH:$ORACLE_HOME
        ```
    - Ejecutar: 
        ```
        source .bash_profile 
        ```
    - Añadir el nombre del host al archivo /etc/hosts: 
        ```
        sudo nano /etc/hosts
        ```
        ```
        127.0.0.1       localhost       maclibro        maclibro.local
        ```
    - Probar la conexión: 
        ```
        sqlplus lucila/l@//192.168.1.18:1521/orcl
        ```
    - Descargar Python del sitio oficial https://www.python.org, e instalar.
    - Instalar pip, si no está instalado:
        ```
        pip --version
        ```
        ```
        easy_install pip
        ```
    - Instalar cx_Oracle: 
        ```
        pip install cx_oracle
        ```
* Instalación del conector de Oracle en Windows.

    - Descargar Oracle Instant Client. http://www.oracle.com/technetwork/database/features/instant-client/index-097480.html
        + instantclient-basic-nt-11.2.0.4.0.zip
        + instantclient-sqlplus-nt-11.2.0.4.0.zip
        + instantclient-sdk-nt-11.2.0.4.0.zip
    - Copiar en un directorio todos los archivos, por ejemplo: C:\instantclient_11_2.
        ```
        sdk
        vc8
        vc9
        adrci.exe
        adrci.sym
        BASIC_README
        genezi.exe
        genezi.sym
        glogin.sql
        oci.dll
        oci.sym
        ocijdbc11.dll
        ocijdbc11.sym
        ociw32.dll
        ociw32.sym
        ojdbc5.jar
        ojdbc6.jar
        orannzsbb11.dll
        orannzsbb11.sym
        oraocci11.dll
        oraocci11.sym
        oraociei11.dll
        oraociei11.sym
        orasql11.dll
        orasql11.sym
        Orasqlplusic11.dll
        sqlplus.exe
        sqlplus.sym
        SQLPLUS_README
        uidrvci.exe
        uidrvci.sym
        xstreams.jar
        ```
    - Añadir C:\instantclient_11_2 al PATH: 
        ```
        1. Ejecutar el comando sysdm.cpl.
        2. Opciones avanzadas.
        3. Variables de entorno.
        4. Variables del sistema.
        5. Elegir de la lista la variable Path.
        6. Editar.
        7. En Valor de la variable, copiar al principio "C:\instantclient_11_2;" con punto y coma al final.
        ```
    - Probar la conexión: 
        ```
        sqlplus lucila/l@//192.168.1.18:1521/orcl
        ```
    - Descargar Microsoft Visual C++ Compiler for Python 2.7 del sitio de Microsoft https://www.microsoft.com/en-us/download/details.aspx?id=44266, e instalar.
    - Descargar Python del sitio oficial https://www.python.org, e instalar con todas las opciones activadas.
    - Instalar cx_Oracle: 
        ```
        pip install cx_oracle
        ```

* Instalar sqlAlchemy: 
        ```
        pip install sqlalchemy
        ```
