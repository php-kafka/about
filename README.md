# PHP Kafka
## Description
This is an effort to collect all things related PHP Kafka in one place  
and give everybody a better information about what is available in our ecosystem.  
If your project is missing, please feel free to create a PR to add it.

## Kafka Integration
### C binding
[librdkafka](https://github.com/edenhill/librdkafka) is a C binding that is used by many  
official language bindings of [Confluent](https://www.confluent.io/), e.g. for Go, Python, C#, etc.  
It is also used in the extensions and bindings for PHP created by the community.

### Extensions
#### arnaud-lb/php-rdkafka
This is the oldest extension and its source can be found [here](https://github.com/arnaud-lb/php-rdkafka).  
Its goal is to stay as close as possible to the API of librdafka.  
It has a very large spectrum of support:
- PHP5 - PHP8
- librdkafka v0.11.6 - latest

#### php-kafka/php-kafka
This is a new extension, created by a contributor of php-rdkafka. The source can be found [here](https://github.com/php-kafka/php-kafka).  
Its goal is to reduce complexity of the librdkafka API and to move faster in terms of adoption.  
It will only support PHP versions that are not EOL and librdkafka versions that are not outdated (roughly 1year).  

### FFI binding
#### idealo/php-rdkafka-ffi
Is an FFI binding that sticks as closely as possibly to the API of php-rdkafka. The source can be found [here](https://github.com/idealo/php-rdkafka-ffi).  
It also offers Admin API (create, alter topics, etc.), which none of the extensions offer so far.

### PHP bindings
#### weiboad/kafka-php
This project was the most popular pure PHP implementation. Its source can be found [here](https://github.com/weiboad/kafka-php).  
The project has not received any attention in over a year, but there was activity in December 2020, maybe the project will be revived.

## Kafka Schema registry
### flix-tech/schema-registry-php-client
Is a REST client to interact with the Kafka schema registry. Its source can be found [here](https://github.com/flix-tech/schema-registry-php-client)
### jobcloud/php-kafka-schema-registry-client
Is a REST client to interact with the Kafka schema registry. Its source can be found [here](https://github.com/jobcloud/php-kafka-schema-registry-client)
### jobcloud/php-console-kafka-schema-registry
Is a project providing symfony console commands to interact with the Kafka schema registry  
Useful for CI / CD for schemas. Its source can be found [here](https://github.com/jobcloud/php-console-kafka-schema-registry).

## PHP libraries
### Description
These libraries use the php extensions and try to make it easier to use the extensions  
and give a more fluid interface / simpler usage, etc.
### php-enqueue/enqueue-dev
Is a project that supports many messaging / streaming tranpsorts besides Kafka (php-rdkafka).  
It integrates easy with Symfony, Laravel, Yii and other PHP framworks / projects. Its source can be found [here](https://github.com/php-enqueue/enqueue-dev)
### jobcloud/php-kafka-lib
Is a very lightweight library, to help use php-rdkafka in an easier and more readable way.  
New features of the extension are adopted in a fast manner. Its source can be found [here](https://github.com/jobcloud/php-kafka-lib)

## Avro
### Description
Avro is a way to define schemas for your messages. This helps improve service communication.  
In the strictest form it allows applications not to break as the schemas evolves.  
It is highly advised to use schemas for your messages.  
You can read more about compatibility [here](https://docs.confluent.io/platform/current/schema-registry/avro.html)
### apache/avro
Official avro support, but no composer integration as of now. The source can be found [here](https://github.com/apache/avro/tree/master/lang/php)
### flix-tech/avro-serde-php
Used for serialization / deserialization of avro messages, can be used async.  
jobcloud/php-kafka-lib uses this library for Avro support.
The source can be found [here](https://github.com/flix-tech/avro-serde-php)
### wikimedia/avro-php
Fork of the offical apache repository with additional fixes. Its source can be found [here](https://github.com/wikimedia/avro-php)

### Avro generator / subschema helpers
#### Description
Avro schemas can get very complex, especially if you have a nested data structure. It is desirable to  
seperate these nested structures in sub-schemas. To do this, we need a tool, that will merge a schema  
and all its sub schemas into a valid schema.
### flix-tech/avro-serde-php
Provides the possibility to create schema with a builder and also to merge schema. Its source can be found [here](https://github.com/flix-tech/avro-serde-php)
### php-kafka/php-avro-schema-generator
Is a small helper library to create a schema from classes (alpha) and to merge schema.  
Its source can be found [here](https://github.com/php-kafka/php-avro-schema-generator)

## Protobuf
### Description
Apache Kafka also supports schema in Protobuf. I have no more info atm, as i am using Avro.  
Contributions for projects, etc. are welcome

## Code examples (producer / consumer)
### php-kafka/php-kafka-examples
Provides examples for extensions in usage with libraries. See examples [here](https://github.com/php-kafka/php-kafka-examples)

## Learning / resources
- [Confluent blog](https://www.confluent.io/blog) has a lot of good articles
- [Enterprise integration patterns](https://www.enterpriseintegrationpatterns.com/) a fantastic book that is still very relevant
- [Designing event driven systems](https://www.confluent.io/designing-event-driven-systems/)
- [Kafka the definitive guide](https://www.confluent.io/resources/kafka-the-definitive-guide/) deep dive into Apache Kafka