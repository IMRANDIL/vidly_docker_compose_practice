FROM node:14.16.0-alpine3.13

# create a new app user
RUN addgroup app && adduser -S -G app app



# create the app directory and set it as the working directory
WORKDIR /app

# copy package.json and package-lock.json if available
COPY package*.json ./

# install dependencies
RUN npm install

# copy the rest of the application files
COPY . .

RUN chown -R app:app /app/docker-entrypoint.sh


# set the user to app
USER app

# set the port that will be exposed
EXPOSE 3001


# set the default command
CMD ["npm", "start"]