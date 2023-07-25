FROM ruby:3.0.5

RUN apt-get update -yqq && apt-get install -yqq --no-install-recommends \
  curl \
  gpg \
  && curl -sSL https://rvm.io/mpapis.asc | gpg --import - \
  && curl -sSL https://rvm.io/pkuczynski.asc | gpg --import - \
  && curl -sSL https://get.rvm.io | bash -s stable

ENV PATH /usr/local/rvm/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

RUN /bin/bash -l -c "rvm requirements"
RUN /bin/bash -l -c "rvm install 3.0.5"
RUN /bin/bash -l -c "gem install bundler jekyll"

WORKDIR /workspace

CMD [ "bash" ]
