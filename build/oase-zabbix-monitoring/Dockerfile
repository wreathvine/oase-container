ARG OASE_VERSION

FROM exastro/oase-backyard:${OASE_VERSION}

ENV LOG_DIR=/exastro/OASE/oase-root/logs/backyardlogs/oase_monitoring

RUN mkdir -p ${LOG_DIR}/debug

CMD ["/bin/sh", "-c", "while true; do python3 /exastro/OASE/oase-root/backyards/monitoring_adapter/ZABBIX_monitoring.py;rc=$?;if [ $rc -ne 0 ] ; then exit $rc;fi;sleep ${INTERVAL_TIME_ZBX_MON:-10}; done"]
