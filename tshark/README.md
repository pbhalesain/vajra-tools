# vajra-tshark

Use following commands to build and run the image
docker build -t pbhalesain/tshark:1.99.8 .
docker run --cap-add net_raw --cap-add net_admin -it pbhalesain/tshark:1.99.8 tshark -i eth0
:
