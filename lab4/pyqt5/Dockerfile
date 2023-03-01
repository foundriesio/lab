# docker build -t my-pyqt5:latest .
#
#
# docker run -it -d -v /run/user/63:/run/user/63 -v /dev/dri:/dev/dri -v /dev/pvr_sync:/dev/pvr_sync --device-cgroup-rule='c 226:* rmw' --device-cgroup-rule='c 10:* rmw' --env QT_QPA_PLATFORM=wayland –env WAYLAND_DISPLAY="wayland-0" my-pyqt5:latest

FROM munoz0raul/pyqt5:latest

LABEL maintainer="Name <email@email.com>"

ENV WAYLAND_DISPLAY="wayland-0"

COPY hello.py /hello.py

ENTRYPOINT ["python3"]
CMD [ "/hello.py" ]