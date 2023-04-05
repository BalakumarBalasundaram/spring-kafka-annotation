 Integrate Spring Boot with Apache Kafka for streaming data
 
Let's take a look at what each of these annotations and methods do:
•	@EnableKafkaStreams: This annotation is used to enable Kafka Streams in a Spring Boot application.
•	@Value("${spring.kafka.bootstrap-servers}"): This annotation is used to inject spring.kafka.bootstrap-serversthe attribute into bootstrapServersthe field.
•	@Value("${spring.kafka.streams.properties.application.id}"): This annotation is used to inject spring.kafka.streams.properties.application.idproperties into applicationIdthe field.
•	@Value("${spring.kafka.streams.properties.commit.interval.ms}"): This annotation is used to inject spring.kafka.streams.properties.commit.interval.msthe attribute into commitIntervalMsthe field.
•	@Value("${spring.kafka.streams.properties.default.key.serde}"): This annotation is used to inject spring.kafka.streams.properties.default.key.serdethe attribute into defaultKeySerdethe field.
•	@Value("${spring.kafka.streams.properties.default.value.serde}"): This annotation is used to inject spring.kafka.streams.properties.default.value.serdethe attribute into defaultValueSerdethe field.
•	public static void main(String[] args): This is KafkaStreamsApplicationthe main method of the class. This method is used to start a Spring Boot application.
•	@Bean: This annotation is used to indicate that the method-generated bean can be injected into other Spring-managed beans.
•	StreamsBuilderFactoryBeanCustomizer streamsBuilderFactoryBeanCustomizer(): This method is used to create StreamsBuilderFactoryBeanCustomizerthe bean. This bean is used to customize the StreamsBuilderFactoryBean.
•	public void customize(StreamsBuilderFactoryBean streamsBuilderFactoryBean): This StreamsBuilderFactoryBeanCustomizeris customizethe method of the interface. This method is used for custom StreamsBuilderFactoryBean.
•	streamsBuilderFactoryBean.setBootstrapServers(bootstrapServers);: This line is used to StreamsBuilderFactoryBeanset the bootstrap server for .
•	streamsBuilderFactoryBean.setApplicationId(applicationId);: This line is used to set the application ID StreamsBuilderFactoryBeanof .
•	streamsBuilderFactoryBean.setCommitInterval(Long.parseLong(commitIntervalMs));: This line is used to StreamsBuilderFactoryBeanset the commit interval for .
•	streamsBuilderFactoryBean.setDefaultKeySerde(Serdes.String());: This line is used to StreamsBuilderFactoryBeanset the default key for serde.
•	streamsBuilderFactoryBean.setDefaultValueSerde(Serdes.String());: This line is used to set the default value StreamsBuilderFactoryBeanof serde.
•	@Bean: This annotation is used to indicate that the method-generated bean can be injected into other Spring-managed beans.
•	KStream<String, String> kStream(StreamsBuilder kStreamBuilder): This method is used to create KStreamthe bean. This bean is used to represent a stream processing topology.
•	KStream<String, String> stream = kStreamBuilder.stream("input-topic");: This line is used to create one from the input topic KStream.
•	stream.to("output-topic");: This line is used to write data KStreamfrom to the output topic.
•	return stream;: This line is used to return KStream.
