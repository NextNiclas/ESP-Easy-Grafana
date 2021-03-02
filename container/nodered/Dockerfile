FROM nodered/node-red:1.2.9

COPY package.json .
RUN npm install --unsafe-perm --no-update-notifier --no-fund --only=production
