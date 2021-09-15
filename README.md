# aws_EFS

Amazon Elastic File System es un servicio de almacenamiento en la nube proporcionado por Amazon Web Services diseñado para proporcionar almacenamiento escalable, elástico, concurrente con algunas restricciones, y almacenamiento de archivos cifrados para usar con los servicios en la nube de AWS y los recursos locales.

¿Qué funciones ofrece AWS Elastic File System?

Amazon EFS incluye las siguientes funciones:

Opciones de almacenamiento. Amazon EFS ofrece dos clases de almacenamiento para archivos: estándar y una zona. Ambas clases están diseñadas para manejar los datos a los que se accede con mayor y menor frecuencia. Con EFS Lifecycle Management, una organización puede reducir los costos al permitir la transferencia automática de archivos a los que se accede con poca frecuencia desde el almacenamiento estándar a EFS Standard-Infrequent Access o EFS One Zone-Infrequent Access.
Rendimiento escalable. Amazon EFS puede proporcionar el rendimiento, IOPS (entrada / salida por segundo) y baja latencia para admitir una variedad de cargas de trabajo. Está diseñado para hacer escalable el acceso y el almacenamiento de archivos, al tiempo que minimiza el tiempo dedicado a la administración.
Seguro y compatible. Amazon Virtual Private Cloud es un entorno de nube seguro y administrado que ejecuta aplicaciones dentro de AWS y controla el acceso de la red virtual a los sistemas de archivos. Amazon VPC permite a los desarrolladores crear VPC completamente aisladas de otras VPC en AWS. Esto proporciona control sobre las redes de AWS, incluida la selección del rango de direcciones IP, la creación de subredes y la configuración de tablas de rutas y puertas de enlace de red.
Además, el acceso a las aplicaciones se puede controlar con AWS Identity and Access Management ( IAM ), que es un conjunto de servicios para administrar usuarios, grupos, roles y políticas de AWS. Proporciona un servicio centralizado, que se puede utilizar para controlar el acceso a los recursos de AWS, así como para supervisar qué usuarios acceden a determinados recursos.

Opciones de copia de seguridad de Amazon EFS

AWS DataSync. DataSync ayuda a establecer y mantener una conexión permanente entre el almacenamiento de datos local y los sistemas de archivos de Amazon EFS, para mover fácilmente los datos entre los dos. DataSync se puede utilizar para importar y exportar regularmente grandes cantidades de datos, migraciones de datos únicas o para la replicación y recuperación de datos.

Copia de seguridad de AWS. Este servicio de respaldo administrado automatiza y rastrea las políticas de respaldo para Amazon EFS. Por ejemplo, cuando las aplicaciones se mueven a la nube, puede resultar difícil administrar los datos que residen en varios servicios sin la intervención manual. AWS Backup permite la configuración y auditoría de los recursos de AWS y automatiza la programación de copias de seguridad.

Familia de AWS Transfer. Este conjunto de servicios permite la transferencia de archivos dentro y fuera de Amazon EFS. Incluye tres servicios diferentes para transferencias de archivos: Protocolo seguro de transferencia de archivos, Protocolo de transferencia de archivos sobre SSL y Protocolo de transferencia de archivos.

Copia de seguridad de EFS a EFS. Este servicio de respaldo crea automáticamente respaldos incrementales de un archivo AWS EFS. Los recursos se pueden definir como código, lo que facilita la configuración, la implementación y la administración de una gran cantidad de recursos de AWS.

Amazon S3. Amazon S3 ( Simple Storage Service ) es un servicio web de AWS para almacenar datos como objetos dentro de una gran cantidad de depósitos de almacenamiento. Amazon S3 se escala automáticamente para adaptarse a grandes colecciones de datos, incluidos objetos de cualquier tamaño.

Glaciar Amazonas . Este servicio de almacenamiento en la nube proporciona un almacenamiento seguro y duradero para el archivo y la copia de seguridad de datos. Glacier está diseñado para datos a los que se accede con poca frecuencia que se pueden archivar y recuperar en un momento posterior.

Este servició solo funciona con instancias typo linux

Primer paso: 

Creamos nuestro sistema de archivos, para esto nos vamos al apartado de 

https://us-east-2.console.aws.amazon.com/efs/home?region=us-east-2#/file-systems

![image](https://user-images.githubusercontent.com/36380066/133524881-cba85416-0c4b-458b-892f-fb06c2a98f3b.png)

![image](https://user-images.githubusercontent.com/36380066/133525095-6df0765d-20bf-4484-9aaa-3aa82e6d4551.png)

Despues vamos a crear nuestras Instancias con las cuales estará trabajando nuestro sistema de archivos


![image](https://user-images.githubusercontent.com/36380066/133526002-9b3b1c76-6d06-4746-88f8-679d4af7f460.png)

Despues de que lo creamos agregamos un grupo de seguridad con el cual solo podrán ingresar a nuestro sistema de ficheros solas instancias que esten asociadas a ese grupo

https://us-east-2.console.aws.amazon.com/ec2/v2/home?region=us-east-2#SecurityGroups:

Seleccionamos la vpc en la cual estaría trabajando nuestras instancias y efs esto hará que se pueda accesar a efs

![image](https://user-images.githubusercontent.com/36380066/133491500-67dc9c7d-d13f-4f1e-8411-f19a5de8e3ab.png)

En esta opcion agregamos la vps en donde estan las instancias, esto permitira que solo las instancias asociadas puedan acceder a nuestro efs

![image](https://user-images.githubusercontent.com/36380066/133526378-950438eb-e284-4357-9987-7e2579901108.png)

Por ultimo solo queda montar nuestros volumenes en nuestras instancias

A traves de estos dos comandos y listo tendrías los volumenes montados en nuestras instancias.

![image](https://user-images.githubusercontent.com/36380066/133526523-f1bdf77b-e4c6-419a-8bf6-6391e7ca233d.png)




