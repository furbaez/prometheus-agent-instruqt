<a href="https://opensource.newrelic.com/oss-category/#new-relic-experimental"><picture><source media="(prefers-color-scheme: dark)" srcset="https://github.com/newrelic/opensource-website/raw/main/src/images/categories/dark/Experimental.png"><source media="(prefers-color-scheme: light)" srcset="https://github.com/newrelic/opensource-website/raw/main/src/images/categories/Experimental.png"><img alt="New Relic Open Source experimental project banner." src="https://github.com/newrelic/opensource-website/raw/main/src/images/categories/Experimental.png"></picture></a>

Prometheus-Agent-Instruqt
=========================

Este es material complementario relacionado con el Laboratorio Instruqt de Prometheus Agent para Kubernetes.

Antecedentes
------------

La capacidad de ejecutar Prometheus Server en "modo agente" se lanzó con Prometheus Server `v2.32.0`. Puede leer más al respecto [aquí](https://prometheus.io/blog/2021/11/16/agent/#prometheus-agent-mode). Posteriormente, New Relic lanzó el [Configurador de Prometheus](https://github.com/newrelic/newrelic-prometheus-configurator), que es una capa de configuración alrededor del Prometheus Agent que configura automáticamente la escritura remota en New Relic y los trabajos de raspado por defecto.

Obtenga más información sobre el Prometheus Agent en [nuestra documentación](https://docs.newrelic.com/docs/infrastructure/prometheus-integrations/install-configure-prometheus-agent/setup-prometheus-agent/).

Instalación
-----------

Este laboratorio se entrega en la plataforma Instruqt y todas las instrucciones se encuentran en el propio laboratorio. Acceda al laboratorio aquí: <https://play.instruqt.com/newrelic/invite/up9jflwp3clf>.

Empezando
---------

-   Cree una cuenta de Instruqt
-   Traiga lo siguiente: ID de cuenta de New Relic, clave de licencia de New Relic, clave de API de usuario de New Relic

### Secciones del Laboratorio

1.  Instalación y Configuración
    -   Instale el Prometheus Agent y otros componentes de New Relic en su clúster.
2.  ¿Dónde están mis métricas de NGINX?
    -   Trabaje con el filtro de integraciones y las etiquetas de Kubernetes para habilitar la recolección de métricas de NGINX.
3.  ¡El agua está fría! Vaya poco a poco
    -   Recoja selectivamente las métricas de Prometheus de Fluenbit implementando una anotación de raspado personalizada.
4.  Obtenga esas dulces y deliciosas métricas de un destino estático
    -   Aprenda cómo configurar el Prometheus Agent para raspar un destino estático que se ejecuta en la VM de Instruqt.
5.  Métricas y Etiquetas de Métricas: Cómo eliminarlas y fingir que fue un accidente (guiño, guiño)
    -   Aprenda cómo eliminar métricas y etiquetas de métricas si la cardinalidad o el volumen de ingestión son una preocupación.
6.  ¿A quién no le encanta un buen tablero?
    -   Despliegue el tablero de inicio rápido de CoreDNS en su cuenta de New Relic.

Contribución
------------

¡Alentamos sus contribuciones para mejorar Prometheus-Agent-Instruqt! Tenga en cuenta que al enviar su solicitud de extracción, deberá firmar el CLA a través de CLA-Assistant. Solo tiene que firmar el CLA una vez por proyecto. Si tiene alguna pregunta o para ejecutar nuestro CLA corporativo, necesario si su contribución es en nombre de una empresa, envíenos un correo electrónico a <opensource@newrelic.com>.

Nota sobre vulnerabilidades

Como se menciona en nuestra [política de seguridad](https://chat.openai.com/security/policy), New Relic se compromete a la privacidad y seguridad de nuestros clientes y sus datos. Creemos que proporcionar una divulgación coordinada por parte de los investigadores de seguridad y participar en la comunidad de seguridad son medios importantes para lograr nuestros objetivos de seguridad.

Si cree que ha encontrado una vulnerabilidad de seguridad en este proyecto o en cualquiera de los productos o sitios web de New Relic, le agradecemos que lo informe a New Relic a través de [HackerOne](https://hackerone.com/newrelic).

Licencia
--------

Prometheus-Agent-Instruqt está bajo la licencia [Apache 2.0](http://apache.org/licenses/LICENSE-2.0.txt).
