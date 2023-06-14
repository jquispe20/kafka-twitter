# kafka-twitter
Proyecto de lectura y procesamiento de tweets en tiempo real

# Comandos útiles

Referencia Vim  
Es muy cómodo poder editar ficheros de texto directamente sobre la terminal. Prácticamente
todas las distribuciones de linux tienen un editor muy conocido llamado vi o vim. Los comandos
que muestro a continuación son los básicos para abrir un fichero, poder editarlo y guardar los
cambios.

Abrir un fichero con vim:  
vim fichero.txt

Para entrar en el modo de escritura una vez que hemos abierto el fichero deberemos pulsar la
tecla “i”.  
Para salir del modo de escritura deberemos pulsar la tecla “ESC”  
Para salir del fichero y guardar los cambios bastará con salir del modo escritura, escribir “wq”

Comandos para Apache Kafka
- Ejecutar Zookeeper:  
./bin/zookeeper-server-start.sh config/zookeeper.properties  
C:\kafka_2.13-3.2.0\bin\windows> .\zookeeper-server-start.bat ..\..\config\zookeeper.properties

- Ejecutar Broker de Kafka:  
./bin/kafka-server-start.sh config/server.properties

- Crear un topic de Kafka con factor de replicación de 3 y dos particiones:  
./bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 3 --partitions 2 --topic testtopic

- Visualizar detalles de un topic de Kafka:  
./bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic testtopic

- Listar los topics de Kafka:  
./bin/kafka-topics.sh --list --zookeeper localhost:2181

- Ejecutar consumidor de consola de Kafka sobre un topic:  
./bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic testtopic --group grupo1

- Ejecutar productor de consola de Kafka sobre un topic:  
./bin/kafka-console-producer.sh --broker-list localhost:9092,localhost:9093,localhost:9094 --topic testtopic

- Describir los grupos de consumidores en Kafka:  
./bin/kafka-consumer-groups.sh --bootstrap-server localhost:9092 --group grupo1 --describe

- Ejecutar Kafka Mirror Maker sobre un topic con la configuración del consumidor y productor:  
./bin/kafka-mirror-maker.sh --consumer.config config/consumer.properties --producer.config config/producer.properties --whitelist testtopic

# Kafka
- Plataforma distribuida de transmisión de datos
- Permite publicar, almacenar, procesar flujos de datos en tiempo real
- Permite desacoplar las fuentes de datos de los consumidores 
- Las fuentes de datos se conectaran a kafka para depositar sus datos
- Apache kafka permite desacoplar aplicaciones entre si que necesitan comunicarse mediante mediante paso de mensajes en tiempo real
- En apache kafka se pueden depositar mensajes de cualquier fuente de datos en forma de eventos
- Los consumidores pueden ser cualquier sistema como bases de datos y herramientas analíticas
- Integración sencilla con tecnologías big data Spark, Hadoop, Flink

# Casos de uso
- Procesamiento en Streaming
- Gestión de logs
- Sistema de recomendaciones en tiempo real
- Recolección de datos e interacciones de usuario en tiempo real 

# Broker intermediario
- Enrutan los mensajes
- Desacoplan las aplicaciones productoras de consumidores
- Organizan y comprueban mensajes
- Almacenan los mensajes
