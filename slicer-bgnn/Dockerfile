FROM stevepieper/slicer
MAINTAINER leipzig@gmail.com

#replace teh conf
RUN rm /etc/nginx/nginx.conf
COPY nginx.conf /etc/nginx/nginx.conf
COPY htpasswd /etc/nginx/.htpasswd
#RUN nginx -t

COPY 1227656.tar.gz /tmp/1227656.tar.gz
RUN gunzip /tmp/1227656.tar.gz && tar -xvf /tmp/1227656.tar
RUN mv /opt/slicer/Slicer /opt/slicer/orig_slicer
RUN mv Slicer-4.11.0-2020-04-01-linux-amd64 /opt/slicer/Slicer

#leipzig BGNN stuff
RUN wget https://github.com/hdr-bgnn/bgnn_related/archive/1.0.tar.gz
RUN tar -xvf 1.0.tar.gz
RUN mv bgnn_related-1.0/.slicerrc.py /home/researcher/.slicerrc.py
RUN mv bgnn_related-1.0 /home/researcher/bgnn_related

ENV labs="${labs}"

#COPY /root/INHSTools.py /opt/slicer/lib/Slicer-4.11/qt-scripted-modules/INHSTools.py

