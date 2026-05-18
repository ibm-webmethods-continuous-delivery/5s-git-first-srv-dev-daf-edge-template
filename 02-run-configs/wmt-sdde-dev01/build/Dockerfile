ARG __ibm_wm_msr_image=iwhicr.azurecr.io/webmethods-edge-runtime:12.0.2
FROM ${__ibm_wm_msr_image}

ARG __new_user_id=1001
ARG __new_grp_id=1001
ARG __img_user_name=sagadmin
ARG __img_grp_name=sagadmin

USER root

RUN usermod -u ${__new_user_id} ${__img_user_name} \
    && groupmod -g ${__new_grp_id} ${__img_grp_name} \
    && chown -R ${__new_user_id}:${__new_grp_id} /opt/webmethods

USER sagadmin
