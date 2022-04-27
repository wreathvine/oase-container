ARG OASE_VERSION

FROM exastro/oase-backyard:${OASE_VERSION}

ENV LOG_DIR=/exastro/OASE/oase-root/logs/backyardlogs/oase_accept

RUN mkdir -p ${LOG_DIR}/debug

CMD ["python3", "/exastro/OASE/oase-root/backyards/accept_driver/oase_accept.py"]
