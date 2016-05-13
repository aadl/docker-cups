FROM debian:stretch

MAINTAINER Ann Arbor District Library <github@aadl.org>

# Set apt sources list to a snapshot
COPY sources.list /etc/apt/

RUN apt-get -o Acquire::Check-Valid-Until=false update && apt-get -y install \
  cups=2.1.3* \
  cups-pdf \
  whois

RUN rm /usr/lib/cups/backend/parallel
RUN rm /usr/lib/cups/backend/serial
RUN rm /usr/lib/cups/backend/usb

COPY etc-cups /etc/cups

RUN mkdir -p /etc/cups/ssl
#VOLUME /etc/cups/
#VOLUME /var/log/cups
#VOLUME /var/spool/cups
#VOLUME /var/cache/cups

COPY etc-pam.d-cups /etc/pam.d/cups

COPY start_cups.sh /root/start_cups.sh
RUN chmod +x /root/start_cups.sh
CMD ["/root/start_cups.sh"]

EXPOSE 631
