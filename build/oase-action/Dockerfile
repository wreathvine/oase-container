ARG OASE_VERSION

FROM exastro/oase-backyard:${OASE_VERSION}

CMD ["/bin/sh", "-c", "while true; do python3 /exastro/OASE/oase-root/backyards/action_driver/oase_action.py;rc=$?;if [ $rc -ne 0 ] ; then exit $rc;fi;sleep ${INTERVAL_TIME_ACTION:-10}; done"]

