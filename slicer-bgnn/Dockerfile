FROM stevepieper/slicer
MAINTAINER leipzig@gmail.com

#replace the conf
RUN rm /etc/nginx/nginx.conf
COPY nginx.conf /etc/nginx/nginx.conf
COPY htpasswd /etc/nginx/.htpasswd

#newer slicer
COPY 1227656.tar.gz /tmp/1227656.tar.gz
RUN gunzip /tmp/1227656.tar.gz && tar -xvf /tmp/1227656.tar
RUN mv /opt/slicer /opt/orig_slicer
RUN mv Slicer-4.11.0-2020-04-01-linux-amd64 /opt/slicer

#leipzig BGNN stuff
ARG bgnnver=1.5
RUN wget https://github.com/hdr-bgnn/bgnn_related/archive/${bgnnver}.tar.gz
RUN tar -xvf ${bgnnver}.tar.gz
RUN mv bgnn_related-${bgnnver}/.slicerrc.py /home/researcher/.slicerrc.py
RUN mv bgnn_related-${bgnnver} /home/researcher/bgnn_related

#lab assignments
ENV labs="${labs}"
ENV SLICER_ARGUMENTS="--additional-module-paths /home/researcher/bgnn_related"
