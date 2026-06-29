FROM alpine:3.20

COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh

RUN echo "Installing things"

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
