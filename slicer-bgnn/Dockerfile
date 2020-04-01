FROM stevepieper/slicer
MAINTAINER leipzig@gmail.com

#replace teh conf
RUN rm /etc/nginx/nginx.conf
COPY nginx.conf /etc/nginx/nginx.conf
COPY htpasswd /etc/nginx/.htpasswd
RUN nginx stop
RUN nginx -t


RUN mv /opt/slicer/Slicer /opt/slicer/orig_slicer
RUN SLICER_URL="https://download.slicer.org/bitstream/1216419" && \
  curl -v -s -L $SLICER_URL | tar xz -C /tmp && \
  mv /tmp/Slicer* /opt/slicer

#leipzig BGNN stuff
RUN git clone https://github.com/muratmaga/bgnn-related
RUN mv bgnn-related/.slicerrc.py


#COPY /root/INHSTools.py /opt/slicer/lib/Slicer-4.11/qt-scripted-modules/INHSTools.py

