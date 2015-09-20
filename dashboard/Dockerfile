FROM ubuntu:14.04

MAINTAINER Kong TO <newlight77@gmail.com>

# install nodejs and npm
RUN apt-get update && apt-get install -y nodejs-legacy npm git git-core

# node -> renamed to nodejs : leading to "/usr/bin/env: node: No such file or directory"
# Either install nodejs-legacy or create link below
#RUN ln -s /usr/bin/nodejs /usr/bin/node

RUN npm install -g gulp grunt bower

ADD ./client /co3f/client
ADD ./server /co3f/server
ADD ./.bowerrc /co3f/.bowerrc
ADD ./.editorconfig /co3f/.editorconfig
ADD ./.gitignore /co3f/.gitignore
ADD ./.jscsrc /co3f/.jscsrc
ADD ./.jshintrc /co3f/.jshintrc
ADD ./bower.json /co3f/bower.json
ADD ./gulp.png /co3f/gulp.png
ADD ./gulp.config.js /co3f/gulp.config.js
ADD ./gulpfile.js /co3f/gulpfile.js
ADD ./karma.conf.js /co3f/karma.conf.js
ADD ./package.json /co3f/package.json

RUN cd /co3f && npm install

EXPOSE 8001

CMD "cd /co3f; gulp serve-dev;"

