---
title: Proteger el acceso principal | Azure Active Directory Identity Protection
description: "Escenario en el que se describe cómo se puede usar Enterprise Mobility + Security para proteger la identidad para el acceso seguro a los recursos de la empresa mediante el aprovechamiento de las funciones de Microsoft Azure Active Directory Identity Protection y de Azure Active Directory Privileged Identity Management."
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: techgroup-identity
ms.assetid: c9aeabcf-db9b-4a35-b1bc-61331c464165
ms.reviewer: v-craic
ms.suite: ems
ms.custom: microsoft-identity-manager
translationtype: Human Translation
ms.sourcegitcommit: 02b0e611805ad2214b1b108b8c466590aad7999a
ms.openlocfilehash: c61f68b5922373ffe5509ddb80a158d6a9757ff1


---

# <a name="protect-at-the-front-door"></a>Proteger el acceso principal

Las soluciones de seguridad tradicionales solían ser suficientes para proteger una empresa. Pero esto era así antes de que el sector de la movilidad creciese y generase un panorama de ataque más grande, y antes de que la transición a la nube hiciese más complejas las interacciones de los empleados con otros usuarios, dispositivos, aplicaciones y datos. Ahora, para proteger realmente la empresa, debe adoptar un enfoque más innovador e integral para la seguridad, que pueda proteger, detectar y responder a amenazas de todo tipo localmente y en la nube.

En más del 63 % de las infracciones de datos, los atacantes obtienen acceso a la red corporativa mediante credenciales de usuario no seguras, predeterminadas o robadas.  La seguridad basada en identidad de Microsoft se centra en las credenciales de usuario e impide el robo de credenciales mediante la administración y la protección de las identidades, incluidas las identidades con y sin privilegios.


## <a name="how-can-enterprise-mobility--security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?

El enfoque de seguridad de Enterprise Mobility + Security (EMS) comienza con una identidad común protegida para el acceso seguro a todos los recursos corporativos locales y en la nube con un [acceso condicional](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access/) basado en riesgos. Mediante el uso de este enfoque, el departamento de TI puede proteger el acceso principal a los recursos de la empresa con accesos condicionales avanzados e innovadores basados en riesgos. EMS proporciona una identidad común protegida para acceder a miles de aplicaciones, lo que ayuda al departamento de TI a administrar y proteger las identidades con privilegios.

## <a name="recommended-solution"></a>Solución recomendada

Para satisfacer los requisitos de este escenario, EMS usa [Azure AD Identity Protection](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/) y [Azure AD Privileged Identity Management](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-configure/). Al implementar estas tecnologías, las organizaciones podrán:

- Obtener información desde una vista consolidada de detección de amenazas basada en aprendizaje automático
- Realizar recomendaciones de corrección
- Calcular la gravedad de los riesgos
- Realizar automáticamente un acceso condicional basado en riesgos para proteger frente a inicios de sesión sospechosos y credenciales en peligro
- Exigir un acceso administrativo a petición y Just-In-Time cuando sea necesario
- Usar alertas, informes de auditoría y revisión de acceso

En el diagrama siguiente se resumen las funciones implicadas en este escenario y su uso para proteger los recursos:

![Protección de los recursos](./media/protect-front-door/protect-front-door-fig1.png)

## <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución

Siga estos pasos para implementar Azure AD Identity Protection y Azure AD Privileged Identity Management:

- Paso 1: habilitar Azure AD Identity Protection
- Paso 2: configurar Azure AD Identity Protection
- Paso 3: supervisar el acceso a los recursos
- Paso 4: habilitar Azure AD Privileged Identity Management
- Paso 5: configurar Azure AD Privileged Identity Management
- Paso 6: operaciones de Privileged Identity Management


## <a name="how-to-protect-your-resources-at-the-front-door"></a>Cómo proteger el acceso principal a los recursos

Cada organización tiene una opinión sobre la prioridad de los incidentes. Lo que es fundamental para una línea de negocio, podría no serlo para otra. Por este motivo, primero debe conocer la clasificación de Azure AD Identity Protection del [nivel de riesgo](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#detection-and-risk), que es una indicación (alta, media o baja) de la gravedad del evento de riesgo. Azure AD Identity Protection también evalúa la probabilidad de que se haya puesto en peligro la identidad de un usuario y asigna su propio nivel de riesgo, denominado [nivel de riesgo del usuario](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#what-is-a-user-risk-level). Azure AD Identity Protection identificará una [vulnerabilidad](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-vulnerabilities/) y le asignará un nivel de riesgo. Hay diferentes [tipos de riesgos](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-risk-events-types/), y cada uno de ellos se clasifica según su importancia. Siga los pasos del 1 al 3 para habilitar, implementar y supervisar los recursos con Azure AD Identity Protection.

En la segunda fase de esta solución (pasos del 4 al 6), se implementará Azure Active Directory (AD) Privileged Identity Management para detectar, restringir y supervisar las identidades con privilegios. Las organizaciones que usan Azure pueden [asignar roles en Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/), y Azure AD Privileged Identity Management puede administrar [algunos de estos roles](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-roles/).

### <a name="step-1-enable-azure-ad-identity-protection"></a>Paso 1: habilitar Azure AD Identity Protection

Antes de implementar esta solución, asegúrese de que el usuario final tiene asignada una [licencia de Azure AD Premium](https://azure.microsoft.com/documentation/articles/active-directory-get-started-premium/). En caso de que use un dominio federado y quiera exigir que el cambio de contraseña en la nube se escriba en diferido localmente, debe habilitar la [escritura diferida de contraseñas](https://azure.microsoft.com/documentation/articles/active-directory-passwords-getting-started/). Cuando acabe de revisar estos requisitos, [habilite Azure AD Identity Protection](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-enable/). Para ello, instálelo desde Marketplace. Una vez finalizada la instalación, tendrá acceso al panel de Azure AD Identity Protection, que podría aparecer vacío, tal como se muestra en la imagen siguiente.

![Azure AD Identity Protection](./media/protect-front-door/protect-front-door-fig2.png)

### <a name="step-2-configure-azure-ad-identity-protection"></a>Paso 2: configurar Azure AD Identity Protection

Cuando planee implementar Azure AD Identity Protection, en primer lugar debe definir las directivas siguientes:

- [Directiva de registro de autenticación multifactor](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#multi-factor-authentication-registration-policy): permite que el departamento de TI exija la autenticación multifactor (MFA) a los usuarios.
- [Directiva de riesgo de usuario](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#user-risk-security-policy): permite que el departamento de TI establezca una directiva de seguridad de riesgo de usuario para impedir que los usuarios inicien sesión en función del nivel de riesgo.
- [Directiva de riesgo de inicio de sesión](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#sign-in-risk-security-policy): permite que el departamento de TI evalúe el riesgo de un inicio de sesión determinado y, según este resultado, aplique correcciones mediante reglas y condiciones predefinidas.

Estas directivas se encuentran en la sección **Configurar** del panel de Azure AD Identity Protection, tal como se muestra en la pantalla siguiente:

![Directivas](./media/protect-front-door/protect-front-door-fig3.png)

Además de configurar directivas de seguridad, puede personalizar qué usuarios recibirán las alertas. Debe usar la opción **Alertas** de la sección Configuración del panel de Azure AD Identity Protection, tal como se muestra en la imagen siguiente:

![Alertas](./media/protect-front-door/protect-front-door-fig4.png)

Observe que, en esta configuración, estos usuarios solo recibirán alertas si el nivel de riesgo de usuario es **Alto**.

### <a name="step-3-monitor-and-remediation"></a>Paso 3: supervisar y corregir

La supervisión continua es una parte integral de todas las operaciones seguras. Con las funciones de [investigación](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#investigation) de Azure AD Identity Protection, el departamento de TI obtendrá información sobre la detección de amenazas basada en aprendizaje automático con notificaciones y sugerencias de corrección. Puede usar el panel de Azure AD Identity Protection para evaluar rápidamente el entorno actual e identificar fácilmente los problemas que deben solucionarse en función de su importancia. También puede limitar su investigación a las áreas siguientes, que encontrará en la sección Investigar del panel de Azure AD Identity Protection:

![Investigación](./media/protect-front-door/protect-front-door-fig5.png)

Tras investigar cada una de esas áreas, los administradores pueden emprender acciones para corregir los [usuarios de riesgo](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#mitigating-user-risk-events) o los [eventos de inicio de sesión](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#mitigating-sign-in-risk-events). Por ejemplo, si identifica un evento de seguridad como [Viajes imposibles a ubicaciones inusuales](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-risk-events-types/#impossible-travel-to-atypical-locations) (el segundo evento de la pantalla siguiente), puede emprender acciones para [corregir](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#remediating-user-risk-events) esta amenaza, por ejemplo, exigiendo el restablecimiento de la contraseña.

![Eventos de riesgo](./media/protect-front-door/protect-front-door-fig6.png)

También puede aprovechar los [informes de acceso y uso de Azure AD Premium](https://azure.microsoft.com/documentation/articles/active-directory-view-access-usage-reports/) para obtener más información sobre el comportamiento de un usuario y las posibles amenazas.

### <a name="step-4-enable-azure-ad-privileged-identity-management"></a>Paso 4: habilitar Azure AD Privileged Identity Management

Para acceder a Azure AD Privileged Identity Management, primero debe [instalarlo desde Marketplace](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-getting-started/). Azure AD Privileged Identity Management y Azure Multi-Factor Authentication (MFA) funcionan conjuntamente para ayudar al departamento de TI a administrar el acceso a aplicaciones y servicios seguros. Después de instalar Azure AD Privileged Identity Management, se realizará una prueba para comprobar si puede usar MFA. Cuando haga clic en la opción para comprobar su cuenta, se le redirigirá a una página web donde deberá escribir sus credenciales. Si su cuenta todavía no está habilitada para MFA, verá un mensaje parecido al que se muestra en la pantalla siguiente:

![Pantalla de inicio de sesión](./media/protect-front-door/protect-front-door-fig7.png)

Haga clic en **Configurarlo ahora** y siga el asistente. Debe escribir el número de teléfono fijo o móvil para realizar la comprobación. Cuando finalice el asistente, verá un mensaje que indicará que la comprobación se ha completado:

![Comprobación](./media/protect-front-door/protect-front-door-fig8.png)

### <a name="step-5-configure-azure-ad-privileged-identity-management"></a>Paso 5: configurar Azure AD Privileged Identity Management

La configuración inicial se realiza mediante un [Asistente para seguridad](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-security-wizard/) que tiene tres fases, como se muestra en la hoja **Proteger su organización**:

![Asistente para seguridad](./media/protect-front-door/protect-front-door-fig9.png)

En la primera fase, se revisan los [roles con privilegios](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-roles/) que detectó Azure AD Privileged Identity Management. En la segunda fase, se reduce el número de usuarios de la organización que tienen asignaciones permanentes de roles con privilegios, lo que reduce directamente la vulnerabilidad frente a infracciones de seguridad. En la última fase, puede revisar los cambios realizados en los usuarios que tienen roles con privilegios.

Si durante este proceso le concedió a otro usuario un rol administrativo, dicho usuario se convirtió en apto para realizar tareas con ese rol, lo que significa que puede [activar ese rol](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-activate-role/) cuando necesite realizar una tarea que requiera ese rol.

### <a name="step-6-privileged-identity-management-operations"></a>Paso 6: operaciones de Privileged Identity Management

Ahora que ha instalado y configurado Azure AD Privileged Identity Management, puede realizar la evaluación inicial para comprobar su esquema actual de rol y las alertas. En la hoja **Privileged Identity Management**, haga clic en **Administrar roles con privilegios**. Verá un panel parecido al que se muestra en la imagen siguiente:

![Roles con privilegios](./media/protect-front-door/protect-front-door-fig10.png)

En este panel verá la actividad actual, como las [alertas de seguridad](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-configure-security-alerts/) y la [revisión de acceso](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-start-security-review/). También puede usar el panel para [agregar](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-give-access-to-pim/) o [quitar](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-give-access-to-pim/#remove-another-users-access-rights-for-managing-pim) el acceso de uno o más usuarios a Azure AD Privileged Identity Management.



<!--HONumber=Dec16_HO2-->


