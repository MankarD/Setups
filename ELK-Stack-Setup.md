# Setups
Java Tools And Setups

ELK Stack
Video : https://youtu.be/n2HHAvpn6Jo
ELK is the combination of 3 open source products

Elastic Search : It is used to store and process logs
Logstash : It is used to collect application logs and store in Elastic Search
Kibana : It will provide user interface to monitor application logs
ELK Setup
Download ELK Softwares

Elastic Search : https://www.elastic.co/downloads/elasticsearch
Kibana : https://www.elastic.co/downloads/kibana
Logstash : https://www.elastic.co/downloads/logstash
Extract all zip files

Run elasticsearch using elasticsearch.bat file (make sure all security settings disable in elasticsearch.yml before running)

 $ elasticsearch.bat
Check Elastic Search Running or not (URL : http://localhost:9200/ )

Run kibana using kibana.bat file (before running kibana, enable elasticsearch url in kibana.yml file)

 $ kibana.bat
Check Kibana running or not ( URL : http://localhost:5601/app/home )

Run Spring Boot Application and generate log file with log messages

create logstash.conf file like below

input {
  file {
	path => "C:/Users/ashok/classes/22-JRTP/workspace/SpringBoot_REST_API/app.log"
	start_position => "beginning"
  }
}

output {
  elasticsearch {
    hosts => ["http://localhost:9200"]
  }
}
Run logstash server using below command
logstash -f logstash-sample.conf

Check logstash server is running or not ( http://localhost:9600 )

Check application logs in Kibana dashboard
