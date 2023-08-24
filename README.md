# Wi-Fi Association_Disassociation Dataset

This project aims to generate a real-time dataset for intrusion detection systems (IDS) in IEEE 802.11 (Wi-Fi) environments, with the main focus on de-authentication and disassociation attacks detection. 
This dataset is part of the main goal of our research, which aims to propose a novel IDS for de-authentication and disassociation attack detection and advance the development of IDSs in all real-world Wi-Fi network infrastructures. To accomplish this, de-authentication and disassociation attacks are executed on a Wi-Fi testbed consisting of 16 devices.

The following illustrates the main objectives of the Wi-Fi De-authentication_Disassociation dataset project:

- building new realistic testbed for de-authentication and disassociation attack datasets 
- generating normal Wi-Fi traffic data using real user devices and launching attacks using two different tools (Kali Linux and Deauther)
- building an automated process that collects, parses, visualizes and analyzes the the network traffic data built on top of Elastic Stack (Elasticsearch, Logstash, and Kibana)
- producing a structured dataset that can be used for further steps in machine/deep learning-based IDS development
- futher preprocessing this dataset and useing it in our IDS development called "Transfer and CNN-Based IDS for De-authentication (Disassociation) DoS Attack Detection";

This Wi-Fi De-authentication_Disassociation dataset project and activities around it can be summarized in the following steps:

## Testbed Setup ##
Our testbed setup was configured as follows:
- 16 client devices which consists of smartphones, tablets, laptops, desktops, and raspberry PIs
- access point which is configured using OPenWrt
- attackers: two different machies are used:
  - attacker1 is configured on a 64-bit Windows 11 machine where a NodeMCU device loaded with deauther tool is connected into
  - attacker2 is configured on Kali Linux virtual machine hosted on a 64-bit Windows 11 machine along with a wireless adaptor (Atheros AR9271) plugted into the network interface  of the host machine
- another  64-bit Windows machine hosts ELK and collects traffic from the access point, parses, stores, analyzes and generates a structured dataset 

The testbed setup can be represented by the following two logical topologies:

![](images/Wi-Fi_traffic_generator_and_attacks_module.png)

The above topoloy shows the logical setup of the client devices for normal traffic, the two attackers carried out from the Kali Linux machine and NodeMCU Deauther tool configured machine, and the OpenWrt-based access point. 
The topoloy below shows the setup for attack and normal traffic collection from the access point and parsing the unstructured traffic data through logstash and developed parsing algorithm, storing at Elasticsearch, analysis and visualization of the structured data by Kibana, and finally generating the dataset which is ready for further machine learning pre-processing. 

![](images/Colleting_parsing_storing_generating_module_v2.png) 
