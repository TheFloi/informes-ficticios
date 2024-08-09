# informe de caso pagina marketing
Informe Forense: Ataque Robo de datos financieros

## 1.- Resumen ejecutivo
Este informe esta basado en un incidente de seguridad que sucedio el dia 8 de Agosto e las 2 pm, en el que se notifico de una fuga de datos financieros sencibles de un usuario, por fortuna el usuario era el helping desk de la empresa y se percato rapidamente, cambiando los datos y evitando que el problema pase a mayores, se realizo una investigacion forense inmmediata y se descubrio comop el atacante logro rrobar esta informacion se identificaron las vulnerabilidades y se proponen soluciones para mitigar el riesgo, y prevenir futuros ataques similares.

## 2.- Metodologia
La metodologias utilizadas para descubrir esta fuga:
    
    - Mediante un monitoreo de transacciones anomalas.
    
    - Alertas de la API
    
    - Analisis de logs del servidor
    
    - reporte de nuestro helping desk

## 3.- Hallazgos
1.- Helping desk descubrio sus datos siendo utilizados sin autorizacion, por lo que hizo el reporte

2.- Nuestro cuerpo de ciberseguridad se percato de un aumento inusual de en la cantidada de transacciones pequeñas y pagos fallidos.

3.- La api notifico, solicitudes desde fuentes geograficas extrañas y anomalas.

4.- En los logs se encontro la misma actividad inusual que mostraban las alertas de la API, junto con intentos de acceso repetido.

5.- Durante la auditoria de seguridad se descubrio una vulnerabilidad importante en el sistema. 

## 4.- Analisis
a partir de los datos y hallazgos inusuales, se reviso el codigo fuente que tenga que ver con pagos y mas que nada con paypal, se busca mas pruebas de logs que haga el ciberdelincuente, sabemos que esta explotando una vulnerabilidad de la empresa asi que estamos monitorizando para encontrar su actividad, analisando el codigo estatico se encontraron varias cosas.

## 5.- Conclusiones
Segun las evidencia y analisis del caso se sabe casi con total certeza que la causa de fuga de los datos fue en una mala estructuracion de la API de pago en paypal, un error de arquitectura de parte de el desarrollador y tambien  el equipo de seguridad, una fuga de informacion tan sencible puede traer consecuencias catastroficas a la empresa (multas millonarias, quiebra, hasta pago con carcel) debemos reconsiderar y juzgar al equipo de seguridad tal vez se necesite hacer cambios, en cuanto a los desarrolladores una estricta advertencia de su falta.  

El problema sera solucionado, siempre y cuando sea inmediato.

## 6.- Recomendaciones 
1.- Revocar las y regenerar las credenciales: se revocaran las credenciales comprometidas y generear nuevas, asegurandose que no se expongan de nuevo.

2.- Inavilitar el sistema de pagos con paypal momentaneamente, para que el ciber delincuente no siga sacando datos sencibles

3.- Notificar a los clientes de esta medida mas no de las razones, no se puede perder reputacion.

4.- Almacenar las credenciales de la API (client ID, cient Secret) en variebles de enorno backend y de manera segura.

5.- Auditoria de testeo de la API usando herramientas para segurar su seguridad y volver a implementar el metodo de pago.

6.- Despedir a un responsable...

## 7.- Anexo.
![Alerta seguridad de Paypal](./alertapaypal.png)
