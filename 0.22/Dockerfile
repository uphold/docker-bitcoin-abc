FROM bitcoinabc/bitcoin-abc-bchn:0.22.7

ENV BITCOIN_ABC_DATA=/home/bitcoin/.bitcoin
ENV BITCOIN_ABC_VERSION=0.22.7
ENV PATH=/opt/bitcoin-abc-${BITCOIN_ABC_VERSION}/bin:$PATH

VOLUME ["/home/bitcoin/.bitcoin"]

EXPOSE 8332 8333 18332 18333 18444

CMD ["bitcoind"]
