# A4988-Stepper-Motor-Driver

 
TECNOLÓGICO NACIONAL DE MÉXICO
INSTITUTO TECNOLÓGICO DE TIJUANA

SUBDIRECCIÓN ACADÉMICA
(COORDINACION)
(ING. SISTEMAS COMPUTACIONALES)


MATERIA:
SISTEMAS PROGRAMABLE

CERTIFICADO: https://www.sololearn.com/certificates/course/en/25113221/1051/landscape/png

DOCENTE:
RENE SOLIS REYES

ALUMNO (A):
ZHENG HU KENNY #19210561



TIJUANA B.C. A 12 DE SEPTIEMBRE DE 2022


El uso de un driver Pololu para el control de un motor paso a paso nos simplifica mucho el trabajo ya que este driver se encarga de generar todas las señales necesarias para su funcionamiento y además nos añade las protecciones necesarias de temperatura y corriente. Otra ventaja que nos proporciona es que solo necesitaremos un par de puertos del micro, en este caso Arduino para controlarlo todo, dejando más puertos libres para otras funciones.

Este producto es una placa de soporte o una placa de arranque para el controlador del A4988 de Allegro con protección contra sobrecorriente. Estas son algunas de las características clave del controlador:

+ Interfaz de control de paso y dirección simple.
+ 6 resoluciones de pasos diferentes: paso completo, 1/2-paso, 1/4-paso, 1/8-paso, 1/16-paso y 1/32-paso.
+ Control de corte inteligente que selecciona automáticamente el modo correcto de caída de corriente (decaimiento rápido o decaimiento lento).
+ Desconexión térmica, bloqueo de bajo voltaje y protección contra cortocircuitos y carga en cortocircuito.
+ El control de corriente ajustable le permite configurar la salida de corriente máxima con un potenciómetro, que le permiten usar voltajes por encima del voltaje nominal de su motor paso a paso para lograr tasas de pasos más altas.

Fig. 2 Esquema del driver A4988

USANDO EL DRIVER
Conexiones de potencia: El controlador requiere un voltaje de suministro lógico (3 – 5.5 V) para ser conectado a través de los pines VDD y GND y un voltaje de suministro del motor (8 – 35 V) para ser conectado a través de VMOT y GND. Puede entregar hasta aprox. 1 A por fase sin disipador de calor o flujo de aire forzado. Conexiones MOTOR: Los motores paso a paso de 4, 6 y 8 cables pueden ser accionados por el A4988 si están conectados correctamente.

Tamaño de microespacio: Los motores paso a paso suelen tener una especificación de tamaño de paso (cómo 1.8° o 200 pasos por revolución), que se aplica a pasos completos. Un controlador de microprocesamiento como el A4988 permite resoluciones más altas al permitir ubicaciones de pasos intermedios. Que se logran energizando las bobinas con niveles de corriente intermedios. Por ejemplo, conducir un motor en el modo de cuarto de paso le dará al motor de 200 pasos por revolución 800 microsteps por revolución usando cuatro niveles de corriente diferentes.

Numero de pasos: Las entradas del selector de pasos (MS1, MS2 y MS3) permiten seleccionar de la resolución de uno de 5 pasos de acuerdo con la tabla siguiente. MS1 y MS3 tienen resistencias internas de 100kΩ y MS2 tiene una resistencia interna de 50kΩ, de manera que dejando estos tres pines de selección de microstep desconectados se obtiene el modo de paso completo. Para que los modos microstep funcionen correctamente, el límite de corriente debe establecerse lo suficientemente bajo para que la limitación de corriente se active. Si no es así, los niveles de corriente intermedios no se mantendrán correctamente, y el motor se saltará los pasos intermedios.

Fig. 3 Tabla microsteps.

Entradas de control: Cada pulso a la entrada STEP corresponde a un microstep del motor paso a paso en la dirección seleccionada por el pin DIR. Tenga en cuenta que los pines STEP y DIR no están conectados a un voltaje en particular internamente, por lo que no debe dejar ninguno de estos pines flotando en su aplicación. Si solo desea girar en una sola dirección, puede unir DIR directamente a VCC o GND. El chip tiene tres entradas diferentes para controlar sus muchos estados de energía: RST, SLP y EN. Tenga en cuenta que el pin RST está flotando; si no está utilizando el pin, puede conectarlo al pin SLP adyacente en el PCB para subirlo y habilitar el tablero.

Fig. 4 Esquema práctico general.

Es recomendable colocarle un pequeño radiador pegado con pasta térmica, incluso dotarle de un ventilador cuando trabajemos con altas corrientes.

¿Cómo proceder? cuando leemos algo como… Estoy usando un controlador el A4988 para alimentar un motor paso a paso, pero antes de conectar cualquier otra cosa al controlador del motor paso a paso, quiero saber cuánta corriente fluirá al pin VMOT del controlador. A continuación proporcionaremos unos pasos a seguir para responder a la pregunta.
