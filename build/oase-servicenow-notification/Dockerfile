ARG OASE_VERSION

FROM exastro/oase-backyard:${OASE_VERSION}

ENV LOG_DIR=/exastro/OASE/oase-root/logs/backyardlogs/servicenow_notification

RUN mkdir -p ${LOG_DIR}/debug

CMD ["/bin/sh", "-c", "while true; do python3 /exastro/OASE/oase-root/backyards/servicenow_notification/ServiceNow_notification.py;rc=$?;if [ $rc -ne 0 ] ; then exit $rc;fi;sleep ${INTERVAL_TIME_SNOW_NOT:-10}; done"]
