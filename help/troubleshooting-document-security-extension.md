---
title: Solución de problemas de AEM Documento Security Extension for Microsoft Office
description: Si tiene problemas para instalar, configurar o utilizar la extensión de seguridad de Documento de AEM para Microsoft Office, siga las instrucciones que se indican en este documento.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
translation-type: tm+mt
source-git-commit: ac26ec61f62d7a3db2429c8a9d3f68b82ba8f77a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# Solución de problemas de AEM Documento Security Extension for Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Solución de problemas de instalación y configuración {#troubleshootinginstallationandconfiguration}

Si tiene problemas para instalar y configurar AEM Documento Security Extension for Microsoft Office, asegúrese de seguir cuidadosamente las instrucciones que se indican en la sección - antes de instalar - del artículo [instalación](installing-configuring-aemdsext.md).

Si ha instalado y configurado todo según la documentación, consulte las siguientes secciones para ver si hay problemas similares a los que está experimentando.

### Documento Security Extension no se puede cargar para aplicaciones de Microsoft Office {#document-security-extension-fails-to-load-for-microsoft-office-applications}

La propiedad LoadBehavior del Registro de Windows especifica el comportamiento de tiempo de ejecución del complemento de seguridad de documento. Si la propiedad LoadBehavior está establecida en 3, todos los complementos se cargan automáticamente. Antes de instalar Documento Security Extension for Microsoft Office, asegúrese de que el valor de la propiedad LoadBehavior está establecido en 3.

1. Realice una copia de seguridad del Registro de Windows antes de realizar cambios en él. Para obtener instrucciones detalladas, consulte [Cómo modificar el Registro de Windows](https://support.microsoft.com/en-us/kb/136393).
1. En el Editor del Registro, navegue toHKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin o HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Establezca el valor de la propiedad **LoadBehavior** en 3.

1. Cierre el Editor del Registro.

Para obtener información detallada sobre LoadBehavior, consulte el artículo [Entradas del Registro para Añadas de VSTO](https://msdn.microsoft.com/en-us/library/bb386106.aspx#LoadBehavior).

## Solución de problemas de tareas administrativas {#admintasks}

En esta sección se analizan los posibles problemas con la Extensión de seguridad de Documento de AEM instalada.

### Las aplicaciones de Microsoft Office no inicio sin problemas al instalar Documento Security Extension {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Para garantizar que las aplicaciones de Office se inicio sin problemas en un equipo que tenga instalado Documento Security Extension y McAfee VirusScan con la opción de protección de acceso activada, desactive la opción Protección contra desbordamientos de búfer en la consola de McAfee VirusScan.
