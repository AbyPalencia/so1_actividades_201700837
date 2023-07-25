# ¿Qué es Kernel?

Se conoce como kernel a la sección más esencial de un sistema operativo. Consiste en la parte que se ocupa de ingresar a los diversos dispositivos que posee un ordenador.

De igual forma, el kernel ordena la forma en la que se ejecutan las diferentes aplicaciones que se cargan en memoria. De esta forma, el kernel trabaja las piezas más importantes de un sistema operativo, trabajando como árbitro entre el hardware y el software.

<p align="center">
    <img width="260" height="200" src="https://tiposde.com/wp-content/uploads/Tipos-de-kernel-400x316.png">
</p>

# Tipos de Kernel

## Exonúcleos

Este tipo de kernel se denomina también sistema operativo verticalmente estructurado, simboliza un acercamiento nuevo y radical a la producción de sistemas operativos. La noción profunda es facilitar que el productor tome todas las decisiones vinculadas a la productividad del hardware.

Los exonúcleos son muy diminutos, debido a que su funcionalidad se vincula únicamente al resguardo y el multiplexado de los materiales. Se denominan de esta forma debido a que toda la funcionalidad deja de estar presente en la memoria y pasa a estar en el exterior, en librerías activas.

## Núcleos monolíticos

Estas estructuras poseen un núcleo enorme y complicado, que abarca todos los servicios del sistema. Está diseñado de manera no modular, y tiene un funcionamiento mayor que el micronúcleo.

## Micro-núcleos o Microkernel

Consisten en núcleos de reducido tamaño que fueron generados sólo con los requerimientos más sencillos del sistema operativo. Las demás funciones son agregadas a través de la suma de módulos exteriores al núcleo, lo que les otorga flexibilidad y permite la extensión. Se consideran más seguros que el kernel monolítico.

## Núcleos híbridos

Consiste en una estructura fundamentada en la unión de microkernel y el núcleo monolítico, dichos sistemas son empleados dentro de los ordenadores mediante los sistemas operativos

<p align="center">
    <img width="260" height="200" src="https://tiposde.com/wp-content/uploads/N%C3%BAcleos-h%C3%ADbridos.png">
</p>

Una cualidad esencial que tiene el núcleo híbrido es que insertan un código extra con el propósito de mejorar la productividad.

Al contrario de los núcleos monolíticos comunes, los controladores de ordenadores y las dimensiones al sistema operativo se pueden descargar o cargar de forma fácil como si fueran módulos, mientras la estructura sigue funcionando sin inconvenientes.

De igual forma, al contrario del kernel monolítico tradicional, es posible que los controladores sean prevolcados (retenidos de forma breve por ejercicios más esenciales) bajo diversas estipulaciones. Esta capacidad fue añadida para trabajar de forma apropiada las suspensiones de hardware, y para beneficiar la base de multiproceso proporcionado.

# Modo Usuario vs Modo Kernel

<p align="center">
    <img width="260" height="200" src="https://learn.microsoft.com/es-es/windows-hardware/drivers/gettingstarted/images/userandkernelmode01.png">
</p>

## Modo Usuario

Al iniciar una aplicación en modo de usuario, Windows crea un proceso para la aplicación. El proceso proporciona a la aplicación un espacio de direcciones virtuales privado y una tabla de identificadores privados. Dado que el espacio de direcciones virtuales de una aplicación es privado, una aplicación no puede modificar los datos que pertenecen a otra aplicación. Cada aplicación se ejecuta de forma aislada y, si una aplicación se bloquea, el bloqueo se limita a esa aplicación. Otras aplicaciones y el sistema operativo no se ven afectados por el bloqueo.

Además de ser privado, el espacio de direcciones virtuales de una aplicación en modo de usuario está limitado. Un proceso que se ejecuta en modo de usuario no puede acceder a direcciones virtuales reservadas para el sistema operativo. Limitar el espacio de direcciones virtuales de una aplicación en modo de usuario impide que la aplicación altere y, posiblemente, dañe los datos críticos del sistema operativo.

## Modo Kernel

Todo el código que se ejecuta en modo kernel comparte un único espacio de direcciones virtuales. Por lo tanto, un controlador en modo kernel no está aislado de otros controladores y del propio sistema operativo. Si un controlador en modo kernel escribe accidentalmente en la dirección virtual incorrecta, los datos que pertenecen al sistema operativo u otro controlador podrían verse comprometidos. Si se bloquea un controlador en modo kernel, se bloquea todo el sistema operativo.

Cuando los programas que se ejecutan en modo de usuario necesitan acceso al hardware, por ejemplo, cámara web, primero tiene que pasar por el kernel mediante un syscall, y para llevar a cabo estas solicitudes, la CPU cambia del modo de usuario al modo kernel en el momento de la ejecución. Después de completar finalmente la ejecución del proceso, la CPU vuelve a cambiar al modo de usuario.