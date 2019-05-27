Building this example:
sudo docker build -t chat1 --build-arg PORT_NO=6666
sudo docker build -t chat2 --build-arg PORT_NO=6668

Running this example:
sudo docker run --rm -it --network host --name chat1 chat1
sudo docker run --rm -it --network host --name chat2 chat2
