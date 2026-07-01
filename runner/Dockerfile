FROM alpine:3.20

COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh

RUN echo "Installing things"
RUN echo "installing something else"
RUN echo "Installing a new package"
RUN echo "doris"

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
