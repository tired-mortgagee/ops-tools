FROM centos:7

RUN touch /etc/yum.repos.d/td-agent-bit.repo \
    && echo "[td-agent-bit]" >> /etc/yum.repos.d/td-agent-bit.repo \
    && echo "name = TD Agent Bit" >> /etc/yum.repos.d/td-agent-bit.repo \
    && echo "baseurl = https://packages.fluentbit.io/centos/7/$basearch/" >> /etc/yum.repos.d/td-agent-bit.repo \
    && echo "gpgcheck=1" >> /etc/yum.repos.d/td-agent-bit.repo \
    && echo "gpgkey=https://packages.fluentbit.io/fluentbit.key" >> /etc/yum.repos.d/td-agent-bit.repo \
    && echo "enabled=1" >> /etc/yum.repos.d/td-agent-bit.repo

RUN yum install -y td-agent-bit

COPY td-agent-bit.conf /etc/td-agent-bit/

VOLUME /var/logroot

EXPOSE 514/udp

CMD ["/opt/td-agent-bit/bin/td-agent-bit", "-c", "/etc/td-agent-bit/td-agent-bit.conf"]
