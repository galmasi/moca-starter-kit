FROM quay.io/dam-agents/claude-code

USER root

# install the E2B basics
RUN apt-get update
RUN apt-get install iputils-ping python3-pip proxychains4 -y
RUN npm i -g @e2b/cli
RUN pip3 install e2b -U --break-system-packages
RUN pip3 install httpx[socks] -U --break-system-packages

# custom harness terminal
COPY harness-terminal.sh /usr/local/bin/harness-terminal
RUN chmod +x /usr/local/bin/harness-terminal


COPY --chown=65532:0 workspace/ /app/working-dir/


# custom environment variables to talk to the E2B server
env E2B_API_KEY=e2b_53ae1fed82754c17ad8077fbc8bcdd90
env E2B_API_URL=https://api.e2btest2.ete14.res.ibm.com
env E2B_SANDBOX_URL=https://sandbox.e2btest2.ete14.res.ibm.com


USER 65532
