FROM alpine:latest
MAINTAINER Pedro Salgado "steenzout@ymail.com"

# setup

RUN set -x \
    && apk add --update \
        && echo 'Download and install packages here' \
	&& rm -rf /var/cache/apk/*


# installation


# cleanup

RUN set -x \
    && apk del \
        && echo 'Append to the previous command the packages you no longer need' \
    && echo 'Python cleanup after' \
    && find /usr/local -depth \
        \( \
            \( -type d -a -name test -o -name tests -o -name __pycache__ \) \
            -o \
            \( -type f -a -name '*.pyc' -o -name '*.pyo' -o -name '*.pkl' \) \
        \) -exec rm -rf '{}' + \
    && rm -rf \
        ~/.cache
