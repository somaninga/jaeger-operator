FROM 368471451480.dkr.ecr.us-west-2.amazonaws.com/nodejs:14
# FROM node:14

# WORKDIR specifies the application directory
WORKDIR /app

# Copying package.json file to the app directory
COPY package*.json /app/

# Installing npm for DOCKER
RUN npm install

RUN npm install @opentelemetry/api @opentelemetry/instrumentation @opentelemetry/tracing @opentelemetry/exporter-collector @opentelemetry/resources @opentelemetry/semantic-conventions @opentelemetry/auto-instrumentations-node @opentelemetry/sdk-node @opentelemetry/exporter-jaeger @opentelemetry/plugin-express @opentelemetry/plugin-http @opentelemetry/propagator-ot-trace @opentelemetry/sdk-trace-base @opentelemetry/sdk-trace-node --save-dev

# Copying rest of the application to app directory
COPY . /app

# Starting the application using npm start

CMD npm run initAll && npm run dev && node --require './nodejsSampleA/tracing.js' && node --require './nodejsSampleB/tracing.js'
