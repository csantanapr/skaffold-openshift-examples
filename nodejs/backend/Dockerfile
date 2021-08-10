ARG IMAGE=registry.access.redhat.com/ubi8/nodejs-14
FROM $IMAGE
ARG ENV=production

WORKDIR /opt/app-root/src

COPY package* ./

RUN if [[ $ENV == production ]]; then npm ci --only=production; else npm install; fi

COPY --chown=1001:0 . .
RUN chmod -R g=u .

ENV PORT=3000


ENV NODE_ENV $ENV
ENV NODE_VERSION $NODEJS_VERSION
CMD npm run $NODE_ENV