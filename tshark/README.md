# vajra-tshark

Use following commands to build and run the image
docker build -t pbhalesain/tshark:1.99.8 .
docker run --cap-add net_raw --cap-add net_admin -it pbhalesain/tshark:1.99.8 tshark -i eth0

to analyse local pcap file

Add the file as a volume first and then run tshark on the added file
docker run --cap-add net_raw --cap-add net_admin -v /Users/pbhalesain/clients/setient/ContainNSM/example.pcap:/data/example.pcap -it pbhalesain/tshark:1.99.8 tshark -r /data/example.pca
