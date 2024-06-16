FROM node:18.8.0

RUN mkdir /app
WORKDIR /app

RUN apt update
#RUN apt install -y libgconf-2-4 libatk1.0-0 libatk-bridge2.0-0 libgdk-pixbuf2.0-0 libgtk-3-0 libgbm-dev libnss3-dev libxss-dev libasound2
COPY package* ./
RUN npm install

#ENV NODE_ENV production
#ENV PORT 3000
#ENV PORT_SSL 3443

#ARG GIT_COMMIT
#ENV GIT_COMMIT ${GIT_COMMIT}

EXPOSE 3000

COPY . ./

CMD ["npm", "start"]