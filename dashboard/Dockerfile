FROM ubuntu:14.04

MAINTAINER Kong TO <newlight77@gmail.com>

# install nodejs and npm
RUN apt-get update && apt-get install -y nodejs npm git git-core

ADD ./client /client
ADD ./server /server
ADD ./.bowerrc /.bowerrc
ADD ./.editorconfig /.editorconfig
ADD ./.gitignore /.gitignore
ADD ./.jscsrc /.jscsrc
ADD ./.jshintrc /.jshintrc
ADD ./bower.json /bower.json
ADD ./gulp.png /gulp.png
ADD ./gulp.config.js /gulp.config.js
ADD ./gulpfile.js /gulpfile.js
ADD ./karma.conf.js /karma.conf.js
ADD ./package.json /package.json

#RUN npm install -g gulp grunt bower && npm install express mongoose cors

EXPOSE 8001

#CMD gulp serve-dev

