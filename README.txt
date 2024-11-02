IPC (Inter-Process Communication)
============================
Inter-process communication (IPC) refers to the mechanisms that allow processes to exchange data and synchronize their operations. IPC is fundamental in multitasking operating systems to allow different processes to coordinate with each other for improved efficiency, data consistency, and task management.

Un proceso contiene:
	ID
	STATS
		- Información actual del estado del proceso
		- Uso de memoria, tiempo de CPU y estado de ejecución
	Puede tener un proceso padre/hijo
		- Un proceso puede crear otros procesos, estableciendo una jerarquía de padre-hijo
		- El proceso padre puede controlar y gestionar los procesos hijos

============================

Localización de Procesos
============================
Los procesos están representados en archivos ejecutables, ubicados cerca de los directorios del sistema:
	|usr
	|root
	|lib

Ejemplo:
		Los ejecutables del sistema están normalmente en /usr/bin, /bin, y /sbin.

============================

Características de IPC
============================
Data transfer
	- Transferencia de datos entre procesos.
Sincronización de procesos
	- Control del flujo de ejecución para evitar conflictos.
Compartimiento de recursos
	- Permite el acceso compartido a archivos, memoria, etc.
Control de procesos
	- Un proceso puede gestionar la creación o finalización de otros procesos.
Descomposición de tareas
	- Divide el trabajo en subtareas gestionadas por diferentes procesos.

============================

Mecanismos
============================
Mecanismos principales de comunicación entre procesos:

	|File-Based IPC
		|Regular
			- Intercambio de archivos entre directorios.
			- Almacenamiento persistente.
			- Acceso múltiple a procesos.
			- Bloqueo de archivos (para comunicación sincrónica).
			- Casos de uso:
				- Archivos de configuración.
				- Datos de usuario.
				- Archivos de registro.
		|Named Pipes (FIFOs)
			- Comunicación unidireccional.
			- Existe un orden en la transferencia de datos.
		|Unix Domain Sockets
			- Comunicación entre procesos en la misma máquina.
			- Alta velocidad, permite conexiones bidireccionales.

	|Signal-based IPC
		|POSIX
			- Estándar para enviar señales entre procesos.
		|System V
			- Otro estándar para la gestión de señales.
			
	|Memory-based IPC
		|Shared memory
			- Área de memoria común entre procesos para acceso rápido.
		|Memory-mapped files
			- Archivos que pueden ser mapeados a memoria compartida.

============================

Casos de Uso
============================
|Sistemas Cliente-Servidor
	|(Client -> Request -> Server)
	|(Server -> Response -> Client)
		- El cliente puede ser cualquier entidad (host o varios terminales)
		- Ejemplo: Un navegador web como cliente y un servidor web para manejar las solicitudes.
		
|Sistemas Distribuidos
	- Procesos repartidos en diferentes máquinas que trabajan como un sistema único.
	- Ejemplo: Infraestructura en la nube (Cloud computing).

============================

Tipos de Comunicación
============================
|Sincrónica
	- La comunicación está bloqueada hasta que el receptor responde.
	- Ejemplo: Llamadas a procedimientos directos.

|Asincrónica
	- La comunicación no se bloquea, permitiendo que el proceso continúe sin esperar respuesta.
	- Ejemplo: Colas de mensajes (message queues).

============================

Modularidad
	- Los procesos están organizados en módulos o segmentos para facilitar la organización del sistema.

Computación Paralela
	- Varios procesos trabajando en paralelo, aprovechando múltiples núcleos de CPU para ejecutar tareas simultáneamente.

Uso de Stdin y Stdout
	- Al ejecutar comandos como `ls`, se usan las entradas y salidas estándar para recibir y enviar información.
