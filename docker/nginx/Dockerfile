# Like what you see? Join us!
# https://www.univention.com/about-us/careers/vacancies/
#
# Copyright 2020-2025 Univention GmbH
#
# https://www.univention.de/
#
# All rights reserved.
#
# The source code of this program is made available
# under the terms of the GNU Affero General Public License version 3
# (GNU AGPL V3) as published by the Free Software Foundation.
#
# Binary versions of this program provided by Univention to you as
# well as other copyrighted, protected or trademarked materials like
# Logos, graphics, fonts, specific documentations and configurations,
# cryptographic keys etc. are subject to a license agreement between
# you and Univention and not subject to the GNU AGPL V3.
#
# In the case you use this program under the terms of the GNU AGPL V3,
# the program is provided in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
# GNU Affero General Public License for more details.
#
# You should have received a copy of the GNU Affero General Public
# License with the Debian GNU/Linux or Univention distribution in file
# /usr/share/common-licenses/AGPL-3; if not, see
# <https://www.gnu.org/licenses/>.
#

ARG UCS_BASE_IMAGE=gitregistry.knut.univention.de/univention/dev/projects/ucs-base-image/ucs-base-521
ARG UCS_BASE_IMAGE_TAG=0.16.2-build-2025-04-24

FROM ${UCS_BASE_IMAGE}:${UCS_BASE_IMAGE_TAG}

RUN \
  apt-get --quiet --quiet update \
  && apt-get --assume-yes --verbose-versions --no-install-recommends install \
    nginx=1.22.* \
  && rm -fr /var/lib/apt/lists/* /var/cache/apt/archives/* \
  && mkdir -p /var/log/nginx \
  && ln -sf /dev/stdout /var/log/nginx/access.log \
  && ln -sf /dev/stderr /var/log/nginx/error.log \
  && adduser --disabled-password --gecos '' nginx

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

STOPSIGNAL SIGQUIT

CMD ["nginx", "-g", "daemon off;"]
