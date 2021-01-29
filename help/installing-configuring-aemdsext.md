---
title: Instalación y configuración de AEM Documento Security Extension for Microsoft Office
description: Este documento le guía a través de la instalación y configuración de Adobe Experience Manager Documento Security Extension 6.2 para Microsoft Office.
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
translation-type: tm+mt
source-git-commit: ac385c538cdd7d3bb4772b92ee7a94b003595f56
workflow-type: tm+mt
source-wordcount: '2796'
ht-degree: 0%

---


# Instalación y configuración de AEM Documento Security Extension for Microsoft Office{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

Este documento le guía a través de la instalación y configuración de Adobe Experience Manager Documento Security Extension for Microsoft Office.

Este documento incluye información sobre las siguientes tareas:

* Instalación de Documento Security Extension para Microsoft Office
* Preconfigurar el instalador para que señale al complemento LiveCycle Rights Management ES2 o posterior o Seguridad de Documento para AEM 6.0 Forms o posterior.
* Configuración de la aplicación automática de la directiva predeterminada

## Antes de realizar la instalación {#before-you-install}

Antes de instalar Documento Security Extension for Microsoft Office, asegúrese de que:

* Ha leído las [Notas de la versión](document-security-extension-release-notes.md).
* Microsoft Office está activado. El cuadro de diálogo de activación no aparece al abrir aplicaciones de Microsoft Office.
* Los últimos Service Packs para Microsoft Windows y Microsoft Office están instalados.
* Si va a instalar Documento Security para Microsoft Office en un idioma no admitido, abra la aplicación de Office al menos una vez.

>[!NOTE]
>
>No instale el software en una carpeta cuyo nombre contenga caracteres de byte de doble. Si lo hace, el menú Seguridad de Documento de AEM no aparece en Microsoft Office.

>[!NOTE]
>
>Se admite la instalación de una versión de 32 bits de la extensión de seguridad de Documento en un sistema operativo de 64 bits, pero no se admite el modo opuesto. No se puede instalar la versión de 64 bits de la extensión Documento Security para Microsoft Office en un sistema operativo de 32 bits.

### Deshabilitar McAfee VirusScan&amp; {#disable-mcafee-virusscan}

Para garantizar que las aplicaciones de Office se inicio sin problemas en un equipo que tenga instalado Documento Security Extension y McAfee VirusScan con la opción de protección de acceso activada, desactive la opción Protección contra desbordamientos de búfer en la consola de McAfee VirusScan.

### Desinstalar complementos de terceros {#uninstall-third-party-plug-ins}

AEM Documento Security Extension for Microsoft Office no admite complementos de terceros para aplicaciones de Microsoft Office. Dado que esta extensión entra en conflicto con los complementos de terceros, desinstale los complementos que no sean de Adobe para Microsoft Office antes de instalar Documento Security para Microsoft Office. Adobe no proporciona compatibilidad con aplicaciones de Documento Security para Microsoft Office con plug-ins de terceros instalados.

## Requisitos del sistema {#system-requirements}

### Documento Security Extension Client {#document-security-extension-client}

Asegúrese de que las siguientes configuraciones mínimas en las que desea instalar Documento Security Extension son:

* Versiones de 32 o 64 bits de Microsoft Windows 7 o Windows 10 en inglés, francés, alemán, japonés, italiano, español, portugués (Brasil), coreano, chino simplificado o chino tradicional.
   **Nota:También se espera que la extensión de seguridad de** *Documento para Microsoft Office funcione en dispositivos Microsoft Surface.*

* Versiones de 32 o 64 bits de Microsoft Office 2013, 2016, 2019 y aplicaciones de escritorio de Microsoft Office instaladas como parte de Office 365 en inglés, francés, alemán, japonés, italiano, español, portugués brasileño, coreano, chino simplificado o chino tradicional.

   **Nota**:  *AEM Documento Security Extension for Microsoft Office no admite complementos de terceros para aplicaciones de Microsoft Office. Dado que esta extensión puede entrar en conflicto con los complementos de terceros, los complementos que no sean de Adobe para las aplicaciones de Microsoft Office deben desinstalarse antes de instalar Documento Security Extension for Microsoft Office. Adobe no proporciona compatibilidad con las Extensiones de seguridad de Documento para aplicaciones de Microsoft Office con plug-ins de terceros instalados.*

* Procesador de 1,3 GHz o superior
* 2 GB de RAM
* 100 MB de espacio disponible en el disco duro

### :Seguridad de los documentos{#document-security}

Para utilizar Documento Security Extension, asegúrese de que puede conectarse a Adobe LiveCycle Rights Management ES2 y posterior o al complemento Documento Security para formularios AEM 6.0 o posterior.

## Instalación de Documento Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office}

Puede descargar el instalador desde la [página de descarga](download-installer.md). No puede personalizar el archivo ejecutable del instalador directamente, pero puede instalarse de forma interactiva o en modo silencioso. Para instalar el software, inicie sesión en Windows como administrador.

Hay instaladores independientes disponibles para las versiones de 32 y 64 bits de Microsoft Office. Para la versión de 32 bits de Microsoft Office, descargue DocumentSecurityExtensionforMicrosoftOffice.exe. Para la versión de 64 bits de Microsoft Office, descargue DocumentSecurityExtensionforMicrosoftOffice64.exe.

>[!NOTE]
>
>Este documento utiliza un archivo de instalación de 32 bits (DocumentSecurityExtensionforMicrosoftOffice.exe) para explicar varios comandos y opciones. Si utiliza la versión de 64 bits de Microsoft Office, utilice el archivo de instalación de 64 bits (DocumentSecurityExtensionforMicrosoftOffice64.exe) para realizar las operaciones que se enumeran en este documento.

### Instalar en modo silencioso {#install-in-silent-mode}

Utilice una utilidad de extracción de archivos, como WinZip, para extraer `DocumentSecurityExtensionforMicrosoftOffice.exe` del archivo de instalación. Abra el símbolo del sistema, vaya a la carpeta que contiene el archivo de configuración y escriba el siguiente texto:

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

El instalador también está disponible como archivo MSI, que se puede utilizar para la personalización.

### Instalar un archivo MSI en modo silencioso {#install-an-msi-file-in-silent-mode}

1. Utilice una utilidad de extracción de archivos, como WinZip, para extraer el archivo `DocumentSecurityExtensionforMicrosoftOffice.msi` del archivo ZIP.

1. Abra el símbolo del sistema, vaya a la carpeta que contiene el archivo MSI y escriba el siguiente texto:

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## Preconfiguración del instalador para conectarse a Documento Security {#preconfiguring-the-installer-to-connect-to-document-security}

Puede preconfigurar el programa de instalación de Documento Security Extension for Microsoft Office para que señale a un servidor de LiveCycle o AEM, de modo que los usuarios que instalen Documento Security Extension for Microsoft Office puedan utilizar las funciones sin necesidad de configurar una conexión. Como tal, los usuarios pueden abrir documentos protegidos sin necesidad de configuración. Sin embargo, no pueden proteger nuevos documentos hasta que configuren el cliente para que utilice un servidor en particular.

Los siguientes pasos describen cómo crear y configurar un archivo MSI. Este archivo MSI contiene los valores del Registro necesarios para preconfigurar el programa de instalación de Documento Security Extension for Microsoft Office en el LiveCycle o en el servidor AEM instalado en la empresa.

### Requisitos previos para personalizar el instalador {#prerequisites-for-customizing-the-installer}

Utilice el editor de la base de datos Orca para personalizar el instalador. Los siguientes pasos describen cómo crear un archivo MSI personalizado mediante la modificación de una copia del archivo de instalación MSI mediante el editor de la base de datos Orca. Orca está disponible como parte del SDK de Windows para Windows Server 2008 y .NET Framework 3.5. Para obtener más información sobre cómo editar los archivos del instalador de Microsoft Windows® mediante Orca, consulte [Soporte técnico de Microsoft](http://support.microsoft.com/kb/255905/EN-US/).

>[!NOTE]
>
>Se recomienda realizar una copia de seguridad completa de todos los archivos del instalador antes de crear el archivo MSI personalizado.

#### Instalar Orca {#install-orca}

1. Descargue el SDK de Windows para Windows Server 2008 y .NET Framework 3.5 desde [Centro de descargas de Microsoft](http://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=11310).
1. Haga clic con el botón doble en el archivo Orca.msi de la carpeta \Microsoft SDK\bin.

   También necesita la variante MSI del archivo del instalador. Póngase en contacto con el servicio de asistencia técnica de Adobe para recibir la versión más reciente del instalador MSI.

   >[!NOTE]
   >
   >Cierre siempre el archivo DocumentSecurityExtensionforMicrosoftOffice.msi antes de ejecutar el programa de instalación. No puede ejecutar el instalador si Orca está utilizando el archivo MSI.

### Crear y configurar el archivo MSI {#create-and-configure-the-msi-file}

1. Haga clic en **[!UICONTROL Inicio > Programas > Orca]**.

1. Haga clic en **[!UICONTROL Archivo > Abrir]** y luego busque el archivo `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Seleccione Propiedad en la lista de tablas (en el lado izquierdo).

1. Edite los siguientes valores de Nombre de clave según corresponda para la instalación empresarial de Seguridad de Rights Management o Documento.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nombre </strong><strong></strong><strong>de clave</strong></p> </td>
   <td><p><strong>Descripción</strong></p> </td>
   <td><p><strong>Valor predeterminado </strong><strong></strong><strong>de clave</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>Nombre para mostrar.</p> </td>
   <td><p>Servidor predeterminado</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>URL del servidor host.</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. Seleccione Registro en la lista de tablas (a la izquierda).

1. Edite el siguiente valor de nombre de clave.

   | **Nombre de clave** | **Descripción** | **Valor predeterminado de clave** |
   |---|---|---|
   | `IsDefault` | El servidor APS predeterminado. | Servidor predeterminado |

1. Guarde el archivo modificado en el mismo directorio que contiene el instalador MSI original.

   >[!NOTE]
   >
   >Una práctica habitual es utilizar el mismo nombre de archivo que el archivo MSI original (por ejemplo, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Configuración de la aplicación automática de una directiva predeterminada {#configuring-automatic-application-of-a-default-policy}

Como parte de la configuración, puede configurar la aplicación automática de una directiva predeterminada para que Documento Security Extension for Microsoft Office proteja todos los documentos guardados.

Puede especificar una de las siguientes opciones:

* Todos los documentos de Protect con una directiva predeterminada.
* Permite a los usuarios guardar de forma opcional un archivo en un formato no protegido cuando no pueden conectarse al servidor. Esta flexibilidad permite tener en cuenta los casos en los que los usuarios crean documentos mientras están desconectados de la red (por ejemplo, mientras se encuentran en un avión).

Después de habilitar la función de política de aplicación automática, el documento se protege con la directiva predeterminada en los siguientes casos:

* El usuario edita y guarda un documento recién creado
* El usuario edita y guarda un documento no protegido
* El usuario abre una aplicación que se abre con un documento predeterminado, edita y, a continuación, guarda el documento

### Configurar la función de política de aplicación automática en el archivo MSI  {#configure-the-auto-apply-policy-feature-in-the-msi-file}

Antes de comenzar, preconfigure el instalador para que señale a su LiveCycle o AEM servidor de formularios, tal como se describe anteriormente en este artículo.

1. Haga clic en **[!UICONTROL Inicio > Programas > Orca]**.

1. Haga clic en **[!UICONTROL Archivo > Abrir]** y luego busque el archivo `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Seleccione Propiedad en la lista de tablas (en el lado izquierdo).

1. Edite los siguientes valores de nombre de clave según corresponda para la instalación empresarial de Rights Management o Documento Security.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nombre de clave</strong></p> </td>
   <td><p><strong>Descripción</strong></p> </td>
   <td><p><strong>Valor predeterminado </strong><strong></strong><strong>de clave</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>Habilite o deshabilite la función de aplicación automática de directivas.</p> <p><code>1</code>: Habilitar</p> <p>0: Deshabilitar</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>GUID de directiva que se usará cuando se guarden nuevos documentos. Se aplica a la función de política de aplicación automática.</p> </td>
   <td><p>Id. de directiva hexadecimal como visible en el servidor RM</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>URL del servidor.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>Número de puerto del servidor.</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>Determina si se pueden crear documentos sin protección de seguridad de Documento si el cliente no puede ponerse en contacto con el servidor para proteger el documento la primera vez que lo guarda.</p> <p>1: Permitir guardar sin proteger </p> <p>0: Impedir la creación de nuevos documentos cuando el cliente no pueda ponerse en contacto con el servidor para guardar el documento.</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>`AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` es útil cuando desea recordar a los clientes que deben proteger todos los documentos sin forzarlos a hacerlo. También es útil cuando sabe que los usuarios crean documentos mientras están desconectados de la red. No desea impedir que creen y guarden documentos.

1. Guarde el archivo modificado en el mismo directorio que contiene el archivo MSI original.

   >[!NOTE]
   >
   >Una práctica habitual es utilizar el mismo nombre de archivo que el archivo MSI original (por ejemplo, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Habilitar la protección automática de nuevos documentos {#enabling-automatic-protection-of-new-documents}

El administrador puede habilitar la capacidad de proteger automáticamente cualquier documento que guarde un usuario. El administrador configura la función de política de aplicación automática en el programa de instalación de Documento Security Extension for Microsoft Office.

Si la política de aplicación automática está activada, todos los documentos que guarda el usuario se protegen con la directiva predeterminada. Esta acción se aplica en estas situaciones:

* Cuando un usuario crea un nuevo documento, lo edita y lo guarda.
* Cuando un usuario abre un documento no protegido, lo edita y lo guarda.

Para obtener información sobre la configuración de la política de aplicación automática, consulte [Configuración de una aplicación automática de la directiva predeterminada](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p).

## Habilitar la interfaz de usuario sin cinta {#enable-ribbon-less-user-interface}

Puede habilitar/deshabilitar la interfaz de usuario sin cintas modificando la configuración en el Registro de Windows. Realice los siguientes pasos para actualizar el Registro y habilitar la interfaz de usuario de cinta menos:

1. Realice una copia de seguridad del Registro de Windows antes de realizar cambios en él. Para obtener instrucciones detalladas, consulte [Cómo modificar el Registro de Windows](https://support.microsoft.com/en-us/kb/136393).
1. En el Editor del Registro, vaya a HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 o HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Cree un nuevo valor Dword (32 bits) denominado **HidePluginUI**.

1. Establezca el valor de la propiedad **HidePluginUI **en 1 para habilitar la interfaz de usuario sin cintas.

1. Cierre el Editor del Registro.

## Habilitar marca de agua para imprimir en Microsoft Excel {#enable-watermark-for-printing-in-microsoft-excel}

Puede cambiar la configuración del Registro de Windows para que las marcas de agua dinámicas coexistan con los encabezados y pies de página existentes. La configuración del Registro hace que la marca de agua solo esté disponible durante la impresión. Realice los siguientes pasos para actualizar el Registro y activar las marcas de agua durante la impresión:

1. Realice una copia de seguridad del Registro de Windows antes de realizar cambios en él. Para obtener instrucciones detalladas, consulte [Cómo modificar el Registro de Windows](https://support.microsoft.com/en-us/kb/136393).
1. En el Editor del Registro, vaya a HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 o HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Cree una nueva clave de Registro **WatermarkMode**.
1. En la clave del Registro WatermarkMode, cree un DWORD **WatermarkMode** y establezca el valor de DWORD **WatermarkMode** en **1**.

1. Cierre el editor del Registro.

>[!NOTE]
>
>En el Explorador de Windows, puede utilizar el menú Archivo o el menú contextual para crear un Documento de Microsoft Excel. Para los documentos creados con métodos especificados, la fecha de impresión no se puede recuperar ni cambiar. Es una limitación de Microsoft Excel. AEM marcas de agua de seguridad de Documento dependen de la fecha de impresión del documento. Así, para esos documentos, la marca de agua se vuelve a una fecha anterior. Además, los encabezados y pies de página tampoco se conservan.

## Añadir una página de portada personalizada en un documento {#coverpage}

Un usuario puede intentar abrir el documento protegido en un equipo que no tenga instalado un complemento de seguridad de Documento AEM para Microsoft Office. Estas máquinas no pueden abrir el documento. En estos equipos, puede mostrar una portada con instrucciones para descargar AEM complemento de seguridad de Documento para Microsoft Office y otra información.

### Antes de configurar una portada {#before-you-configure-a-cover-page}

* Realice una copia de seguridad del archivo CommonResources.dll. La ruta predeterminada es:

   * **(Para oficinas de 32 bits en equipos de 32 bits)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(Para oficinas de 32 bits en equipos de 64 bits)** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(Para oficinas de 64 bits en equipos de 64 bits)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Asegúrese de tener instalado Microsoft Visual Studio 2008 o posterior. También puede utilizar cualquier otra utilidad para editar los archivos DLL.
* Extraiga el archivo templates.zip. El archivo contiene plantillas .xlsx, .docx y .pptx para la página de portada. Utilice solo las plantillas proporcionadas para los tipos de archivo .xlsx, .docx y .pptx. Puede crear sus propias plantillas para otros tipos de archivo. Personalice las plantillas para incluir mensajes e instrucciones personalizados. Puede encontrar template.zip en:

[Obtener archivo](assets/templates.zip)

### Estructura del archivo CommonResources.dll {#structure-of-the-commonresources-dll-file}

El archivo CommonResources.dll contiene información sobre las plantillas de recursos. Contiene dos identificadores de nombre TEMPLATE_FILE y RT_MANIFEST. Para habilitar una portada personalizada, se modifica el identificador del nombre TEMPLATE_FILE. El identificador del nombre TEMPLATE_FILE tiene seis recursos:

<table>
 <tbody>
  <tr>
   <td><p><strong>Medio</strong></p> </td>
   <td><p><strong>Representa </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### Configure la plantilla como una portada {#configure-the-template-as-a-cover-page}

1. Abra Microsoft Visual Studio. Explore y abra el archivo CommonResources.dll para editarlo.

   >[!NOTE]
   >
   >Si el archivo no aparece en la ventana Explorador de soluciones, vuelva a abrirlo con la opción Abrir con. Seleccione el editor de recursos como editor.

1. En la ventana Explorador de soluciones, expanda el directorio TEMPLATE_FILE y elimine los recursos 101.

1. Añada los recursos:

   1. Con un proyecto seleccionado en el Explorador de soluciones, en el menú Proyecto, haga clic en Propiedades.
   1. Seleccione la ficha Recursos.
   1. En la barra de herramientas del Diseñador de recursos, elija Añadir recurso y haga clic en la flecha. Para el tipo de recurso, seleccione TEMPLATE_FILE y haga clic en importar.
   1. En el cuadro de diálogo Añadir archivo existente a recursos, busque el archivo Resource.xlsx y haga clic en Abrir. El archivo se agrega al directorio TEMPLATE_FILE.

   >[!NOTE]
   >
   >Asegúrese de que la configuración de idioma es correcta. Elimine el recurso con lenguaje neutro.

1. Repita los pasos 2 y 3 para todos los tipos de recursos.

   >[!NOTE]
   >
   >No elimine ni agregue tipos de recursos en orden aleatorio. Después de 101, configure 102, etc.

### Empaquete el archivo CommonResources.dll personalizado con el instalador de AEM extensión de seguridad de Documento para Microsoft Office {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

Puede personalizar el archivo CommonResources.dll para incluir la adición de una portada personalizada. Después de personalizar el archivo, puede reemplazar manualmente el archivo original por el archivo personalizado en todas las estaciones de trabajo o puede elegir un método automatizado para reemplazar el archivo.

En un entorno grande, es difícil y tedioso reemplazar manualmente el `CommonResources.dll file` predeterminado por un archivo `CommonResources.dll` personalizado. Puede utilizar una herramienta de autoextracción y empaquetado (por ejemplo, WinZip Self-Extractor) para empaquetar el archivo CommonResources.dll personalizado con AEM programa de instalación de Documento Security Extension for Microsoft Office. Más adelante, puede distribuir el instalador personalizado a toda la estación de trabajo. Este método reduce el tiempo necesario para reemplazar el archivo predeterminado `CommonResources.dll` por un archivo personalizado. También garantiza que toda la estación de trabajo tenga el archivo CommonResources.dll requerido. La herramienta de autoextracción y empaquetado es sólo uno de los muchos métodos posibles para reemplazar automáticamente un archivo. Puede elegir cualquier método adecuado para su entorno.

Puede realizar los siguientes pasos para empaquetar el archivo `CommonResources.dll`personalizado con el instalador de AEM extensión de seguridad de Documento para Microsoft Office:

1. Instale una herramienta de autoextractor y empaquetador. Por ejemplo, WinZip Self-Extractor.
1. Cree una nueva carpeta. Por ejemplo, YOUR_FOLDER_NAME
1. Coloque el instalador original de AEM extensión de seguridad de Documento y el archivo CommonResources.dll personalizado en la carpeta recién creada.
1. Cree un archivo por lotes en la carpeta. Por ejemplo, YOUR_FOLDER_NAME\Installer.bat
1. Abra el archivo por lotes para editarlo y agregue el siguiente código al archivo por lotes:

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   Si está utilizando cualquier otra versión de LiveCycle o AEM Forms en JEE, aparte de LiveCycle Rights Management ES 4 y versión 11.0.0, sustituya la ruta de la clave del Registro de la siguiente manera:

   * (Livecycle Rights Management ES2 y versión 9.0): *HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * (Livecycle Rights Management ES3 y versión 10.0)
   * (Livecycle Rights Management ES4 y versión 11.0) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (AEM 6.0 Forms en JEE y versiones posteriores) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. En el código anterior, reemplace todas las instancias de YOUR_FOLDER_NAME por el nombre de la carpeta que creó en el paso 2.
1. **(Para AEM extensión Seguridad de Documento para el programa de instalación de Microsoft Office solo con extensión .exe)** Reemplace la siguiente línea de código:

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
con

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. Guarde y cierre el archivo por lotes.
1. Utilice una herramienta de autoextracción y empaquetado para empaquetar la carpeta que contiene el archivo CommonResources.dll personalizado, el instalador original de AEM extensión de seguridad de Documento para Microsoft Office y el archivo por lotes.

   >[!NOTE]
   >
   >Asegúrese de que el paquete de extracción automática está configurado para ejecutarse como administrador y automáticamente
   >ejecuta el archivo por lotes al completar la extracción.

Ahora, el instalador de extracción automática de AEM extensión de seguridad de Documento para Microsoft Office empaqueta el archivo CommonResources.dll personalizado y está listo para su distribución.