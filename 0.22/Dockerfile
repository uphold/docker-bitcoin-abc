FROM bitcoinabc/bitcoin-abc-bchn:0.22.7

ENV BITCOIN_ABC_DATA=/bitcoin/.bitcoin
ENV BITCOIN_ABC_VERSION=0.22.7
ENV PATH=/opt/bitcoin-abc-${BITCOIN_ABC_VERSION}/bin:$PATH

COPY docker-entrypoint.sh /entrypoint.sh

EXPOSE 8332 8333 18332 18333 18444

ENTRYPOINT ["/entrypoint.sh"]
