---
# required metadata

title: Consideraciones de diseño
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 639dfd46-33ea-4cfd-918d-f3d8e57645ed

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Consideraciones de diseño

A fin de seleccionar los productos y tecnologías adecuados para implementar los requisitos de diseño de la infraestructura para BYOD, necesita comprender los requisitos detallados en la sección Previsión de la solución de infraestructura BYOD de este documento. En la tabla siguiente se enumeran los productos, tecnologías y servicios de Microsoft que se pueden usar para implementar una solución de infraestructura BYOD.

Los productos, tecnologías y servicios de Microsoft relativos a una solución de infraestructura para BYOD que se mencionarán en esta guía son los siguientes:

## Usuario y dispositivo

- Windows Server 2012 R2
- Windows 10
- Unión al espacio de trabajo
- Servicio de registro de dispositivo
- Inscripción de dispositivos
- Perfil de Wi-Fi
- Portal de empresa
- Protocolo HTTPS

## Acceso a datos y protección de datos

- Windows Server 2012 R2
- Servicios de dominio de Active Directory (AD DS)
- Active Directory de Azure (Azure AD)
- Azure Multi-Factor Authentication (MFA)
- Servicios de federación de Active Directory (AD FS)
- Control de acceso dinámico
- Servicio de administración de permisos de Microsoft
- Administración de los derechos de Azure 
- Cifrado SMB
- Inicio de sesión único (SS)
- Carpetas de trabajo
- Proxy de aplicación web (WAP)

## Management

- Microsoft Intune
- Directivas de administración de dispositivos
- Infraestructura de administración unificada
- Eliminación selectiva
- Distribución de software
- Informes de uso de punto de distribución y administración
- Administrador de configuración de System Center 2012 R2

## Aplicaciones

- Proxy de aplicación web
- Desencadenador automático VPN
- RemoteApp
- Instantáneas de sesión
- Reconexión rápida
- Almacenamiento de desduplicación
- Ciclo de vida de desarrollo de seguridad (SDL)
- Servicios de federación de Active Directory (AD FS)
- Protocolo HTTPS

En las secciones siguientes, se describe el proceso de diseño, pero como se menciona en la sección Previsión de la solución de infraestructura BYOD de este documento, el proceso de definición de requisitos y diseño es iterativo hasta que se completa.
El resto del documento aborda las consideraciones de diseño y los productos, tecnologías y servicios enumerados en la tabla anterior. Cuando se pueden usar varios productos, tecnologías y servicios de Microsoft para tratar las diversas consideraciones de diseño, se analizan las diferencias entre ellos.

El diseño de la infraestructura para admitir BYOD permite responder a las preguntas que se plantearon con anterioridad en este artículo, y muestra las funciones y opciones tecnológicas que tiene a su disposición. El diseño que se describe en este documento usa tecnología de Microsoft. Sin embargo, las opciones e indicaciones de diseño pueden aplicarse a cualquier infraestructura que se use para integrar el modelo de BYOD.




<!--HONumber=Apr16_HO2-->


