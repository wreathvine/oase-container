ARG OASE_VERSION

FROM exastro/oase-backyard:${OASE_VERSION}

ENV LOG_DIR=/exastro/OASE/oase-root/logs/backyardlogs/oase_agent

RUN mkdir -p ${LOG_DIR}/debug

CMD ["/bin/sh", "-c", "while true; do python3 /exastro/OASE/oase-root/backyards/agent_driver/oase_agent.py;rc=$?;if [ $rc -ne 0 ] ; then exit $rc;fi;sleep ${INTERVAL_TIME_AGENT:-10}; done"]
