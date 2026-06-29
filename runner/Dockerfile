FROM alpine:3.20

COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh

RUN echo "Installing things"
RUN echo "installing something else"

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
