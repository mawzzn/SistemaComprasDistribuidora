HEAD

# SistemaComprasDistribuidora

\# compilacion

javac SistemaComprasDistribuidora.java

\# ejecucion

java SistemaComprasDistribuidora

\# datos recomendados

Cliente: Pedro Morales

Total compra: $42000

Distancia: 12 km

Vehículo: Chevrolet N300, 1200, Gasolina, 2 pasajeros

Resultado esperado: $42000 + (12 × $150) = $43800

# SistemaComprasDistribuidora

ef9eebeb20e612d7e76532b78a1accdf3b01a831



\## Descripción del Proyecto

Sistema integral para gestión de compras y cálculo automático de costos de envío a domicilio para una distribuidora de alimentos, desarrollado en Java puro sin herramientas IDE.

\## Contexto del Negocio

Una empresa de distribución de alimentos ha implementado un servicio de despacho a domicilio con las siguientes características:

•	Radio de cobertura: 20 kilómetros

•	Tarifas diferenciadas según monto de compra

•	Registro de información del vehículo de reparto

•	Cálculo automático de costos totales

\## Requerimientos Funcionales

\# RF-1 - Registro de Cliente

•	Descripción: El sistema debe capturar información básica del cliente

•	Criterio de Aceptación: 

	Solicitar nombre completo del cliente

	Validar entrada de datos no vacía

\# RF-2 - Registro de Compra

•	Descripción: El sistema debe registrar el monto total de la compra

•	Criterio de Aceptación: 

	Aceptar valores numéricos decimales

	Mostrar formato monetario con símbolo de pesos

\# RF-3 - Cálculo de Distancia

•	Descripción: El sistema debe registrar la distancia de envío

•	Criterio de Aceptación: 

	Aceptar distancias en kilómetros (decimal)

	Validar que no exceda el radio de cobertura (20 km)

 

\# RF-4 - Registro de Vehículo de Reparto

•	Descripción: El sistema debe capturar información del vehículo asignado

•	Criterio de Aceptación: 

	Marca (String)

	Modelo (String)

	Cilindrada (int)

	Tipo de combustible (String)

	Capacidad de pasajeros (int)

\# RF-5 - Aplicación de Reglas de Negocio

•	Descripción: El sistema debe calcular costo de envío según reglas establecidas

•	Criterios de Aceptación: 

	Compra ≥ $50,000: Envío GRATUITO

	Compra $25,000 - $49,999: $150 por kilómetro

	Compra < $25,000: $300 por kilómetro

	Distancia > 20 km: Rechazar pedido

\# RF-6 - Cálculo de Total Final

•	Descripción: El sistema debe sumar compra + costo de envío

•	Criterio de Aceptación: 

	Operación aritmética correcta

	Mostrar desglose detallado

	Formato monetario apropiado

\# RF-7 - Generación de Resumen

•	Descripción: El sistema debe mostrar resumen completo del pedido

•	Criterio de Aceptación: 

	Datos del cliente

	Detalles de la compra

	Cálculo del envío

	Información del vehículo

	Total final

 

\## Requerimientos No Funcionales

\# RNF-1 - Portabilidad

•	Descripción: El sistema debe ejecutarse en cualquier plataforma con JVM

•	Criterio de Aceptación: Funcionar en Windows, Linux, macOS sin modificaciones

\# RNF-2 - Compilación Manual

•	Descripción: El código debe compilarse exclusivamente con javac

•	Criterio de Aceptación: 

	Sin dependencias de IDE

•	Compilación exitosa por línea de comandos

\# RNF-3 - Usabilidad

•	Descripción: Interfaz de consola clara y comprensible

•	Criterio de Aceptación: 

	Mensajes descriptivos para cada entrada

	Formato visual organizado

	Instrucciones claras

\# RNF-4 - Manejo de Memoria

•	Descripción: Gestión eficiente de recursos del sistema

•	Criterio de Aceptación: 

	Cerrar Scanner correctamente

	Sin memory leaks

\# RNF-5 - Mantenibilidad

•	Descripción: Código legible y bien documentado

•	Criterio de Aceptación: 

	100% del código comentado

	Nombres de variables descriptivos

	Estructura lógica clara

 

\# RNF-6 - Precisión de Cálculos

•	Descripción: Operaciones monetarias precisas

•	Criterio de Aceptación: 

	Uso de tipo double para decimales

	Formateo apropiado de moneda



\## F.- Historias de Usuario - Sistema de Distribuidora de Alimentos

Historia de Usuario 1: Realizar Pedido con Cálculo Automático

Como cliente de la distribuidora Quiero realizar un pedido y que el sistema calcule automáticamente el costo de envío Para conocer el total exacto que debo pagar antes de confirmar mi pedido

Criterios de Aceptación:

•	Poder ingresar mi nombre completo

•	Poder ingresar el monto total de mi compra

•	Poder ingresar la distancia desde mi hogar

•	El sistema debe calcular automáticamente el costo de envío según las reglas

•	Debe mostrarme un resumen detallado con todos los costos

Supuestos:

•	El cliente conoce la distancia aproximada desde la distribuidora

•	El cliente tiene el total exacto de su compra

•	La distancia está dentro del radio de cobertura

Definición de Terminado:

•	El cálculo es matemáticamente correcto según las reglas de negocio

•	Se muestra desglose completo de costos

•	El formato de salida es claro y profesional



\## Historia de Usuario 2: Verificar Elegibilidad para Envío Gratis

Como cliente frecuente Quiero saber si mi compra califica para envío gratuito Para planificar mis compras y obtener el mejor beneficio

Criterios de Aceptación:

•	Si mi compra es ≥ $50,000, debe mostrar "ENVÍO GRATIS"

•	Debe explicar claramente por qué califico para envío gratis

•	El costo de envío debe aparecer como $0 en el resumen

Supuestos:

•	El cliente está dentro del radio de 20 km

•	El monto ingresado es correcto

Definición de Terminado:

•	Mensaje de felicitación por envío gratis

•	Costo de envío = 0 en cálculos

•	Resumen muestra claramente el beneficio obtenido



\## Historia de Usuario 3: Obtener Tarifa Preferencial

Como cliente con compra mediana Quiero acceder a la tarifa preferencial de $150/km Para pagar menos por el envío que la tarifa estándar

Criterios de Aceptación:

•	Para compras entre $25,000 - $49,999 aplicar tarifa de $150/km

•	Mostrar mensaje explicando la tarifa preferencial

•	Calcular correctamente: distancia × $150

Supuestos:

•	La compra está en el rango especificado

•	La distancia es válida (≤ 20 km)

Definición de Terminado:

•	Cálculo correcto de envío con tarifa $150/km

•	Mensaje informativo sobre tarifa preferencial

•	Desglose detallado en el resumen



\## Historia de Usuario 4: Registrar Información del Vehículo de Reparto

Como administrador de la distribuidora Quiero registrar los datos del vehículo asignado al pedido Para tener control del inventario de vehículos y seguimiento de envíos

Criterios de Aceptación:

•	Capturar marca del vehículo

•	Capturar modelo del vehículo

•	Capturar cilindrada (número entero)

•	Capturar tipo de combustible

•	Capturar capacidad de pasajeros

•	Mostrar toda la información en el resumen final

Supuestos:

•	El administrador conoce las especificaciones del vehículo

•	Los datos son veraces y actualizados

Definición de Terminado:

•	Todos los campos de vehículo completados

•	Información mostrada en formato especificado

•	Datos almacenados correctamente en variables



\## Historia de Usuario 005: Validar Radio de Cobertura

Como cliente potencial Quiero saber si mi ubicación está dentro del área de cobertura Para confirmar si puedo recibir el servicio de envío

Criterios de Aceptación:

•	Si la distancia > 20 km, mostrar mensaje de "fuera de cobertura"

•	Explicar claramente que no se puede realizar el envío

•	No realizar cálculos de costo si está fuera del área

Supuestos:

•	El cliente proporciona la distancia real

•	La medición se hace en línea recta

Definición de Terminado:

•	Validación correcta de distancia máxima

•	Mensaje claro de rechazo cuando corresponda

•	No procesamiento de pedidos fuera del área



\## Historia de Usuario 6: Obtener Resumen Detallado del Pedido

Como cliente que confirma su pedido Quiero ver un resumen completo y detallado Para verificar que toda la información es correcta antes del pago

Criterios de Aceptación:

•	Mostrar mis datos personales

•	Mostrar monto de compra original

•	Mostrar distancia de envío

•	Mostrar cálculo del costo de envío (si aplica)

•	Mostrar total final claramente

•	Mostrar información del vehículo asignado

Supuestos:

•	Todos los datos ingresados son correctos

•	El cliente puede leer y entender el formato de salida

Definición de Terminado:

•	Formato visual atractivo y organizado

•	Todos los elementos requeridos presentes

•	Cálculos matemáticamente correctos

•	Información del vehículo completa



\## Historia de Usuario 007: Sistema Sin Dependencias Externas

Como desarrollador o usuario técnico Quiero que el sistema funcione solo con Java básico Para poder ejecutarlo en cualquier ambiente sin instalaciones adicionales

Criterios de Aceptación:

•	Compilar únicamente con javac

•	Ejecutar únicamente con java

•	No requerir librerías externas

•	Funcionar en Windows, Linux y macOS

Supuestos:

•	JDK está correctamente instalado

•	Variables de entorno configuradas

Definición de Terminado:

•	Compilación exitosa por línea de comandos

•	Ejecución correcta en diferentes sistemas operativos

•	Sin errores de dependencias faltantes





