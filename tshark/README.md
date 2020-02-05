# vajra-tshark

Use following commands to build and run the image
docker build -t pbhalesain/tshark:1.99.8 .
docker run --cap-add net_raw --cap-add net_admin -it pbhalesain/tshark:1.99.8 tshark -i eth0

to analyse local pcap file

Add the file as a volume first and then run tshark on the added file
docker run --cap-add net_raw --cap-add net_admin -v /Users/pbhalesain/clients/setient/ContainNSM/example.pcap:/data/example.pcap -it pbhalesain/tshark:1.99.8 tshark -r /data/example.pca

docker run --cap-add net_raw --cap-add net_admin -v /Users/pbhalesain/clients/setient/vajra-tools/tshark/example.pcap:/data/example.pcap -it pbhalesain/tshark:1.99.8 tshark -r /data/example.pcap -T fields -e frame.number -e frame.time_relative -e wlan.sa -e wlan.da -e wlan.ta -e wlan.ra -e frame.time_delta_displayed -e frame.len -E header=y -E separator=, -E quote=d -E occurrence=f


docker run --cap-add net_raw --cap-add net_admin -v /Users/pbhalesain/clients/setient/vajra-tools/tshark/example.pcap:/data/example.pcap -it pbhalesain/tshark:1.99.8 tshark -r /data/example.pcap -T fields -e frame.number -e frame.time -e eth.src -e eth.dst -e ip.src -e ip.dst -e ip.proto -E header=y -E separator=, -E quote=d -E occurrence=f 
