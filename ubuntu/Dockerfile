FROM ubuntu:latest
MAINTAINER Pedro Salgado "steenzout@ymail.com"

# setup

RUN set -x \
    && apt-get update \
        && echo 'Download and install packages here' \
	&& rm -rf /var/lib/apt/lists/*


# installation


# cleanup

RUN set -x \
    && apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false -o APT::AutoRemove::SuggestsImportant=false \
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
