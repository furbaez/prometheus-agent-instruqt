---
slug: instalación-y-configuración 
id: 
type: challenge 
title: 1. Instalación y Configuración 
teaser: Instale el Agente Prometheus y otros componentes de New Relic en su clúster notes:

-   type: text contents: |- Por favor, espere mientras construimos su clúster de Kubernetes.

    Este es un buen momento para obtener su ID de cuenta de New Relic, clave de licencia y clave de API de usuario. Los necesitará en el primer desafío de laboratorio. tabs:

-   title: Terminal type: terminal hostname: kubernetes-vm

-   title: Plataforma New Relic type: website url: <https://one.newrelic.com/> new_window: true dificultad: básico tiempo_limite: 900

* * * * *

Descripción general
===================

### Objetivo: ¡Instalar cosas!

* * * * *

### Un poco sobre su clúster de Kubernetes:

Mientras el carrete giraba, se creó un clúster de Kubernetes de un solo nodo utilizando [Minikube](https://minikube.sigs.k8s.io/docs/). Además, se agregó el controlador de ingreso NGINX (una fuente simple de métricas de Prometheus) para brindarle algunas métricas con las que trabajar.

Es una buena idea hacer una verificación rápida para asegurarse de que todo esté funcionando correctamente.

Ejecute el siguiente comando:

arduinoCopy code

`kubectl get pods -A`

Su clúster debería verse algo así:

![kubectl](https://p191.p3.n0.cdn.getcloudapp.com/items/rRugng1D/32d6b07d-ea6e-4ec8-b333-4ec0a37fc717.jpg?source=viewer&v=babd92dc9aecec85c0a65873f957d0c8)

Si no es así, espere un minuto e inténtelo nuevamente. No debería tomar mucho tiempo para que todos los componentes entren en un estado `Running`.

Instrucciones de instalación
============================

Instalemos el Agente Prometheus y otros componentes de New Relic. En este paso, necesitará:

-   ID de cuenta de New Relic
-   Clave de licencia de New Relic
-   Clave de API de usuario de New Relic (comienza con NRAK)

Si no sabe dónde encontrar estos elementos, haga clic en su avatar en la parte inferior izquierda y seleccione `API Keys`.

![apikeys](https://p191.p3.n0.cdn.getcloudapp.com/items/X6uKO7bn/af9f789b-a69f-44e6-ac44-fa9d28c1451f.jpg?v=7a6cc2303cc63704ff6a7155becd807d)

Los 3 elementos están disponibles en esta interfaz.

![keys](https://p191.p3.n0.cdn.getcloudapp.com/items/GGu7k5KP/8558a2b0-6a4c-4adc-980a-9cebedcfa09e.jpg?v=82e08fcd64f92c847edffdac85b64561)

Ejecute el script `install.sh` e ingrese su información en las solicitudes para instalar New Relic en su clúster.

bashCopy code
```
`./install.sh`
```

Deberías ver una salida similar a esta:

! [install](https://p191.p3.n0.cdn.getcloudapp.com/items/9ZuKd4j2/226fa774-d184-4934-9919-914b22a9e800.jpg?v=092d5a9cf748fde5af97d4fcef05fa20)

Si recibes un error o necesitas limpiar y comenzar de nuevo por cualquier motivo, ejecuta el script `cleanup.sh`.

bashCopy code

`./cleanup.sh`

Si tienes curiosidad por lo que se instaló, puedes ejecutar `cat ./install.sh` para ver los comandos que se usaron. (Sí, el script de bash probablemente podría usar alguna validación adicional de entrada y comprobación de errores...)

Valida tu instalación
=====================

Si todo salió según lo planeado, deberías poder ver todos los componentes de New Relic instalados bajo el espacio de nombres `newrelic`.

Puedes observar el progreso de la instalación de los pods con este comando:

arduinoCopy code

`watch kubectl get pods -n newrelic`

Cuando todo esté completo, tus resultados deberían verse algo así: ![](https://lh3.googleusercontent.com/pw/AMWts8CFTPqI9LYtpaANjcq_yY4ldQCWfljaIzfYzDcNkj3IgzNEAd-QygIjSZY8TREaELyptuBYB1HkyseHLp1thWjOWwTMCIiZ8_wcul0eqe8tDSjcx0bFLqMWBOATOk14LE53ab0vavKlYCoZGm2zbHPc=w1502-h394-no?authuser=0)

Utiliza `ctrl + c` para cancelar el comando `watch`.

Además de los componentes instalados en el clúster, se instaló un panel de control en tu cuenta de New Relic llamado `Prometheus Agent Instruqt Lab`. Verifica los `Paneles de control` en tu cuenta de New Relic para validar que esto se creó correctamente. Lo utilizarás a lo largo del laboratorio.

El panel se verá así:

![Dashboard](https://p191.p3.n0.cdn.getcloudapp.com/items/BlubKqdR/fd47200d-df0d-4ae0-ac86-69cf1a362bff.jpg?v=6edcfa2d55f07502a777db64866693b0)

Recapitulación
==============

El script de instalación utilizó Helm para instalar los siguientes componentes en tu clúster:

-   Agente de Prometheus de New Relic
-   Infraestructura de New Relic para Kubernetes **
-   Registro de New Relic
-   Integración de eventos de Kubernetes de New Relic **
-   Inyección de metadatos de New Relic **

> ** - no se utiliza para este laboratorio, pero forma parte de los componentes básicos de K8s de New Relic.

* * * * *

NOTA: Los ejercicios en este laboratorio se construyeron alrededor de la modificación del archivo de valores de Helm para la gráfica del agente de Prometheus (`newrelic-prometheus-configurator`) directamente y no la gráfica del paraguas `nri-bundle`. Esto mantiene el laboratorio un poco más simple y menos propenso a errores.

Los usuarios normalmente despliegan el gráfico "nri-bundle" y lo configuran para incluir el agente Prometheus (estableciendo `newrelic-prometheus-agent.enabled` como `true` en el archivo `values.yaml`).

Un ejemplo del archivo `values.yaml` para el `nri-bundle` se puede encontrar [aquí](https://github.com/newrelic-experimental/prometheus-agent-instruqt/blob/main/prom-agent/values-nri-bundle.yaml).

* * * * *

¡Lo lograste!
=============

Haz clic en el botón "Check" para asegurarte de que todo esté funcionando correctamente y luego sigue con el siguiente desafío.

