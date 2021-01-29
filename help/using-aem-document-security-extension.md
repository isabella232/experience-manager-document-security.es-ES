---
title: Uso de AEM Documento Security Extension for Microsoft Office
description: Puede controlar el uso que hacen los destinatarios de los archivos protegidos por políticas, independientemente de la amplitud de su distribución. El documento explica cómo proteger archivos y cómo trabajar con archivos protegidos.
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
translation-type: tm+mt
source-git-commit: 21288f7f1c8f786d3c4c363986226038bdb03e26
workflow-type: tm+mt
source-wordcount: '6270'
ht-degree: 0%

---


# Uso de AEM Documento Security Extension for Microsoft Office{#using-aem-document-security-extension-for-microsoft-office}

## Archivos de Protect con AEM Documento Security Extension {#usingaemdocumentsecurityextensiontoprotectfiles}

Puede controlar el uso que hacen los destinatarios de los archivos protegidos por políticas, independientemente de la amplitud de su distribución.

Con Documento Security Extension for Microsoft Office, puede realizar estas tareas:

* Configurar la conexión a Documento Security
* Aplicar una política a un archivo
* Abrir las páginas web de Documento Security para crear y administrar políticas de usuario
* Eliminar la protección de una política de un archivo
* Cambiar la política aplicada a un archivo
* Abra las páginas web de Documento Security para anular el acceso a los archivos o cambiar la política del archivo
* Abrir las páginas web de Documento Security para vista del historial de auditoría del archivo

### Conectar con un servidor de seguridad de Documento {#connect-to-a-document-security-server}

Si desea aplicar políticas a los archivos, debe configurar los parámetros de conexión de Seguridad de Documento. Según la instalación de Documento Security Extension for Microsoft Office, es posible que ya tenga la configuración de conexión predeterminada. Puede agregar la configuración de conexión para una o varias instancias de Documento Security. Puede obtener información del servidor del administrador de seguridad de Documento.

Debe configurar el servidor que desea utilizar para proteger archivos o administrar los archivos protegidos como servidor predeterminado. Al aplicar una política a un archivo nuevo o abrir las páginas web de Documento Security, Documento Security Extension for Microsoft Office se conecta al servidor predeterminado. Si protege los archivos con más de una instancia de Documento Security, debe cambiar la configuración predeterminada del servidor al cambiar entre servidores. Puede abrir archivos protegidos por cualquier instancia de Documento Security siempre y cuando tenga autorización para abrir el archivo.

Si el servidor de seguridad de Documento utiliza la autenticación basada en certificados, deberá instalar el certificado que recibió en el equipo local. Se le solicitará que elija la autenticación de certificado y proporcione el certificado que desea utilizar para la autenticación.

Después de configurar los parámetros de conexión para una instancia de Documento Security en una aplicación de Microsoft Office, se configura para todos los formatos de Word, Excel y PowerPoint.

#### Instalar el certificado del lado del cliente {#install-the-client-side-certificate}

Si necesita acceder a las páginas web de Documento Security mediante autenticación mediante certificado o autenticación bidireccional, recibirá el certificado que debe instalar en su equipo local. Recibirá un archivo de certificado (archivo .PFX o .P12) y su contraseña.

1. Guarde el archivo de certificado en el equipo local.
1. Haga clic con el botón doble en el archivo de certificado para abrir el Asistente de importación de certificado y haga clic en **Siguiente**.
1. Haga clic en **Siguiente** si el archivo de certificado aparece enumerado en el cuadro de nombre de archivo. Haga clic en **Examinar** si desea encontrar otro certificado.
1. Introduzca la contraseña que ha recibido y haga clic en **Siguiente**.
1. En el cuadro de diálogo Almacén de certificados, seleccione Colocar todos los certificados en el siguiente almacén y haga clic en **Examinar**.
1. En el cuadro de diálogo Seleccionar almacén de certificados, seleccione Personal, haga clic en **Aceptar**, haga clic en **Siguiente** y, a continuación, haga clic en **Finalizar**.

#### Configurar la configuración de conexión {#configure-connection-settings}

1. En Documento Security Extension for Microsoft Office 2010 y Office 2013, en la ficha **Seguridad de Documento**, seleccione **Elegir servidor**.
1. Haga clic en **Nuevo** para crear una nueva configuración de conexión o seleccione una conexión existente y haga clic en **Editar**.
1. Escriba un nombre para la conexión en el cuadro **Nombre**. Puede usar cualquier nombre.
1. Escriba la dirección del servidor en el cuadro **Dirección del servidor**.
1. Escriba el puerto del servidor en el cuadro **Puerto**.
1. (Opcional) Si desea recordar su nombre de usuario y contraseña, seleccione **Recordar contraseña en este equipo** y escriba su nombre de usuario y contraseña en los cuadros correspondientes. Se recomienda no seleccionar esta opción si otras personas pueden tener acceso al equipo.
1. Haga clic en **Conectar a este servidor**. Documento Security Extension for Microsoft Office intenta conectarse al servidor especificado. Según el tipo de autenticación especificado, realice una de las siguientes acciones:

   **Nombre de usuario y contraseña**

   Introduzca el nombre de usuario y la contraseña que ha recibido del administrador de Documento Security.

   **Autenticación de certificado**

   Elija esta opción para seleccionar el certificado que recibió e instaló en su almacén de certificados personal.

   Si solo se configura un tipo de autenticación en Seguridad de Documento, solo aparecerá esa opción.

>[!NOTE]
>
>Si no puede conectar con el servidor, intente abrir las páginas web de seguridad de Documento en Internet Explorer. Si no puede conectar con el servidor mediante Internet Explorer o si aparece una advertencia sobre el certificado del servidor, Documento Security Extension for Microsoft Office no podrá conectarse al servidor. Póngase en contacto con el administrador del servidor para obtener ayuda.

>[!NOTE]
>
>Si no puede conectarse a Documento Security, aparece un mensaje que indica que &quot;El nombre de usuario y la contraseña son incorrectos, compruebe la configuración e inténtelo de nuevo&quot;. Este mensaje puede aparecer si no se puede conectar por otro motivo. Si se está conectando al servidor por primera vez, compruebe que ha establecido correctamente el nombre y el puerto del servidor.

#### Especifique el servidor predeterminado {#specify-the-default-server}

1. Haga lo siguiente:

   * En Documento Security Extension for Microsoft Office 2010 y Office 2013 en la ficha **Seguridad de Documento**, seleccione **Elegir servidor**.

1. Seleccione un servidor para especificar como predeterminado y haga clic en **Establecer predeterminado**. Aparece una estrella junto al servidor predeterminado.

### Uso de proveedores de autenticación de terceros {#using-third-party-authentication-providers}

Puede utilizar proveedores de autenticación de terceros con AEM Forms Documento Security. Estos proveedores de autenticación le ayudan a agregar una capa de acceso adicional a los documentos protegidos. AEM Forms Documento Security admite los siguientes flujos de trabajo de autenticación extendidos:

* Autenticación extendida mediante la URL de AEM Forms predeterminada
* Autenticación extendida mediante una dirección URL personalizada
* Flujo de trabajo de autenticación ampliado predeterminado con proveedores de identidad de terceros configurados en AEM Forms en el servidor JEE
* Flujo de trabajo de autenticación extendido personalizado con proveedores de identidad de terceros configurados en AEM Forms en el servidor JEE
* Autenticación extendida mediante una página personalizada para enumerar autenticaciones SAML

#### Autenticación extendida mediante la dirección URL predeterminada de AEM Forms {#extended-authentication-using-default-aem-forms-url}

Puede utilizar la URL de AEM Forms predeterminada para la autenticación extendida. La página de aterrizaje predeterminada contiene la marca de Adobe. Además, la configuración predeterminada de AEM Forms se usa al usar la dirección URL predeterminada de AEM Forms para la autenticación extendida.

Realice los siguientes pasos para habilitar la autenticación extendida con la dirección URL de aterrizaje de Adobe predeterminada:

1. Abra la interfaz de usuario del administrador de AEM Forms.
1. Vaya a Servicios > Seguridad de Documento > Configuración > Configuración del servidor.
1. Active la opción Permitir autenticación extendida.
1. Especifique la URL predeterminada de aterrizaje de autenticación extendida de la dirección URL. La dirección URL predeterminada es http://localhost:8080/edc/extendedauthentication/welcome.jsp.

   Haga clic en **[!UICONTROL Guardar]**.

   >[!NOTE]
   >
   >Utilice un nombre de host completo en la dirección URL. Se recomienda utilizar el protocolo HTTPS.

   Ahora, la seguridad de AEM Forms documento está configurada para utilizar la autenticación extendida con la dirección URL de aterrizaje de AEM Forms predeterminada.

   ![](assets/third-party-authentication.png)

#### Autenticación extendida con una dirección URL de aterrizaje personalizada {#extended-authentication-with-a-custom-landing-url}

Puede utilizar una dirección URL personalizada para la autenticación extendida. Proporciona la flexibilidad de mostrar una página de autenticación personalizada con marca personalizada. Por ejemplo, la marca de su organización.

Puede empaquetar la página de autenticación personalizada en un archivo de guerra e implementar el archivo de guerra en el servidor de AEM Forms. El archivo de guerra contiene una lógica completa para aceptar las credenciales de usuario y autenticarse con el servidor de AEM Forms. AEM Forms Documento Security tiene los siguientes requisitos para la página de autenticación personalizada:

* La página de autenticación debe enviar el nombre de usuario como j_username y la contraseña como j_password. La página también debe enviar source_url y login_url como parámetros ocultos.
* Si la autenticación se realiza correctamente, la página debe cerrarse automáticamente.

Realice los siguientes pasos para habilitar la autenticación ampliada con una dirección URL de aterrizaje personalizada:

1. Implemente el archivo de guerra de autenticación personalizada en el servidor de AEM Forms.
1. Abra la interfaz de usuario del administrador de AEM Forms.
1. Vaya a Servicios > Seguridad de Documento > Configuración > Configuración del servidor.
1. Active la opción Permitir autenticación extendida y especifique la URL de aterrizaje de autenticación extendida personalizada.
1. Añada las siguientes entradas al archivo config.xml en el nodo SSO después de la entrada *&lt;node name=&quot;AllowedUrls&quot;>*:

   >[!NOTE]
   >
   >&lt;entry>!!discoiqbr!!&lt;entry>!!discoiqbr!!&lt;entry>!!discoiqbr!!

   Para obtener información paso a paso sobre la actualización del archivo config.xml, consulte [Edición manual del archivo de configuración de seguridad de documento](https://helpx.adobe.com/aem-forms/6-3/admin-help/configuring-client-server-options.html#manually_editing_the_document_security_configuration_file).

   Ahora, la seguridad de AEM Forms documento está configurada para utilizar la autenticación extendida con una dirección URL de aterrizaje personalizada

#### Flujo de trabajo de autenticación extendido predeterminado con proveedores de identidad de terceros configurados en el servidor de AEM Forms {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

La autenticación extendida puede utilizar diferentes tipos de autenticación disponibles en el servidor de AEM Forms. Por ejemplo, SAML, [Más ejemplos].

Nota: Si los proveedores de SAML están configurados en el servidor de AEM Forms, antes de mostrar la dirección URL de aterrizaje se muestra una página que contiene todos los proveedores de identidad configurados para autenticaciones SAML.

La siguiente pantalla se muestra cuando se abre un documento protegido en Acrobat.

#### Flujo de trabajo de autenticación extendido personalizado cuando los proveedores SAML están configurados en el servidor de AEM Forms {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

Si los proveedores de SAML están configurados en el servidor de AEM Forms, antes de mostrar la dirección URL de aterrizaje se muestra una página que contiene todos los proveedores de identidad configurados para autenticaciones SAML.

Los requisitos para configurar un flujo de trabajo de autenticación extendido personalizado cuando los proveedores SAML están configurados en el servidor de AEM Forms son:

* Las autenticaciones SAML están configuradas en el servidor de AEM Forms
* La guerra personalizada, que contiene una página de autenticación personalizada y una lógica completa para aceptar las credenciales de usuario y autenticarse con el servidor de AEM Forms, se implementa en el servidor de AEM Forms.

#### Uso de la página personalizada para enumerar las autenticaciones de SAML {#using-custom-page-for-listing-saml-authentications}

También puede mostrar una página personalizada para incluir todos los proveedores de autenticación configurados en el servidor de AEM Forms. Realice los siguientes pasos para crear una página de este tipo:

1. Empaquete la página de autenticación personalizada en un archivo de guerra e implemente el archivo de guerra en el servidor de AEM Forms. El archivo de guerra contiene una lógica completa para aceptar las credenciales de usuario y autenticarse con el servidor de AEM Forms.
1. Abra la interfaz de usuario de administración de AEM Forms y vaya a **[!UICONTROL Configuración]** **[!UICONTROL Administración de usuarios]** > **[!UICONTROL Configuración]** > **[!UICONTROL Configuración de Proveedor de servicio de SAML]**.
1. Añada lo siguiente en el campo Propiedades personalizadas y haga clic en **[!UICONTROL Guardar]**.

   *saml.sp.disdiscover.url=/demoJSP/saml_discovery.jsp*

   Ahora, la seguridad de AEM Forms documento está configurada para mostrar una página personalizada que contenga todos los proveedores de autenticación configurados.

### Obtener una cuenta de usuario {#obtaining-a-user-account}

Si todavía no tiene una cuenta de Documento Security, Documento Security puede iniciar el proceso de registro cuando se produzcan estos eventos:

* Un usuario de Documento Security que desea enviarle un archivo protegido por una política le agrega a una política.
* El administrador de seguridad de Documento crea una cuenta para usted.

Después de registrarse y activar la cuenta, puede utilizar los archivos protegidos por políticas que recibió autorización para utilizar mediante una política.

>[!NOTE]
Si recibe un archivo protegido por una política y no tiene una cuenta de Documento Security, o si recibe una invitación para registrarse, póngase en contacto con la persona que le envió el archivo para obtener ayuda.

Si recibe una invitación por correo electrónico de Documento Security para registrarse, puede hacerlo utilizando la URL del mensaje de correo electrónico para abrir la página de registro en línea. Después de registrarse, recibirá un segundo aviso sobre la activación de su cuenta.

#### Obtener una cuenta de usuario externa {#obtain-an-external-user-account}

1. Abra el correo electrónico de registro de Documento Security. La dirección URL que contiene el mensaje es un vínculo a la página de registro de usuarios externos de Documento Security. Si no recibe un mensaje de registro, póngase en contacto con la persona que le envió el archivo para obtener ayuda.
1. Haga clic en la dirección URL o cópiela y péguela en el explorador.
1. Escriba su nombre, organización y contraseña en los cuadros correspondientes. La contraseña puede ser cualquier combinación de ocho caracteres.

   >[!NOTE]
   Asegúrese de elegir una contraseña que sea fácil de recordar; no hay ningún método disponible para buscar contraseñas olvidadas.

1. Haga clic en **Registrar**. Aparece un mensaje que le informa de que debe buscar un mensaje de correo electrónico de activación en su correo electrónico.
1. Abra el correo electrónico de confirmación de registro de Documento Security.
1. Haga clic en la dirección URL que aparece en el mensaje.
1. Haga clic en el vínculo a la página Inicio de sesión.
1. En el cuadro **Nombre de usuario**, escriba la dirección de correo electrónico en la que se registró con Documento Security. Esta dirección de correo electrónico es el nombre de usuario predeterminado de Documento Security.
1. En el cuadro **Contraseña**, escriba la contraseña que creó al registrarse.
1. Haga clic en **Inicio de sesión**.

### Crear y administrar políticas {#creating-and-managing-policies}

Si tiene permiso del administrador de seguridad de Documento, puede crear políticas para aplicarlas a sus propios archivos en la página de políticas de las páginas web de seguridad de Documento.

Algunos de los ajustes de directiva disponibles para crear políticas en las páginas web de seguridad de Documento no son compatibles con los archivos de Word, Excel y PowerPoint. Las siguientes tablas describen cómo los permisos de directivas se asignan a las funciones de Word, Excel y PowerPoint.

<table>
 <thead>
  <tr>
   <th><p>Permisos   </p></th>
   <th><p>Compatibilidad con Word, Excel y PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Imprimir &gt; No permitido</p></td>
   <td><p>No se permite imprimir el archivo.</p></td>
  </tr>
  <tr>
   <td><p>Imprimir &gt; Permitido</p></td>
   <td><p>Se permite imprimir el archivo.</p><p><strong>Nota</strong>:  <i>Si una política concede el permiso de copia pero no el permiso de impresión, se puede imprimir el contenido copiado en otro archivo.</i></p></td>
  </tr>
  <tr>
   <td><p>Print &gt; Low Res. Sólo</p></td>
   <td><p>No aplicable.</p></td>
  </tr>
  <tr>
   <td><p>Change &gt; Any</p></td>
   <td><p>El archivo se puede cambiar.</p><p>Cuando no se concede este permiso, no se pueden modificar los archivos protegidos de Word y Excel. Puede modificar los archivos de PowerPoint, pero no puede guardar los cambios ni las presentaciones de diapositivas de vista para los archivos modificados.</p></td>
  </tr>
  <tr>
   <td><p>Cambio &gt; No permitido</p></td>
   <td><p>Los usuarios no pueden modificar los archivos protegidos.</p></td>
  </tr>
  <tr>
   <td><p>Cambiar &gt; Modificar páginas</p></td>
   <td><p>No aplicable.</p><p>Incluye la inserción, eliminación y rotación de páginas.</p></td>
  </tr>
  <tr>
   <td><p>Cambiar &gt; Fill &amp; Sign</p></td>
   <td><p>No aplicable.</p></td>
  </tr>
  <tr>
   <td><p>Sin conexión</p></td>
   <td><p>El archivo se puede abrir sin conexión.</p></td>
  </tr>
  <tr>
   <td><p>Copiar</p></td>
   <td><p>El contenido del archivo se puede copiar en otros archivos.</p></td>
  </tr>
  <tr>
   <td><p>Reader de pantalla </p></td>
   <td><p>Los lectores de pantalla (dispositivos para usuarios con deficiencias visuales) pueden leer el contenido del archivo.</p></td>
  </tr>
  <tr>
   <td><p>Validez del permiso</p></td>
   <td><p>Compatible.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Configuración general</p></th>
   <th><p>Compatibilidad con Word, Excel y PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Período de validez</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Documento de auditoría</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Período de arrendamiento sin conexión automático</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Proveedores de autorización externa</p></td>
   <td><p>Compatible.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Configuración avanzada</p></th>
   <th><p>Compatibilidad con Word, Excel y PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Marcas de agua dinámicas</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Complementos de certificación</p></td>
   <td><p>No aplicable.</p></td>
  </tr>
  <tr>
   <td><p>Algoritmo de codificación y longitud de clave </p></td>
   <td><p>Todas las opciones son compatibles.</p></td>
  </tr>
  <tr>
   <td><p>Restricción de documento</p></td>
   <td><p>Todo el contenido del archivo siempre se cifra independientemente de la configuración de la directiva.</p></td>
  </tr>
  <tr>
   <td><p>Mensaje de error de acceso denegado</p></td>
   <td><p>Compatible.</p></td>
  </tr>
 </tbody>
</table>

Para obtener más información sobre la creación y administración de políticas, consulte [Ayuda para el usuario final de seguridad de Documento](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

### Aplicar directivas {#applying-policies}

Puede aplicar cualquier política disponible a un archivo, incluidas las políticas que haya creado y las que formen parte de conjuntos de políticas a los que tenga acceso. Antes de aplicar una política, debe guardar el archivo.

Después de aplicar una política, se agrega a la lista Utilizada recientemente en el menú Seguridad de Documento de AEM para facilitar la aplicación de las políticas que se utilizan con más frecuencia. Si utiliza más de una instancia de Documento Security, la lista Utilizado recientemente muestra las directivas únicamente para el servidor al que está conectado actualmente o para el servidor predeterminado si aún no ha iniciado sesión en una instancia de Documento Security.

>[!NOTE]
Las políticas solo se pueden aplicar a archivos de documento de Word (.doc, también.docx y .docm en Microsoft Office 2010 y 2013), archivos de libros de Excel (.xls, también .xlsx y .xlsm en Microsoft Office 2010 y 2013) y archivos de presentación de PowerPoint (.ppt, también .pptx y .pptm en Microsoft Office 2010 y 2013). No puede aplicar políticas a archivos de plantilla de Word (.dot), archivos de plantilla de Excel (.xlt) ni archivos de plantilla de diseño de PowerPoint (.pot).

#### Aplicar una directiva {#apply-a-policy}

1. En Documento Security Extension for Microsoft Office 2010 y 2013, en la ficha **Seguridad de Documento**, seleccione **Seguridad > Elegir directiva**.

   Si ha elegido el nombre de usuario y la contraseña como método de autenticación en el servidor y aún no ha proporcionado la información de inicio de sesión para Documento Security, aparecerá un cuadro de diálogo en el que se solicitará su nombre de usuario y contraseña.

1. Seleccione una directiva en la lista y haga clic en **Aplicar**.
1. Guarde el archivo.

#### Aplicar una directiva {#apply-a-recently-used-policy} usada recientemente

1. En Documento Security Extension for Microsoft Office 2010 y 2013, en la ficha **Seguridad de Documento**, seleccione **Proteger > ***[Nombre de directiva]*.
1. Guarde el archivo.

## Trabajar con archivos protegidos por políticas {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

Los archivos protegidos por políticas contienen propiedad intelectual propiedad del editor del archivo y protegidos por Documento Security.

Puede utilizar archivos protegidos por políticas tanto si es interno como externo a la organización del editor de archivos. Para abrir archivos protegidos por políticas, Documento Security debe reconocerle, ya sea mediante la inclusión en un LDAP vinculado o una lista de Active Directory, agregándolo como usuario local para LiveCycles o formularios AEM en JEE, o mediante el registro en Documento Security después de ser invitado como usuario.

Si recibe un archivo protegido por una política y no tiene una cuenta de Documento Security, o si recibe una invitación para registrarse, póngase en contacto con la persona que le envió el archivo para obtener ayuda.

### Uso de archivos protegidos por políticas en Microsoft Office {#working-with-policy-protected-files-in-microsoft-office}

Documento Security Extension for Microsoft Office restringe ciertas funciones de Word, Excel y PowerPoint para proteger la propiedad intelectual del editor del archivo. Si no tiene permiso para cambiar el archivo, no puede guardar las modificaciones.

Si está trabajando con un archivo protegido por una política, es posible que algunas características del producto no estén disponibles o que no funcionen como de costumbre. Si también tiene un archivo no protegido abierto, la mayoría de las funciones se activan para el archivo no protegido, excepto las que permiten importar o copiar contenido de un archivo protegido por una política para el que no tiene permisos de copia o exportación.

>[!NOTE]
Cuando se utilizan aplicaciones de Office compatibles con Documento Security Extension, se recomienda desactivar la configuración DEP de Windows. Además, para garantizar que las aplicaciones de Office se inicio sin problemas en un equipo que tenga instalado Documento Security Extension y McAfee VirusScan con la opción de protección de acceso activada, desactive la opción Protección contra desbordamientos de búfer en la consola de McAfee VirusScan.

Si una función no está disponible, el nombre del comando en el menú y el botón de barra de herramientas relacionado no estarán disponibles. En Documento Security Extension for Microsoft Office, cuando pasa el puntero del ratón sobre el comando o el botón, una información de objeto indica que Documento Security ha bloqueado el comando.

### Abrir archivos protegidos por políticas {#opening-policy-protected-files}

Puede abrir archivos protegidos por políticas utilizando los mismos métodos que utiliza para abrir cualquier otro archivo. Si no ha iniciado sesión en Documento Security, se le pedirá que lo haga a menos que no esté conectado a Internet y pueda abrir el archivo sin conexión. Si cancela el proceso de inicio de sesión, se deniega el acceso.

Si no tiene permiso para abrir el archivo, se le informará de que se ha denegado el acceso. Si se han revocado los privilegios de acceso a archivos, también se le puede dirigir a una versión actualizada del archivo si hay uno disponible. Si no puede abrir un archivo protegido por una política, póngase en contacto con el editor de archivos para obtener ayuda adicional.

Cuando se abre un archivo protegido, el texto de la barra de título que sigue al nombre del archivo indica que el archivo está protegido por AEM seguridad de Documento.

Al abrir un documento protegido en Documento Security Extension for Microsoft Office desde SharePoint Server, asegúrese de que esté abierto el programa de Microsoft Office asociado al tipo de archivo, como Microsoft Word, Microsoft Excel o Microsoft PowerPoint. Si intenta abrir el archivo sin abrir la aplicación asociada, es posible que el documento no se abra y se muestre un mensaje de error que indique que debe instalar el complemento aplicable. Además de abrir la aplicación requerida, se recomienda borrar la carpeta de la memoria caché antes de abrir un documento protegido en Documento Security Extension for Microsoft Office desde SharePoint Server. Además, cuando se abre un documento protegido desde SharePoint Server, todos los permisos del documento se desactivan, independientemente de la política que se haya aplicado.

Según el método de autenticación implementado en Documento Security, se le puede pedir que elija el método de autenticación al abrir un documento protegido. Si Documento Security admite más de un método de autenticación, se le presentarán las opciones de autenticación. Por ejemplo, si Documento Security Server proporciona autenticación de nombre de usuario/contraseña y de certificado, puede elegir el método de autenticación adecuado. Si la autenticación basada en certificados está habilitada, se le pedirá que utilice el certificado que ha recibido e instalado.

La experiencia del usuario al abrir archivos protegidos depende de la configuración de autenticación mutua en el servidor. Si solo hay un certificado de cliente válido instalado, no aparece ningún cuadro de diálogo de autenticación y los archivos se abren correctamente. Sin embargo, si hay varios certificados de cliente instalados en un equipo, aparece un cuadro de diálogo de autenticación. El usuario debe elegir un certificado válido para abrir el archivo protegido.

### Quitando protección de políticas de un archivo {#removing-policy-protection-from-a-file}

Si está autorizado, puede eliminar la protección de políticas de los archivos protegidos. Si lo hace, Documento Security dejará de proteger el archivo.

1. En Documento Security Extension for Microsoft Office 2010 y 2013, en la ficha **Seguridad de Documento**, seleccione **Quitar**.

   Si todavía no ha proporcionado la información de inicio de sesión para Documento Security, aparecerá un cuadro de diálogo en el que se solicitará su nombre de usuario y contraseña.

>[!NOTE]
Si no puede quitar una política de un archivo protegido por usted, póngase en contacto con un administrador de seguridad de Documento.

### Visualización de la configuración de seguridad {#viewing-security-settings}

Puede vista los permisos que tiene para imprimir, copiar, cambiar y acceder al archivo sin conexión, junto con el período de validez del archivo.

En Documento Security Extension for Microsoft Office 2010, el grupo Estado de seguridad de la ficha Seguridad de Documento muestra sus permisos para el archivo.

Haga lo siguiente:

* En Documento Security Extension for Microsoft Office 2010 y 2013, en la ficha **Seguridad de Documento**, en el grupo **Estado de seguridad**, haga clic en cualquier elemento.

### Guardar documentos cuando la política de aplicación automática está habilitada {#saving-documents-when-auto-apply-policy-is-enabled}

Si el administrador ha habilitado la funcionalidad de política de aplicación automática, cualquier documento que cree o edite se protegerá automáticamente al guardar el documento.

Si la política de aplicación automática está activada, Documento Security Extension for Microsoft Office le pedirá que inicie sesión en el servidor de seguridad de Documento. Deberá proporcionar su nombre de usuario y contraseña para que el servidor pueda autenticarse. Si ha proporcionado las credenciales de inicio de sesión correctas, el documento se guardará y protegerá.

>[!NOTE]
Si no puede iniciar sesión en Documento Security, es posible que el documento se guarde o no. Esto depende de cómo haya configurado el administrador la política de aplicación automática. Consulte con el administrador cómo se gestionan los documentos en esta situación.

### Sincronizando para acceso sin conexión {#synchronizing-for-offline-access}

Las políticas pueden permitirle abrir archivos sin conexión y sin estar conectado a Documento Security. Debe haber iniciado sesión anteriormente en Documento Security para poder establecer sus credenciales con el servidor antes de poder trabajar sin conexión. Si planea trabajar con archivos sin conexión, se recomienda sincronizar con Documento Security antes de desconectar para garantizar que la configuración de directiva de los archivos esté actualizada con el servidor. También se recomienda abrir el archivo en línea una vez antes de abrirlo sin conexión. Si no abre el archivo una vez en línea o no se sincroniza con el servidor, es posible que aún pueda utilizar archivos protegidos por políticas sin conexión. Sin embargo, el período de concesión sin conexión no debe haber caducado y la configuración de directiva del archivo no debe haber cambiado desde la última sincronización manual o automática con el servidor.

Haga lo siguiente:

* En Documento Security Extension for Microsoft Office 2010 y 2013, en la ficha **Seguridad de Documento**, seleccione **Sincronizar sin conexión**.

   ***nota**: El botón Sincronizar sin conexión está disponible aunque el usuario no tenga permiso sin conexión para el documento. Sin embargo, seleccionar el botón no hace nada. *

### Uso de marcas de agua dinámicas {#working-with-dynamic-watermarks}

Documento Security Extension for Microsoft Office admite la inclusión de marcas de agua dinámicas basadas en texto en documentos protegidos por políticas. Una marca de agua dinámica puede incluir información que puede cambiar, como la fecha, la hora, el nombre de usuario o el nombre de la política. Si un usuario imprime un archivo protegido por una política y dicho archivo contiene una marca de agua dinámica y el permiso de impresión, la marca de agua aparece en el resultado.

Documento Security Extension no admite funciones de marca de agua enriquecidas como marcas de agua basadas en PDF, varios elementos en una marca de agua, opciones de formato de texto y rango de páginas.

Puede crear una marca de agua dinámica mediante las páginas web de seguridad de Documento. Para obtener más información sobre cómo crear e incluir marcas de agua dinámicas en un documento protegido por una política, consulte [Ayuda para el usuario final de seguridad de Documento](http://www.adobe.com/go/learn_lc_euRightsMgmt_11).

Documento Security Extension for Microsoft Office ofrece compatibilidad con estas funciones de marca de agua:

<table>
 <thead>
  <tr>
   <th><p>Opciones de marca de agua de documento Security</p></th>
   <th><p>Compatibilidad con Word, Excel y PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Nombre de directiva</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Watermark name</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Usar como fondo</p></td>
   <td><p>El comportamiento de visualización de una marca de agua dinámica es el mismo independientemente de si selecciona Usar como fondo.</p><p>En Word 2010 y 2013, las marcas de agua dinámicas solo aparecen en Diseño de impresión y vista de Previsualización de impresión. </p><p>Para Excel 2010 y 2013 también , aparece en las vistas Previsualización de impresión y Diseño de página.</p></td>
  </tr>
  <tr>
   <td><p>Posición vertical</p></td>
   <td><p>Compatible</p></td>
  </tr>
  <tr>
   <td><p>Posición horizontal</p></td>
   <td><p>Compatible</p><p>En Excel 2010 y 2013, la colocación horizontal de marcas de agua mediante puntos no funciona.</p></td>
  </tr>
  <tr>
   <td><p>Escala</p></td>
   <td><p>Compatible</p></td>
  </tr>
  <tr>
   <td><p>Posición</p></td>
   <td><p>Compatible</p></td>
  </tr>
  <tr>
   <td><p>Opacidad</p></td>
   <td><p>Compatible</p></td>
  </tr>
 </tbody>
</table>

### Abrir las páginas Web de Documento Security {#opening-the-document-security-web-pages}

Puede abrir las páginas web de seguridad de Documento para crear y actualizar las directivas de usuario, así como la información de estado de vista y auditoría de los archivos protegidos por políticas. También puede utilizar las páginas web de seguridad de Documento para cambiar políticas o anular el acceso a un archivo protegido por una política.

Para abrir las páginas web de Documento Security, en Documento Security Extension for Microsoft Office 2010 y 2013, en la ficha **Seguridad de Documento**, seleccione **Crear y administrar políticas**. Si todavía no ha proporcionado la información de inicio de sesión, el explorador se abre en la página de inicio de sesión del servidor.

### Cambio de directivas {#changing-policies}

Si tiene permisos, normalmente como administrador de seguridad de Documento o editor de archivos, puede aplicar una política diferente a un archivo o cambiar la configuración de la política aplicada actualmente.

Para cambiar la configuración de una directiva, utilice las páginas web de seguridad de Documento.

1. Haga lo siguiente:

   * En Documento Security Extension for Microsoft Office 2010 o 2013, en la ficha **Seguridad de Documento**, seleccione **Seguridad > Cambiar seguridad**.

1. Seleccione una directiva en la lista y haga clic en **Aplicar**.

### Revocando privilegios de acceso a archivos {#revoking-file-access-privileges}

Puede anular la capacidad de abrir archivos protegidos. Cuando se revocan los privilegios de acceso para un archivo, también se puede especificar el mensaje que aparece para cualquiera que intente abrir el archivo y la dirección URL de una versión actualizada del archivo si se va a reemplazar con una copia revisada.

1. Haga lo siguiente:

   * En Documento Security Extension for Microsoft Office 2010 y 2013, en la ficha **Seguridad de Documento**, seleccione **Revocar**.

   Las páginas web de Documento Security se abren a la página de Revocar Documentos.

1. Especifique un mensaje para mostrar y, si está disponible, una dirección URL para la versión actualizada y haga clic en **Aceptar**.

Para obtener más información sobre la anulación de privilegios de acceso a archivos, consulte la [Ayuda del usuario final de seguridad de Documento](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

Los privilegios de acceso se pueden restablecer a través de las páginas web de Documento Security.

### Visualización del historial de auditoría de archivos {#viewing-the-file-audit-history}

Documento Security puede guardar el historial de auditoría de los archivos protegidos por políticas para que pueda auditar las acciones que los usuarios realizan en los archivos.

Los eventos auditados para archivos de Word, Excel y PowerPoint incluyen:

**Proteger una nueva** directiva de documento aplicada a un archivo

**Vista** DocumentFile abierta

**Cerrar** DocumentFile cerrado

**Anular privilegios de** DocumentAccess eliminados para el archivo

**Anular revocación de privilegios** de DocumentAccess devueltos al archivo

**Modificar** DocumentFile cambiado y guardado localmente

**Imprimir archivo de alta** resolución impreso

**Cambio de la protección** de Security HandlerPolicy eliminada del archivo

**Cambiar directiva en** documentoNueva directiva aplicada al archivo desde las páginas web de Documento Security

### Vista del historial de auditoría de un archivo {#view-the-audit-history-for-a-file}

En Documento Security Extension for Microsoft Office 2010 y 2013, en la ficha **Seguridad de Documento**, seleccione **Historial de auditoría**.

Las páginas web de Documento Security se abren a la página Eventos, que muestra eventos auditados para el archivo actual.

### Funciones restringidas de Microsoft Office {#microsoft-office-restricted-features}

Para proteger la propiedad intelectual, algunas funciones de Microsoft Office no están disponibles cuando se abre un archivo protegido por una política. La lista de las funciones no disponibles depende de los permisos que se concedan al usuario actual. Algunas funciones no están disponibles solo para un archivo protegido y otras no para todos los archivos cuando se encuentra en una sesión protegida. Por lo general, se encuentra en una sesión protegida desde el momento en que abre un archivo protegido por una política hasta que cierra la aplicación o la sesión caduca.

La mayoría de las políticas otorgan permisos completos al editor de archivos. Es posible que otros usuarios observen restricciones de funciones adicionales.

Si un comando no está disponible, el nombre del comando en el menú y el botón de barra de herramientas relacionado aparecen atenuados.

>[!NOTE]
La aplicación de una política a un archivo que contiene un vínculo a un archivo incrustado no se aplica al archivo vinculado. Documento Security para Microsoft Office no extiende la protección a los archivos vinculados.

* Los archivos de Word, Excel y PowerPoint protegidos por políticas no se pueden abrir en una ventana del explorador de Internet Explorer.
* Los usuarios a los que solo se concedió el permiso de modificación no pueden copiar contenido en un archivo desde otra aplicación mediante el Portapapeles de Windows. Los usuarios pueden copiar contenido en archivos activando la opción Portapapeles de Microsoft Office.
* Al abrir un archivo protegido por una política en Microsoft Office, la tecla Impr Pant deja de estar disponible hasta que se cierre la aplicación o la sesión caduque.
* Documento Security para Microsoft Office no admite la creación y el control de versiones distribuidas basadas en la Web (Web-based Distributed Authoring and Versioning, WebDAV). En la mayoría de los casos, no se puede abrir un archivo protegido por una política desde una carpeta WebDAV. Si puede abrir un archivo protegido por una política, no tiene permisos para guardar, imprimir, cambiar o copiar del archivo.

La seguridad general que se aplica a los archivos protegidos por políticas incluye las siguientes restricciones:

Muchas funciones comunes pueden estar restringidas en Word, Excel y PowerPoint durante una sesión protegida.

Si se abre un archivo protegido por una política que no permite al usuario realizar cambios, los comandos que cambien el archivo de alguna manera no estarán disponibles. Sólo están disponibles los comandos que abren o crean nuevos documentos y cambian las preferencias de la aplicación.

#### Restricciones de Word 2010 y Word 2013 {#word-2010-and-word-2013-restrictions}

Al abrir un archivo protegido por una política en Word, la información de recuperación automática de archivos no estará disponible hasta que cierre y reinicie Word. Además, las funciones enumeradas a continuación están restringidas en las situaciones descritas:

**Archivo > Nuevo > Nuevo a partir de** existenteDisponible, pero no se pueden guardar los archivos creados con este comando mientras esté abierto un archivo protegido por una política. El contenido del nuevo archivo no se puede copiar en otro archivo.

**Archivo >** GuardarRestringido con el permiso de modificación.

**Archivo > Guardar** comoTodas las opciones restringidas por el permiso de modificación.

**Archivo >** ImprimirTodas las opciones restringidas por el permiso de impresión. No disponible a menos que la política permita la impresión de alta resolución.

**Archivo > Guardar y** enviarTodas las opciones no están disponibles durante una sesión protegida.

**Archivo > Información > Documento de Protect > Cifrar con contraseña, Añadir firma digital, Marcar como final, Restringir permisos por** personasNo disponibles durante una sesión protegida.

**Archivo >** Flujos de trabajoNo disponible durante una sesión protegida.

***nota **: La capacidad de inicio de un flujo de trabajo de las versiones de Microsoft Office 2010 de Word, Excel y PowerPoint solo está disponible en los grupos de Office Professional Plus 2010, Office Enterprise 2010 y Office Ultimate 2010, así como en las versiones independientes de estos programas de Office 2010.*

**Entrada de blog >** PublicarNo disponible durante una sesión protegida.

**Archivo > Servidor >** Menú Tareas del servidor de archivosNo disponible durante una sesión protegida.

**Inicio > Portapapeles >** CopiarRestringido con el permiso Copiar. Si no se permite copiar, el contenido copiado no se puede pegar en ningún otro archivo ni en el portapapeles de Office. El contenido se puede copiar dentro del archivo protegido si el usuario tiene el permiso de cambio.

**Inicio > Portapapeles >** PegarRestringido con el permiso Cambiar.

**Inicio > Portapapeles > Pegado** especialRestringido por el permiso de modificación.

**Insertar > Texto >** ObjetoNo disponible durante una sesión protegida. Los archivos protegidos por políticas no se pueden insertar en ningún momento.

**** CorreoLa mayoría de las opciones de esta ficha no están disponibles durante una sesión protegida.

**Revisar > Revisión >** ReferenciaRestringido por el permiso Copiar. No disponible si no se permite copiar.

**Revisar > Revisión >** SinónimosRestringido por el permiso de copia. No disponible si no se permite copiar.

**Revisar > Idioma > Traducir > Traducir** documentoHabilitado con el permiso de copia.

**Revisar > Idioma > Traducir > Traducir** texto seleccionadoHabilitado con el permiso Copiar.

**Revisar > Idioma > Traducir > Mini** traductorHabilitado con el permiso de copia.

**Revisar > Comparar >** CompararNo disponible durante una sesión protegida. Los archivos protegidos por políticas no se pueden comparar en ningún momento.

**Revisar > Protect > Bloquear** autoresNo disponible durante una sesión protegida.

**Revisar > Protect > Restringir** ediciónNo disponible durante una sesión protegida.

**Vista >** MacrosAlgunas macros están restringidas por el permiso de copia y no están disponibles a menos que se permita copiar.

**Añadir-** insNo se puede agregar ni eliminar durante una sesión protegida.

**Colaboración** en líneaNo disponible durante una sesión protegida.

**Documento maestro y** subdocumentosLos subdocumentos se rigen por la directiva de documentos maestro cuando se abren en el documento maestro. Si se abren por separado, los subdocumentos no se pueden imprimir, copiar ni modificar.

**** ResummarizeNo disponible durante una sesión protegida.

**Marcos (y todos los comandos relacionados)** No disponibles durante una sesión protegida.

**Panel** documentoNo disponible durante una sesión protegida.

**Programador >** Plantilla de DocumentoNo disponible durante una sesión protegida. Para acceder a este comando, seleccione Archivo > Opciones > Personalizar > ficha Programador > Plantillas > Plantilla de Documento.

**Esquema > Documento maestro > Crear subdocumento, Insertar** subdocumentoNo disponible durante una sesión protegida.

#### Restricciones de Excel 2010 y Excel 2013 {#excel-2010-and-excel-2013-restrictions}

Las siguientes funciones están restringidas en las situaciones descritas:

**Archivo > Nuevo > Nuevo a partir de** existenteDisponible, pero los archivos creados con este comando durante una sesión protegida no se pueden guardar. El contenido del nuevo archivo no se puede copiar en otro archivo.

**Archivo > Guardar, Guardar** comoRestringido por el permiso de modificación.

**Archivo > Guardar como >** PDFUndisponible durante una sesión protegida.

**Archivo >** ImprimirRestringido por el permiso de impresión. No disponible a menos que la política permita la impresión de alta resolución.

**Archivo > Información >** Documento de ProtectNo disponible durante una sesión protegida.

**Archivo > Información >** Libro de ProtectNo disponible durante una sesión protegida.

**Archivo > Guardar y** enviarNo disponible durante una sesión protegida.

**Archivo > Opciones > Añadir** complementosNo se puede agregar ni eliminar durante una sesión protegida.

**Archivo >** Flujos de trabajoNo disponible durante una sesión protegida.

***nota **: La capacidad de inicio de un flujo de trabajo de las versiones de Microsoft Office 2010 de Word, Excel y PowerPoint solo está disponible en los grupos de Office Professional Plus 2010, Office Enterprise 2010 y Office Ultimate 2010, así como en las versiones independientes de estos programas de Office 2010.*

**Archivo > Servidor >** Menú Tareas del servidor de archivosNo disponible durante una sesión protegida.

**Inicio > Portapapeles >** CopiarRestringido con el permiso Copiar. Si no se permite copiar, el contenido copiado no se puede pegar en ningún otro archivo ni en el portapapeles de Microsoft Office. El contenido se puede copiar dentro del archivo protegido si el usuario tiene el permiso de cambio.

**Inicio > Portapapeles >** PegarRestringido con el permiso Cambiar.

**Inicio > Portapapeles > Pegado** especialRestringido por el permiso de modificación.

**Inicio > Celdas > Formato > Mover o copiar** hojaNo disponible durante una sesión protegida.

**Inicio > Celdas > Insertar > Insertar** hojaNo disponible durante una sesión protegida.

**Inicio > Celdas > Eliminar > Eliminar** hojaNo disponible durante una sesión protegida.

**Inicio > Edición > Rellenar > Otras** hojasRestringido por el permiso de modificación.

**Insertar > Tablas >** TablaRestringido por el permiso Cambiar.

**No se pueden seleccionar Insertar > Tablas > Archivos protegidos por** TablaDinámica (PivotTablePolicy) en el Asistente para creación.

**Insertar > Texto >** ObjetoNo disponible durante una sesión protegida. Los archivos protegidos por políticas no se pueden insertar en ningún momento.

**Insertar > Texto > Encabezado y** pie de páginaRestringido por el permiso Cambiar. No disponible para un documento protegido por una política.

**No se pueden importar datos > Obtener** datos externos de archivos protegidos por políticas.

**Datos > Contorno >** SubtotalesRestringido por el permiso de modificación.

**Datos > Herramientas de datos >** Validación de datosRestringido por el permiso de modificación.

**Revisar > Revisión >** ReferenciaRestringido por el permiso Copiar.

**Revisar > Revisión >** SinónimosRestringido por el permiso de copia.

**Revisar > Idioma >** TraducirRestringido con el permiso Copiar.

**Revisar > Cambios >** Hoja de ProtectNo disponible durante una sesión protegida.

**Revisar > Cambios >** Libro de ProtectNo disponible durante una sesión protegida.

**Revisar > Cambios > Compartir** libroNo disponible durante una sesión protegida.

**Revisar > Cambios > Protect y compartir** libroNo disponible durante una sesión protegida.

**Revisar > Cambios > Permitir que los usuarios modifiquen** intervalosNo disponible durante una sesión protegida.

**Revisar > Cambios > Rastrear cambios > Resaltar** cambiosNo disponible para un archivo protegido por una política que contenga una marca de agua dinámica.

**Vista >** MacrosRestringido por el permiso de modificación.

**Vista > Guardar** WorkspaceCommand no funciona.

**Desarrollador > XML >** Paquetes de expansiónAlgunas macros están restringidas por el permiso de copia y no están disponibles a menos que se permita copiar.

**Fórmulas > Auditoría de fórmulas >** Comprobación de erroresRestringido por el permiso de modificación. No disponible a menos que se permita el cambio.

**Colaboración** en líneaNo disponible durante una sesión protegida.

**Guardar** información de AutorrecuperaciónNo disponible durante una sesión protegida.

***Nota **: Si intenta cambiar una celda en un archivo protegido por una política para el que no tiene permisos para realizar cambios, Excel muestra un mensaje de advertencia incorrecto que indica que debe quitar la protección del archivo mediante el comando Desproteger hoja. El uso del comando Desproteger hoja no elimina la protección de directivas del archivo.*

#### Restricciones de PowerPoint 2010 y PowerPoint 2013 {#powerpoint-2010-and-powerpoint-2013-restrictions}

Las siguientes funciones están restringidas en las situaciones descritas:

**Archivo > Nuevo > Nuevo a partir de** existenteDisponible, pero los archivos creados con este comando durante una sesión protegida no se pueden guardar. El contenido del nuevo archivo no se puede copiar en otro archivo.

**Archivo >** GuardarRestringido con el permiso de modificación.

**Archivo > Guardar** comoTodas las opciones restringidas por el permiso de modificación.

**Archivo >** ImprimirTodas las opciones restringidas por el permiso de impresión. No disponible a menos que la política permita la impresión de alta resolución.

**Archivo > Guardar y** enviarNo disponible durante una sesión protegida.

**Archivo > Información > Presentación de Protect > Cifrar con contraseña, Añadir una firma digital, Marcar como final, Restringir permisos por** personasNo disponibles durante una sesión protegida.

**Archivo > Opciones de PowerPoint > Guardar** información de AutorrecuperaciónNo disponible durante una sesión protegida.

**Archivo > Servidor >** Menú Tareas del servidor de archivosNo disponible durante una sesión protegida.

**Inicio > Portapapeles >** CopiarRestringido con el permiso Copiar. Si no se permite copiar, el contenido copiado no se puede pegar dentro del documento, en ningún otro archivo o en el portapapeles de Office. El contenido se puede copiar dentro del archivo protegido si el usuario tiene el permiso de cambio.

**Inicio > Portapapeles >** PegarRestringido con el permiso Cambiar. Si no se permite copiar, el contenido copiado no se puede pegar dentro del documento.

**Inicio > Portapapeles > Pegado** especialRestringido por el permiso de modificación.

**Inicio > Diapositivas > Nuevas diapositivas > Diapositivas del esquema, Reutilizar** diapositivasNo disponible durante una sesión protegida.

**Insertar > Texto >** ObjetoNo disponible durante una sesión protegida. Los archivos protegidos por políticas no se pueden insertar en ningún momento.

**Diseño > Fondo > Estilos de fondo, Ocultar gráficos de fondo, Formato** de fondoNo disponible para un archivo protegido por una política que contenga una marca de agua dinámica.

**Presentación con diapositivas > Configurar > Grabar** presentación con diapositivasRestringido por el permiso de cambio.

**Revisar > Revisión >** SinónimosRestringido por el permiso de copia.

**Revisar > Idioma >** TraducirRestringido con el permiso Copiar.

**Revisar > Idioma > Traducir > Mini** traductorHabilitado con el permiso de copia.

**Vista > Vistas de presentación >** Presentación con diapositivasRestringido por el permiso de modificación. Si no se permiten cambios, no se podrán ver presentaciones de diapositivas si se ha modificado el archivo.

**Vista >** MacrosAlgunas macros están restringidas por el permiso de copia y no están disponibles a menos que se permita copiar.

**Añadir-** insNo se puede agregar ni eliminar durante una sesión protegida.

**Colaboración** en líneaNo disponible durante una sesión protegida.

## Usar proveedores de autenticación de terceros {#use-third-party-authentication-providers}

Puede utilizar proveedores de autenticación de terceros con AEM Forms Documento Security. Estos proveedores de autenticación le ayudan a agregar una capa de acceso adicional a los documentos protegidos. AEM Forms Documento Security admite los siguientes flujos de trabajo de autenticación extendidos:

* Autenticación extendida mediante la URL de AEM Forms predeterminada
* Autenticación extendida mediante una dirección URL personalizada
* Flujo de trabajo de autenticación ampliado predeterminado con proveedores de identidad de terceros configurados en AEM Forms en el servidor JEE
* Flujo de trabajo de autenticación extendido personalizado con proveedores de identidad de terceros configurados en AEM Forms en el servidor JEE
* Autenticación extendida mediante una página personalizada para enumerar autenticaciones SAML

Para ver los pasos detallados para configurar flujos de trabajo de autenticación extendidos, consulte el artículo [Escenarios de autenticación extendidos](http://blogs.adobe.com/livecycle/2011/12/extended-authentication-scenarios.html)

## Glosario {#glossary}

Para obtener información sobre los formularios de LiveCycle y AEM en la terminología JEE, consulte [Glosario](http://www.adobe.com/go/learn_aemforms_designer_65).
