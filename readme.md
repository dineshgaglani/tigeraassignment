creating an image for the docker : \
docker build . -t tigeraassignmentimage

Starting a container for the image: \
docker run -p 8000:8000 tigeraassignmentimage

To run the blackbox test, on the host machine shell, type the below lines \
pip install pytest \
pytest testjokeapi.py

Incase you want to execute the test on the python-django server container itself:\
docker cp testjokeapi.py <container id>:/assignment/ \
docker exec -it <container id> sh \
pip install pytest \
pytest testjokeapi.py


Description:
The project combidocker exec 02fd34873da8 nes 2 apis into 1, the tests are a part of tigera/assignment/tigeraassignment/tigeraassignment/tests folder
There are 4 unit tests: \
Happy path \
First redocker cp testjokeapi.py 02fd34873da8:/assignment/sponse returns incorrect for first name \
First response returns incorrect for last name \
First response fails \

An additional test that did not pass is: non-ASCII character returned in first request

Another black box test that verifies if the server is up is in the testjokeapi.py file
The output the file returns is below: \
docker cp testjokeapi.py "<container-id>":/assignment/ \
docker exec "<container-id>" pip install pytest \
docker exec "<container-id>" pytest testjokeapi.py \
============================= test session starts ==============================
platform linux2 -- Python 2.7.16, pytest-4.6.2, py-1.8.0, pluggy-0.12.0
rootdir: /assignment
collected 1 item

testjokeapi.py .                                                         [100%]

=========================== 1 passed in 1.16 seconds ===========================
