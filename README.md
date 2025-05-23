# Entrega-Medico-UML---Francisco-Canales-UllloaClínica EMF – Francisco Canales Ulloa

En este trabajo analizare 3 tipos de diagrama los cuales son: Caso de uso, diagrama UML y diagrama de implementación.
Tratare de encontrar 3 errores de cada diagrama y dar de mi punto de vista las correcciones que se pueden hacer 
Diagrama caso de uso:
 
Este es el diagrama en cuestión donde debo encontrar 3 errores y poder corregirlos.
1-. Diagrama caso de uso:
•	Error en los actores
o	El actor “APIReservaExterna” se representa como que realizara acciones en el sistema lo cual las APIs no deberían actuar como actores externos ya que son interface y no usuarios
o	Este debería formar parte del sistema o que sea representado como interacción externa, no como un actor humano


•	Ambigüedad al momento de “Notificar cambios por correo”
o	No hay claridad si el actor inicia este caso de uso. Este debería estar vinculado a un actor claro que lo inicie
o	Una solución seria definir que el administrador active la notificación que establezca correctamente la relación entre si
•	Cierta inconsistencia al momento de “Agregar motivo de cancelación”
o	En este caso parece ser una subactividad dentro de “cancelar reserva”, donde debería ser parte de un flujo interno y no un caso separado a ese nivel.
o	Para corregir este, se debería incluir una acción como una extensión o paso dentro del caso de uso principal de “cancelar reserva” en lugar de tenerla separada
2-. Diagrama UML:
 
Encontrar 3 errores en el diagrama UML
•	Relación de herencia entre componentes de notificación
o	NotificadorCorreo y NotificadorSMS  están relacionados como tipos de notificadores pero no tienen relación de herencia o implementación entre si junto con GestorNotificaciones. Dicha clase que es GestorNotificaciones debe depender de una interfaz común como Notificador que implemente o extiende entre las ya mencionadas
o	Una corrección seria crear una clase o interfaz con el método notificar() e implementar en NotificadorCorreo y NotificarSMS
•	Clase sala poco clara 
o	Esta tiene un método como marcarDisponible() y marcarOcupada() lo cual no se logra observar si SistemaReservas invoca o como se integra esta lógica en el flujo de reservas. Acá hace falta el vínculo de colaboración / invocación entre SistemaReservas y Sala
o	Una solución podría ser agregar una relación directa la cual muestre las llamadas desde SistemaReservas a esos métodos de Sala
•	Falta de relación explicita entre Reserva y SistemaReservas
o	Esta contiene atributos relevantes tales como fecha y estado pero no se relaciona ni con usuario, SistemaReservas y Sala. Esto impide comprender la creación, modificación o asociación de una reserva con una sala o usuario
•	Una solución seria:
o	asociar Reserva con Usuario
o	Asociar Reserva con Sala
o	Mostrar como SistemaReserva crea y gestiona instancias de Reserva



