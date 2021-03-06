<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `ghost`

-	[`ghost:0.11.7`](#ghost0117)
-	[`ghost:0.11`](#ghost011)
-	[`ghost:0`](#ghost0)
-	[`ghost:latest`](#ghostlatest)
-	[`ghost:0.11.7-alpine`](#ghost0117-alpine)
-	[`ghost:0.11-alpine`](#ghost011-alpine)
-	[`ghost:0-alpine`](#ghost0-alpine)
-	[`ghost:alpine`](#ghostalpine)

## `ghost:0.11.7`

```console
$ docker pull ghost@sha256:c4b4fd1963d40854804d9b6f6f1c13f1b746220cd85c9622d32bbbb0e3ba6f92
```

-	Platforms:
	-	linux; amd64

### `ghost:0.11.7` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **111.4 MB (111422619 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bb11280273b50175846e355c7946efc15812a96dcd68986df3b515cf19db35f1`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:10:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:07:44 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Fri, 07 Apr 2017 17:22:07 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Fri, 07 Apr 2017 17:22:08 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 07 Apr 2017 17:42:47 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:57 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 20 Apr 2017 14:42:14 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:42:19 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Thu, 20 Apr 2017 14:42:19 GMT
CMD ["node"]
# Thu, 20 Apr 2017 16:01:32 GMT
RUN groupadd user && useradd --create-home --home-dir /home/user -g user user
# Thu, 20 Apr 2017 16:01:32 GMT
ENV GOSU_VERSION=1.7
# Thu, 20 Apr 2017 20:08:24 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Thu, 20 Apr 2017 20:08:25 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Thu, 20 Apr 2017 20:08:25 GMT
WORKDIR /usr/src/ghost
# Thu, 20 Apr 2017 20:08:26 GMT
ENV GHOST_VERSION=0.11.7
# Thu, 20 Apr 2017 20:09:23 GMT
RUN set -ex; 		buildDeps=' 		gcc 		make 		python 		unzip 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apt-get purge -y --auto-remove $buildDeps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Thu, 20 Apr 2017 20:09:24 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Thu, 20 Apr 2017 20:09:25 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R user:user "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Thu, 20 Apr 2017 20:09:26 GMT
VOLUME [/var/lib/ghost]
# Thu, 20 Apr 2017 20:09:26 GMT
COPY file:9cace68ea99d0317c469464495249094669747893a60585016756f169051a609 in /usr/local/bin/ 
# Thu, 20 Apr 2017 20:09:28 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Thu, 20 Apr 2017 20:09:28 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 20 Apr 2017 20:09:29 GMT
EXPOSE 2368/tcp
# Thu, 20 Apr 2017 20:09:29 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2726297beaf19be957416750338c095ae15b94adc0e8c1306cebbf113f8b9a5c`  
		Last Modified: Tue, 21 Mar 2017 19:58:58 GMT  
		Size: 18.6 MB (18606479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1c75255d33f781986e7e2731d7b17bf4675d02f4e956371310df4658cf1b1b2`  
		Last Modified: Thu, 23 Mar 2017 00:09:59 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c48deb3bd78b506d15abe7050a46deee302eb4f22d5adf606585294a27db959c`  
		Last Modified: Fri, 07 Apr 2017 17:48:00 GMT  
		Size: 119.1 KB (119061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed263e062728d3aa71f25aadd88fb7378277d7475e1a0a59a0a159bb45931a0f`  
		Last Modified: Fri, 07 Apr 2017 18:02:40 GMT  
		Size: 12.3 MB (12252077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e621205ed034f9c20194946bb307773b3c9edccc3df4aba32dc8f4641c3a466`  
		Last Modified: Thu, 20 Apr 2017 14:59:14 GMT  
		Size: 886.3 KB (886267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d5900ecbacf6cd00d6e4d53f7586f48c8646b53685d36d426d2f974a50aa9e1`  
		Last Modified: Thu, 20 Apr 2017 20:11:02 GMT  
		Size: 4.4 KB (4415 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb257d6041e3bcf1b8715eaee956ba824044d154651f0c312899a3b1a8a3e903`  
		Last Modified: Thu, 20 Apr 2017 20:11:02 GMT  
		Size: 818.8 KB (818819 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:104f241a85f5a8b70d9bf10aa0859cb0e7a802bc331e5115d27b15cc10f3799e`  
		Last Modified: Thu, 20 Apr 2017 20:10:59 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b3af0619ee78ec15114f4c516a9f892f3acad1be803a40b6f117c2976ebf6932`  
		Last Modified: Thu, 20 Apr 2017 20:11:06 GMT  
		Size: 27.3 MB (27291601 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:561a68f79ad8c30b0eacb68d97b2c6e84b183c1e57c199e97674dce9cfa9e23a`  
		Last Modified: Thu, 20 Apr 2017 20:11:00 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:010f358661a4723dbe91adc0566658126471465b3b481a620460243c0268a6cf`  
		Last Modified: Thu, 20 Apr 2017 20:10:59 GMT  
		Size: 617.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c26cd0d71f3974d21c5f0b1e04da21c5a2d5b43d50df7f9f15d319fdb1a5cce`  
		Last Modified: Thu, 20 Apr 2017 20:11:01 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `ghost:0.11`

```console
$ docker pull ghost@sha256:c4b4fd1963d40854804d9b6f6f1c13f1b746220cd85c9622d32bbbb0e3ba6f92
```

-	Platforms:
	-	linux; amd64

### `ghost:0.11` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **111.4 MB (111422619 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bb11280273b50175846e355c7946efc15812a96dcd68986df3b515cf19db35f1`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:10:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:07:44 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Fri, 07 Apr 2017 17:22:07 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Fri, 07 Apr 2017 17:22:08 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 07 Apr 2017 17:42:47 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:57 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 20 Apr 2017 14:42:14 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:42:19 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Thu, 20 Apr 2017 14:42:19 GMT
CMD ["node"]
# Thu, 20 Apr 2017 16:01:32 GMT
RUN groupadd user && useradd --create-home --home-dir /home/user -g user user
# Thu, 20 Apr 2017 16:01:32 GMT
ENV GOSU_VERSION=1.7
# Thu, 20 Apr 2017 20:08:24 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Thu, 20 Apr 2017 20:08:25 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Thu, 20 Apr 2017 20:08:25 GMT
WORKDIR /usr/src/ghost
# Thu, 20 Apr 2017 20:08:26 GMT
ENV GHOST_VERSION=0.11.7
# Thu, 20 Apr 2017 20:09:23 GMT
RUN set -ex; 		buildDeps=' 		gcc 		make 		python 		unzip 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apt-get purge -y --auto-remove $buildDeps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Thu, 20 Apr 2017 20:09:24 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Thu, 20 Apr 2017 20:09:25 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R user:user "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Thu, 20 Apr 2017 20:09:26 GMT
VOLUME [/var/lib/ghost]
# Thu, 20 Apr 2017 20:09:26 GMT
COPY file:9cace68ea99d0317c469464495249094669747893a60585016756f169051a609 in /usr/local/bin/ 
# Thu, 20 Apr 2017 20:09:28 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Thu, 20 Apr 2017 20:09:28 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 20 Apr 2017 20:09:29 GMT
EXPOSE 2368/tcp
# Thu, 20 Apr 2017 20:09:29 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2726297beaf19be957416750338c095ae15b94adc0e8c1306cebbf113f8b9a5c`  
		Last Modified: Tue, 21 Mar 2017 19:58:58 GMT  
		Size: 18.6 MB (18606479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1c75255d33f781986e7e2731d7b17bf4675d02f4e956371310df4658cf1b1b2`  
		Last Modified: Thu, 23 Mar 2017 00:09:59 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c48deb3bd78b506d15abe7050a46deee302eb4f22d5adf606585294a27db959c`  
		Last Modified: Fri, 07 Apr 2017 17:48:00 GMT  
		Size: 119.1 KB (119061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed263e062728d3aa71f25aadd88fb7378277d7475e1a0a59a0a159bb45931a0f`  
		Last Modified: Fri, 07 Apr 2017 18:02:40 GMT  
		Size: 12.3 MB (12252077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e621205ed034f9c20194946bb307773b3c9edccc3df4aba32dc8f4641c3a466`  
		Last Modified: Thu, 20 Apr 2017 14:59:14 GMT  
		Size: 886.3 KB (886267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d5900ecbacf6cd00d6e4d53f7586f48c8646b53685d36d426d2f974a50aa9e1`  
		Last Modified: Thu, 20 Apr 2017 20:11:02 GMT  
		Size: 4.4 KB (4415 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb257d6041e3bcf1b8715eaee956ba824044d154651f0c312899a3b1a8a3e903`  
		Last Modified: Thu, 20 Apr 2017 20:11:02 GMT  
		Size: 818.8 KB (818819 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:104f241a85f5a8b70d9bf10aa0859cb0e7a802bc331e5115d27b15cc10f3799e`  
		Last Modified: Thu, 20 Apr 2017 20:10:59 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b3af0619ee78ec15114f4c516a9f892f3acad1be803a40b6f117c2976ebf6932`  
		Last Modified: Thu, 20 Apr 2017 20:11:06 GMT  
		Size: 27.3 MB (27291601 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:561a68f79ad8c30b0eacb68d97b2c6e84b183c1e57c199e97674dce9cfa9e23a`  
		Last Modified: Thu, 20 Apr 2017 20:11:00 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:010f358661a4723dbe91adc0566658126471465b3b481a620460243c0268a6cf`  
		Last Modified: Thu, 20 Apr 2017 20:10:59 GMT  
		Size: 617.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c26cd0d71f3974d21c5f0b1e04da21c5a2d5b43d50df7f9f15d319fdb1a5cce`  
		Last Modified: Thu, 20 Apr 2017 20:11:01 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `ghost:0`

```console
$ docker pull ghost@sha256:c4b4fd1963d40854804d9b6f6f1c13f1b746220cd85c9622d32bbbb0e3ba6f92
```

-	Platforms:
	-	linux; amd64

### `ghost:0` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **111.4 MB (111422619 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bb11280273b50175846e355c7946efc15812a96dcd68986df3b515cf19db35f1`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:10:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:07:44 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Fri, 07 Apr 2017 17:22:07 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Fri, 07 Apr 2017 17:22:08 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 07 Apr 2017 17:42:47 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:57 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 20 Apr 2017 14:42:14 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:42:19 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Thu, 20 Apr 2017 14:42:19 GMT
CMD ["node"]
# Thu, 20 Apr 2017 16:01:32 GMT
RUN groupadd user && useradd --create-home --home-dir /home/user -g user user
# Thu, 20 Apr 2017 16:01:32 GMT
ENV GOSU_VERSION=1.7
# Thu, 20 Apr 2017 20:08:24 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Thu, 20 Apr 2017 20:08:25 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Thu, 20 Apr 2017 20:08:25 GMT
WORKDIR /usr/src/ghost
# Thu, 20 Apr 2017 20:08:26 GMT
ENV GHOST_VERSION=0.11.7
# Thu, 20 Apr 2017 20:09:23 GMT
RUN set -ex; 		buildDeps=' 		gcc 		make 		python 		unzip 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apt-get purge -y --auto-remove $buildDeps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Thu, 20 Apr 2017 20:09:24 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Thu, 20 Apr 2017 20:09:25 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R user:user "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Thu, 20 Apr 2017 20:09:26 GMT
VOLUME [/var/lib/ghost]
# Thu, 20 Apr 2017 20:09:26 GMT
COPY file:9cace68ea99d0317c469464495249094669747893a60585016756f169051a609 in /usr/local/bin/ 
# Thu, 20 Apr 2017 20:09:28 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Thu, 20 Apr 2017 20:09:28 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 20 Apr 2017 20:09:29 GMT
EXPOSE 2368/tcp
# Thu, 20 Apr 2017 20:09:29 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2726297beaf19be957416750338c095ae15b94adc0e8c1306cebbf113f8b9a5c`  
		Last Modified: Tue, 21 Mar 2017 19:58:58 GMT  
		Size: 18.6 MB (18606479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1c75255d33f781986e7e2731d7b17bf4675d02f4e956371310df4658cf1b1b2`  
		Last Modified: Thu, 23 Mar 2017 00:09:59 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c48deb3bd78b506d15abe7050a46deee302eb4f22d5adf606585294a27db959c`  
		Last Modified: Fri, 07 Apr 2017 17:48:00 GMT  
		Size: 119.1 KB (119061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed263e062728d3aa71f25aadd88fb7378277d7475e1a0a59a0a159bb45931a0f`  
		Last Modified: Fri, 07 Apr 2017 18:02:40 GMT  
		Size: 12.3 MB (12252077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e621205ed034f9c20194946bb307773b3c9edccc3df4aba32dc8f4641c3a466`  
		Last Modified: Thu, 20 Apr 2017 14:59:14 GMT  
		Size: 886.3 KB (886267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d5900ecbacf6cd00d6e4d53f7586f48c8646b53685d36d426d2f974a50aa9e1`  
		Last Modified: Thu, 20 Apr 2017 20:11:02 GMT  
		Size: 4.4 KB (4415 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb257d6041e3bcf1b8715eaee956ba824044d154651f0c312899a3b1a8a3e903`  
		Last Modified: Thu, 20 Apr 2017 20:11:02 GMT  
		Size: 818.8 KB (818819 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:104f241a85f5a8b70d9bf10aa0859cb0e7a802bc331e5115d27b15cc10f3799e`  
		Last Modified: Thu, 20 Apr 2017 20:10:59 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b3af0619ee78ec15114f4c516a9f892f3acad1be803a40b6f117c2976ebf6932`  
		Last Modified: Thu, 20 Apr 2017 20:11:06 GMT  
		Size: 27.3 MB (27291601 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:561a68f79ad8c30b0eacb68d97b2c6e84b183c1e57c199e97674dce9cfa9e23a`  
		Last Modified: Thu, 20 Apr 2017 20:11:00 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:010f358661a4723dbe91adc0566658126471465b3b481a620460243c0268a6cf`  
		Last Modified: Thu, 20 Apr 2017 20:10:59 GMT  
		Size: 617.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c26cd0d71f3974d21c5f0b1e04da21c5a2d5b43d50df7f9f15d319fdb1a5cce`  
		Last Modified: Thu, 20 Apr 2017 20:11:01 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `ghost:latest`

```console
$ docker pull ghost@sha256:c4b4fd1963d40854804d9b6f6f1c13f1b746220cd85c9622d32bbbb0e3ba6f92
```

-	Platforms:
	-	linux; amd64

### `ghost:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **111.4 MB (111422619 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bb11280273b50175846e355c7946efc15812a96dcd68986df3b515cf19db35f1`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:10:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:07:44 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Fri, 07 Apr 2017 17:22:07 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Fri, 07 Apr 2017 17:22:08 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 07 Apr 2017 17:42:47 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:57 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 20 Apr 2017 14:42:14 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:42:19 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Thu, 20 Apr 2017 14:42:19 GMT
CMD ["node"]
# Thu, 20 Apr 2017 16:01:32 GMT
RUN groupadd user && useradd --create-home --home-dir /home/user -g user user
# Thu, 20 Apr 2017 16:01:32 GMT
ENV GOSU_VERSION=1.7
# Thu, 20 Apr 2017 20:08:24 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Thu, 20 Apr 2017 20:08:25 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Thu, 20 Apr 2017 20:08:25 GMT
WORKDIR /usr/src/ghost
# Thu, 20 Apr 2017 20:08:26 GMT
ENV GHOST_VERSION=0.11.7
# Thu, 20 Apr 2017 20:09:23 GMT
RUN set -ex; 		buildDeps=' 		gcc 		make 		python 		unzip 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apt-get purge -y --auto-remove $buildDeps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Thu, 20 Apr 2017 20:09:24 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Thu, 20 Apr 2017 20:09:25 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R user:user "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Thu, 20 Apr 2017 20:09:26 GMT
VOLUME [/var/lib/ghost]
# Thu, 20 Apr 2017 20:09:26 GMT
COPY file:9cace68ea99d0317c469464495249094669747893a60585016756f169051a609 in /usr/local/bin/ 
# Thu, 20 Apr 2017 20:09:28 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Thu, 20 Apr 2017 20:09:28 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 20 Apr 2017 20:09:29 GMT
EXPOSE 2368/tcp
# Thu, 20 Apr 2017 20:09:29 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2726297beaf19be957416750338c095ae15b94adc0e8c1306cebbf113f8b9a5c`  
		Last Modified: Tue, 21 Mar 2017 19:58:58 GMT  
		Size: 18.6 MB (18606479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1c75255d33f781986e7e2731d7b17bf4675d02f4e956371310df4658cf1b1b2`  
		Last Modified: Thu, 23 Mar 2017 00:09:59 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c48deb3bd78b506d15abe7050a46deee302eb4f22d5adf606585294a27db959c`  
		Last Modified: Fri, 07 Apr 2017 17:48:00 GMT  
		Size: 119.1 KB (119061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed263e062728d3aa71f25aadd88fb7378277d7475e1a0a59a0a159bb45931a0f`  
		Last Modified: Fri, 07 Apr 2017 18:02:40 GMT  
		Size: 12.3 MB (12252077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e621205ed034f9c20194946bb307773b3c9edccc3df4aba32dc8f4641c3a466`  
		Last Modified: Thu, 20 Apr 2017 14:59:14 GMT  
		Size: 886.3 KB (886267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d5900ecbacf6cd00d6e4d53f7586f48c8646b53685d36d426d2f974a50aa9e1`  
		Last Modified: Thu, 20 Apr 2017 20:11:02 GMT  
		Size: 4.4 KB (4415 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb257d6041e3bcf1b8715eaee956ba824044d154651f0c312899a3b1a8a3e903`  
		Last Modified: Thu, 20 Apr 2017 20:11:02 GMT  
		Size: 818.8 KB (818819 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:104f241a85f5a8b70d9bf10aa0859cb0e7a802bc331e5115d27b15cc10f3799e`  
		Last Modified: Thu, 20 Apr 2017 20:10:59 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b3af0619ee78ec15114f4c516a9f892f3acad1be803a40b6f117c2976ebf6932`  
		Last Modified: Thu, 20 Apr 2017 20:11:06 GMT  
		Size: 27.3 MB (27291601 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:561a68f79ad8c30b0eacb68d97b2c6e84b183c1e57c199e97674dce9cfa9e23a`  
		Last Modified: Thu, 20 Apr 2017 20:11:00 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:010f358661a4723dbe91adc0566658126471465b3b481a620460243c0268a6cf`  
		Last Modified: Thu, 20 Apr 2017 20:10:59 GMT  
		Size: 617.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c26cd0d71f3974d21c5f0b1e04da21c5a2d5b43d50df7f9f15d319fdb1a5cce`  
		Last Modified: Thu, 20 Apr 2017 20:11:01 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `ghost:0.11.7-alpine`

```console
$ docker pull ghost@sha256:2a95d2571d61e13202574c12abbb30ddefad70cd1b539c520cc8749b544cbaf8
```

-	Platforms:
	-	linux; amd64

### `ghost:0.11.7-alpine` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **42.3 MB (42302941 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a218d29997a39f0f039def06eac0f9cd455786316d3b31e912d55168f0669a83`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:21 GMT
ADD file:3df55c321c1c8d73f22bc69240c0764290d6cb293da46ba8f94ed25473fb5853 in / 
# Fri, 03 Mar 2017 22:03:51 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Tue, 04 Apr 2017 19:53:26 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:34 GMT
RUN addgroup -g 1000 node     && adduser -u 1000 -G node -s /bin/sh -D node     && apk add --no-cache         libstdc++     && apk add --no-cache --virtual .build-deps         binutils-gold         curl         g++         gcc         gnupg         libgcc         linux-headers         make         python   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xf "node-v$NODE_VERSION.tar.xz"     && cd "node-v$NODE_VERSION"     && ./configure     && make -j$(getconf _NPROCESSORS_ONLN)     && make install     && apk del .build-deps     && cd ..     && rm -Rf "node-v$NODE_VERSION"     && rm "node-v$NODE_VERSION.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt
# Thu, 20 Apr 2017 14:41:29 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:41:36 GMT
RUN apk add --no-cache --virtual .build-deps-yarn curl gnupg   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn   && apk del .build-deps-yarn
# Thu, 20 Apr 2017 14:41:37 GMT
CMD ["node"]
# Thu, 20 Apr 2017 20:09:47 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Thu, 20 Apr 2017 20:09:49 GMT
RUN apk add --no-cache 		bash 		tar
# Thu, 20 Apr 2017 20:09:50 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Thu, 20 Apr 2017 20:09:50 GMT
WORKDIR /usr/src/ghost
# Thu, 20 Apr 2017 20:09:51 GMT
ENV GHOST_VERSION=0.11.7
# Thu, 20 Apr 2017 20:10:34 GMT
RUN set -ex; 		apk add --no-cache --virtual .build-deps 		ca-certificates 		gcc 		make 		openssl 		python 		unzip 	; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apk del .build-deps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Thu, 20 Apr 2017 20:10:35 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Thu, 20 Apr 2017 20:10:37 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R node:node "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Thu, 20 Apr 2017 20:10:37 GMT
VOLUME [/var/lib/ghost]
# Thu, 20 Apr 2017 20:10:38 GMT
COPY file:2cb0a64ef22301242537372657c5d88304b43153f351a7f2d0d61e05c3dfb29a in /usr/local/bin/ 
# Thu, 20 Apr 2017 20:10:39 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 20 Apr 2017 20:10:39 GMT
EXPOSE 2368/tcp
# Thu, 20 Apr 2017 20:10:40 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:7095154754192bfc2306f3b2b841ef82771b7ad39526537234adb1e74ae81a93`  
		Last Modified: Fri, 03 Mar 2017 20:34:19 GMT  
		Size: 2.3 MB (2313384 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef19eb3aaa8d2dfabaf5c800ad7b6a47ba903ccbb83a3c5fc00e92724c17bf48`  
		Last Modified: Fri, 07 Apr 2017 17:59:51 GMT  
		Size: 10.5 MB (10484958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0da182fec9e38735c84aea5b3f3b95e998395ef29ab0aef25bbb0a8a78c7cb58`  
		Last Modified: Thu, 20 Apr 2017 14:56:46 GMT  
		Size: 896.1 KB (896142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd69751ca1220e3e5a9be7badab2da075cc4336ffc7cbfd07f5a427528427e86`  
		Last Modified: Thu, 20 Apr 2017 20:12:24 GMT  
		Size: 8.3 KB (8318 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9d400c0c941cefbcddccf18b2802b972dceaacad021b0e403623158fbe904cf`  
		Last Modified: Thu, 20 Apr 2017 20:12:22 GMT  
		Size: 1.3 MB (1340403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f27a50571167b9243164d6a9426027ad33c69261a25b12ce59b1cc6dd6b95eda`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a52bd0f5fcc76f3896bf1612a3df3914fd4a8d55c5be16012919ec6c2525525`  
		Last Modified: Thu, 20 Apr 2017 20:12:28 GMT  
		Size: 27.3 MB (27258795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:345ef92805c54454c6f763913fa514ff59a1cce974e78c15198683d4b3af54ef`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2a278ec740a7ad3dedc42d6ec1122f6e1859c7becbcad755a4d75adf068d454`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 598.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `ghost:0.11-alpine`

```console
$ docker pull ghost@sha256:2a95d2571d61e13202574c12abbb30ddefad70cd1b539c520cc8749b544cbaf8
```

-	Platforms:
	-	linux; amd64

### `ghost:0.11-alpine` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **42.3 MB (42302941 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a218d29997a39f0f039def06eac0f9cd455786316d3b31e912d55168f0669a83`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:21 GMT
ADD file:3df55c321c1c8d73f22bc69240c0764290d6cb293da46ba8f94ed25473fb5853 in / 
# Fri, 03 Mar 2017 22:03:51 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Tue, 04 Apr 2017 19:53:26 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:34 GMT
RUN addgroup -g 1000 node     && adduser -u 1000 -G node -s /bin/sh -D node     && apk add --no-cache         libstdc++     && apk add --no-cache --virtual .build-deps         binutils-gold         curl         g++         gcc         gnupg         libgcc         linux-headers         make         python   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xf "node-v$NODE_VERSION.tar.xz"     && cd "node-v$NODE_VERSION"     && ./configure     && make -j$(getconf _NPROCESSORS_ONLN)     && make install     && apk del .build-deps     && cd ..     && rm -Rf "node-v$NODE_VERSION"     && rm "node-v$NODE_VERSION.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt
# Thu, 20 Apr 2017 14:41:29 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:41:36 GMT
RUN apk add --no-cache --virtual .build-deps-yarn curl gnupg   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn   && apk del .build-deps-yarn
# Thu, 20 Apr 2017 14:41:37 GMT
CMD ["node"]
# Thu, 20 Apr 2017 20:09:47 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Thu, 20 Apr 2017 20:09:49 GMT
RUN apk add --no-cache 		bash 		tar
# Thu, 20 Apr 2017 20:09:50 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Thu, 20 Apr 2017 20:09:50 GMT
WORKDIR /usr/src/ghost
# Thu, 20 Apr 2017 20:09:51 GMT
ENV GHOST_VERSION=0.11.7
# Thu, 20 Apr 2017 20:10:34 GMT
RUN set -ex; 		apk add --no-cache --virtual .build-deps 		ca-certificates 		gcc 		make 		openssl 		python 		unzip 	; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apk del .build-deps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Thu, 20 Apr 2017 20:10:35 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Thu, 20 Apr 2017 20:10:37 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R node:node "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Thu, 20 Apr 2017 20:10:37 GMT
VOLUME [/var/lib/ghost]
# Thu, 20 Apr 2017 20:10:38 GMT
COPY file:2cb0a64ef22301242537372657c5d88304b43153f351a7f2d0d61e05c3dfb29a in /usr/local/bin/ 
# Thu, 20 Apr 2017 20:10:39 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 20 Apr 2017 20:10:39 GMT
EXPOSE 2368/tcp
# Thu, 20 Apr 2017 20:10:40 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:7095154754192bfc2306f3b2b841ef82771b7ad39526537234adb1e74ae81a93`  
		Last Modified: Fri, 03 Mar 2017 20:34:19 GMT  
		Size: 2.3 MB (2313384 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef19eb3aaa8d2dfabaf5c800ad7b6a47ba903ccbb83a3c5fc00e92724c17bf48`  
		Last Modified: Fri, 07 Apr 2017 17:59:51 GMT  
		Size: 10.5 MB (10484958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0da182fec9e38735c84aea5b3f3b95e998395ef29ab0aef25bbb0a8a78c7cb58`  
		Last Modified: Thu, 20 Apr 2017 14:56:46 GMT  
		Size: 896.1 KB (896142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd69751ca1220e3e5a9be7badab2da075cc4336ffc7cbfd07f5a427528427e86`  
		Last Modified: Thu, 20 Apr 2017 20:12:24 GMT  
		Size: 8.3 KB (8318 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9d400c0c941cefbcddccf18b2802b972dceaacad021b0e403623158fbe904cf`  
		Last Modified: Thu, 20 Apr 2017 20:12:22 GMT  
		Size: 1.3 MB (1340403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f27a50571167b9243164d6a9426027ad33c69261a25b12ce59b1cc6dd6b95eda`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a52bd0f5fcc76f3896bf1612a3df3914fd4a8d55c5be16012919ec6c2525525`  
		Last Modified: Thu, 20 Apr 2017 20:12:28 GMT  
		Size: 27.3 MB (27258795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:345ef92805c54454c6f763913fa514ff59a1cce974e78c15198683d4b3af54ef`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2a278ec740a7ad3dedc42d6ec1122f6e1859c7becbcad755a4d75adf068d454`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 598.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `ghost:0-alpine`

```console
$ docker pull ghost@sha256:2a95d2571d61e13202574c12abbb30ddefad70cd1b539c520cc8749b544cbaf8
```

-	Platforms:
	-	linux; amd64

### `ghost:0-alpine` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **42.3 MB (42302941 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a218d29997a39f0f039def06eac0f9cd455786316d3b31e912d55168f0669a83`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:21 GMT
ADD file:3df55c321c1c8d73f22bc69240c0764290d6cb293da46ba8f94ed25473fb5853 in / 
# Fri, 03 Mar 2017 22:03:51 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Tue, 04 Apr 2017 19:53:26 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:34 GMT
RUN addgroup -g 1000 node     && adduser -u 1000 -G node -s /bin/sh -D node     && apk add --no-cache         libstdc++     && apk add --no-cache --virtual .build-deps         binutils-gold         curl         g++         gcc         gnupg         libgcc         linux-headers         make         python   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xf "node-v$NODE_VERSION.tar.xz"     && cd "node-v$NODE_VERSION"     && ./configure     && make -j$(getconf _NPROCESSORS_ONLN)     && make install     && apk del .build-deps     && cd ..     && rm -Rf "node-v$NODE_VERSION"     && rm "node-v$NODE_VERSION.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt
# Thu, 20 Apr 2017 14:41:29 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:41:36 GMT
RUN apk add --no-cache --virtual .build-deps-yarn curl gnupg   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn   && apk del .build-deps-yarn
# Thu, 20 Apr 2017 14:41:37 GMT
CMD ["node"]
# Thu, 20 Apr 2017 20:09:47 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Thu, 20 Apr 2017 20:09:49 GMT
RUN apk add --no-cache 		bash 		tar
# Thu, 20 Apr 2017 20:09:50 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Thu, 20 Apr 2017 20:09:50 GMT
WORKDIR /usr/src/ghost
# Thu, 20 Apr 2017 20:09:51 GMT
ENV GHOST_VERSION=0.11.7
# Thu, 20 Apr 2017 20:10:34 GMT
RUN set -ex; 		apk add --no-cache --virtual .build-deps 		ca-certificates 		gcc 		make 		openssl 		python 		unzip 	; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apk del .build-deps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Thu, 20 Apr 2017 20:10:35 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Thu, 20 Apr 2017 20:10:37 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R node:node "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Thu, 20 Apr 2017 20:10:37 GMT
VOLUME [/var/lib/ghost]
# Thu, 20 Apr 2017 20:10:38 GMT
COPY file:2cb0a64ef22301242537372657c5d88304b43153f351a7f2d0d61e05c3dfb29a in /usr/local/bin/ 
# Thu, 20 Apr 2017 20:10:39 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 20 Apr 2017 20:10:39 GMT
EXPOSE 2368/tcp
# Thu, 20 Apr 2017 20:10:40 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:7095154754192bfc2306f3b2b841ef82771b7ad39526537234adb1e74ae81a93`  
		Last Modified: Fri, 03 Mar 2017 20:34:19 GMT  
		Size: 2.3 MB (2313384 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef19eb3aaa8d2dfabaf5c800ad7b6a47ba903ccbb83a3c5fc00e92724c17bf48`  
		Last Modified: Fri, 07 Apr 2017 17:59:51 GMT  
		Size: 10.5 MB (10484958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0da182fec9e38735c84aea5b3f3b95e998395ef29ab0aef25bbb0a8a78c7cb58`  
		Last Modified: Thu, 20 Apr 2017 14:56:46 GMT  
		Size: 896.1 KB (896142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd69751ca1220e3e5a9be7badab2da075cc4336ffc7cbfd07f5a427528427e86`  
		Last Modified: Thu, 20 Apr 2017 20:12:24 GMT  
		Size: 8.3 KB (8318 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9d400c0c941cefbcddccf18b2802b972dceaacad021b0e403623158fbe904cf`  
		Last Modified: Thu, 20 Apr 2017 20:12:22 GMT  
		Size: 1.3 MB (1340403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f27a50571167b9243164d6a9426027ad33c69261a25b12ce59b1cc6dd6b95eda`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a52bd0f5fcc76f3896bf1612a3df3914fd4a8d55c5be16012919ec6c2525525`  
		Last Modified: Thu, 20 Apr 2017 20:12:28 GMT  
		Size: 27.3 MB (27258795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:345ef92805c54454c6f763913fa514ff59a1cce974e78c15198683d4b3af54ef`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2a278ec740a7ad3dedc42d6ec1122f6e1859c7becbcad755a4d75adf068d454`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 598.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `ghost:alpine`

```console
$ docker pull ghost@sha256:2a95d2571d61e13202574c12abbb30ddefad70cd1b539c520cc8749b544cbaf8
```

-	Platforms:
	-	linux; amd64

### `ghost:alpine` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **42.3 MB (42302941 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a218d29997a39f0f039def06eac0f9cd455786316d3b31e912d55168f0669a83`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:21 GMT
ADD file:3df55c321c1c8d73f22bc69240c0764290d6cb293da46ba8f94ed25473fb5853 in / 
# Fri, 03 Mar 2017 22:03:51 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Tue, 04 Apr 2017 19:53:26 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:34 GMT
RUN addgroup -g 1000 node     && adduser -u 1000 -G node -s /bin/sh -D node     && apk add --no-cache         libstdc++     && apk add --no-cache --virtual .build-deps         binutils-gold         curl         g++         gcc         gnupg         libgcc         linux-headers         make         python   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xf "node-v$NODE_VERSION.tar.xz"     && cd "node-v$NODE_VERSION"     && ./configure     && make -j$(getconf _NPROCESSORS_ONLN)     && make install     && apk del .build-deps     && cd ..     && rm -Rf "node-v$NODE_VERSION"     && rm "node-v$NODE_VERSION.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt
# Thu, 20 Apr 2017 14:41:29 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:41:36 GMT
RUN apk add --no-cache --virtual .build-deps-yarn curl gnupg   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn   && apk del .build-deps-yarn
# Thu, 20 Apr 2017 14:41:37 GMT
CMD ["node"]
# Thu, 20 Apr 2017 20:09:47 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Thu, 20 Apr 2017 20:09:49 GMT
RUN apk add --no-cache 		bash 		tar
# Thu, 20 Apr 2017 20:09:50 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Thu, 20 Apr 2017 20:09:50 GMT
WORKDIR /usr/src/ghost
# Thu, 20 Apr 2017 20:09:51 GMT
ENV GHOST_VERSION=0.11.7
# Thu, 20 Apr 2017 20:10:34 GMT
RUN set -ex; 		apk add --no-cache --virtual .build-deps 		ca-certificates 		gcc 		make 		openssl 		python 		unzip 	; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apk del .build-deps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Thu, 20 Apr 2017 20:10:35 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Thu, 20 Apr 2017 20:10:37 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R node:node "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Thu, 20 Apr 2017 20:10:37 GMT
VOLUME [/var/lib/ghost]
# Thu, 20 Apr 2017 20:10:38 GMT
COPY file:2cb0a64ef22301242537372657c5d88304b43153f351a7f2d0d61e05c3dfb29a in /usr/local/bin/ 
# Thu, 20 Apr 2017 20:10:39 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 20 Apr 2017 20:10:39 GMT
EXPOSE 2368/tcp
# Thu, 20 Apr 2017 20:10:40 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:7095154754192bfc2306f3b2b841ef82771b7ad39526537234adb1e74ae81a93`  
		Last Modified: Fri, 03 Mar 2017 20:34:19 GMT  
		Size: 2.3 MB (2313384 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef19eb3aaa8d2dfabaf5c800ad7b6a47ba903ccbb83a3c5fc00e92724c17bf48`  
		Last Modified: Fri, 07 Apr 2017 17:59:51 GMT  
		Size: 10.5 MB (10484958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0da182fec9e38735c84aea5b3f3b95e998395ef29ab0aef25bbb0a8a78c7cb58`  
		Last Modified: Thu, 20 Apr 2017 14:56:46 GMT  
		Size: 896.1 KB (896142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd69751ca1220e3e5a9be7badab2da075cc4336ffc7cbfd07f5a427528427e86`  
		Last Modified: Thu, 20 Apr 2017 20:12:24 GMT  
		Size: 8.3 KB (8318 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9d400c0c941cefbcddccf18b2802b972dceaacad021b0e403623158fbe904cf`  
		Last Modified: Thu, 20 Apr 2017 20:12:22 GMT  
		Size: 1.3 MB (1340403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f27a50571167b9243164d6a9426027ad33c69261a25b12ce59b1cc6dd6b95eda`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a52bd0f5fcc76f3896bf1612a3df3914fd4a8d55c5be16012919ec6c2525525`  
		Last Modified: Thu, 20 Apr 2017 20:12:28 GMT  
		Size: 27.3 MB (27258795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:345ef92805c54454c6f763913fa514ff59a1cce974e78c15198683d4b3af54ef`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2a278ec740a7ad3dedc42d6ec1122f6e1859c7becbcad755a4d75adf068d454`  
		Last Modified: Thu, 20 Apr 2017 20:12:21 GMT  
		Size: 598.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
