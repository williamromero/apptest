The default interactive shell is now zsh.
To update your account to use zsh, please run `chsh -s /bin/zsh`.
For more details, please visit https://support.apple.com/kb/HT208050.
imac-de-william:apptest williamromero$ docker-compose build
db uses an image, skipping
Building app
Step 1/25 : FROM ruby:2.5-alpine
 ---> cbd297d70a23
Step 2/25 : RUN apk update
 ---> Using cache
 ---> 7563418647a8
Step 3/25 : RUN apk add nodejs
 ---> Using cache
 ---> 10d2afb46c90
Step 4/25 : ADD Gemfile Gemfile
 ---> Using cache
 ---> 5781b9a2c43c
Step 5/25 : ADD Gemfile.lock Gemfile.lock
 ---> Using cache
 ---> 3fa06e42ae21
Step 6/25 : RUN apk update &&     apk add --no-cache     tzdata git make     build-base bash openssh     mysql     mysql-client     mysql-dev      imagemagick
 ---> Using cache
 ---> 9438b14e6d17
Step 7/25 : RUN gem install bundler:2.1.4
 ---> Using cache
 ---> 9eb7bcd81f0b
Step 8/25 : RUN apk add --no-cache build-base
 ---> Using cache
 ---> aa28e87d0947
Step 9/25 : RUN gem install mysql2
 ---> Using cache
 ---> a0fe4ba168df
Step 10/25 : RUN gem install ffi
 ---> Using cache
 ---> f8cfff1ca19c
Step 11/25 : RUN gem install nokogiri
 ---> Using cache
 ---> 82d4b5f860e1
Step 12/25 : RUN bundle install
 ---> Running in d0d597e65e5f
Your Ruby version is 2.5.7, but your Gemfile specified 2.5.1
ERROR: Service 'app' failed to build: The command '/bin/sh -c bundle install' returned a non-zero code: 18
imac-de-william:apptest williamromero$ docker-compose build
db uses an image, skipping
Building app
Step 1/25 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/25 : RUN apk update
---> Using cache
---> 7563418647a8
Step 3/25 : RUN apk add nodejs
---> Using cache
---> 10d2afb46c90
Step 4/25 : ADD Gemfile Gemfile
---> Using cache
---> 0685a33eb22f
Step 5/25 : ADD Gemfile.lock Gemfile.lock
---> Using cache
---> 4ca73d276b87
Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Using cache
---> 00f0f0cbf5f1
Step 7/25 : RUN gem install bundler:2.1.4
---> Using cache
---> 388ace140a91
Step 8/25 : RUN apk add --no-cache build-base
---> Using cache
---> c4cfbd6c002c
Step 9/25 : RUN gem install mysql2
---> Using cache
---> f3797bfb9540
Step 10/25 : RUN gem install ffi
---> Using cache
---> 168caed753c3
Step 11/25 : RUN gem install nokogiri
---> Using cache
---> 79c3a848e1cc
Step 12/25 : RUN bundle install
---> Using cache
---> f7045d1a7da3
Step 13/25 : ENV RAILS_ROOT ./apptest
---> Using cache
---> 8a099c3cd559
Step 14/25 : COPY . /apptest
---> 5365f8e29581
Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Running in 01932fb52c32
Removing intermediate container 01932fb52c32
 ---> 27464f54401d
Step 16/25 : WORKDIR $RAILS_ROOT
---> Running in 6f0498f9c75d
Removing intermediate container 6f0498f9c75d
---> c069b72be9da
Step 17/25 : ENV RAILS_ENV='production'
---> Running in 6fd7b10fa710
Removing intermediate container 6fd7b10fa710
---> 62d13b53e29e
Step 18/25 : ENV RACK_ENV='production'
---> Running in 187df6477c1f
Removing intermediate container 187df6477c1f
---> f2098d9f8cd8
Step 19/25 : ENV PORT 3000
---> Running in 67737c5d916d
Removing intermediate container 67737c5d916d
---> 1f1454d07c33
Step 20/25 : COPY Gemfile Gemfile
---> 34c19af3fd15
Step 21/25 : COPY Gemfile.lock Gemfile.lock
---> 8c318a801296
Step 22/25 : COPY . .
---> 776b894f26f8
Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in 835a810ae030
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
Removing intermediate container 835a810ae030
---> 5b156f9bf1c1
Step 24/25 : EXPOSE 3000
---> Running in 5910efd50b4b
Removing intermediate container 5910efd50b4b
---> 3b899bc9f4ca
Step 25/25 : RUN bundle exec puma -p 3000 -e production
---> Running in 7fbaaf06a1a6
Puma starting in single mode...

- Version 3.12.1 (ruby 2.5.7-p206), codename: Llamas in Pajamas
- Min threads: 5, max threads: 5
- Environment: production
- Listening on tcp://0.0.0.0:3000
  Use Ctrl-C to stop
  ERROR: Service 'app' failed to build: The command '/bin/sh -c bundle exec puma -p 3000 -e production' returned a non-zero code: 137
  imac-de-william:apptest williamromero\$ docker-compose build --no-cache
  db uses an image, skipping
  Building app
  Step 1/24 : FROM ruby:2.5-alpine
  ---> cbd297d70a23
  Step 2/24 : RUN apk update
  ---> Running in a86d8eed8da4
  fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
  fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
  v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
  v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
  OK: 11264 distinct packages available
  Removing intermediate container a86d8eed8da4
  ---> 2552203edb0a
  Step 3/24 : RUN apk add nodejs
  ---> Running in 9d0ecf3d0c90
  (1/4) Installing c-ares (1.15.0-r0)
  (2/4) Installing nghttp2-libs (1.40.0-r0)
  (3/4) Installing libuv (1.34.0-r0)
  (4/4) Installing nodejs (12.15.0-r1)
  Executing busybox-1.31.1-r9.trigger
  OK: 54 MiB in 41 packages
  Removing intermediate container 9d0ecf3d0c90
  ---> 55cd9930e6ba
  Step 4/24 : ADD Gemfile Gemfile
  ---> 39b606a75d4f
  Step 5/24 : ADD Gemfile.lock Gemfile.lock
  ---> c1e110efb37b
  Step 6/24 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
  ---> Running in 7133a41434ae
  fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
  fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
  v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
  v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
  OK: 11264 distinct packages available
  fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
  fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
  (1/89) Installing bash (5.0.11-r1)
  Executing bash-5.0.11-r1.post-install
  (2/89) Installing binutils (2.33.1-r0)
  (3/89) Installing libmagic (5.37-r1)
  (4/89) Installing file (5.37-r1)
  (5/89) Installing isl (0.18-r0)
  (6/89) Installing libgomp (9.2.0-r3)
  (7/89) Installing libatomic (9.2.0-r3)
  (8/89) Installing mpfr4 (4.0.2-r1)
  (9/89) Installing mpc1 (1.1.0-r1)
  (10/89) Installing gcc (9.2.0-r3)
  (11/89) Installing musl-dev (1.1.24-r0)
  (12/89) Installing libc-dev (0.7.2-r0)
  (13/89) Installing g++ (9.2.0-r3)
  (14/89) Installing make (4.2.1-r2)
  (15/89) Installing fortify-headers (1.1-r0)
  (16/89) Installing build-base (0.5-r1)
  (17/89) Installing libcurl (7.67.0-r0)
  (18/89) Installing expat (2.2.9-r1)
  (19/89) Installing pcre2 (10.34-r1)
  (20/89) Installing git (2.24.1-r0)
  (21/89) Installing libxau (1.0.9-r0)
  (22/89) Installing libbsd (0.10.0-r0)
  (23/89) Installing libxdmcp (1.1.3-r0)
  (24/89) Installing libxcb (1.13.1-r0)
  (25/89) Installing libx11 (1.6.9-r0)
  (26/89) Installing libxext (1.3.4-r0)
  (27/89) Installing libbz2 (1.0.8-r1)
  (28/89) Installing libpng (1.6.37-r1)
  (29/89) Installing freetype (2.10.1-r0)
  (30/89) Installing libuuid (2.34-r1)
  (31/89) Installing fontconfig (2.13.1-r2)
  (32/89) Installing lcms2 (2.9-r1)
  (33/89) Installing libltdl (2.4.6-r7)
  (34/89) Installing xz-libs (5.2.4-r0)
  (35/89) Installing libxml2 (2.9.10-r2)
  (36/89) Installing imagemagick-libs (7.0.9.7-r0)
  (37/89) Installing libxrender (0.9.10-r3)
  (38/89) Installing pixman (0.38.4-r0)
  (39/89) Installing cairo (1.16.0-r2)
  (40/89) Installing libblkid (2.34-r1)
  (41/89) Installing libmount (2.34-r1)
  (42/89) Installing pcre (8.43-r0)
  (43/89) Installing glib (2.62.4-r0)
  (44/89) Installing dbus-libs (1.12.16-r2)
  (45/89) Installing avahi-libs (0.7-r4)
  (46/89) Installing nettle (3.5.1-r0)
  (47/89) Installing p11-kit (0.23.18.1-r0)
  (48/89) Installing libtasn1 (4.15.0-r0)
  (49/89) Installing libunistring (0.9.10-r0)
  (50/89) Installing gnutls (3.6.10-r0)
  (51/89) Installing cups-libs (2.2.12-r1)
  (52/89) Installing jbig2dec (0.17-r0)
  (53/89) Installing libjpeg-turbo (2.0.4-r0)
  (54/89) Installing tiff (4.1.0-r0)
  (55/89) Installing ghostscript (9.50-r0)
  (56/89) Installing libde265 (1.0.3-r0)
  (57/89) Installing x265-libs (3.2.1-r0)
  (58/89) Installing libheif (1.6.0-r0)
  (59/89) Installing libcroco (0.6.13-r1)
  (60/89) Installing shared-mime-info (1.15-r0)
  (61/89) Installing gdk-pixbuf (2.40.0-r0)
  (62/89) Installing libxft (2.3.3-r0)
  (63/89) Installing fribidi (1.0.8-r0)
  (64/89) Installing graphite2 (1.3.13-r1)
  (65/89) Installing harfbuzz (2.6.4-r0)
  (66/89) Installing pango (1.44.7-r0)
  (67/89) Installing librsvg (2.46.4-r0)
  (68/89) Installing libwebp (1.0.3-r0)
  (69/89) Installing imagemagick (7.0.9.7-r0)
  (70/89) Installing mariadb-common (10.4.12-r0)
  (71/89) Installing libaio (0.3.112-r1)
  (72/89) Installing linux-pam (1.3.1-r1)
  (73/89) Installing mariadb (10.4.12-r0)
  Executing mariadb-10.4.12-r0.pre-install
  (74/89) Installing mysql (10.4.12-r0)
  (75/89) Installing mariadb-client (10.4.12-r0)
  (76/89) Installing mysql-client (10.4.12-r0)
  (77/89) Installing openssl-dev (1.1.1d-r3)
  (78/89) Installing mariadb-connector-c (3.1.6-r0)
  (79/89) Installing mariadb-connector-c-dev (3.1.6-r0)
  (80/89) Installing mariadb-embedded (10.4.12-r0)
  (81/89) Installing mariadb-dev (10.4.12-r0)
  (82/89) Installing openssh-keygen (8.1_p1-r0)
  (83/89) Installing libedit (20191211.3.1-r0)
  (84/89) Installing openssh-client (8.1_p1-r0)
  (85/89) Installing openssh-sftp-server (8.1_p1-r0)
  (86/89) Installing openssh-server-common (8.1_p1-r0)
  (87/89) Installing openssh-server (8.1_p1-r0)
  (88/89) Installing openssh (8.1_p1-r0)
  (89/89) Installing tzdata (2019c-r0)
  Executing busybox-1.31.1-r9.trigger
  Executing fontconfig-2.13.1-r2.trigger
  Executing shared-mime-info-1.15-r0.trigger
  Executing gdk-pixbuf-2.40.0-r0.trigger
  OK: 522 MiB in 130 packages
  Removing intermediate container 7133a41434ae
  ---> 360d44357b88
  Step 7/24 : RUN gem install bundler:2.1.4
  ---> Running in 8cced70b16f9
  Successfully installed bundler-2.1.4
  1 gem installed
  Removing intermediate container 8cced70b16f9
  ---> 10b8e0f32e79
  Step 8/24 : RUN apk add --no-cache build-base
  ---> Running in 35e3987feaf2
  fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
  fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
  OK: 522 MiB in 130 packages
  Removing intermediate container 35e3987feaf2
  ---> 06f83302e44a
  Step 9/24 : RUN gem install mysql2
  ---> Running in c6c797f6e5ac
  Building native extensions. This could take a while...
  Successfully installed mysql2-0.5.3
  1 gem installed
  Removing intermediate container c6c797f6e5ac
  ---> 65c7227f4490
  Step 10/24 : RUN gem install ffi
  ---> Running in abcb5d38c80f
  Building native extensions. This could take a while...
  Successfully installed ffi-1.12.2
  1 gem installed
  Removing intermediate container abcb5d38c80f
  ---> a2dcbb5c02b7
  Step 11/24 : RUN gem install nokogiri
  ---> Running in 6cdeca8c4d12
  Successfully installed mini_portile2-2.4.0
  Building native extensions. This could take a while...
  Successfully installed nokogiri-1.10.8
  2 gems installed
  Removing intermediate container 6cdeca8c4d12
  ---> a25f8f699139
  Step 12/24 : RUN bundle install
  ---> Running in e10aacc27c8c
  The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
  Fetching gem metadata from https://rubygems.org/............
  Fetching gem metadata from https://rubygems.org/.
  Resolving dependencies...
  Fetching rake 12.3.3
  Installing rake 12.3.3
  Fetching concurrent-ruby 1.1.6
  Installing concurrent-ruby 1.1.6
  Fetching i18n 1.6.0
  Installing i18n 1.6.0
  Fetching minitest 5.12.2
  Installing minitest 5.12.2
  Fetching thread_safe 0.3.6
  Installing thread_safe 0.3.6
  Fetching tzinfo 1.2.5
  Installing tzinfo 1.2.5
  Fetching activesupport 5.2.3
  Installing activesupport 5.2.3
  Fetching builder 3.2.3
  Installing builder 3.2.3
  Fetching erubi 1.9.0
  Installing erubi 1.9.0
  Using mini_portile2 2.4.0
  Fetching nokogiri 1.10.4
  Installing nokogiri 1.10.4 with native extensions
  Fetching rails-dom-testing 2.0.3
  Installing rails-dom-testing 2.0.3
  Fetching crass 1.0.4
  Installing crass 1.0.4
  Fetching loofah 2.3.0
  Installing loofah 2.3.0
  Fetching rails-html-sanitizer 1.2.0
  Installing rails-html-sanitizer 1.2.0
  Fetching actionview 5.2.3
  Installing actionview 5.2.3
  Fetching rack 2.0.7
  Installing rack 2.0.7
  Fetching rack-test 1.1.0
  Installing rack-test 1.1.0
  Fetching actionpack 5.2.3
  Installing actionpack 5.2.3
  Fetching nio4r 2.5.2
  Installing nio4r 2.5.2 with native extensions
  Fetching websocket-extensions 0.1.4
  Installing websocket-extensions 0.1.4
  Fetching websocket-driver 0.7.1
  Installing websocket-driver 0.7.1 with native extensions
  Fetching actioncable 5.2.3
  Installing actioncable 5.2.3
  Fetching globalid 0.4.2
  Installing globalid 0.4.2
  Fetching activejob 5.2.3
  Installing activejob 5.2.3
  Fetching mini_mime 1.0.2
  Installing mini_mime 1.0.2
  Fetching mail 2.7.1
  Installing mail 2.7.1
  Fetching actionmailer 5.2.3
  Installing actionmailer 5.2.3
  Fetching activemodel 5.2.3
  Installing activemodel 5.2.3
  Fetching arel 9.0.0
  Installing arel 9.0.0
  Fetching activerecord 5.2.3
  Installing activerecord 5.2.3
  Fetching mimemagic 0.3.3
  Installing mimemagic 0.3.3
  Fetching marcel 0.3.3
  Installing marcel 0.3.3
  Fetching activestorage 5.2.3
  Installing activestorage 5.2.3
  Fetching public_suffix 4.0.1
  Installing public_suffix 4.0.1
  Fetching addressable 2.7.0
  Installing addressable 2.7.0
  Fetching io-like 0.3.0
  Installing io-like 0.3.0
  Fetching archive-zip 0.12.0
  Installing archive-zip 0.12.0
  Fetching bindex 0.8.1
  Installing bindex 0.8.1 with native extensions
  Fetching msgpack 1.3.1
  Installing msgpack 1.3.1 with native extensions
  Fetching bootsnap 1.4.5
  Installing bootsnap 1.4.5 with native extensions
  Using bundler 2.1.4
  Fetching byebug 11.0.1
  Installing byebug 11.0.1 with native extensions
  Fetching regexp_parser 1.6.0
  Installing regexp_parser 1.6.0
  Fetching xpath 3.2.0
  Installing xpath 3.2.0
  Fetching capybara 3.29.0
  Installing capybara 3.29.0
  Fetching childprocess 2.0.0
  Installing childprocess 2.0.0 with native extensions
  Fetching chromedriver-helper 2.1.1
  Installing chromedriver-helper 2.1.1
  Fetching coffee-script-source 1.12.2
  Installing coffee-script-source 1.12.2
  Fetching execjs 2.7.0
  Installing execjs 2.7.0
  Fetching coffee-script 2.4.1
  Installing coffee-script 2.4.1
  Fetching method_source 0.9.2
  Installing method_source 0.9.2
  Fetching thor 1.0.1
  Installing thor 1.0.1
  Fetching railties 5.2.3
  Installing railties 5.2.3
  Fetching coffee-rails 4.2.2
  Installing coffee-rails 4.2.2
  Fetching ffi 1.11.1
  Installing ffi 1.11.1 with native extensions
  Fetching jbuilder 2.9.1
  Installing jbuilder 2.9.1
  Fetching rb-fsevent 0.10.3
  Installing rb-fsevent 0.10.3
  Fetching rb-inotify 0.10.0
  Installing rb-inotify 0.10.0
  Fetching ruby_dep 1.5.0
  Installing ruby_dep 1.5.0
  Fetching listen 3.1.5
  Installing listen 3.1.5
  Using mysql2 0.5.3
  Fetching puma 3.12.1
  Installing puma 3.12.1 with native extensions
  Fetching sprockets 3.7.2
  Installing sprockets 3.7.2
  Fetching sprockets-rails 3.2.1
  Installing sprockets-rails 3.2.1
  Fetching rails 5.2.3
  Installing rails 5.2.3
  Fetching rubyzip 1.2.4
  Installing rubyzip 1.2.4
  Fetching sass-listen 4.0.0
  Installing sass-listen 4.0.0
  Fetching sass 3.7.4
  Installing sass 3.7.4
  Fetching tilt 2.0.10
  Installing tilt 2.0.10
  Fetching sass-rails 5.1.0
  Installing sass-rails 5.1.0
  Fetching selenium-webdriver 3.142.4
  Installing selenium-webdriver 3.142.4
  Fetching turbolinks-source 5.2.0
  Installing turbolinks-source 5.2.0
  Fetching turbolinks 5.2.1
  Installing turbolinks 5.2.1
  Fetching uglifier 4.2.0
  Installing uglifier 4.2.0
  Fetching web-console 3.7.0
  Installing web-console 3.7.0
  Bundle complete! 16 Gemfile dependencies, 76 gems now installed.
  Use `bundle info [gemname]` to see where a bundled gem is installed.
  Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0

Post-install message from chromedriver-helper:

+--------------------------------------------------------------------+
| |
| NOTICE: chromedriver-helper is deprecated after 2019-03-31. |
| |
| Please update to use the 'webdrivers' gem instead. |
| See https://github.com/flavorjones/chromedriver-helper/issues/83 |
| |
+--------------------------------------------------------------------+

Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

- If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

- If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

- For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Removing intermediate container e10aacc27c8c
---> 73f66c31e850
Step 13/24 : ENV RAILS_ROOT ./apptest
---> Running in c6c90ea4ed7c
Removing intermediate container c6c90ea4ed7c
---> c088907e96b8
Step 14/24 : COPY . /apptest
---> 39a82ee918c7
Step 15/24 : RUN mkdir -p $RAILS_ROOT
 ---> Running in 0b30d0a68141
Removing intermediate container 0b30d0a68141
 ---> 6f70c804a18f
Step 16/24 : WORKDIR $RAILS_ROOT
---> Running in 7b494afebcf2
Removing intermediate container 7b494afebcf2
---> e1fe9d62f867
Step 17/24 : ENV RAILS_ENV='production'
---> Running in 4adc0a4c1806
Removing intermediate container 4adc0a4c1806
---> a41da9e2d3a8
Step 18/24 : ENV RACK_ENV='production'
---> Running in c08b6a5a443e
Removing intermediate container c08b6a5a443e
---> d11e787dc907
Step 19/24 : ENV PORT 3000
---> Running in face2569162a
Removing intermediate container face2569162a
---> 76f6d95179e1
Step 20/24 : COPY Gemfile Gemfile
---> 76bc8ebed0af
Step 21/24 : COPY Gemfile.lock Gemfile.lock
---> af4cc345c8fa
Step 22/24 : COPY . .
---> cd7d7b256262
Step 23/24 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in 9e486e8260d8
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
Removing intermediate container 9e486e8260d8
---> 5af08ff3bf4c
Step 24/24 : EXPOSE 3000
---> Running in 7c8868850639
Removing intermediate container 7c8868850639
---> dcf1008e1c08
Successfully built dcf1008e1c08
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Running in 5b3144fc2a91
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
libapr1 libaprutil1 libgdbm6
Suggested packages:
gdbm-l10n
The following NEW packages will be installed:
apache2-utils libapr1 libaprutil1 libgdbm6
0 upgraded, 4 newly installed, 0 to remove and 9 not upgraded.
Need to get 495 kB of archives.
After this operation, 1157 kB of additional disk space will be used.
Get:1 http://deb.debian.org/debian buster/main amd64 libapr1 amd64 1.6.5-1+b1 [102 kB]
Get:2 http://deb.debian.org/debian buster/main amd64 libgdbm6 amd64 1.18.1-4 [64.7 kB]
Get:3 http://deb.debian.org/debian buster/main amd64 libaprutil1 amd64 1.6.1-4 [91.8 kB]
Get:4 http://deb.debian.org/debian buster/main amd64 apache2-utils amd64 2.4.38-3+deb10u3 [236 kB]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 495 kB in 1s (915 kB/s)
Selecting previously unselected package libapr1:amd64.
(Reading database ... 7203 files and directories currently installed.)
Preparing to unpack .../libapr1_1.6.5-1+b1_amd64.deb ...
Unpacking libapr1:amd64 (1.6.5-1+b1) ...
Selecting previously unselected package libgdbm6:amd64.
Preparing to unpack .../libgdbm6_1.18.1-4_amd64.deb ...
Unpacking libgdbm6:amd64 (1.18.1-4) ...
Selecting previously unselected package libaprutil1:amd64.
Preparing to unpack .../libaprutil1_1.6.1-4_amd64.deb ...
Unpacking libaprutil1:amd64 (1.6.1-4) ...
Selecting previously unselected package apache2-utils.
Preparing to unpack .../apache2-utils_2.4.38-3+deb10u3_amd64.deb ...
Unpacking apache2-utils (2.4.38-3+deb10u3) ...
Setting up libapr1:amd64 (1.6.5-1+b1) ...
Setting up libgdbm6:amd64 (1.18.1-4) ...
Setting up libaprutil1:amd64 (1.6.1-4) ...
Setting up apache2-utils (2.4.38-3+deb10u3) ...
Processing triggers for libc-bin (2.28-10) ...
Removing intermediate container 5b3144fc2a91
---> f98b62bc8652
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Running in 62f541e94bfc
Removing intermediate container 62f541e94bfc
---> 990d05403899
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Running in 60860dedef50
Removing intermediate container 60860dedef50
 ---> 51de3697998c
Step 5/9 : RUN mkdir log
 ---> Running in 70af0e53877d
Removing intermediate container 70af0e53877d
 ---> 2edbf98b2226
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> 8a738d1535ee
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Running in 55c62ccb9ea2
Removing intermediate container 55c62ccb9ea2
---> c333761c51db
Step 8/9 : EXPOSE 80
---> Running in 23af5ef54c8a
Removing intermediate container 23af5ef54c8a
---> 9b9b1dc9d6ec
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Running in 7c53cdcfa7d4
Removing intermediate container 7c53cdcfa7d4
---> a6cba090d4d0
Successfully built a6cba090d4d0
Successfully tagged apptest_web:latest
imac-de-william:apptest williamromero$ docker-compose up -d
Creating network "apptest_default" with the default driver
Creating apptest_db_1 ... done
Creating apptest_app_1 ... done
Creating apptest_web_1 ... done
imac-de-william:apptest williamromero$ docker-compose exec app bundle exec rake db:create db:schema:load
Created database 'apptest'
-- create_table("posts", {:options=>"ENGINE=InnoDB DEFAULT CHARSET=utf8", :force=>:cascade})
-> 0.0436s
imac-de-william:apptest williamromero\$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Gemfile
        modified:   docker-compose.yml
        modified:   docker/app/Dockerfile

no changes added to commit (use "git add" and/or "git commit -a")
imac-de-william:apptest williamromero\$ git diff docker-compose.yml
diff --git a/docker-compose.yml b/docker-compose.yml
index 7743fe3..5d0a497 100644
--- a/docker-compose.yml
+++ b/docker-compose.yml
@@ -4,6 +4,7 @@ services:
build:
context: .
dockerfile: docker/app/Dockerfile

- command: bundle exec puma -p 3000 -e production
  depends_on: - db
  volumes:
  imac-de-william:apptest williamromero\$ git diff docker/app/Dockerfile
  diff --git a/docker/app/Dockerfile b/docker/app/Dockerfile
  index b7a026c..aff14d1 100644
  --- a/docker/app/Dockerfile
  +++ b/docker/app/Dockerfile
  @@ -44,4 +44,5 @@ COPY . .
  RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile

EXPOSE 3000
-CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]
+# CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]
+# RUN bundle exec puma -p 3000 -e production
imac-de-william:apptest williamromero$ shh root@157.245.211.227
bash: shh: command not found
imac-de-william:apptest williamromero$ ssh root@157.245.211.227
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 4.15.0-66-generic x86_64)

- Documentation: https://help.ubuntu.com
- Management: https://landscape.canonical.com
- Support: https://ubuntu.com/advantage

System information as of Thu Feb 20 02:39:30 UTC 2020

System load: 0.0
Usage of /: 32.5% of 24.06GB
Memory usage: 40%
Swap usage: 0%
Processes: 92
Users logged in: 0
IP address for eth0: 157.245.211.227
IP address for eth1: 10.132.7.149
IP address for docker0: 172.17.0.1
IP address for br-7f66bbf64ec9: 172.23.0.1

102 packages can be updated.
55 updates are security updates.

Last login: Thu Feb 20 00:28:53 2020 from 190.148.52.47
root@dockserver:~# pwd
/root
root@dockserver:~# pwd
/root
root@dockserver:~# ls
apptest
root@dockserver:~# cd apptest
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
ecf56006e7c0 apptest_web "nginx -g 'daemon of…" 2 hours ago Up 2 hours 0.0.0.0:80->80/tcp apptest_web_1
d96f6c2d4dfc mysql:5.7.18 "docker-entrypoint.s…" 2 hours ago Up 2 hours 0.0.0.0:3306->3306/tcp apptest_db_1
root@dockserver:~/apptest# docker-compose down
Stopping apptest_web_1 ... done
Stopping apptest_db_1 ... done
Removing apptest_web_1 ... done
Removing apptest_app_1 ... done
Removing apptest_db_1 ... done
Removing network apptest_default
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
root@dockserver:~/apptest# docker-compose build
db uses an image, skipping
Building app
^CERROR: Aborting.
root@dockserver:~/apptest# docker-compose build --no-cache
db uses an image, skipping
Building app
Step 1/25 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/25 : RUN apk update
---> Running in 54ac09bba5a1
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
Removing intermediate container 54ac09bba5a1
---> 9978a1f8499d
Step 3/25 : RUN apk add nodejs
---> Running in 16393b7d92bc
(1/4) Installing c-ares (1.15.0-r0)
(2/4) Installing nghttp2-libs (1.40.0-r0)
(3/4) Installing libuv (1.34.0-r0)
(4/4) Installing nodejs (12.15.0-r1)
Executing busybox-1.31.1-r9.trigger
OK: 54 MiB in 41 packages
Removing intermediate container 16393b7d92bc
---> 74ed3bb33ee0
Step 4/25 : ADD Gemfile Gemfile
---> a3641ca3d19d
Step 5/25 : ADD Gemfile.lock Gemfile.lock
---> b1be35d0b100
Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Running in cd2f09c2220f
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
(1/89) Installing bash (5.0.11-r1)
Executing bash-5.0.11-r1.post-install
(2/89) Installing binutils (2.33.1-r0)
(3/89) Installing libmagic (5.37-r1)
(4/89) Installing file (5.37-r1)
(5/89) Installing isl (0.18-r0)
(6/89) Installing libgomp (9.2.0-r3)
(7/89) Installing libatomic (9.2.0-r3)
(8/89) Installing mpfr4 (4.0.2-r1)
(9/89) Installing mpc1 (1.1.0-r1)
(10/89) Installing gcc (9.2.0-r3)
(11/89) Installing musl-dev (1.1.24-r0)
(12/89) Installing libc-dev (0.7.2-r0)
(13/89) Installing g++ (9.2.0-r3)
(14/89) Installing make (4.2.1-r2)
(15/89) Installing fortify-headers (1.1-r0)
(16/89) Installing build-base (0.5-r1)
(17/89) Installing libcurl (7.67.0-r0)
(18/89) Installing expat (2.2.9-r1)
(19/89) Installing pcre2 (10.34-r1)
(20/89) Installing git (2.24.1-r0)
(21/89) Installing libxau (1.0.9-r0)
(22/89) Installing libbsd (0.10.0-r0)
(23/89) Installing libxdmcp (1.1.3-r0)
(24/89) Installing libxcb (1.13.1-r0)
(25/89) Installing libx11 (1.6.9-r0)
(26/89) Installing libxext (1.3.4-r0)
(27/89) Installing libbz2 (1.0.8-r1)
(28/89) Installing libpng (1.6.37-r1)
(29/89) Installing freetype (2.10.1-r0)
(30/89) Installing libuuid (2.34-r1)
(31/89) Installing fontconfig (2.13.1-r2)
(32/89) Installing lcms2 (2.9-r1)
(33/89) Installing libltdl (2.4.6-r7)
(34/89) Installing xz-libs (5.2.4-r0)
(35/89) Installing libxml2 (2.9.10-r2)
(36/89) Installing imagemagick-libs (7.0.9.7-r0)
(37/89) Installing libxrender (0.9.10-r3)
(38/89) Installing pixman (0.38.4-r0)
(39/89) Installing cairo (1.16.0-r2)
(40/89) Installing libblkid (2.34-r1)
(41/89) Installing libmount (2.34-r1)
(42/89) Installing pcre (8.43-r0)
(43/89) Installing glib (2.62.4-r0)
(44/89) Installing dbus-libs (1.12.16-r2)
(45/89) Installing avahi-libs (0.7-r4)
(46/89) Installing nettle (3.5.1-r0)
(47/89) Installing p11-kit (0.23.18.1-r0)
(48/89) Installing libtasn1 (4.15.0-r0)
(49/89) Installing libunistring (0.9.10-r0)
(50/89) Installing gnutls (3.6.10-r0)
(51/89) Installing cups-libs (2.2.12-r1)
(52/89) Installing jbig2dec (0.17-r0)
(53/89) Installing libjpeg-turbo (2.0.4-r0)
(54/89) Installing tiff (4.1.0-r0)
(55/89) Installing ghostscript (9.50-r0)
(56/89) Installing libde265 (1.0.3-r0)
(57/89) Installing x265-libs (3.2.1-r0)
(58/89) Installing libheif (1.6.0-r0)
(59/89) Installing libcroco (0.6.13-r1)
(60/89) Installing shared-mime-info (1.15-r0)
(61/89) Installing gdk-pixbuf (2.40.0-r0)
(62/89) Installing libxft (2.3.3-r0)
(63/89) Installing fribidi (1.0.8-r0)
(64/89) Installing graphite2 (1.3.13-r1)
(65/89) Installing harfbuzz (2.6.4-r0)
(66/89) Installing pango (1.44.7-r0)
(67/89) Installing librsvg (2.46.4-r0)
(68/89) Installing libwebp (1.0.3-r0)
(69/89) Installing imagemagick (7.0.9.7-r0)
(70/89) Installing mariadb-common (10.4.12-r0)
(71/89) Installing libaio (0.3.112-r1)
(72/89) Installing linux-pam (1.3.1-r1)
(73/89) Installing mariadb (10.4.12-r0)
Executing mariadb-10.4.12-r0.pre-install
(74/89) Installing mysql (10.4.12-r0)
(75/89) Installing mariadb-client (10.4.12-r0)
(76/89) Installing mysql-client (10.4.12-r0)
(77/89) Installing openssl-dev (1.1.1d-r3)
(78/89) Installing mariadb-connector-c (3.1.6-r0)
(79/89) Installing mariadb-connector-c-dev (3.1.6-r0)
(80/89) Installing mariadb-embedded (10.4.12-r0)
(81/89) Installing mariadb-dev (10.4.12-r0)
(82/89) Installing openssh-keygen (8.1_p1-r0)
(83/89) Installing libedit (20191211.3.1-r0)
(84/89) Installing openssh-client (8.1_p1-r0)
(85/89) Installing openssh-sftp-server (8.1_p1-r0)
(86/89) Installing openssh-server-common (8.1_p1-r0)
(87/89) Installing openssh-server (8.1_p1-r0)
(88/89) Installing openssh (8.1_p1-r0)
(89/89) Installing tzdata (2019c-r0)
Executing busybox-1.31.1-r9.trigger
Executing fontconfig-2.13.1-r2.trigger
Executing shared-mime-info-1.15-r0.trigger
Executing gdk-pixbuf-2.40.0-r0.trigger
OK: 522 MiB in 130 packages
Removing intermediate container cd2f09c2220f
---> 99d6bf925748
Step 7/25 : RUN gem install bundler:2.1.4
---> Running in 5d8740a4384a
Successfully installed bundler-2.1.4
1 gem installed
Removing intermediate container 5d8740a4384a
---> 685853dd4ddf
Step 8/25 : RUN apk add --no-cache build-base
---> Running in bd6118d18f29
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
OK: 522 MiB in 130 packages
Removing intermediate container bd6118d18f29
---> 86d155ce78ac
Step 9/25 : RUN gem install mysql2
---> Running in 9b9fcb40009e
Building native extensions. This could take a while...
Successfully installed mysql2-0.5.3
1 gem installed
Removing intermediate container 9b9fcb40009e
---> 9385ac435ddb
Step 10/25 : RUN gem install ffi
---> Running in 033ec960e2ec
Building native extensions. This could take a while...
Successfully installed ffi-1.12.2
1 gem installed
Removing intermediate container 033ec960e2ec
---> 796ac45c319f
Step 11/25 : RUN gem install nokogiri
---> Running in 9e6e8592b17b
Successfully installed mini_portile2-2.4.0
Building native extensions. This could take a while...
Successfully installed nokogiri-1.10.8
2 gems installed
Removing intermediate container 9e6e8592b17b
---> 62264f5e5eb6
Step 12/25 : RUN bundle install
---> Running in 3483d212042c
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/............
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Fetching rake 12.3.3
Installing rake 12.3.3
Fetching concurrent-ruby 1.1.6
Installing concurrent-ruby 1.1.6
Fetching i18n 1.6.0
Installing i18n 1.6.0
Fetching minitest 5.12.2
Installing minitest 5.12.2
Fetching thread_safe 0.3.6
Installing thread_safe 0.3.6
Fetching tzinfo 1.2.5
Installing tzinfo 1.2.5
Fetching activesupport 5.2.3
Installing activesupport 5.2.3
Fetching builder 3.2.3
Installing builder 3.2.3
Fetching erubi 1.9.0
Installing erubi 1.9.0
Using mini_portile2 2.4.0
Fetching nokogiri 1.10.4
Installing nokogiri 1.10.4 with native extensions
Fetching rails-dom-testing 2.0.3
Installing rails-dom-testing 2.0.3
Fetching crass 1.0.4
Installing crass 1.0.4
Fetching loofah 2.3.0
Installing loofah 2.3.0
Fetching rails-html-sanitizer 1.2.0
Installing rails-html-sanitizer 1.2.0
Fetching actionview 5.2.3
Installing actionview 5.2.3
Fetching rack 2.0.7
Installing rack 2.0.7
Fetching rack-test 1.1.0
Installing rack-test 1.1.0
Fetching actionpack 5.2.3
Installing actionpack 5.2.3
Fetching nio4r 2.5.2
Installing nio4r 2.5.2 with native extensions
Fetching websocket-extensions 0.1.4
Installing websocket-extensions 0.1.4
Fetching websocket-driver 0.7.1
Installing websocket-driver 0.7.1 with native extensions
Fetching actioncable 5.2.3
Installing actioncable 5.2.3
Fetching globalid 0.4.2
Installing globalid 0.4.2
Fetching activejob 5.2.3
Installing activejob 5.2.3
Fetching mini_mime 1.0.2
Installing mini_mime 1.0.2
Fetching mail 2.7.1
Installing mail 2.7.1
Fetching actionmailer 5.2.3
Installing actionmailer 5.2.3
Fetching activemodel 5.2.3
Installing activemodel 5.2.3
Fetching arel 9.0.0
Installing arel 9.0.0
Fetching activerecord 5.2.3
Installing activerecord 5.2.3
Fetching mimemagic 0.3.3
Installing mimemagic 0.3.3
Fetching marcel 0.3.3
Installing marcel 0.3.3
Fetching activestorage 5.2.3
Installing activestorage 5.2.3
Fetching public_suffix 4.0.1
Installing public_suffix 4.0.1
Fetching addressable 2.7.0
Installing addressable 2.7.0
Fetching io-like 0.3.0
Installing io-like 0.3.0
Fetching archive-zip 0.12.0
Installing archive-zip 0.12.0
Fetching bindex 0.8.1
Installing bindex 0.8.1 with native extensions
Fetching msgpack 1.3.1
Installing msgpack 1.3.1 with native extensions
Fetching bootsnap 1.4.5
Installing bootsnap 1.4.5 with native extensions
Using bundler 2.1.4
Fetching byebug 11.0.1
Installing byebug 11.0.1 with native extensions
Fetching regexp_parser 1.6.0
Installing regexp_parser 1.6.0
Fetching xpath 3.2.0
Installing xpath 3.2.0
Fetching capybara 3.29.0
Installing capybara 3.29.0
Fetching childprocess 2.0.0
Installing childprocess 2.0.0 with native extensions
Fetching chromedriver-helper 2.1.1
Installing chromedriver-helper 2.1.1
Fetching coffee-script-source 1.12.2
Installing coffee-script-source 1.12.2
Fetching execjs 2.7.0
Installing execjs 2.7.0
Fetching coffee-script 2.4.1
Installing coffee-script 2.4.1
Fetching method_source 0.9.2
Installing method_source 0.9.2
Fetching thor 1.0.1
Installing thor 1.0.1
Fetching railties 5.2.3
Installing railties 5.2.3
Fetching coffee-rails 4.2.2
Installing coffee-rails 4.2.2
Fetching ffi 1.11.1
Installing ffi 1.11.1 with native extensions
Fetching jbuilder 2.9.1
Installing jbuilder 2.9.1
Fetching rb-fsevent 0.10.3
Installing rb-fsevent 0.10.3
Fetching rb-inotify 0.10.0
Installing rb-inotify 0.10.0
Fetching ruby_dep 1.5.0
Installing ruby_dep 1.5.0
Fetching listen 3.1.5
Installing listen 3.1.5
Using mysql2 0.5.3
Fetching puma 3.12.1
Installing puma 3.12.1 with native extensions
Fetching sprockets 3.7.2
Installing sprockets 3.7.2
Fetching sprockets-rails 3.2.1
Installing sprockets-rails 3.2.1
Fetching rails 5.2.3
Installing rails 5.2.3
Fetching rubyzip 1.2.4
Installing rubyzip 1.2.4
Fetching sass-listen 4.0.0
Installing sass-listen 4.0.0
Fetching sass 3.7.4
Installing sass 3.7.4
Fetching tilt 2.0.10
Installing tilt 2.0.10
Fetching sass-rails 5.1.0
Installing sass-rails 5.1.0
Fetching selenium-webdriver 3.142.4
Installing selenium-webdriver 3.142.4
Fetching turbolinks-source 5.2.0
Installing turbolinks-source 5.2.0
Fetching turbolinks 5.2.1
Installing turbolinks 5.2.1
Fetching uglifier 4.2.0
Installing uglifier 4.2.0
Fetching web-console 3.7.0
Installing web-console 3.7.0
Bundle complete! 16 Gemfile dependencies, 76 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0

Post-install message from chromedriver-helper:

+--------------------------------------------------------------------+
| |
| NOTICE: chromedriver-helper is deprecated after 2019-03-31. |
| |
| Please update to use the 'webdrivers' gem instead. |
| See https://github.com/flavorjones/chromedriver-helper/issues/83 |
| |
+--------------------------------------------------------------------+

Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

- If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

- If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

- For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Removing intermediate container 3483d212042c
---> 28716385eb74
Step 13/25 : ENV RAILS_ROOT ./apptest
---> Running in 1c1a018cf436
Removing intermediate container 1c1a018cf436
---> 2fd3c6bb64e9
Step 14/25 : COPY . /apptest
---> f5cc86176340
Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Running in 64b81645e94d
Removing intermediate container 64b81645e94d
 ---> 90475134eeb2
Step 16/25 : WORKDIR $RAILS_ROOT
---> Running in 9de86995c2bf
Removing intermediate container 9de86995c2bf
---> 3dc538e1fce5
Step 17/25 : ENV RAILS_ENV='production'
---> Running in c71c99861622
Removing intermediate container c71c99861622
---> dab2b8094db3
Step 18/25 : ENV RACK_ENV='production'
---> Running in 4abe55437cf9
Removing intermediate container 4abe55437cf9
---> 2821e044a4c9
Step 19/25 : ENV PORT 3000
---> Running in 2b0243298b04
Removing intermediate container 2b0243298b04
---> 30c84cf4288c
Step 20/25 : COPY Gemfile Gemfile
---> 4ac0f2d9fa61
Step 21/25 : COPY Gemfile.lock Gemfile.lock
---> 68cb830d2e47
Step 22/25 : COPY . .
---> 9651f762f1e1
Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in a78af2936582
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T02:44:02.104322 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T02:44:02.105603 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T02:44:02.147303 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T02:44:02.148362 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container a78af2936582
---> 1e85f64e5938
Step 24/25 : EXPOSE 3000
---> Running in b356e05255e0
Removing intermediate container b356e05255e0
---> 79d390421e39
Step 25/25 : CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]
---> Running in c0a27f0228a7
Removing intermediate container c0a27f0228a7
---> 056b35ab341d
Successfully built 056b35ab341d
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Running in 3614f3718b96
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
libapr1 libaprutil1 libgdbm6
Suggested packages:
gdbm-l10n
The following NEW packages will be installed:
apache2-utils libapr1 libaprutil1 libgdbm6
0 upgraded, 4 newly installed, 0 to remove and 9 not upgraded.
Need to get 495 kB of archives.
After this operation, 1157 kB of additional disk space will be used.
Get:1 http://deb.debian.org/debian buster/main amd64 libapr1 amd64 1.6.5-1+b1 [102 kB]
Get:2 http://deb.debian.org/debian buster/main amd64 libgdbm6 amd64 1.18.1-4 [64.7 kB]
Get:3 http://deb.debian.org/debian buster/main amd64 libaprutil1 amd64 1.6.1-4 [91.8 kB]
Get:4 http://deb.debian.org/debian buster/main amd64 apache2-utils amd64 2.4.38-3+deb10u3 [236 kB]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 495 kB in 0s (17.1 MB/s)
Selecting previously unselected package libapr1:amd64.
(Reading database ... 7203 files and directories currently installed.)
Preparing to unpack .../libapr1_1.6.5-1+b1_amd64.deb ...
Unpacking libapr1:amd64 (1.6.5-1+b1) ...
^CERROR: Aborting.
root@dockserver:~/apptest# git remote -v update && git status
Fetching origin
From https://github.com/williamromero/apptest
= [up to date] master -> origin/master
= [up to date] dependabot/bundler/loofah-2.4.0 -> origin/dependabot/bundler/loofah-2.4.0
= [up to date] dependabot/bundler/puma-3.12.2 -> origin/dependabot/bundler/puma-3.12.2
= [up to date] dependabot/bundler/rack-2.2.2 -> origin/dependabot/bundler/rack-2.2.2
= [up to date] dependabot/bundler/rubyzip-1.3.0 -> origin/dependabot/bundler/rubyzip-1.3.0
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Gemfile

no changes added to commit (use "git add" and/or "git commit -a")
root@dockserver:~/apptest# exit
logout
Connection to 157.245.211.227 closed.
imac-de-william:apptest williamromero$ ls
Gemfile                 app                     db                      lib                     public                  vendor
Gemfile.lock            bin                     db-data                 log                     storage                 yarn.lock
README.md               config                  docker                  node_modules            test
Rakefile                config.ru               docker-compose.yml      package.json            tmp
imac-de-william:apptest williamromero$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Gemfile
        modified:   docker-compose.yml
        modified:   docker/app/Dockerfile

no changes added to commit (use "git add" and/or "git commit -a")
imac-de-william:apptest williamromero$ git add docker-compose.yml docker/app/Dockerfile
imac-de-william:apptest williamromero$ git commit -m "Added modificaitons on docker-compose"
[master 04dda9d] Added modificaitons on docker-compose
2 files changed, 3 insertions(+), 1 deletion(-)
imac-de-william:apptest williamromero$ git push -u origin master
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 4 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (6/6), 638 bytes | 638.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
remote: 
remote: GitHub found 4 vulnerabilities on williamromero/apptest's default branch (1 high, 1 moderate, 2 low). To find out more, visit:
remote:      https://github.com/williamromero/apptest/network/alerts
remote: 
To https://github.com/williamromero/apptest.git
   0d2a267..04dda9d  master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
imac-de-william:apptest williamromero$ ssh root@157.245.211.227
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 4.15.0-66-generic x86_64)

- Documentation: https://help.ubuntu.com
- Management: https://landscape.canonical.com
- Support: https://ubuntu.com/advantage

System information as of Thu Feb 20 02:46:40 UTC 2020

System load: 0.1 Users logged in: 0
Usage of /: 37.2% of 24.06GB IP address for eth0: 157.245.211.227
Memory usage: 23% IP address for eth1: 10.132.7.149
Swap usage: 0% IP address for docker0: 172.17.0.1
Processes: 84

102 packages can be updated.
55 updates are security updates.

Last login: Thu Feb 20 02:39:30 2020 from 190.148.52.47
root@dockserver:~# cd apptest
root@dockserver:~/apptest# docker-compose build --no-cache
db uses an image, skipping
Building app
Step 1/25 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/25 : RUN apk update
---> Running in 7cadb3df9dc6
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
Removing intermediate container 7cadb3df9dc6
---> d20c88d4e0ae
Step 3/25 : RUN apk add nodejs
---> Running in 10c38227fd47
(1/4) Installing c-ares (1.15.0-r0)
(2/4) Installing nghttp2-libs (1.40.0-r0)
(3/4) Installing libuv (1.34.0-r0)
(4/4) Installing nodejs (12.15.0-r1)
Executing busybox-1.31.1-r9.trigger
OK: 54 MiB in 41 packages
Removing intermediate container 10c38227fd47
---> a46caa0d754d
Step 4/25 : ADD Gemfile Gemfile
---> 81076fb5690b
Step 5/25 : ADD Gemfile.lock Gemfile.lock
---> 1302a45217f4
Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Running in 6e034e39d0ac
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
(1/89) Installing bash (5.0.11-r1)
Executing bash-5.0.11-r1.post-install
(2/89) Installing binutils (2.33.1-r0)
(3/89) Installing libmagic (5.37-r1)
(4/89) Installing file (5.37-r1)
(5/89) Installing isl (0.18-r0)
(6/89) Installing libgomp (9.2.0-r3)
(7/89) Installing libatomic (9.2.0-r3)
(8/89) Installing mpfr4 (4.0.2-r1)
(9/89) Installing mpc1 (1.1.0-r1)
(10/89) Installing gcc (9.2.0-r3)
(11/89) Installing musl-dev (1.1.24-r0)
(12/89) Installing libc-dev (0.7.2-r0)
(13/89) Installing g++ (9.2.0-r3)
(14/89) Installing make (4.2.1-r2)
(15/89) Installing fortify-headers (1.1-r0)
(16/89) Installing build-base (0.5-r1)
(17/89) Installing libcurl (7.67.0-r0)
(18/89) Installing expat (2.2.9-r1)
(19/89) Installing pcre2 (10.34-r1)
(20/89) Installing git (2.24.1-r0)
(21/89) Installing libxau (1.0.9-r0)
(22/89) Installing libbsd (0.10.0-r0)
(23/89) Installing libxdmcp (1.1.3-r0)
(24/89) Installing libxcb (1.13.1-r0)
(25/89) Installing libx11 (1.6.9-r0)
(26/89) Installing libxext (1.3.4-r0)
(27/89) Installing libbz2 (1.0.8-r1)
(28/89) Installing libpng (1.6.37-r1)
(29/89) Installing freetype (2.10.1-r0)
(30/89) Installing libuuid (2.34-r1)
(31/89) Installing fontconfig (2.13.1-r2)
(32/89) Installing lcms2 (2.9-r1)
(33/89) Installing libltdl (2.4.6-r7)
(34/89) Installing xz-libs (5.2.4-r0)
(35/89) Installing libxml2 (2.9.10-r2)
(36/89) Installing imagemagick-libs (7.0.9.7-r0)
(37/89) Installing libxrender (0.9.10-r3)
(38/89) Installing pixman (0.38.4-r0)
(39/89) Installing cairo (1.16.0-r2)
(40/89) Installing libblkid (2.34-r1)
(41/89) Installing libmount (2.34-r1)
(42/89) Installing pcre (8.43-r0)
(43/89) Installing glib (2.62.4-r0)
(44/89) Installing dbus-libs (1.12.16-r2)
(45/89) Installing avahi-libs (0.7-r4)
(46/89) Installing nettle (3.5.1-r0)
(47/89) Installing p11-kit (0.23.18.1-r0)
(48/89) Installing libtasn1 (4.15.0-r0)
(49/89) Installing libunistring (0.9.10-r0)
(50/89) Installing gnutls (3.6.10-r0)
(51/89) Installing cups-libs (2.2.12-r1)
(52/89) Installing jbig2dec (0.17-r0)
(53/89) Installing libjpeg-turbo (2.0.4-r0)
(54/89) Installing tiff (4.1.0-r0)
(55/89) Installing ghostscript (9.50-r0)
(56/89) Installing libde265 (1.0.3-r0)
(57/89) Installing x265-libs (3.2.1-r0)
(58/89) Installing libheif (1.6.0-r0)
(59/89) Installing libcroco (0.6.13-r1)
(60/89) Installing shared-mime-info (1.15-r0)
(61/89) Installing gdk-pixbuf (2.40.0-r0)
(62/89) Installing libxft (2.3.3-r0)
(63/89) Installing fribidi (1.0.8-r0)
(64/89) Installing graphite2 (1.3.13-r1)
(65/89) Installing harfbuzz (2.6.4-r0)
(66/89) Installing pango (1.44.7-r0)
(67/89) Installing librsvg (2.46.4-r0)
(68/89) Installing libwebp (1.0.3-r0)
(69/89) Installing imagemagick (7.0.9.7-r0)
(70/89) Installing mariadb-common (10.4.12-r0)
(71/89) Installing libaio (0.3.112-r1)
(72/89) Installing linux-pam (1.3.1-r1)
(73/89) Installing mariadb (10.4.12-r0)
Executing mariadb-10.4.12-r0.pre-install
(74/89) Installing mysql (10.4.12-r0)
(75/89) Installing mariadb-client (10.4.12-r0)
(76/89) Installing mysql-client (10.4.12-r0)
(77/89) Installing openssl-dev (1.1.1d-r3)
(78/89) Installing mariadb-connector-c (3.1.6-r0)
(79/89) Installing mariadb-connector-c-dev (3.1.6-r0)
(80/89) Installing mariadb-embedded (10.4.12-r0)
(81/89) Installing mariadb-dev (10.4.12-r0)
(82/89) Installing openssh-keygen (8.1_p1-r0)
(83/89) Installing libedit (20191211.3.1-r0)
(84/89) Installing openssh-client (8.1_p1-r0)
(85/89) Installing openssh-sftp-server (8.1_p1-r0)
(86/89) Installing openssh-server-common (8.1_p1-r0)
(87/89) Installing openssh-server (8.1_p1-r0)
(88/89) Installing openssh (8.1_p1-r0)
(89/89) Installing tzdata (2019c-r0)
Executing busybox-1.31.1-r9.trigger
Executing fontconfig-2.13.1-r2.trigger
Executing shared-mime-info-1.15-r0.trigger
Executing gdk-pixbuf-2.40.0-r0.trigger
OK: 522 MiB in 130 packages
Removing intermediate container 6e034e39d0ac
---> 49184896363a
Step 7/25 : RUN gem install bundler:2.1.4
---> Running in f02418ca4320
Successfully installed bundler-2.1.4
1 gem installed
Removing intermediate container f02418ca4320
---> 06676c0bfd84
Step 8/25 : RUN apk add --no-cache build-base
---> Running in 14ce8b3c0627
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
OK: 522 MiB in 130 packages
Removing intermediate container 14ce8b3c0627
---> a5946107aaed
Step 9/25 : RUN gem install mysql2
---> Running in b2aff74aceec
Building native extensions. This could take a while...
Successfully installed mysql2-0.5.3
1 gem installed
Removing intermediate container b2aff74aceec
---> e2ac231902fc
Step 10/25 : RUN gem install ffi
---> Running in c6d3a17df9c9
Building native extensions. This could take a while...
Successfully installed ffi-1.12.2
1 gem installed
Removing intermediate container c6d3a17df9c9
---> c1619eb8683c
Step 11/25 : RUN gem install nokogiri
---> Running in 998f801de311
Successfully installed mini_portile2-2.4.0
Building native extensions. This could take a while...
Successfully installed nokogiri-1.10.8
2 gems installed
Removing intermediate container 998f801de311
---> 31fa4f6c4ea5
Step 12/25 : RUN bundle install
---> Running in 33d386a993ff
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/............
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Fetching rake 12.3.3
Installing rake 12.3.3
Fetching concurrent-ruby 1.1.6
Installing concurrent-ruby 1.1.6
Fetching i18n 1.6.0
Installing i18n 1.6.0
Fetching minitest 5.12.2
Installing minitest 5.12.2
Fetching thread_safe 0.3.6
Installing thread_safe 0.3.6
Fetching tzinfo 1.2.5
Installing tzinfo 1.2.5
Fetching activesupport 5.2.3
Installing activesupport 5.2.3
Fetching builder 3.2.3
Installing builder 3.2.3
Fetching erubi 1.9.0
Installing erubi 1.9.0
Using mini_portile2 2.4.0
Fetching nokogiri 1.10.4
Installing nokogiri 1.10.4 with native extensions
Fetching rails-dom-testing 2.0.3
Installing rails-dom-testing 2.0.3
Fetching crass 1.0.4
Installing crass 1.0.4
Fetching loofah 2.3.0
Installing loofah 2.3.0
Fetching rails-html-sanitizer 1.2.0
Installing rails-html-sanitizer 1.2.0
Fetching actionview 5.2.3
Installing actionview 5.2.3
Fetching rack 2.0.7
Installing rack 2.0.7
Fetching rack-test 1.1.0
Installing rack-test 1.1.0
Fetching actionpack 5.2.3
Installing actionpack 5.2.3
Fetching nio4r 2.5.2
Installing nio4r 2.5.2 with native extensions
Fetching websocket-extensions 0.1.4
Installing websocket-extensions 0.1.4
Fetching websocket-driver 0.7.1
Installing websocket-driver 0.7.1 with native extensions
Fetching actioncable 5.2.3
Installing actioncable 5.2.3
Fetching globalid 0.4.2
Installing globalid 0.4.2
Fetching activejob 5.2.3
Installing activejob 5.2.3
Fetching mini_mime 1.0.2
Installing mini_mime 1.0.2
Fetching mail 2.7.1
Installing mail 2.7.1
Fetching actionmailer 5.2.3
Installing actionmailer 5.2.3
Fetching activemodel 5.2.3
Installing activemodel 5.2.3
Fetching arel 9.0.0
Installing arel 9.0.0
Fetching activerecord 5.2.3
Installing activerecord 5.2.3
Fetching mimemagic 0.3.3
Installing mimemagic 0.3.3
Fetching marcel 0.3.3
Installing marcel 0.3.3
Fetching activestorage 5.2.3
Installing activestorage 5.2.3
Fetching public_suffix 4.0.1
Installing public_suffix 4.0.1
Fetching addressable 2.7.0
Installing addressable 2.7.0
Fetching io-like 0.3.0
Installing io-like 0.3.0
Fetching archive-zip 0.12.0
Installing archive-zip 0.12.0
Fetching bindex 0.8.1
Installing bindex 0.8.1 with native extensions
Fetching msgpack 1.3.1
Installing msgpack 1.3.1 with native extensions
Fetching bootsnap 1.4.5
Installing bootsnap 1.4.5 with native extensions
Using bundler 2.1.4
Fetching byebug 11.0.1
Installing byebug 11.0.1 with native extensions
Fetching regexp_parser 1.6.0
Installing regexp_parser 1.6.0
Fetching xpath 3.2.0
Installing xpath 3.2.0
Fetching capybara 3.29.0
Installing capybara 3.29.0
Fetching childprocess 2.0.0
Installing childprocess 2.0.0 with native extensions
Fetching chromedriver-helper 2.1.1
Installing chromedriver-helper 2.1.1
Fetching coffee-script-source 1.12.2
Installing coffee-script-source 1.12.2
Fetching execjs 2.7.0
Installing execjs 2.7.0
Fetching coffee-script 2.4.1
Installing coffee-script 2.4.1
Fetching method_source 0.9.2
Installing method_source 0.9.2
Fetching thor 1.0.1
Installing thor 1.0.1
Fetching railties 5.2.3
Installing railties 5.2.3
Fetching coffee-rails 4.2.2
Installing coffee-rails 4.2.2
Fetching ffi 1.11.1
Installing ffi 1.11.1 with native extensions
Fetching jbuilder 2.9.1
Installing jbuilder 2.9.1
Fetching rb-fsevent 0.10.3
Installing rb-fsevent 0.10.3
Fetching rb-inotify 0.10.0
Installing rb-inotify 0.10.0
Fetching ruby_dep 1.5.0
Installing ruby_dep 1.5.0
Fetching listen 3.1.5
Installing listen 3.1.5
Using mysql2 0.5.3
Fetching puma 3.12.1
Installing puma 3.12.1 with native extensions
Fetching sprockets 3.7.2
Installing sprockets 3.7.2
Fetching sprockets-rails 3.2.1
Installing sprockets-rails 3.2.1
Fetching rails 5.2.3
Installing rails 5.2.3
Fetching rubyzip 1.2.4
Installing rubyzip 1.2.4
Fetching sass-listen 4.0.0
Installing sass-listen 4.0.0
Fetching sass 3.7.4
Installing sass 3.7.4
Fetching tilt 2.0.10
Installing tilt 2.0.10
Fetching sass-rails 5.1.0
Installing sass-rails 5.1.0
Fetching selenium-webdriver 3.142.4
Installing selenium-webdriver 3.142.4
Fetching turbolinks-source 5.2.0
Installing turbolinks-source 5.2.0
Fetching turbolinks 5.2.1
Installing turbolinks 5.2.1
Fetching uglifier 4.2.0
Installing uglifier 4.2.0
Fetching web-console 3.7.0
Installing web-console 3.7.0
Bundle complete! 16 Gemfile dependencies, 76 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0

Post-install message from chromedriver-helper:

+--------------------------------------------------------------------+
| |
| NOTICE: chromedriver-helper is deprecated after 2019-03-31. |
| |
| Please update to use the 'webdrivers' gem instead. |
| See https://github.com/flavorjones/chromedriver-helper/issues/83 |
| |
+--------------------------------------------------------------------+

Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

- If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

- If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

- For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Removing intermediate container 33d386a993ff
---> 88f483ea3b38
Step 13/25 : ENV RAILS_ROOT ./apptest
---> Running in f8213e6ca826
Removing intermediate container f8213e6ca826
---> f1a09b1e8c8f
Step 14/25 : COPY . /apptest
---> 07b40c041d60
Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Running in ecd149ba4cb0
Removing intermediate container ecd149ba4cb0
 ---> b589741c4e61
Step 16/25 : WORKDIR $RAILS_ROOT
---> Running in 24ffe003ad13
Removing intermediate container 24ffe003ad13
---> b20c03cabe4f
Step 17/25 : ENV RAILS_ENV='production'
---> Running in eecf31318c08
Removing intermediate container eecf31318c08
---> e9367a4a0b5e
Step 18/25 : ENV RACK_ENV='production'
---> Running in 164e639f7e78
Removing intermediate container 164e639f7e78
---> 3d1be655cfd8
Step 19/25 : ENV PORT 3000
---> Running in 8386c8cfdf0a
Removing intermediate container 8386c8cfdf0a
---> 3943a598b670
Step 20/25 : COPY Gemfile Gemfile
---> a93929928cca
Step 21/25 : COPY Gemfile.lock Gemfile.lock
---> 0f584728dd7b
Step 22/25 : COPY . .
---> 04ed34aac4d2
Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in ea7d0e09e841
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T02:50:06.579405 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T02:50:06.580566 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T02:50:06.644422 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T02:50:06.645567 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container ea7d0e09e841
---> bca6b8457701
Step 24/25 : EXPOSE 3000
---> Running in 0475b4cbc86b
Removing intermediate container 0475b4cbc86b
---> 24292f327131
Step 25/25 : CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]
---> Running in 39243e780495
Removing intermediate container 39243e780495
---> 01785695c472
Successfully built 01785695c472
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Running in 57a3b1934663
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
libapr1 libaprutil1 libgdbm6
Suggested packages:
gdbm-l10n
The following NEW packages will be installed:
apache2-utils libapr1 libaprutil1 libgdbm6
0 upgraded, 4 newly installed, 0 to remove and 9 not upgraded.
Need to get 495 kB of archives.
After this operation, 1157 kB of additional disk space will be used.
Get:1 http://deb.debian.org/debian buster/main amd64 libapr1 amd64 1.6.5-1+b1 [102 kB]
Get:2 http://deb.debian.org/debian buster/main amd64 libgdbm6 amd64 1.18.1-4 [64.7 kB]
Get:3 http://deb.debian.org/debian buster/main amd64 libaprutil1 amd64 1.6.1-4 [91.8 kB]
Get:4 http://deb.debian.org/debian buster/main amd64 apache2-utils amd64 2.4.38-3+deb10u3 [236 kB]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 495 kB in 0s (26.4 MB/s)
Selecting previously unselected package libapr1:amd64.
(Reading database ... 7203 files and directories currently installed.)
Preparing to unpack .../libapr1_1.6.5-1+b1_amd64.deb ...
Unpacking libapr1:amd64 (1.6.5-1+b1) ...
Selecting previously unselected package libgdbm6:amd64.
Preparing to unpack .../libgdbm6_1.18.1-4_amd64.deb ...
Unpacking libgdbm6:amd64 (1.18.1-4) ...
Selecting previously unselected package libaprutil1:amd64.
Preparing to unpack .../libaprutil1_1.6.1-4_amd64.deb ...
Unpacking libaprutil1:amd64 (1.6.1-4) ...
Selecting previously unselected package apache2-utils.
Preparing to unpack .../apache2-utils_2.4.38-3+deb10u3_amd64.deb ...
Unpacking apache2-utils (2.4.38-3+deb10u3) ...
Setting up libapr1:amd64 (1.6.5-1+b1) ...
Setting up libgdbm6:amd64 (1.18.1-4) ...
Setting up libaprutil1:amd64 (1.6.1-4) ...
Setting up apache2-utils (2.4.38-3+deb10u3) ...
Processing triggers for libc-bin (2.28-10) ...
Removing intermediate container 57a3b1934663
---> 69e6dfb01887
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Running in 9c21ef4363c8
Removing intermediate container 9c21ef4363c8
---> cfede7f3ddae
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Running in 23af416684cb
Removing intermediate container 23af416684cb
 ---> 1f10950e9428
Step 5/9 : RUN mkdir log
 ---> Running in 1b141c250cc2
Removing intermediate container 1b141c250cc2
 ---> 5a7d1163e2c9
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> e0e00e764c3d
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Running in 426d435eff7b
Removing intermediate container 426d435eff7b
---> 2eadd588de53
Step 8/9 : EXPOSE 80
---> Running in a989b78f2841
Removing intermediate container a989b78f2841
---> 505fa9a38d4e
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Running in ded44117042d
Removing intermediate container ded44117042d
---> 2fc981991e9c
Successfully built 2fc981991e9c
Successfully tagged apptest_web:latest
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
root@dockserver:~/apptest# docker container list
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
root@dockserver:~/apptest# docker-compose up -d
Creating network "apptest_default" with the default driver
Creating apptest_db_1 ...
Creating apptest_db_1 ... done
Creating apptest_app_1 ...
Creating apptest_app_1 ... done
Creating apptest_web_1 ...
Creating apptest_web_1 ... done
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
aee7b729fb89 apptest_web "nginx -g 'daemon of…" 14 seconds ago Up 12 seconds 0.0.0.0:80->80/tcp apptest_web_1
6766cd595aab mysql:5.7.18 "docker-entrypoint.s…" 16 seconds ago Up 15 seconds 0.0.0.0:3306->3306/tcp apptest_db_1
root@dockserver:~/apptest# packet_write_wait: Connection to 157.245.211.227 port 22: Broken pipe
imac-de-william:apptest williamromero\$ ssh root@157.245.211.227
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 4.15.0-66-generic x86_64)

- Documentation: https://help.ubuntu.com
- Management: https://landscape.canonical.com
- Support: https://ubuntu.com/advantage

System information as of Thu Feb 20 03:58:44 UTC 2020

System load: 0.0
Usage of /: 43.0% of 24.06GB
Memory usage: 40%
Swap usage: 0%
Processes: 92
Users logged in: 1
IP address for eth0: 157.245.211.227
IP address for eth1: 10.132.7.149
IP address for docker0: 172.17.0.1
IP address for br-2507b11afb93: 172.24.0.1

105 packages can be updated.
58 updates are security updates.

Last login: Thu Feb 20 02:46:41 2020 from 190.148.52.47
root@dockserver:~# ls
apptest
root@dockserver:~# l
apptest/
root@dockserver:~# cd apptest
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
aee7b729fb89 apptest_web "nginx -g 'daemon of…" About an hour ago Up About an hour 0.0.0.0:80->80/tcp apptest_web_1
6766cd595aab mysql:5.7.18 "docker-entrypoint.s…" About an hour ago Up About an hour 0.0.0.0:3306->3306/tcp apptest_db_1
root@dockserver:~/apptest# docker-compose down
Stopping apptest_web_1 ... done
Stopping apptest_db_1 ... done
Removing apptest_web_1 ... done
Removing apptest_app_1 ... done
Removing apptest_db_1 ... done
Removing network apptest_default
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# cd docker
root@dockserver:~/apptest/docker# ls
app db.env web
root@dockserver:~/apptest/docker# cd app
root@dockserver:~/apptest/docker/app# ls
Dockerfile
root@dockserver:~/apptest/docker/app# nano Dockerfile
root@dockserver:~/apptest/docker/app# cd ..
root@dockserver:~/apptest/docker# ls
app db.env web
root@dockserver:~/apptest/docker# cd ..
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# nano docker-compose.yml
root@dockserver:~/apptest# docker-compose build
ERROR: The Compose file './docker-compose.yml' is invalid because:
services.app.build contains unsupported option: 'command'
root@dockserver:~/apptest# LS
root@dockserver:~/apptest# LS
root@dockserver:~/apptest# LS
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# nano docker-compose.yml
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# cd docker
root@dockserver:~/apptest/docker# ls
app db.env web
root@dockserver:~/apptest/docker# cd app
root@dockserver:~/apptest/docker/app# ls
Dockerfile
root@dockserver:~/apptest/docker/app# nano Dockerfile
root@dockserver:~/apptest/docker/app# cd ..
root@dockserver:~/apptest/docker# ls
app db.env web
root@dockserver:~/apptest/docker# cd ..
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# docker-compose build
db uses an image, skipping
Building app
^CERROR: Aborting.
root@dockserver:~/apptest# docker-compose build --no-cache
db uses an image, skipping
Building app
Step 1/25 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/25 : RUN apk update
---> Running in 9c26b3486d50
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
Removing intermediate container 9c26b3486d50
---> dbafcc02d8b3
Step 3/25 : RUN apk add nodejs
---> Running in 51fb172d11c9
(1/4) Installing c-ares (1.15.0-r0)
(2/4) Installing nghttp2-libs (1.40.0-r0)
(3/4) Installing libuv (1.34.0-r0)
(4/4) Installing nodejs (12.15.0-r1)
Executing busybox-1.31.1-r9.trigger
OK: 54 MiB in 41 packages
Removing intermediate container 51fb172d11c9
---> 82b6ccb5aa1f
Step 4/25 : ADD Gemfile Gemfile
---> b5190f081386
Step 5/25 : ADD Gemfile.lock Gemfile.lock
---> f537a16b1d93
Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Running in ab4e7e508a16
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
(1/89) Installing bash (5.0.11-r1)
Executing bash-5.0.11-r1.post-install
(2/89) Installing binutils (2.33.1-r0)
(3/89) Installing libmagic (5.37-r1)
(4/89) Installing file (5.37-r1)
(5/89) Installing isl (0.18-r0)
(6/89) Installing libgomp (9.2.0-r3)
(7/89) Installing libatomic (9.2.0-r3)
(8/89) Installing mpfr4 (4.0.2-r1)
(9/89) Installing mpc1 (1.1.0-r1)
(10/89) Installing gcc (9.2.0-r3)
(11/89) Installing musl-dev (1.1.24-r0)
(12/89) Installing libc-dev (0.7.2-r0)
(13/89) Installing g++ (9.2.0-r3)
(14/89) Installing make (4.2.1-r2)
(15/89) Installing fortify-headers (1.1-r0)
(16/89) Installing build-base (0.5-r1)
(17/89) Installing libcurl (7.67.0-r0)
(18/89) Installing expat (2.2.9-r1)
(19/89) Installing pcre2 (10.34-r1)
(20/89) Installing git (2.24.1-r0)
(21/89) Installing libxau (1.0.9-r0)
(22/89) Installing libbsd (0.10.0-r0)
(23/89) Installing libxdmcp (1.1.3-r0)
(24/89) Installing libxcb (1.13.1-r0)
(25/89) Installing libx11 (1.6.9-r0)
(26/89) Installing libxext (1.3.4-r0)
(27/89) Installing libbz2 (1.0.8-r1)
(28/89) Installing libpng (1.6.37-r1)
(29/89) Installing freetype (2.10.1-r0)
(30/89) Installing libuuid (2.34-r1)
(31/89) Installing fontconfig (2.13.1-r2)
(32/89) Installing lcms2 (2.9-r1)
(33/89) Installing libltdl (2.4.6-r7)
(34/89) Installing xz-libs (5.2.4-r0)
(35/89) Installing libxml2 (2.9.10-r2)
(36/89) Installing imagemagick-libs (7.0.9.7-r0)
(37/89) Installing libxrender (0.9.10-r3)
(38/89) Installing pixman (0.38.4-r0)
(39/89) Installing cairo (1.16.0-r2)
(40/89) Installing libblkid (2.34-r1)
(41/89) Installing libmount (2.34-r1)
(42/89) Installing pcre (8.43-r0)
(43/89) Installing glib (2.62.4-r0)
(44/89) Installing dbus-libs (1.12.16-r2)
(45/89) Installing avahi-libs (0.7-r4)
(46/89) Installing nettle (3.5.1-r0)
(47/89) Installing p11-kit (0.23.18.1-r0)
(48/89) Installing libtasn1 (4.15.0-r0)
(49/89) Installing libunistring (0.9.10-r0)
(50/89) Installing gnutls (3.6.10-r0)
(51/89) Installing cups-libs (2.2.12-r1)
(52/89) Installing jbig2dec (0.17-r0)
(53/89) Installing libjpeg-turbo (2.0.4-r0)
(54/89) Installing tiff (4.1.0-r0)
(55/89) Installing ghostscript (9.50-r0)
(56/89) Installing libde265 (1.0.3-r0)
(57/89) Installing x265-libs (3.2.1-r0)
(58/89) Installing libheif (1.6.0-r0)
(59/89) Installing libcroco (0.6.13-r1)
(60/89) Installing shared-mime-info (1.15-r0)
(61/89) Installing gdk-pixbuf (2.40.0-r0)
(62/89) Installing libxft (2.3.3-r0)
(63/89) Installing fribidi (1.0.8-r0)
(64/89) Installing graphite2 (1.3.13-r1)
(65/89) Installing harfbuzz (2.6.4-r0)
(66/89) Installing pango (1.44.7-r0)
(67/89) Installing librsvg (2.46.4-r0)
(68/89) Installing libwebp (1.0.3-r0)
(69/89) Installing imagemagick (7.0.9.7-r0)
(70/89) Installing mariadb-common (10.4.12-r0)
(71/89) Installing libaio (0.3.112-r1)
(72/89) Installing linux-pam (1.3.1-r1)
(73/89) Installing mariadb (10.4.12-r0)
Executing mariadb-10.4.12-r0.pre-install
(74/89) Installing mysql (10.4.12-r0)
(75/89) Installing mariadb-client (10.4.12-r0)
(76/89) Installing mysql-client (10.4.12-r0)
(77/89) Installing openssl-dev (1.1.1d-r3)
(78/89) Installing mariadb-connector-c (3.1.6-r0)
(79/89) Installing mariadb-connector-c-dev (3.1.6-r0)
(80/89) Installing mariadb-embedded (10.4.12-r0)
(81/89) Installing mariadb-dev (10.4.12-r0)
(82/89) Installing openssh-keygen (8.1_p1-r0)
(83/89) Installing libedit (20191211.3.1-r0)
(84/89) Installing openssh-client (8.1_p1-r0)
(85/89) Installing openssh-sftp-server (8.1_p1-r0)
(86/89) Installing openssh-server-common (8.1_p1-r0)
(87/89) Installing openssh-server (8.1_p1-r0)
(88/89) Installing openssh (8.1_p1-r0)
(89/89) Installing tzdata (2019c-r0)
Executing busybox-1.31.1-r9.trigger
Executing fontconfig-2.13.1-r2.trigger
Executing shared-mime-info-1.15-r0.trigger
Executing gdk-pixbuf-2.40.0-r0.trigger
OK: 522 MiB in 130 packages
Removing intermediate container ab4e7e508a16
---> fb84634c63d9
Step 7/25 : RUN gem install bundler:2.1.4
---> Running in 41f9df77999d
Successfully installed bundler-2.1.4
1 gem installed
Removing intermediate container 41f9df77999d
---> cb1ff97e32e0
Step 8/25 : RUN apk add --no-cache build-base
---> Running in 3e0e3c59a227
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
OK: 522 MiB in 130 packages
Removing intermediate container 3e0e3c59a227
---> d95716d66622
Step 9/25 : RUN gem install mysql2
---> Running in a9aaa1d816e9
Building native extensions. This could take a while...
Successfully installed mysql2-0.5.3
1 gem installed
Removing intermediate container a9aaa1d816e9
---> f9083f35a67c
Step 10/25 : RUN gem install ffi
---> Running in 7df9e5743e9b
Building native extensions. This could take a while...
Successfully installed ffi-1.12.2
1 gem installed
Removing intermediate container 7df9e5743e9b
---> 12cc4462bf21
Step 11/25 : RUN gem install nokogiri
---> Running in 511abdc605b2
Successfully installed mini_portile2-2.4.0
Building native extensions. This could take a while...
Successfully installed nokogiri-1.10.8
2 gems installed
Removing intermediate container 511abdc605b2
---> 5ac704e1bd0b
Step 12/25 : RUN bundle install
---> Running in 3bba5d90fc9d
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/............
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Fetching rake 12.3.3
Installing rake 12.3.3
Fetching concurrent-ruby 1.1.6
Installing concurrent-ruby 1.1.6
Fetching i18n 1.6.0
Installing i18n 1.6.0
Fetching minitest 5.12.2
Installing minitest 5.12.2
Fetching thread_safe 0.3.6
Installing thread_safe 0.3.6
Fetching tzinfo 1.2.5
Installing tzinfo 1.2.5
Fetching activesupport 5.2.3
Installing activesupport 5.2.3
Fetching builder 3.2.3
Installing builder 3.2.3
Fetching erubi 1.9.0
Installing erubi 1.9.0
Using mini_portile2 2.4.0
Fetching nokogiri 1.10.4
Installing nokogiri 1.10.4 with native extensions
Fetching rails-dom-testing 2.0.3
Installing rails-dom-testing 2.0.3
Fetching crass 1.0.4
Installing crass 1.0.4
Fetching loofah 2.3.0
Installing loofah 2.3.0
Fetching rails-html-sanitizer 1.2.0
Installing rails-html-sanitizer 1.2.0
Fetching actionview 5.2.3
Installing actionview 5.2.3
Fetching rack 2.0.7
Installing rack 2.0.7
Fetching rack-test 1.1.0
Installing rack-test 1.1.0
Fetching actionpack 5.2.3
Installing actionpack 5.2.3
Fetching nio4r 2.5.2
Installing nio4r 2.5.2 with native extensions
Fetching websocket-extensions 0.1.4
Installing websocket-extensions 0.1.4
Fetching websocket-driver 0.7.1
Installing websocket-driver 0.7.1 with native extensions
Fetching actioncable 5.2.3
Installing actioncable 5.2.3
Fetching globalid 0.4.2
Installing globalid 0.4.2
Fetching activejob 5.2.3
Installing activejob 5.2.3
Fetching mini_mime 1.0.2
Installing mini_mime 1.0.2
Fetching mail 2.7.1
Installing mail 2.7.1
Fetching actionmailer 5.2.3
Installing actionmailer 5.2.3
Fetching activemodel 5.2.3
Installing activemodel 5.2.3
Fetching arel 9.0.0
Installing arel 9.0.0
Fetching activerecord 5.2.3
Installing activerecord 5.2.3
Fetching mimemagic 0.3.3
Installing mimemagic 0.3.3
Fetching marcel 0.3.3
Installing marcel 0.3.3
Fetching activestorage 5.2.3
Installing activestorage 5.2.3
Fetching public_suffix 4.0.1
Installing public_suffix 4.0.1
Fetching addressable 2.7.0
Installing addressable 2.7.0
Fetching io-like 0.3.0
Installing io-like 0.3.0
Fetching archive-zip 0.12.0
Installing archive-zip 0.12.0
Fetching bindex 0.8.1
Installing bindex 0.8.1 with native extensions
Fetching msgpack 1.3.1
Installing msgpack 1.3.1 with native extensions
Fetching bootsnap 1.4.5
Installing bootsnap 1.4.5 with native extensions
Using bundler 2.1.4
Fetching byebug 11.0.1
Installing byebug 11.0.1 with native extensions
Fetching regexp_parser 1.6.0
Installing regexp_parser 1.6.0
Fetching xpath 3.2.0
Installing xpath 3.2.0
Fetching capybara 3.29.0
Installing capybara 3.29.0
Fetching childprocess 2.0.0
Installing childprocess 2.0.0 with native extensions
Fetching chromedriver-helper 2.1.1
Installing chromedriver-helper 2.1.1
Fetching coffee-script-source 1.12.2
Installing coffee-script-source 1.12.2
Fetching execjs 2.7.0
Installing execjs 2.7.0
Fetching coffee-script 2.4.1
Installing coffee-script 2.4.1
Fetching method_source 0.9.2
Installing method_source 0.9.2
Fetching thor 1.0.1
Installing thor 1.0.1
Fetching railties 5.2.3
Installing railties 5.2.3
Fetching coffee-rails 4.2.2
Installing coffee-rails 4.2.2
Fetching ffi 1.11.1
Installing ffi 1.11.1 with native extensions
Fetching jbuilder 2.9.1
Installing jbuilder 2.9.1
Fetching rb-fsevent 0.10.3
Installing rb-fsevent 0.10.3
Fetching rb-inotify 0.10.0
Installing rb-inotify 0.10.0
Fetching ruby_dep 1.5.0
Installing ruby_dep 1.5.0
Fetching listen 3.1.5
Installing listen 3.1.5
Using mysql2 0.5.3
Fetching puma 3.12.1
Installing puma 3.12.1 with native extensions
Fetching sprockets 3.7.2
Installing sprockets 3.7.2
Fetching sprockets-rails 3.2.1
Installing sprockets-rails 3.2.1
Fetching rails 5.2.3
Installing rails 5.2.3
Fetching rubyzip 1.2.4
Installing rubyzip 1.2.4
Fetching sass-listen 4.0.0
Installing sass-listen 4.0.0
Fetching sass 3.7.4
Installing sass 3.7.4
Fetching tilt 2.0.10
Installing tilt 2.0.10
Fetching sass-rails 5.1.0
Installing sass-rails 5.1.0
Fetching selenium-webdriver 3.142.4
Installing selenium-webdriver 3.142.4
Fetching turbolinks-source 5.2.0
Installing turbolinks-source 5.2.0
Fetching turbolinks 5.2.1
Installing turbolinks 5.2.1
Fetching uglifier 4.2.0
Installing uglifier 4.2.0
Fetching web-console 3.7.0
Installing web-console 3.7.0
Bundle complete! 16 Gemfile dependencies, 76 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0

Post-install message from chromedriver-helper:

+--------------------------------------------------------------------+
| |
| NOTICE: chromedriver-helper is deprecated after 2019-03-31. |
| |
| Please update to use the 'webdrivers' gem instead. |
| See https://github.com/flavorjones/chromedriver-helper/issues/83 |
| |
+--------------------------------------------------------------------+

Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

- If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

- If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

- For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Removing intermediate container 3bba5d90fc9d
---> 099f7c9bfcff
Step 13/25 : ENV RAILS_ROOT ./apptest
---> Running in b6b59f2b2adc
Removing intermediate container b6b59f2b2adc
---> 224dc7a7fc02
Step 14/25 : COPY . /apptest
---> 77d6c1a85b74
Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Running in aafe08afe093
Removing intermediate container aafe08afe093
 ---> 8cfc288aeec6
Step 16/25 : WORKDIR $RAILS_ROOT
---> Running in 397ab077eca8
Removing intermediate container 397ab077eca8
---> 109dcb3cac74
Step 17/25 : ENV RAILS_ENV='production'
---> Running in aaf23e7ebbf5
Removing intermediate container aaf23e7ebbf5
---> 4be517158919
Step 18/25 : ENV RACK_ENV='production'
---> Running in d4464445036d
Removing intermediate container d4464445036d
---> 7dad9c7278ef
Step 19/25 : ENV PORT 3000
---> Running in 77c9d470ab01
Removing intermediate container 77c9d470ab01
---> 504eb660739f
Step 20/25 : COPY Gemfile Gemfile
---> acb2dc8dcdf7
Step 21/25 : COPY Gemfile.lock Gemfile.lock
---> d54a86db0cb4
Step 22/25 : COPY . .
---> ada0b78078c2
Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in 4fd5f68b2821
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T04:13:30.362360 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T04:13:30.363605 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T04:13:30.403533 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T04:13:30.404632 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container 4fd5f68b2821
---> bc4d699fed58
Step 24/25 : EXPOSE 3000
---> Running in df2c67827dc5
Removing intermediate container df2c67827dc5
---> 11ce2a06782d
Step 25/25 : RUN bundle exec puma -p 3000 -e production
---> Running in 2d9fd07de39e
Puma starting in single mode...

- Version 3.12.1 (ruby 2.5.7-p206), codename: Llamas in Pajamas
- Min threads: 5, max threads: 5
- Environment: production
  ! Unable to load application: ArgumentError: Missing `secret_key_base` for 'production' environment, set this string with `rails credentials:edit`
  bundler: failed to load command: puma (/usr/local/bundle/bin/puma)
  ArgumentError: Missing `secret_key_base` for 'production' environment, set this string with `rails credentials:edit`
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:585:in `validate_secret_key_base' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:432:in`secret_key_base'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:176:in `key_generator' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:205:in`message_verifier'
  /usr/local/bundle/gems/activestorage-5.2.3/lib/active_storage/engine.rb:81:in `block (2 levels) in <class:Engine>' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:69:in`block in execute_hook'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:62:in `with_execution_control' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:67:in`execute_hook'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:52:in `block in run_load_hooks' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:51:in`each'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:51:in `run_load_hooks' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application/finisher.rb:75:in`block in <module:Finisher>'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:32:in `instance_exec' /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:32:in`run'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:61:in `block in run_initializers' /usr/local/lib/ruby/2.5.0/tsort.rb:228:in`block in tsort_each'
  /usr/local/lib/ruby/2.5.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component' /usr/local/lib/ruby/2.5.0/tsort.rb:431:in`each_strongly_connected_component_from'
  /usr/local/lib/ruby/2.5.0/tsort.rb:349:in `block in each_strongly_connected_component' /usr/local/lib/ruby/2.5.0/tsort.rb:347:in`each'
  /usr/local/lib/ruby/2.5.0/tsort.rb:347:in `call' /usr/local/lib/ruby/2.5.0/tsort.rb:347:in`each_strongly_connected_component'
  /usr/local/lib/ruby/2.5.0/tsort.rb:226:in `tsort_each' /usr/local/lib/ruby/2.5.0/tsort.rb:205:in`tsort_each'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:60:in `run_initializers' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:361:in`initialize!'
  /apptest/config/environment.rb:5:in `<top (required)>' config.ru:3:in`require_relative'
  config.ru:3:in `block in <main>' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in`instance_eval'
  /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in `initialize' config.ru:in`new'
  config.ru:in `<main>' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in`eval'
  /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in `new_from_string' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:40:in`parse_file'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/configuration.rb:320:in `load_rackup' /usr/local/bundle/gems/puma-3.12.1/lib/puma/configuration.rb:245:in`app'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/runner.rb:147:in `load_and_bind' /usr/local/bundle/gems/puma-3.12.1/lib/puma/single.rb:98:in`run'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/launcher.rb:186:in `run' /usr/local/bundle/gems/puma-3.12.1/lib/puma/cli.rb:80:in`run'
  /usr/local/bundle/gems/puma-3.12.1/bin/puma:10:in `<top (required)>' /usr/local/bundle/bin/puma:23:in`load'
  /usr/local/bundle/bin/puma:23:in `<top (required)>'
  ERROR: Service 'app' failed to build: The command '/bin/sh -c bundle exec puma -p 3000 -e production' returned a non-zero code: 1
  root@dockserver:~/apptest# ls
  Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
  Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
  root@dockserver:~/apptest# cd docker/app/
  root@dockserver:~/apptest/docker/app# ls
  Dockerfile
  root@dockserver:~/apptest/docker/app# nano Dockerfile
  root@dockserver:~/apptest/docker/app# cd ..
  root@dockserver:~/apptest/docker# CD ..
  CD: command not found
  root@dockserver:~/apptest/docker# cd ..
  root@dockserver:~/apptest# ls
  Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
  Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
  root@dockserver:~/apptest# docker-compose build
  db uses an image, skipping
  Building app
  Step 1/25 : FROM ruby:2.5-alpine
  ---> cbd297d70a23
  Step 2/25 : RUN apk update
  ---> Using cache
  ---> dbafcc02d8b3
  Step 3/25 : RUN apk add nodejs
  ---> Using cache
  ---> 82b6ccb5aa1f
  Step 4/25 : ADD Gemfile Gemfile
  ---> Using cache
  ---> b5190f081386
  Step 5/25 : ADD Gemfile.lock Gemfile.lock
  ---> Using cache
  ---> f537a16b1d93
  Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
  ---> Using cache
  ---> fb84634c63d9
  Step 7/25 : RUN gem install bundler:2.1.4
  ---> Using cache
  ---> cb1ff97e32e0
  Step 8/25 : RUN apk add --no-cache build-base
  ---> Using cache
  ---> d95716d66622
  Step 9/25 : RUN gem install mysql2
  ---> Using cache
  ---> f9083f35a67c
  Step 10/25 : RUN gem install ffi
  ---> Using cache
  ---> 12cc4462bf21
  Step 11/25 : RUN gem install nokogiri
  ---> Using cache
  ---> 5ac704e1bd0b
  Step 12/25 : RUN bundle install
  ---> Using cache
  ---> 099f7c9bfcff
  Step 13/25 : ENV RAILS_ROOT ./apptest
  ---> Using cache
  ---> 224dc7a7fc02
  Step 14/25 : COPY . /apptest
  ---> cb06faddbb64
  Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Running in f3754cc09e68
Removing intermediate container f3754cc09e68
 ---> affec4d94177
Step 16/25 : WORKDIR $RAILS_ROOT
  ---> Running in 2a32b0265f04
  Removing intermediate container 2a32b0265f04
  ---> cd344734c0ab
  Step 17/25 : ENV RAILS_ENV='production'
  ---> Running in 8454cfb0baab
  Removing intermediate container 8454cfb0baab
  ---> cbbc0f646dd8
  Step 18/25 : ENV RACK_ENV='production'
  ---> Running in 611865663c85
  Removing intermediate container 611865663c85
  ---> ef37c41f682d
  Step 19/25 : ENV PORT 3000
  ---> Running in f6d954935500
  Removing intermediate container f6d954935500
  ---> 072814bf5898
  Step 20/25 : COPY Gemfile Gemfile
  ---> 6404b9394ad5
  Step 21/25 : COPY Gemfile.lock Gemfile.lock
  ---> 26d27074cf8e
  Step 22/25 : COPY . .
  ---> 3cfa804b00df
  Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
  ---> Running in 67bdcf146ec3
  Yarn executable was not detected in the system.
  Download Yarn at https://yarnpkg.com/en/docs/install
  I, [2020-02-20T04:15:53.162454 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
  I, [2020-02-20T04:15:53.163589 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
  I, [2020-02-20T04:15:53.225805 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
  I, [2020-02-20T04:15:53.226887 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
  Removing intermediate container 67bdcf146ec3
  ---> fbd1432d2913
  Step 24/25 : EXPOSE 3000
  ---> Running in a747c970863b
  Removing intermediate container a747c970863b
  ---> 386f3fd6a7dd
  Step 25/25 : RUN SECRET_KEY_BASE=1 bundle exec puma -p 3000 -e production
  ---> Running in 08866a5dcdbe
  Puma starting in single mode...
- Version 3.12.1 (ruby 2.5.7-p206), codename: Llamas in Pajamas
- Min threads: 5, max threads: 5
- Environment: production
- Listening on tcp://0.0.0.0:3000
  Use Ctrl-C to stop
  ^CERROR: Aborting.
  root@dockserver:~/apptest# docker-compose up -d
  Creating network "apptest_default" with the default driver
  Creating apptest_db_1 ...
  Creating apptest_db_1 ... done
  Creating apptest_app_1 ...
  Creating apptest_app_1 ... done
  Creating apptest_web_1 ...
  Creating apptest_web_1 ... done
  root@dockserver:~/apptest# docker ps
  CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
  2f583b377f9e apptest_web "nginx -g 'daemon of…" 4 seconds ago Up 3 seconds 0.0.0.0:80->80/tcp apptest_web_1
  a7927b89bbc9 mysql:5.7.18 "docker-entrypoint.s…" 6 seconds ago Up 5 seconds 0.0.0.0:3306->3306/tcp apptest_db_1
  root@dockserver:~/apptest# docker-compose down
  Stopping apptest_web_1 ... done
  Stopping apptest_db_1 ... done
  Removing apptest_web_1 ... done
  Removing apptest_app_1 ... done
  Removing apptest_db_1 ... done
  Removing network apptest_default
  root@dockserver:~/apptest# docker-compose up -d
  Creating network "apptest_default" with the default driver
  Creating apptest_db_1 ...
  Creating apptest_db_1 ... done
  Creating apptest_app_1 ...
  Creating apptest_app_1 ... done
  Creating apptest_web_1 ...
  Creating apptest_web_1 ... done
  root@dockserver:~/apptest# docker run -it apptest_app
  Puma starting in single mode...
- Version 3.12.1 (ruby 2.5.7-p206), codename: Llamas in Pajamas
- Min threads: 5, max threads: 5
- Environment: production
  ! Unable to load application: ArgumentError: Missing `secret_key_base` for 'production' environment, set this string with `rails credentials:edit`
  bundler: failed to load command: puma (/usr/local/bundle/bin/puma)
  ArgumentError: Missing `secret_key_base` for 'production' environment, set this string with `rails credentials:edit`
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:585:in `validate_secret_key_base' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:432:in`secret_key_base'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:176:in `key_generator' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:205:in`message_verifier'
  /usr/local/bundle/gems/activestorage-5.2.3/lib/active_storage/engine.rb:81:in `block (2 levels) in <class:Engine>' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:69:in`block in execute_hook'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:62:in `with_execution_control' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:67:in`execute_hook'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:52:in `block in run_load_hooks' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:51:in`each'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:51:in `run_load_hooks' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application/finisher.rb:75:in`block in <module:Finisher>'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:32:in `instance_exec' /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:32:in`run'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:61:in `block in run_initializers' /usr/local/lib/ruby/2.5.0/tsort.rb:228:in`block in tsort_each'
  /usr/local/lib/ruby/2.5.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component' /usr/local/lib/ruby/2.5.0/tsort.rb:431:in`each_strongly_connected_component_from'
  /usr/local/lib/ruby/2.5.0/tsort.rb:349:in `block in each_strongly_connected_component' /usr/local/lib/ruby/2.5.0/tsort.rb:347:in`each'
  /usr/local/lib/ruby/2.5.0/tsort.rb:347:in `call' /usr/local/lib/ruby/2.5.0/tsort.rb:347:in`each_strongly_connected_component'
  /usr/local/lib/ruby/2.5.0/tsort.rb:226:in `tsort_each' /usr/local/lib/ruby/2.5.0/tsort.rb:205:in`tsort_each'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:60:in `run_initializers' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:361:in`initialize!'
  /apptest/config/environment.rb:5:in `<top (required)>' config.ru:3:in`require_relative'
  config.ru:3:in `block in <main>' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in`instance_eval'
  /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in `initialize' config.ru:in`new'
  config.ru:in `<main>' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in`eval'
  /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in `new_from_string' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:40:in`parse_file'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/configuration.rb:320:in `load_rackup' /usr/local/bundle/gems/puma-3.12.1/lib/puma/configuration.rb:245:in`app'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/runner.rb:147:in `load_and_bind' /usr/local/bundle/gems/puma-3.12.1/lib/puma/single.rb:98:in`run'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/launcher.rb:186:in `run' /usr/local/bundle/gems/puma-3.12.1/lib/puma/cli.rb:80:in`run'
  /usr/local/bundle/gems/puma-3.12.1/bin/puma:10:in `<top (required)>' /usr/local/bundle/bin/puma:23:in`load'
  /usr/local/bundle/bin/puma:23:in `<top (required)>'
  root@dockserver:~/apptest# docker run -it apptest_app
  Puma starting in single mode...
- Version 3.12.1 (ruby 2.5.7-p206), codename: Llamas in Pajamas
- Min threads: 5, max threads: 5
- Environment: production
  ! Unable to load application: ArgumentError: Missing `secret_key_base` for 'production' environment, set this string with `rails credentials:edit`
  bundler: failed to load command: puma (/usr/local/bundle/bin/puma)
  ArgumentError: Missing `secret_key_base` for 'production' environment, set this string with `rails credentials:edit`
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:585:in `validate_secret_key_base' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:432:in`secret_key_base'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:176:in `key_generator' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:205:in`message_verifier'
  /usr/local/bundle/gems/activestorage-5.2.3/lib/active_storage/engine.rb:81:in `block (2 levels) in <class:Engine>' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:69:in`block in execute_hook'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:62:in `with_execution_control' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:67:in`execute_hook'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:52:in `block in run_load_hooks' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:51:in`each'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:51:in `run_load_hooks' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application/finisher.rb:75:in`block in <module:Finisher>'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:32:in `instance_exec' /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:32:in`run'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:61:in `block in run_initializers' /usr/local/lib/ruby/2.5.0/tsort.rb:228:in`block in tsort_each'
  /usr/local/lib/ruby/2.5.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component' /usr/local/lib/ruby/2.5.0/tsort.rb:431:in`each_strongly_connected_component_from'
  /usr/local/lib/ruby/2.5.0/tsort.rb:349:in `block in each_strongly_connected_component' /usr/local/lib/ruby/2.5.0/tsort.rb:347:in`each'
  /usr/local/lib/ruby/2.5.0/tsort.rb:347:in `call' /usr/local/lib/ruby/2.5.0/tsort.rb:347:in`each_strongly_connected_component'
  /usr/local/lib/ruby/2.5.0/tsort.rb:226:in `tsort_each' /usr/local/lib/ruby/2.5.0/tsort.rb:205:in`tsort_each'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:60:in `run_initializers' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:361:in`initialize!'
  /apptest/config/environment.rb:5:in `<top (required)>' config.ru:3:in`require_relative'
  config.ru:3:in `block in <main>' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in`instance_eval'
  /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in `initialize' config.ru:in`new'
  config.ru:in `<main>' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in`eval'
  /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in `new_from_string' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:40:in`parse_file'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/configuration.rb:320:in `load_rackup' /usr/local/bundle/gems/puma-3.12.1/lib/puma/configuration.rb:245:in`app'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/runner.rb:147:in `load_and_bind' /usr/local/bundle/gems/puma-3.12.1/lib/puma/single.rb:98:in`run'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/launcher.rb:186:in `run' /usr/local/bundle/gems/puma-3.12.1/lib/puma/cli.rb:80:in`run'
  /usr/local/bundle/gems/puma-3.12.1/bin/puma:10:in `<top (required)>' /usr/local/bundle/bin/puma:23:in`load'
  /usr/local/bundle/bin/puma:23:in `<top (required)>'
  root@dockserver:~/apptest# docker ps
  CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
  572e8845a235 apptest_web "nginx -g 'daemon of…" 3 minutes ago Up 3 minutes 0.0.0.0:80->80/tcp apptest_web_1
  ac8dde452dd6 mysql:5.7.18 "docker-entrypoint.s…" 3 minutes ago Up 3 minutes 0.0.0.0:3306->3306/tcp apptest_db_1
  root@dockserver:~/apptest# cd docker/app/
  root@dockserver:~/apptest/docker/app# ls
  Dockerfile
  root@dockserver:~/apptest/docker/app# nano Dockerfile
  root@dockserver:~/apptest/docker/app# docker-compose down
  Stopping apptest_web_1 ... done
  Stopping apptest_db_1 ... done
  Removing apptest_web_1 ... done
  Removing apptest_app_1 ... done
  Removing apptest_db_1 ... done
  Removing network apptest_default
  root@dockserver:~/apptest/docker/app# docker-compose build -t
  Build or rebuild services.

Services are built once and then tagged as `project_service`,
e.g. `composetest_db`. If you change a service's `Dockerfile` or the
contents of its build directory, you can run `docker-compose build` to rebuild it.

Usage: build [options][--build-arg key=val...] [SERVICE...]

Options:
--force-rm Always remove intermediate containers.
--no-cache Do not use cache when building the image.
--pull Always attempt to pull a newer version of the image.
--build-arg key=val Set build-time variables for one service.
root@dockserver:~/apptest/docker/app# docker-compose build --no-cache
db uses an image, skipping
Building app
Step 1/25 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/25 : RUN apk update
---> Running in 45cc3ed27ec6
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
Removing intermediate container 45cc3ed27ec6
---> 58d30dcbaf24
Step 3/25 : RUN apk add nodejs
---> Running in 3c756145495c
(1/4) Installing c-ares (1.15.0-r0)
(2/4) Installing nghttp2-libs (1.40.0-r0)
(3/4) Installing libuv (1.34.0-r0)
(4/4) Installing nodejs (12.15.0-r1)
Executing busybox-1.31.1-r9.trigger
OK: 54 MiB in 41 packages
Removing intermediate container 3c756145495c
---> 570156984051
Step 4/25 : ADD Gemfile Gemfile
---> ad1a260077de
Step 5/25 : ADD Gemfile.lock Gemfile.lock
---> d9e4c1e7c3ae
Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Running in e1c977b67de4
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
(1/89) Installing bash (5.0.11-r1)
Executing bash-5.0.11-r1.post-install
(2/89) Installing binutils (2.33.1-r0)
(3/89) Installing libmagic (5.37-r1)
(4/89) Installing file (5.37-r1)
(5/89) Installing isl (0.18-r0)
(6/89) Installing libgomp (9.2.0-r3)
(7/89) Installing libatomic (9.2.0-r3)
(8/89) Installing mpfr4 (4.0.2-r1)
(9/89) Installing mpc1 (1.1.0-r1)
(10/89) Installing gcc (9.2.0-r3)
(11/89) Installing musl-dev (1.1.24-r0)
(12/89) Installing libc-dev (0.7.2-r0)
(13/89) Installing g++ (9.2.0-r3)
(14/89) Installing make (4.2.1-r2)
(15/89) Installing fortify-headers (1.1-r0)
(16/89) Installing build-base (0.5-r1)
(17/89) Installing libcurl (7.67.0-r0)
(18/89) Installing expat (2.2.9-r1)
(19/89) Installing pcre2 (10.34-r1)
(20/89) Installing git (2.24.1-r0)
(21/89) Installing libxau (1.0.9-r0)
(22/89) Installing libbsd (0.10.0-r0)
(23/89) Installing libxdmcp (1.1.3-r0)
(24/89) Installing libxcb (1.13.1-r0)
(25/89) Installing libx11 (1.6.9-r0)
(26/89) Installing libxext (1.3.4-r0)
(27/89) Installing libbz2 (1.0.8-r1)
(28/89) Installing libpng (1.6.37-r1)
(29/89) Installing freetype (2.10.1-r0)
(30/89) Installing libuuid (2.34-r1)
(31/89) Installing fontconfig (2.13.1-r2)
(32/89) Installing lcms2 (2.9-r1)
(33/89) Installing libltdl (2.4.6-r7)
(34/89) Installing xz-libs (5.2.4-r0)
(35/89) Installing libxml2 (2.9.10-r2)
(36/89) Installing imagemagick-libs (7.0.9.7-r0)
(37/89) Installing libxrender (0.9.10-r3)
(38/89) Installing pixman (0.38.4-r0)
(39/89) Installing cairo (1.16.0-r2)
(40/89) Installing libblkid (2.34-r1)
(41/89) Installing libmount (2.34-r1)
(42/89) Installing pcre (8.43-r0)
(43/89) Installing glib (2.62.4-r0)
(44/89) Installing dbus-libs (1.12.16-r2)
(45/89) Installing avahi-libs (0.7-r4)
(46/89) Installing nettle (3.5.1-r0)
(47/89) Installing p11-kit (0.23.18.1-r0)
(48/89) Installing libtasn1 (4.15.0-r0)
(49/89) Installing libunistring (0.9.10-r0)
(50/89) Installing gnutls (3.6.10-r0)
(51/89) Installing cups-libs (2.2.12-r1)
(52/89) Installing jbig2dec (0.17-r0)
(53/89) Installing libjpeg-turbo (2.0.4-r0)
(54/89) Installing tiff (4.1.0-r0)
(55/89) Installing ghostscript (9.50-r0)
(56/89) Installing libde265 (1.0.3-r0)
(57/89) Installing x265-libs (3.2.1-r0)
(58/89) Installing libheif (1.6.0-r0)
(59/89) Installing libcroco (0.6.13-r1)
(60/89) Installing shared-mime-info (1.15-r0)
(61/89) Installing gdk-pixbuf (2.40.0-r0)
(62/89) Installing libxft (2.3.3-r0)
(63/89) Installing fribidi (1.0.8-r0)
(64/89) Installing graphite2 (1.3.13-r1)
(65/89) Installing harfbuzz (2.6.4-r0)
(66/89) Installing pango (1.44.7-r0)
(67/89) Installing librsvg (2.46.4-r0)
(68/89) Installing libwebp (1.0.3-r0)
(69/89) Installing imagemagick (7.0.9.7-r0)
(70/89) Installing mariadb-common (10.4.12-r0)
(71/89) Installing libaio (0.3.112-r1)
(72/89) Installing linux-pam (1.3.1-r1)
(73/89) Installing mariadb (10.4.12-r0)
Executing mariadb-10.4.12-r0.pre-install
(74/89) Installing mysql (10.4.12-r0)
(75/89) Installing mariadb-client (10.4.12-r0)
(76/89) Installing mysql-client (10.4.12-r0)
(77/89) Installing openssl-dev (1.1.1d-r3)
(78/89) Installing mariadb-connector-c (3.1.6-r0)
(79/89) Installing mariadb-connector-c-dev (3.1.6-r0)
(80/89) Installing mariadb-embedded (10.4.12-r0)
(81/89) Installing mariadb-dev (10.4.12-r0)
(82/89) Installing openssh-keygen (8.1_p1-r0)
(83/89) Installing libedit (20191211.3.1-r0)
(84/89) Installing openssh-client (8.1_p1-r0)
(85/89) Installing openssh-sftp-server (8.1_p1-r0)
(86/89) Installing openssh-server-common (8.1_p1-r0)
(87/89) Installing openssh-server (8.1_p1-r0)
(88/89) Installing openssh (8.1_p1-r0)
(89/89) Installing tzdata (2019c-r0)
Executing busybox-1.31.1-r9.trigger
Executing fontconfig-2.13.1-r2.trigger
Executing shared-mime-info-1.15-r0.trigger
Executing gdk-pixbuf-2.40.0-r0.trigger
OK: 522 MiB in 130 packages
Removing intermediate container e1c977b67de4
---> be116c9eaf71
Step 7/25 : RUN gem install bundler:2.1.4
---> Running in a894bdb10b41
Successfully installed bundler-2.1.4
1 gem installed
Removing intermediate container a894bdb10b41
---> a8c5f1494291
Step 8/25 : RUN apk add --no-cache build-base
---> Running in 8f2a90b73e2d
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
OK: 522 MiB in 130 packages
Removing intermediate container 8f2a90b73e2d
---> ec6f50aca4e5
Step 9/25 : RUN gem install mysql2
---> Running in bb25d2597f99
Building native extensions. This could take a while...
Successfully installed mysql2-0.5.3
1 gem installed
Removing intermediate container bb25d2597f99
---> 4bbe69c28409
Step 10/25 : RUN gem install ffi
---> Running in 4371a9f113ed
Building native extensions. This could take a while...
Successfully installed ffi-1.12.2
1 gem installed
Removing intermediate container 4371a9f113ed
---> 7fadd5e643be
Step 11/25 : RUN gem install nokogiri
---> Running in 2c9313d05f77
Successfully installed mini_portile2-2.4.0
Building native extensions. This could take a while...
Successfully installed nokogiri-1.10.8
2 gems installed
Removing intermediate container 2c9313d05f77
---> 3c92d16034fa
Step 12/25 : RUN bundle install
---> Running in bfcb8722664c
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/............
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Fetching rake 12.3.3
Installing rake 12.3.3
Fetching concurrent-ruby 1.1.6
Installing concurrent-ruby 1.1.6
Fetching i18n 1.6.0
Installing i18n 1.6.0
Fetching minitest 5.12.2
Installing minitest 5.12.2
Fetching thread_safe 0.3.6
Installing thread_safe 0.3.6
Fetching tzinfo 1.2.5
Installing tzinfo 1.2.5
Fetching activesupport 5.2.3
Installing activesupport 5.2.3
Fetching builder 3.2.3
Installing builder 3.2.3
Fetching erubi 1.9.0
Installing erubi 1.9.0
Using mini_portile2 2.4.0
Fetching nokogiri 1.10.4
Installing nokogiri 1.10.4 with native extensions
Fetching rails-dom-testing 2.0.3
Installing rails-dom-testing 2.0.3
Fetching crass 1.0.4
Installing crass 1.0.4
Fetching loofah 2.3.0
Installing loofah 2.3.0
Fetching rails-html-sanitizer 1.2.0
Installing rails-html-sanitizer 1.2.0
Fetching actionview 5.2.3
Installing actionview 5.2.3
Fetching rack 2.0.7
Installing rack 2.0.7
Fetching rack-test 1.1.0
Installing rack-test 1.1.0
Fetching actionpack 5.2.3
Installing actionpack 5.2.3
Fetching nio4r 2.5.2
Installing nio4r 2.5.2 with native extensions
Fetching websocket-extensions 0.1.4
Installing websocket-extensions 0.1.4
Fetching websocket-driver 0.7.1
Installing websocket-driver 0.7.1 with native extensions
Fetching actioncable 5.2.3
Installing actioncable 5.2.3
Fetching globalid 0.4.2
Installing globalid 0.4.2
Fetching activejob 5.2.3
Installing activejob 5.2.3
Fetching mini_mime 1.0.2
Installing mini_mime 1.0.2
Fetching mail 2.7.1
Installing mail 2.7.1
Fetching actionmailer 5.2.3
Installing actionmailer 5.2.3
Fetching activemodel 5.2.3
Installing activemodel 5.2.3
Fetching arel 9.0.0
Installing arel 9.0.0
Fetching activerecord 5.2.3
Installing activerecord 5.2.3
Fetching mimemagic 0.3.3
Installing mimemagic 0.3.3
Fetching marcel 0.3.3
Installing marcel 0.3.3
Fetching activestorage 5.2.3
Installing activestorage 5.2.3
Fetching public_suffix 4.0.1
Installing public_suffix 4.0.1
Fetching addressable 2.7.0
Installing addressable 2.7.0
Fetching io-like 0.3.0
Installing io-like 0.3.0
Fetching archive-zip 0.12.0
Installing archive-zip 0.12.0
Fetching bindex 0.8.1
Installing bindex 0.8.1 with native extensions
Fetching msgpack 1.3.1
Installing msgpack 1.3.1 with native extensions
Fetching bootsnap 1.4.5
Installing bootsnap 1.4.5 with native extensions
Using bundler 2.1.4
Fetching byebug 11.0.1
Installing byebug 11.0.1 with native extensions
Fetching regexp_parser 1.6.0
Installing regexp_parser 1.6.0
Fetching xpath 3.2.0
Installing xpath 3.2.0
Fetching capybara 3.29.0
Installing capybara 3.29.0
Fetching childprocess 2.0.0
Installing childprocess 2.0.0 with native extensions
Fetching chromedriver-helper 2.1.1
Installing chromedriver-helper 2.1.1
Fetching coffee-script-source 1.12.2
Installing coffee-script-source 1.12.2
Fetching execjs 2.7.0
Installing execjs 2.7.0
Fetching coffee-script 2.4.1
Installing coffee-script 2.4.1
Fetching method_source 0.9.2
Installing method_source 0.9.2
Fetching thor 1.0.1
Installing thor 1.0.1
Fetching railties 5.2.3
Installing railties 5.2.3
Fetching coffee-rails 4.2.2
Installing coffee-rails 4.2.2
Fetching ffi 1.11.1
Installing ffi 1.11.1 with native extensions
Fetching jbuilder 2.9.1
Installing jbuilder 2.9.1
Fetching rb-fsevent 0.10.3
Installing rb-fsevent 0.10.3
Fetching rb-inotify 0.10.0
Installing rb-inotify 0.10.0
Fetching ruby_dep 1.5.0
Installing ruby_dep 1.5.0
Fetching listen 3.1.5
Installing listen 3.1.5
Using mysql2 0.5.3
Fetching puma 3.12.1
Installing puma 3.12.1 with native extensions
Fetching sprockets 3.7.2
Installing sprockets 3.7.2
Fetching sprockets-rails 3.2.1
Installing sprockets-rails 3.2.1
Fetching rails 5.2.3
Installing rails 5.2.3
Fetching rubyzip 1.2.4
Installing rubyzip 1.2.4
Fetching sass-listen 4.0.0
Installing sass-listen 4.0.0
Fetching sass 3.7.4
Installing sass 3.7.4
Fetching tilt 2.0.10
Installing tilt 2.0.10
Fetching sass-rails 5.1.0
Installing sass-rails 5.1.0
Fetching selenium-webdriver 3.142.4
Installing selenium-webdriver 3.142.4
Fetching turbolinks-source 5.2.0
Installing turbolinks-source 5.2.0
Fetching turbolinks 5.2.1
Installing turbolinks 5.2.1
Fetching uglifier 4.2.0
Installing uglifier 4.2.0
Fetching web-console 3.7.0
Installing web-console 3.7.0
Bundle complete! 16 Gemfile dependencies, 76 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0

Post-install message from chromedriver-helper:

+--------------------------------------------------------------------+
| |
| NOTICE: chromedriver-helper is deprecated after 2019-03-31. |
| |
| Please update to use the 'webdrivers' gem instead. |
| See https://github.com/flavorjones/chromedriver-helper/issues/83 |
| |
+--------------------------------------------------------------------+

Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

- If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

- If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

- For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Removing intermediate container bfcb8722664c
---> 0276723282d3
Step 13/25 : ENV RAILS_ROOT ./apptest
---> Running in 3c97843f68d2
Removing intermediate container 3c97843f68d2
---> e1ff02fd951b
Step 14/25 : COPY . /apptest
---> 1884d556d5b4
Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Running in 7e1a3e4a8105
Removing intermediate container 7e1a3e4a8105
 ---> 6f0b1b745b60
Step 16/25 : WORKDIR $RAILS_ROOT
---> Running in c07946983d46
Removing intermediate container c07946983d46
---> b49d91d39003
Step 17/25 : ENV RAILS_ENV='production'
---> Running in a835285cdd25
Removing intermediate container a835285cdd25
---> f19fe86ad12d
Step 18/25 : ENV RACK_ENV='production'
---> Running in 9fc946471e83
Removing intermediate container 9fc946471e83
---> cdee3c526258
Step 19/25 : ENV PORT 3000
---> Running in 9a2785e7fe52
Removing intermediate container 9a2785e7fe52
---> 63420c73d2c7
Step 20/25 : COPY Gemfile Gemfile
---> 4a38b33b798f
Step 21/25 : COPY Gemfile.lock Gemfile.lock
---> 8ad4926c5df2
Step 22/25 : COPY . .
---> e3f41eaa8fa4
Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in 8791388942fd
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T04:30:16.212714 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T04:30:16.213996 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T04:30:16.282905 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T04:30:16.284090 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container 8791388942fd
---> 7727e905131d
Step 24/25 : EXPOSE 3000
---> Running in a0033e85c5c2
Removing intermediate container a0033e85c5c2
---> dc726da05d1d
Step 25/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bundle exec puma -p 3000
---> Running in d02b4b30eed7
Puma starting in single mode...

- Version 3.12.1 (ruby 2.5.7-p206), codename: Llamas in Pajamas
- Min threads: 5, max threads: 5
- Environment: production
- Listening on tcp://0.0.0.0:3000
  Use Ctrl-C to stop
  ^CERROR: Aborting.
  root@dockserver:~/apptest/docker/app# docker ps
  CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
  root@dockserver:~/apptest/docker/app# docker-compose up -d
  Creating network "apptest_default" with the default driver
  Creating apptest_db_1 ...
  Creating apptest_db_1 ... done
  Creating apptest_app_1 ...
  Creating apptest_app_1 ... done
  Creating apptest_web_1 ...
  Creating apptest_web_1 ... done
  root@dockserver:~/apptest/docker/app# ls
  Dockerfile
  root@dockserver:~/apptest/docker/app# cd ..
  root@dockserver:~/apptest/docker# ls
  app db.env web
  root@dockserver:~/apptest/docker# cd ..
  root@dockserver:~/apptest# ls
  Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
  Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
  root@dockserver:~/apptest# docker ps
  CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
  ce331dc10d46 apptest_web "nginx -g 'daemon of…" 4 minutes ago Up 4 minutes 0.0.0.0:80->80/tcp apptest_web_1
  6f88adb78b3d mysql:5.7.18 "docker-entrypoint.s…" 4 minutes ago Up 4 minutes 0.0.0.0:3306->3306/tcp apptest_db_1
  root@dockserver:~/apptest# docker-compose down
  Stopping apptest_web_1 ... done
  Stopping apptest_db_1 ... done
  Removing apptest_web_1 ... done
  Removing apptest_app_1 ... done
  Removing apptest_db_1 ... done
  Removing network apptest_default
  root@dockserver:~/apptest# cd ..
  root@dockserver:~# df -h
  Filesystem Size Used Avail Use% Mounted on
  udev 481M 0 481M 0% /dev
  tmpfs 99M 644K 98M 1% /run
  /dev/vda1 25G 14G 11G 57% /
  tmpfs 493M 0 493M 0% /dev/shm
  tmpfs 5.0M 0 5.0M 0% /run/lock
  tmpfs 493M 0 493M 0% /sys/fs/cgroup
  /dev/vda15 105M 3.6M 101M 4% /boot/efi
  tmpfs 99M 0 99M 0% /run/user/0
  root@dockserver:~# cd docker
  -bash: cd: docker: No such file or directory
  root@dockserver:~# ls
  apptest
  root@dockserver:~# cd apptest
  root@dockserver:~/apptest# ls
  Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
  Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
  root@dockserver:~/apptest# cd db-data
  root@dockserver:~/apptest/db-data# ls
  auto.cnf binlog.000003 ca.pem ib_buffer_pool ibdata1 mysql_upgrade_info public_key.pem sys
  binlog.000001 binlog.index client-cert.pem ib_logfile0 mysql performance_schema server-cert.pem undo_001
  binlog.000002 ca-key.pem client-key.pem ib_logfile1 mysql.ibd private_key.pem server-key.pem undo_002
  root@dockserver:~/apptest/db-data# ls -la
  total 74400
  drwxr-xr-x 5 root root 4096 Feb 19 15:57 .
  drwxr-xr-x 16 root root 4096 Feb 20 04:07 ..
  -rw-r--r-- 1 root root 56 Feb 19 15:57 auto.cnf
  -rw-r--r-- 1 root root 178 Feb 19 15:57 binlog.000001
  -rw-r--r-- 1 root root 178 Feb 19 15:57 binlog.000002
  -rw-r--r-- 1 root root 178 Feb 19 15:57 binlog.000003
  -rw-r--r-- 1 root root 48 Feb 19 15:57 binlog.index
  -rw-r--r-- 1 root root 1680 Feb 19 15:57 ca-key.pem
  -rw-r--r-- 1 root root 1112 Feb 19 15:57 ca.pem
  -rw-r--r-- 1 root root 1112 Feb 19 15:57 client-cert.pem
  -rw-r--r-- 1 root root 1680 Feb 19 15:57 client-key.pem
  -rw-r--r-- 1 root root 4701 Feb 19 15:57 ib_buffer_pool
  -rw-r--r-- 1 root root 50331648 Feb 19 15:57 ib_logfile0
  -rw-r--r-- 1 root root 50331648 Feb 19 15:57 ib_logfile1
  -rw-r--r-- 1 root root 79691776 Feb 19 15:57 ibdata1
  drwxr-xr-x 2 root root 4096 Feb 19 15:57 mysql
  -rw-r--r-- 1 root root 37748736 Feb 19 15:57 mysql.ibd
  -rw-r--r-- 1 root root 6 Feb 19 15:57 mysql_upgrade_info
  drwxr-xr-x 2 root root 4096 Feb 19 15:57 performance_schema
  -rw-r--r-- 1 root root 1676 Feb 19 15:57 private_key.pem
  -rw-r--r-- 1 root root 452 Feb 19 15:57 public_key.pem
  -rw-r--r-- 1 root root 1112 Feb 19 15:57 server-cert.pem
  -rw-r--r-- 1 root root 1680 Feb 19 15:57 server-key.pem
  drwxr-xr-x 2 root root 4096 Feb 19 15:57 sys
  -rw-r--r-- 1 root root 12582912 Feb 19 15:57 undo_001
  -rw-r--r-- 1 root root 12582912 Feb 19 15:57 undo_002
  root@dockserver:~/apptest/db-data# ls -lh
  total 73M
  -rw-r--r-- 1 root root 56 Feb 19 15:57 auto.cnf
  -rw-r--r-- 1 root root 178 Feb 19 15:57 binlog.000001
  -rw-r--r-- 1 root root 178 Feb 19 15:57 binlog.000002
  -rw-r--r-- 1 root root 178 Feb 19 15:57 binlog.000003
  -rw-r--r-- 1 root root 48 Feb 19 15:57 binlog.index
  -rw-r--r-- 1 root root 1.7K Feb 19 15:57 ca-key.pem
  -rw-r--r-- 1 root root 1.1K Feb 19 15:57 ca.pem
  -rw-r--r-- 1 root root 1.1K Feb 19 15:57 client-cert.pem
  -rw-r--r-- 1 root root 1.7K Feb 19 15:57 client-key.pem
  -rw-r--r-- 1 root root 4.6K Feb 19 15:57 ib_buffer_pool
  -rw-r--r-- 1 root root 48M Feb 19 15:57 ib_logfile0
  -rw-r--r-- 1 root root 48M Feb 19 15:57 ib_logfile1
  -rw-r--r-- 1 root root 76M Feb 19 15:57 ibdata1
  drwxr-xr-x 2 root root 4.0K Feb 19 15:57 mysql
  -rw-r--r-- 1 root root 36M Feb 19 15:57 mysql.ibd
  -rw-r--r-- 1 root root 6 Feb 19 15:57 mysql_upgrade_info
  drwxr-xr-x 2 root root 4.0K Feb 19 15:57 performance_schema
  -rw-r--r-- 1 root root 1.7K Feb 19 15:57 private_key.pem
  -rw-r--r-- 1 root root 452 Feb 19 15:57 public_key.pem
  -rw-r--r-- 1 root root 1.1K Feb 19 15:57 server-cert.pem
  -rw-r--r-- 1 root root 1.7K Feb 19 15:57 server-key.pem
  drwxr-xr-x 2 root root 4.0K Feb 19 15:57 sys
  -rw-r--r-- 1 root root 12M Feb 19 15:57 undo_001
  -rw-r--r-- 1 root root 12M Feb 19 15:57 undo_002
  root@dockserver:~/apptest/db-data# cd ..
  root@dockserver:~/apptest# ls
  Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
  Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
  root@dockserver:~/apptest# ls -lh
  total 88K
  -rw-r--r-- 1 root root 2.3K Feb 19 17:30 Gemfile
  -rw-r--r-- 1 root root 5.2K Feb 19 15:57 Gemfile.lock
  -rw-r--r-- 1 root root 374 Feb 19 15:57 README.md
  -rw-r--r-- 1 root root 227 Feb 19 15:57 Rakefile
  drwxr-xr-x 10 root root 4.0K Feb 19 15:57 app
  drwxr-xr-x 2 root root 4.0K Feb 19 15:57 bin
  drwxr-xr-x 5 root root 4.0K Feb 19 17:08 config
  -rw-r--r-- 1 root root 130 Feb 19 15:57 config.ru
  drwxr-xr-x 3 root root 4.0K Feb 19 15:57 db
  drwxr-xr-x 5 root root 4.0K Feb 19 15:57 db-data
  drwxr-xr-x 4 root root 4.0K Feb 19 15:57 docker
  -rw-r--r-- 1 root root 635 Feb 20 04:07 docker-compose.yml
  drwxr-xr-x 4 root root 4.0K Feb 19 15:57 lib
  drwxr-xr-x 2 root root 4.0K Feb 19 15:57 log
  -rw-r--r-- 1 root root 65 Feb 19 15:57 package.json
  drwxr-xr-x 2 root root 4.0K Feb 19 15:57 public
  drwxr-xr-x 2 root root 4.0K Feb 19 15:57 storage
  drwxr-xr-x 9 root root 4.0K Feb 19 15:57 test
  drwxr-xr-x 2 root root 4.0K Feb 19 15:57 tmp
  drwxr-xr-x 2 root root 4.0K Feb 19 15:57 vendor
  -rw-r--r-- 1 root root 86 Feb 19 17:30 yarn.lock
  root@dockserver:~/apptest# cd ..
  root@dockserver:~# ls
  apptest
  root@dockserver:~# ls -lh
  total 4.0K
  drwxr-xr-x 16 root root 4.0K Feb 20 04:07 apptest
  root@dockserver:~# pwd
  /root
  root@dockserver:~# ls
  apptest
  root@dockserver:~# ls
  apptest
  root@dockserver:~# cd apptest
  root@dockserver:~/apptest# ls
  Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
  Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
  root@dockserver:~/apptest# ls
  Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
  Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
  root@dockserver:~/apptest# ls
  Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
  Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
  root@dockserver:~/apptest# cd docker
  root@dockserver:~/apptest/docker# ls
  app db.env web
  root@dockserver:~/apptest/docker# cd app
  root@dockserver:~/apptest/docker/app# ls
  Dockerfile
  root@dockserver:~/apptest/docker/app# nano Dockerfile
  root@dockserver:~/apptest/docker/app# CD ..
  CD: command not found
  root@dockserver:~/apptest/docker/app# cd ..
  root@dockserver:~/apptest/docker# ls
  app db.env web
  root@dockserver:~/apptest/docker# cd app
  root@dockserver:~/apptest/docker/app# ls
  Dockerfile
  root@dockserver:~/apptest/docker/app# cd ..
  root@dockserver:~/apptest/docker# ls
  app db.env web
  root@dockserver:~/apptest/docker# cd web
  root@dockserver:~/apptest/docker/web# ls
  Dockerfile nginx.conf
  root@dockserver:~/apptest/docker/web# cd ..
  root@dockserver:~/apptest/docker# ls
  app db.env web
  root@dockserver:~/apptest/docker# cd ..
  root@dockserver:~/apptest# ls
  Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
  Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
  root@dockserver:~/apptest# nano docker-compose.yml
  root@dockserver:~/apptest# docker image

Usage: docker image COMMAND

Manage images

Commands:
build Build an image from a Dockerfile
history Show the history of an image
import Import the contents from a tarball to create a filesystem image
inspect Display detailed information on one or more images
load Load an image from a tar archive or STDIN
ls List images
prune Remove unused images
pull Pull an image or a repository from a registry
push Push an image or a repository to a registry
rm Remove one or more images
save Save one or more images to a tar archive (streamed to STDOUT by default)
tag Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

Run 'docker image COMMAND --help' for more information on a command.
root@dockserver:~/apptest# docker images ls
REPOSITORY TAG IMAGE ID CREATED SIZE
root@dockserver:~/apptest# docker image list
REPOSITORY TAG IMAGE ID CREATED SIZE
<none> <none> dc726da05d1d 21 minutes ago 1.24GB
<none> <none> 386f3fd6a7dd 36 minutes ago 1.24GB
<none> <none> 11ce2a06782d 38 minutes ago 1.24GB
apptest_web latest 2fc981991e9c 2 hours ago 146MB
apptest_app latest 01785695c472 2 hours ago 1.24GB
<none> <none> 056b35ab341d 2 hours ago 1.24GB
<none> <none> 11a7dd8b487a 4 hours ago 146MB
<none> <none> 5e7a9767b3b1 4 hours ago 1.24GB
<none> <none> 5f643c831951 7 hours ago 146MB
<none> <none> 76d963f31e53 7 hours ago 1.24GB
<none> <none> 2948e188a79c 7 hours ago 146MB
<none> <none> 587e2094db66 7 hours ago 1.24GB
<none> <none> 0890028a0365 10 hours ago 146MB
<none> <none> 819ed6dc1d1f 10 hours ago 1.24GB
<none> <none> eca142d9e1f0 10 hours ago 86.2MB
<none> <none> a773b45c51e3 10 hours ago 86.2MB
<none> <none> 6254871f89d6 10 hours ago 86.2MB
<none> <none> ab9597db79c5 10 hours ago 598MB
nginx latest 2073e0bcb60e 2 weeks ago 127MB
ruby 2.5-alpine cbd297d70a23 4 weeks ago 54.9MB
mysql 5.7.18 44a8e1a5c0b2 2 years ago 407MB
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# docker image

Usage: docker image COMMAND

Manage images

Commands:
build Build an image from a Dockerfile
history Show the history of an image
import Import the contents from a tarball to create a filesystem image
inspect Display detailed information on one or more images
load Load an image from a tar archive or STDIN
ls List images
prune Remove unused images
pull Pull an image or a repository from a registry
push Push an image or a repository to a registry
rm Remove one or more images
save Save one or more images to a tar archive (streamed to STDOUT by default)
tag Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

Run 'docker image COMMAND --help' for more information on a command.
root@dockserver:~/apptest# docker image prune
WARNING! This will remove all dangling images.
Are you sure you want to continue? [y/N] y
Deleted Images:
deleted: sha256:2948e188a79c3dcc7e7facd4df9ec7e847f89d288b19f757be961520c9a4a657
deleted: sha256:9182c73c20fcfcc27a5ecea31e654632eebcbedf80da31c031ed81624bb55106
deleted: sha256:f57ba991daae13cae73baa763e972badb3a85e7c47b3522091fc7a3b62c31e21
deleted: sha256:37a0726b6f0e2b5dfc59dd1218275ca244ba3bc6a619f7e4d8665f4f8f71a8e5
deleted: sha256:1fd9c15a4bd776dd56688380dc1e43ccbd7dda8a9779c5c6477850650942497a
deleted: sha256:a4c0af7e2b3856a9e408b0367ad13d9b2be72605e60e6f86d77499c03ce2f2c8
deleted: sha256:6254871f89d6c39c0b55046af553907a4772aa98c9b9effb8134e569c4fdbe19
deleted: sha256:32cbb78002811400542a8eb8e7c2c1ccca3533011fb6a97ffc9d8df18150ed00
deleted: sha256:cb2efd6413b2acf6c753c6dfd1334def230947f2eeea8456a7fe31bb58a56926
deleted: sha256:0d1725488b43e2e8b8e2bf37bf86c32ce469e7b2775757a860d2993c6f436f72
deleted: sha256:ee950b97462538faab45d72b1406126c3c92760726f918d670ab80816e95a736
deleted: sha256:a7aa17c90d3164a4f4a59c685144c938ac976dd50911726e29d3ca275d33600f
deleted: sha256:c36fb067f11272f55736ceb6063e47672d7d3ffa5e90c8941bdb0fe3a469abc2
deleted: sha256:9be050acb43a72c08b1eb4485a462212c43cbfdebfdf0fa765f9580cc58e9b9b
deleted: sha256:ab9597db79c5c267480f35273476afa2b7a2166c91c134f5bb7a9da161369581
deleted: sha256:6a2c77cef51a9714261f041986fa4acf829106d4bf2bb64d331b5946e16e1c25
deleted: sha256:2855023271190f133a4af60f5b44df776f378babf3fa1c460b6124b1d1659702
deleted: sha256:b7023c8fea03a9df5747297d904932abbceccd25fe4cbc560fafc5cba728ef12
deleted: sha256:5d0287e04e2d164bcf51aaf3a27e8c825381cbbaed6f728d634478f07f977ca2
deleted: sha256:ee3744d9db81b0378fff0b77e3a19ec8b5136f3acd401c20abd8fceb389fba1f
deleted: sha256:a36b593f32f5814ddedb3686e8b151755337f480d44959799b94806176924133
deleted: sha256:a4e8adff44620d5c079ac02ff9d3a83dbf80f8d27bf5d324dbd5fe3730d158dc
deleted: sha256:29b2cbf4445890a09e9eeb07e480843c3bef5cffb045907edee35de476a61687
deleted: sha256:3b3a27511e8234a704cd352abfadbd02b5b7f0d4c7faa27086013178822efb7c
deleted: sha256:1cafec53d5fa648c980236d8331f245c245b19acb9a53b1a6b7e029e622c77d1
deleted: sha256:7092affe0b8335681f81daff3eee7bc1e4446d77495b1290c5355f2e5b39572c
deleted: sha256:e01733d367d0c82d854c1bf16d45d7793cb876a80749e38e0cf24e702f1dea0a
deleted: sha256:41f6285bd6817ca8e0eb825d1b8664f1b477c7e7da07800337d27cbd124606fc
deleted: sha256:9fb37d65b35e18b60e9bf4cd52b3cd12e5f23bdf2ae9460edaf0931523e43b67
deleted: sha256:499b6957f575b18b74a67a3c9860a0db86d88aee52335ca396ac47bd33d7d144
deleted: sha256:c1b52bb927049b2dce8e83990dd25c353823bc96407a072099d5a56dc1098efa
deleted: sha256:74618a9ac9184b2a427369ba536111ec08bf1bced5395f900209535b75ccda1f
deleted: sha256:5e7a9767b3b1427f2abc064fa5b79a0137e03d79a2d3ebcede135e17bd3e07b1
deleted: sha256:2857364d9222b732ba4507a89b458fe4f6fc33528bb612ba3223b9a3f9d77538
deleted: sha256:80ff1bb9acbbcd3c49f480ccc1b9631641d61382a24c29daaf16469a71c784be
deleted: sha256:573a8a56ab9279fb5a03fe07e15a28194f4839502c7e06a5057bb7919550eda9
deleted: sha256:016080b5397406957abc592e4bf46be9d2895ce75c17170a69990a1235dcc104
deleted: sha256:8cb3f2c1393249b23a7712e54ad099229e66611c27676585502e330079894caf
deleted: sha256:c3578d7d772f1af34edfea1843ef9b8acc0e4ec4139a33e54b77e7ad686047cd
deleted: sha256:46c6e77cffa3e77a395c3bb2a7103405b9ff84f446dd4f559c29c8b5b0235207
deleted: sha256:0bc33a8dfcee067ef51171c9e383de32db127057652399250e678d0f610b6435
deleted: sha256:b4b6d78765a08978ffba802ec35e304df6f478bbf5e95885dc9db0d293c6ecdd
deleted: sha256:aa4d161388e2c35d886e850f4271f1a713a644e7b6055f1a70d5461756df2fad
deleted: sha256:74ea65dff953c303677b28638b3d3f80059c5f66cd42c64f90fe877b999ab6f5
deleted: sha256:5c89670b82d5f5d367e96fbffa886b0931c3b0128738fee2d40626db7aabd0ec
deleted: sha256:0d35ab720efa318a95589388f889f6b64fbc1dcaf465bab6786e3c6be694af50
deleted: sha256:b6d2757695411c214c05e84687cdd28fe35c0310bbaff3c6714125bf8f97e10c
deleted: sha256:f53caadd11acd1cba7a560a26693da10cf28404d4a7344301b5721981f38b3bb
deleted: sha256:d0a753447d101dd0c9c382c2fe87026e40f4c6493c1e6ec2708121ef43e4d8f9
deleted: sha256:47623f75d93af729bfc03896b7ff06cce76403162ed49e2a1942e4554bf37597
deleted: sha256:606caa503fb31a39da8c452ef54ad3bcc4dcac6d9601657c8be82c23cbc08448
deleted: sha256:3575c005ba81d840694b34794c100ff04c699d4a0df89818b588f02090d8f75f
deleted: sha256:e6b18597f22c3c779319ba164952e66617a5624bb88d1b4a98cc24370e4845ae
deleted: sha256:47803b63c1604a54eb98ff13ef5ab648686ab89069ed6d1cc13e63b8ee8caf4d
deleted: sha256:99c9994fac9c665216f6a9f2d065845b20bc2ff75bb47f7badeca446658b4f75
deleted: sha256:3bc5a50da7c96302047ed3be79a27084fb74927c9c1f9319428143697d252270
deleted: sha256:1884c68701401e413a239a74e9f23e23c26f5805d254a40bccb7047a331bd0fd
deleted: sha256:4f57eddcf314a9c759b823f27c844f0bd70ed5706170b14258f44383a3eb2c39
deleted: sha256:b815e6d8ee0114d56e5f964c3c1c16f86f2707ee236c121ef9458004943fc45b
deleted: sha256:aaea64bfbcf1e3e599f330d21a817d3619ecbf74550cf751fa7dd797ee42f07c
deleted: sha256:b4b70c17b9f4b0d0ad5ba5fdfa4adad6e0a428822b724083ac72b0c1c7401195
deleted: sha256:d7321f001d68b92597c8026fbd9c9455428ed6351a42daae980e00d031ba1dc0
deleted: sha256:eb1a57b4ebd949d2fc05c220763a1e17eec6c9d350e75886e4bc8d85717ce78f
deleted: sha256:15cf3e48f80f842d557c7d7ac91b2be22afc17be74ea69fa3771d1808f7f0561
deleted: sha256:14a389124c576b653308dbd6f094303dcb588aef0141ec63452cd9064420b47c
deleted: sha256:07553c74b169121ab4a290d634127fde6ab384e05855fbc1fc0dc368a78f10e6
deleted: sha256:a8f950b69504ccc973df7870040f7030dc1794a8d3dad3a085ebe4548be1a39d
deleted: sha256:0e06d5e7aa539d91a0e8cd481449b10d67bd5a5957e7b382f642110c964b4c12
deleted: sha256:dc6a9765b55d23e45c67ae117ca5bd3358989b8a641d700984349bc9c10e8871
deleted: sha256:0beec6888a94e9a38d7e634b0e2b4af8e65a1ba4bd7aef1dd3893fef79f989a2
deleted: sha256:0a87b50250902fa74f7ad958abb04b920ac1b37c3644fc83452dd9baff8f0daf
deleted: sha256:dd326e77833865c9d166c7a872dad4dcd9a990e393b39cae441befdc070fa86d
deleted: sha256:eca142d9e1f0cea445a572c402641a3c3c3b1688051e6e21f8d55a40cf87f48a
deleted: sha256:a2de18b73fbf773fcc6e66ca617c589a3217916512bc202967bec2fb5924689e
deleted: sha256:118c77036793b20730eb382c50d53ebb17ef83ac27c565ab709e38279f429259
deleted: sha256:5e12757dd06759799120fb7f0e382b2b4eab3221299f50cf45e8bc30a7bdedba
deleted: sha256:2ee9906c3ecb6024943a1c8294d7cf9b920c3658716ce9224c00c55839c2102e
deleted: sha256:4a97880f70de3b41a3c2863aca78102acf928c9fa071f0eed9b88b10b4e2dd13
deleted: sha256:3d388bca2f992ad1df9f872cd57a49d96927163ee320385c4308ff7cf062e086
deleted: sha256:c2d25ec418f3c13102e1f67c26a45f8198d382877391f747197fb80ebcc79d89
deleted: sha256:5f643c8319511b623859dde0793105fe5363a998853b3b57644247b4d92251b9
deleted: sha256:2dd0516fbea231db42587256c2caaba2ca0502226a9dff69236757fa82d79934
deleted: sha256:1b03552a10060d58cff5f9450174ebd9a704dab7602011e231ce10c9aea6e98d
deleted: sha256:60a978650837c351a5be0850a50272700de7c2eb8f5fc587717401e3e3be2855
deleted: sha256:402b8447578d2fcc19100a2498ce75276c79b0c98a5c32d021f48997d4d898c9
deleted: sha256:6954ff4f4f978da8be6b2ad7b2ed2eecc036e6ca20741442082e5e258ca54a82
deleted: sha256:a68c86cc401e021ab729c0a9707be7cfc9252d8828f4a970f333b04f40a5d13b
deleted: sha256:6464a1b2ab80f17667fb7de6408a2f494764faa140f5930fbaee900eb9faec46
deleted: sha256:c06b3bd37c4e8c186dda32e181eebc0ecb4e4db7738e1e780f0cc9017d4b8b9b
deleted: sha256:4a14d1f92bbe3e71886d31b33cfc79958dbd329d5e60d68dd6c360765e96dab7
deleted: sha256:65402ffe5aadc22b4916736f36aeb2fe5be5096ce04c971101854f15a479fbb0
deleted: sha256:58f6494c4f205eaa43c0b31779a55ba878547e2ecc18cb0be30adbb10fdcc03f
deleted: sha256:b2647a40cf6fb81e60799f45071e1d01c24162e28ce9f038e3673548f06487a1
deleted: sha256:819ed6dc1d1f5322c4ab7c4ac45c236182ba4c25c89350b4a38edb383e3529cf
deleted: sha256:7299adf93195c903976c0c1c238cee4b91605a0945c367b70b3aa95e3c7a2f3b
deleted: sha256:f047a803ec427bfddd2deb60fd260f0cc167c39347573e4c7617d21bfde9223c
deleted: sha256:d7027b1d4da6eb8975fb3b46b25f7d6d021cf5e096ec76570db5405c0354be3c
deleted: sha256:6a92161a2371b90f773e187ebe96595d68f1eb1e8597e8cf82d355c37668c239
deleted: sha256:c3dd022db08a23f5a73b5d877d56f9b1d15314f2cc6584b370e7d3d04fcb7a7e
deleted: sha256:2e9a37c5df17bc0b260a9695a580821675167d2cddbbef059cb4334c98b465f7
deleted: sha256:47d34526438807689762bb59f3e1cb0154492cfb015ce05abebe66f788ddf854
deleted: sha256:10ea9863b4604bbffb4303e93c7fb58140f9f60e355f3f9686472529745794a9
deleted: sha256:e5b89659050e2e78fe7e2a3cfd72adafa74587adba625887495de6546f388ae2
deleted: sha256:ce1e82ad91b52c2ea31b7046a231e3474f2c6914a51f3775e9ef116f2c86d950
deleted: sha256:d5a4086775726a0aa6f35f0396a4377702902a0f972bb234e5f127d20ad21aa4
deleted: sha256:56fffdc3ea60ea31c317df55e30b0866a670a26958302749a794472e6c7752df
deleted: sha256:eb02d06f04353b757b4140d053a4cd377c572ed4261163240d516d957bf17c65
deleted: sha256:7f8ae5cb7561ed5b7b20138a0f70d25d8b0ce5c51606442da08a7e7405c5cbd1
deleted: sha256:4682973fa227cbe0e9b808ed83a6923fdd3f34bf3d4c683275c426c431b98237
deleted: sha256:4ba53f993a5052eaae04e481b1cd42c12a4717665397523ddad118b3048b8893
deleted: sha256:0890028a03657c9e79805296fc3f0672d38fda8d008f2ce8c80dc3f7de752a5f
deleted: sha256:d63eeb9b800455f5dc03a1d7d1ad7a249d55b9d8be219e853375b699506eb328
deleted: sha256:1999466a260cc93acd020cf048c71de492c7c85e0d533a691b1e75c0e4cd7139
deleted: sha256:efe20e72da475ebcda40970be5e46f9d2120cc1cfc576a48d5996889e6d6a6c2
deleted: sha256:4fcbc4a96847b2bd765489af0de4fa13e1a436d59c015c99c90c8c1b44b08e62
deleted: sha256:8fe04c6c718b1921315c8271e130d81c79441c6e064a856c0df210dedb2b5260
deleted: sha256:babb27270ca318c4118f227f464bd79b2a47532e3cb9a976be2756f80456e58a
deleted: sha256:7f98101e441205ce5369545336c4d2ab985652be077347ed1854105e010c0cc0
deleted: sha256:65ba018fec06b2b8ba86d22e956b0332fb6a9679814cfc9a28fe6aa24d146b49
deleted: sha256:4eee0459c81e451517b05d1df26517a7a5ea6ca441cc535a60c634acfe6828cd
deleted: sha256:c7f7ebf2ca91568023c4dc84b40050b6ed3fa0adf21205095bea9f5e865ca290
deleted: sha256:52f02274e383c93fe78805a95f097fc114f34c11ebf5472d1ee7c037ac7808b1
deleted: sha256:f9d83a568f742635f479a1fe1e4657d4b5713cf986e239b1582b40fb9f743365
deleted: sha256:11a7dd8b487a919b177c170f4130ca2b0ad83eed178b8de1219ddd12e5b8cd66
deleted: sha256:766085926422201a175aea59f0587ba24dc5632efd9cd35a553b625f83010842
deleted: sha256:3035aa53ee6594557cafb349b1beb23e35c94cbbc0aaa45b1702f5e595d84507
deleted: sha256:1001456b64c987b7b3cf51c3c7daedddd1ea129b606795c46664c06420d8a644
deleted: sha256:ba4d10c87d61aaded7bf61313dea98c5930da0f4a84f9c57aa45872d6f098c26
deleted: sha256:0ca6f2993fa97305b9bfa0495bdda3cee435dd775902b34d0cc637b86ecf7ef7
deleted: sha256:114c251d9cee7da700ffdc5009a0b300cbfabb81c67bef7e9fe6a99a0537b879
deleted: sha256:8c64b5c9226be76bddab8795f697d9457a8716e024aa35eac9e7a38ce3ed8d52
deleted: sha256:02d8b0ea35f2ef3b18d9c192ce3a2d52f578ab832c1b3eb60525e4e1affbb597
deleted: sha256:5b25d384361a33fb004ec146a6781890347132bd07d5c358782ef221741419bc
deleted: sha256:9c0c528884dec55c6c479452ad9854e462ec1729e90bae1215abc46c6add0bde
deleted: sha256:06c86c0a1677f7b68cfc345d4aaeeb22616321d0855d284381b24b01bbdf5d9f
deleted: sha256:b128ec32cf90ac5b716451aeb1e2e6ba6332ee1b8d05d5644c65a1eda31317da
deleted: sha256:587e2094db666d77cde531905e2741d16682608dc0cdac32a85ad9a94d0dd5be
deleted: sha256:e72257bad8af39c4a162f530e9a9f96b49308397ef17e5d2049d57f7129b97da
deleted: sha256:2ee7a932fefdb5050f64108c8faeb93bba0e023ef5a28644cdfedce5841d43d4
deleted: sha256:60736d54a1e107254c9b7b7614cb0ed754d163cd816e2a54e365d01c91bf8907
deleted: sha256:5abd4a9ec2a2fbede83c7ff15b00b341b9c258afd2e190ef3a2a54d8943a3ce3
deleted: sha256:6b9ad75e7e7f970e2830c748bde608697f30f77159943647f9295d8bfbf07d16
deleted: sha256:3fd7a51059f4892a9c0adaa43b59f8c625e00dded6a2337f0de48bb8aaae0764
deleted: sha256:f7bf705d4a59c3a0ff995e27e4942d8071c7b7f0d03603ad88e5ae8d8865a44a
deleted: sha256:6d7bdfb4f784378473baf177a0ac74ae5f8e8ac7b64d88ba3b848228501fa6c1
deleted: sha256:53d076658a191ed91cf2789c2b05abec0bd17523f9390cbd5e006b0ba060e406
deleted: sha256:6496336f1754c223034a8f50b1ddefa0da97374fabed2dba72fcccab4ebf2ee0
deleted: sha256:77af7d1e4181eedd0b681c8886e30259bcce9517ce7ee751126eb7a231e7935a
deleted: sha256:7920747d07e5b6e9f174125e1debe95d3c26f17fa3d8e71cb851e459a608e47f
deleted: sha256:e79e1a05f48c20040b5d8e44ed8911561cd5487210eef171f4e208927432adad
deleted: sha256:3818df030c5b4c0be7f9b3355059e60e0d53d4a9e2959b511cbdc19b61e2b2b0
deleted: sha256:6401899d1dfe98560242d9e53ca9d975ea057ef718642260435391f41dda7bd3
deleted: sha256:f5ca78f12a13eb24c0b977bfe61293ba3f67606787a3eebefb3686b219aea8f1
deleted: sha256:3f57aee5e5f2e784cd4100ef3a7cca2da68aebf195cdcafed5addb83e0bf2326
deleted: sha256:263b26ca10104d5958c983e7d2088c5a6595d50da567b88ed902046d576a1d81
deleted: sha256:55bb3cf9db5004e872c0686eaf9e54a31d47de36f36df3d960ce75ab8106d7c1
deleted: sha256:c86caae810c0e03bc90cd3096d3d7100f187690cd7cfcb29a312c3278079cc9d
deleted: sha256:2e14675032af946257d4206c422d96e86d3f8a695e6649ae22b7b2a1a458d41e
deleted: sha256:9c040fe30edc49e0a7fc17c6be583538f3bdcff9e65375b82cf9ccfe2fb20d2f
deleted: sha256:273626b572c7b8267d2ee85fc2d0994d8232a1fea18738d226031ee803d5a2e2
deleted: sha256:8c9b5e07c1f03af3efd96fa4072a655df7745a89b967e642145939996dfd2434
deleted: sha256:59e32cfc1a939da6c9ed71d90331720b7c1f58d2fa843ec6de879ad311be8e9f
deleted: sha256:48c1108425011b210702ccfd539efe549bc0d622c88a7d1a487ffc816a6273df
deleted: sha256:0d802eecc52464b2573217ceb9e7fb3a094820a06a33e70c07eade8a96e7b2e1
deleted: sha256:eea45ea9f205fd3191c2b3094be657537c18260de638a1cacd1dd3e59d6c6074
deleted: sha256:9c74c10c241d4644a427961940d9f5724c6882cc76f98f2229a6c0db70504285
deleted: sha256:47b0f2ba3a6908fe00aca89dc86acee1ffb7d0aa2f7d5ac8e17849b5594ed99f
deleted: sha256:47a22fdc40f1f9438257313c041296547958f713e4e0ba5111a9ffd9bd5718e0
deleted: sha256:c59267daaae0ff8a2187903f1af2d77cdb94dd5737bfddf5208e701a24fb0e90
deleted: sha256:af99b284f97780cab9d0e973e5c9ae686c3f20e24f80b0fccab8f0378dc82834
deleted: sha256:687e36b42b771eefa071ee7a22c410e83f5b3317b015afbba4eceb680e86666b
deleted: sha256:887b047b12900e00e461bed132526ece60f3c9095b375f4958904472135bc435
deleted: sha256:24a2e7ba16bc9ea9a599de85144ab188f7d2b226ec9cfc58f08d3463e58167b3
deleted: sha256:a29a11b82be4150c9a7dd912e1cb4d37eb8c5b3095da5adb985d69b355f953cb
deleted: sha256:b756c8595e6ef68c5cac43e08d88ade88f44b0ec4fe82c87bf7abb623a1dbd19
deleted: sha256:ad5f7f53cfbe5ab0bf9b11527e40590407b08310b9303b9e7a623a4534bff876
deleted: sha256:386f3fd6a7dd500193a3ae1cb53cb06239dd248eca309ddb70a0b3955596ffa7
deleted: sha256:fbd1432d2913adcbc2b8c49f256b41ee8536571d753b15840126020b4f67a160
deleted: sha256:50f4242d28fa2b2662965ca052d76d8422fd49b9fd0752c07fe1aa5baa6aade0
deleted: sha256:3cfa804b00dfdfee90c30b4dbdf7c09b214ffafc3dbb1915896ba8e90e5d9c9d
deleted: sha256:3908e886b537768254d68698efe394fd8e171ad370a75fd9a4efa07d898c7779
deleted: sha256:26d27074cf8e4b4aa53068f4e100eaa1efd78b62049df408ee85ac3f29297185
deleted: sha256:e7df8393329b5ab2bf21a91582da9ad0250ef84c42bcbd1c01f597a8f55478fd
deleted: sha256:6404b9394ad506b075fddfb48653632d7da4877f20ffca7248224a1bae0bb58e
deleted: sha256:41f053fb21ccb9e9f3562277b2229f0bfb1409adbc135481a77e1c076fe38d39
deleted: sha256:072814bf58983a794c97854240d0a33e71cceac517a46eb7925499f0c0dd476b
deleted: sha256:ef37c41f682d072cc710b24f6f25d99fe38e51c1f8ae2a75ef5575051f52d56a
deleted: sha256:cbbc0f646dd84b01fb987c2ffffe40c97449bb20a0f2d79a174f3e9b0cab0f0e
deleted: sha256:cd344734c0ab7f9fe18cf4ed4efed9901192efec974f1a0d1e280638cc1a1400
deleted: sha256:affec4d94177e36c85228f63388ce26ec6b4438df5d258043480d2a820684cb6
deleted: sha256:cb06faddbb64181592f350cacf62dd913878f849a35627fe0ee2dbc01e71c664
deleted: sha256:9a7a448ca754e62f8d780196d3e7c90e7f2f534af1bc898e05cd39931316146f
deleted: sha256:a773b45c51e3a7107589da00f66d3033277b14f436bd0c3e01d1f712543399b2
deleted: sha256:befa7053d5231aa17a1eb9ac36d37a40959b0fc61b68fd4876f6d4295f535be4
deleted: sha256:f0b338bf1d4ac53ee150c498b8fe301fc0308776d9ec3def742231d1a870741c
deleted: sha256:838a67c37f4aae60a9c87f02bc6b3f08502f46b815269d1560f1d3ec658cc602
deleted: sha256:66d2e97d51d97dd54465a3548512d6d84d051a473fdade7b9871a7d0f1b3fb62
deleted: sha256:b945d0744b302d1cc77a56529abbc391371156d3c3f2b36a89925493eb989f04
deleted: sha256:f2b43611a6094876f8cedfa3522742dda083c218d071aa66bf7446f76d40dcb3
deleted: sha256:cca59e515bd2cee52e3bca0d568ef5eeb86650942cf16cfc1dd075a00e93ebdb
deleted: sha256:056b35ab341d55bd00454c547fe95928011125f0ef98b4665a9cb7a6e2837e75
deleted: sha256:79d390421e39125a3fe27a3114f012d729d96e560df438696c926c41dfe0b03f
deleted: sha256:1e85f64e59380eacb2c120820fc3582d41c6321745bde9d421f0c1d5f461a68e
deleted: sha256:a5d435ba21fca7450de80340f613e6a5688c07134e0572d7412f0b6ceef921c4
deleted: sha256:9651f762f1e1f6d130210baca2bf3715ea3c393e6f97634383b97d0cb82c7b5f
deleted: sha256:271f20ed1d645ec55c20d60c5de3176121c66ee58f949888bd6c2fb2e222d8e3
deleted: sha256:68cb830d2e47084f34845370b7df765bcf0fe34c44b77324c285c3d7fdb7e241
deleted: sha256:9ebe8ad6878450076a163c4b87a65535690ba6ac9b55b11b45cab7dcb8945998
deleted: sha256:4ac0f2d9fa61f212f90385d54eb99b64db8ff94b516901147d96d8caf6d11336
deleted: sha256:c7db692ca2a70a2fc05376b5eb796ddad3d84a05a8ce93d25dd87d4ffc75744f
deleted: sha256:30c84cf4288c3c01972501ce4b6ca0581138260c9c8571f51d077df8f45d4d35
deleted: sha256:2821e044a4c98caaa306cf8d867c40356409fb872de4c0b30049c0021e3a1f52
deleted: sha256:dab2b8094db38e46a01e38d180f9848e574441e737d77788b9342850d9dc6ebe
deleted: sha256:3dc538e1fce50d1f756a92ddc9281aa24c2039f272508d7b942817a27fdc7066
deleted: sha256:90475134eeb25b2739c6dd75233f741730e736440d6752ba7be00876c569c0de
deleted: sha256:f5cc86176340147dbc2bc609868d4eecd70de6f9221fc7fd3c07786a8c08751e
deleted: sha256:e05b13d1a009fbdc39c29e94b9049d45b04408a7948af08a43edbb0e2a5f5e1a
deleted: sha256:2fd3c6bb64e9f0d34954e8e08b020c2e9ff79e9b406418d57b8584fc5fffb9be
deleted: sha256:28716385eb74df8cbd70f28acd6e64e14dbdcd3c6a5883cfddee06cd12b603a7
deleted: sha256:96deaf66d4767bb5b3225585f715e5094ac33fc113205f76a02b6f182ef8e969
deleted: sha256:62264f5e5eb6bd1abbdf4befeed6b17d9365328a77977810762d8bf554d4844c
deleted: sha256:111f84549d8319ba16429df7848e4ab0f739065068db8b581ee22624505862bc
deleted: sha256:796ac45c319f46ab42651334425c51cbe8d0e805922c7246350b92bfa810be2d
deleted: sha256:6da0cd2dcbd3cc6ff3d23e67aed19a7264b794d4c3f5a06de50866d09ac9fa81
deleted: sha256:9385ac435ddb1447a481f18bb0e6b5bbe310638ff4fdea95cd97b9e5b679c72d
deleted: sha256:b8905a8e936a775cd57cd250b69143fa30403185bf62b177206002cc39f27bf2
deleted: sha256:86d155ce78ac5c51657bf4b411a7015a76dbb13edef7357b5c570410f730fed0
deleted: sha256:ac9a897265c0ad8f0d9a1c879ee8f5569ec5f4ccc3fd5f4d5a52976e0fe0b28e
deleted: sha256:685853dd4ddff018a7d64555eddf701c0f66c8ce1165be5f47f0a43708d37ca2
deleted: sha256:8512579bb95f17c3839d2dac94f9f385101791426a7ee092c00be4702f5e8987
deleted: sha256:99d6bf92574887e403d58d5e3976b3bb6edf346e9418058f3d210132d5898761
deleted: sha256:93c34cda5cd528dff4b4170ee048afd7beb9fff80df13de627965f0af78abbfe
deleted: sha256:b1be35d0b1006f50035170235e3710029fd1d7ded8981eefa630f01457fea542
deleted: sha256:ff0492315bfd4dafae63bc286fbbae668a4f4e084040e4fa1d2ee8895c927d51
deleted: sha256:a3641ca3d19d46c233fed1f38c433773511ba23476f3085ec8bb172bfd6d4b54
deleted: sha256:73fa6d3f271b5494c7a06af189e5ca89d2bc0ad7bc959a7989b57b9052554d95
deleted: sha256:74ed3bb33ee0862c3a7029e7d05726e7999b4d93ae96d6c38e579b5c24b563b9
deleted: sha256:5b6dfb3aefe17a043ce65c9d736ad6ad1453363440a8cc760e8b8d48b2b0c47f
deleted: sha256:9978a1f8499dcf8c1ace1af2e3e779a02ca18ea3a5c37a90cc03ee5e47d7d504
deleted: sha256:a5c19296220fd44bb62c8d974bfff2aa6ad72dff7d54cc07340e5afd6419e3bd
deleted: sha256:dc726da05d1d08d267659b0f4d9dbfbb4d983c96a977768b32b402dbe9f98a60
deleted: sha256:7727e905131d10ff221faf12cfba53137b5e1cb14b981e62e65cf1de18a7516f
deleted: sha256:ec16a383e8dbea85d1e770685af659263f56d5b7a3f6bd80be4ef5fd549e2d84
deleted: sha256:e3f41eaa8fa4f084b48616d5bbca16a514fc171ca7c854d9d1f8ad3f4c743048
deleted: sha256:b692fc3fd54613124483ce2159393b275c0aeff47331d6379023410c140e1608
deleted: sha256:8ad4926c5df29bd82b06eb6a79d2184ebbfd3c0c53b95954802b14c8255b9918
deleted: sha256:95b467074b6943c6dd436700cf2b27733eb01b1f3853587007b39c3b8b7b1075
deleted: sha256:4a38b33b798f30a346cd5371c2cd01c1bcc6eb557c2f9c9bda7767ac3951fe19
deleted: sha256:6b1598c263f1047d822bb663064bf7edc2fcd48cbec07bf59eb22e83400ca38a
deleted: sha256:63420c73d2c774310d4a8fb2f9fd1347112e866949bce93469344ef2628d6863
deleted: sha256:cdee3c526258c22cf480813d9e990787c7055892600b71592bc4357495063085
deleted: sha256:f19fe86ad12d75bd7c910d6e325c0c803126737a81bba5b202c44deccf8f6264
deleted: sha256:b49d91d39003f66fadfa938673c05a773effaf52fc6e495ac92896340a9e4629
deleted: sha256:6f0b1b745b606b660a8caca2996b721fbd22b7382bea7b5c3fd5cafd05c33e80
deleted: sha256:1884d556d5b433393b92dab14c47c8959b42e4c304f256c3032b0dee427a5e2c
deleted: sha256:4616d594e19418d7b9a029cb7600191dfed3697d81330d7e95d7035a9cb86c2d
deleted: sha256:e1ff02fd951b305b4fa0899528f0b874078b8a521e60dfc4632848de2a6a49b3
deleted: sha256:0276723282d3292cbb89f6da95305db4a7fbd67cc06560fb21b93eeee9547562
deleted: sha256:34e2a1bb6988043d64a82a1d24c76389f7e5e164447f0d4577f8768544537d98
deleted: sha256:3c92d16034facb2010d3e968645a888141172c63a36a990e16b69a151776ddfd
deleted: sha256:0edd0decad3f6bc319dba1322d519aca19c93a0f36338dfd3488fca59526b171
deleted: sha256:7fadd5e643be535bedc951d40249e6c924d7539cfc2fd35b0967233aabfde9a4
deleted: sha256:85f962187e6d062f4340294260b4138d6f73228048f31cc1efd7e637ac079d93
deleted: sha256:4bbe69c2840980082967f6413e26ac67c598d1eb0b09381681c48f86e015f5ec
deleted: sha256:d152e6e62b9ba80b119b459490650b8076d5cd6d89df9deed30cc31f9049bce9
deleted: sha256:ec6f50aca4e5ac24f379060e505bdfd18c243eb43754c51dd9b94098fade9241
deleted: sha256:576267e345df4920957d3cde2660d727774ab3ea999472a1c98e1cd2fcc87259
deleted: sha256:a8c5f149429196f9fd96a196210262d6e09c6f9f79b71ddeefecb09ecfcd7927
deleted: sha256:d04f081b4e5b1690fb7a41c1619260f1c64a9afa8a9eb2dcdd9d97d7b5c79a5b
deleted: sha256:be116c9eaf71f66a0659ed419ba66ac3b57ff394974ee011513fe187f52970c0
deleted: sha256:b396ccf7854ff92e53699c251a7585f663444064d0847c6483dc9362d49716e5
deleted: sha256:d9e4c1e7c3aeb2eb1b3db834dee425fe748ae49268bb0b7c6a139526c1607f67
deleted: sha256:f80615d63ed2a8252e146843bd0e2f5a0405d2237bb459dfec9d36022beac000
deleted: sha256:ad1a260077de5eeb6a7c3e50ed0c9e58e76f4d57a9f0538853c1ab741ada6d45
deleted: sha256:1c8494be54778704365eeb1c6ce64851a376fb79fd50a0ea06d29d74ab8b5120
deleted: sha256:570156984051228c0ad63d72e97f4c28ef361145da8f4424ca97e31842da42c6
deleted: sha256:47f27f1459607c8bad1f93903f0cde17209beab9becc7128e67edc1286271681
deleted: sha256:58d30dcbaf244e9752fce4225a3d4633035a564f80469e8e91e85f964f2b0708
deleted: sha256:c5eaf06e0df999ab056f4df6c9761ad321fceaaeb265a8b5af14bacf095902a5

Total reclaimed space: 6.445GB
root@dockserver:~/apptest# cd ..
root@dockserver:~# ls
apptest
root@dockserver:~# cd ..
root@dockserver:/# df -h
Filesystem Size Used Avail Use% Mounted on
udev 481M 0 481M 0% /dev
tmpfs 99M 644K 98M 1% /run
/dev/vda1 25G 7.6G 17G 32% /
tmpfs 493M 0 493M 0% /dev/shm
tmpfs 5.0M 0 5.0M 0% /run/lock
tmpfs 493M 0 493M 0% /sys/fs/cgroup
/dev/vda15 105M 3.6M 101M 4% /boot/efi
tmpfs 99M 0 99M 0% /run/user/0
root@dockserver:/# cd apptest
-bash: cd: apptest: No such file or directory
root@dockserver:/# ls
bin dev home initrd.img.old lib64 media opt root sbin srv tmp var vmlinuz.old
boot etc initrd.img lib lost+found mnt proc run snap sys usr vmlinuz
root@dockserver:/# docker container

Usage: docker container COMMAND

Manage containers

Commands:
attach Attach local standard input, output, and error streams to a running container
commit Create a new image from a container's changes
cp Copy files/folders between a container and the local filesystem
create Create a new container
diff Inspect changes to files or directories on a container's filesystem
exec Run a command in a running container
export Export a container's filesystem as a tar archive
inspect Display detailed information on one or more containers
kill Kill one or more running containers
logs Fetch the logs of a container
ls List containers
pause Pause all processes within one or more containers
port List port mappings or a specific mapping for the container
prune Remove all stopped containers
rename Rename a container
restart Restart one or more containers
rm Remove one or more containers
run Run a command in a new container
start Start one or more stopped containers
stats Display a live stream of container(s) resource usage statistics
stop Stop one or more running containers
top Display the running processes of a container
unpause Unpause all processes within one or more containers
update Update configuration of one or more containers
wait Block until one or more containers stop, then print their exit codes

Run 'docker container COMMAND --help' for more information on a command.
root@dockserver:/# docker container prune
WARNING! This will remove all stopped containers.
Are you sure you want to continue? [y/N] y
Deleted Containers:
bfc2fe6dc648b364ed6cab0674b01d6ed8022562cbfb833e9f1ccfbd371be3ef
9256e03f08654145d13051080852c674c9247c8f7117773caf65b3cd3e88ab05
2d9fd07de39ed2a2aa12e0bb912b9cb0c119f21a7643a32a944b1c1d94043206
d40093fcb59459f7741581894f60c7da3e8a5aea7d21728016ee085332ba2bb7

Total reclaimed space: 723.6kB
root@dockserver:/# df -h
Filesystem Size Used Avail Use% Mounted on
udev 481M 0 481M 0% /dev
tmpfs 99M 644K 98M 1% /run
/dev/vda1 25G 7.6G 17G 32% /
tmpfs 493M 0 493M 0% /dev/shm
tmpfs 5.0M 0 5.0M 0% /run/lock
tmpfs 493M 0 493M 0% /sys/fs/cgroup
/dev/vda15 105M 3.6M 101M 4% /boot/efi
tmpfs 99M 0 99M 0% /run/user/0
root@dockserver:/# ls
bin dev home initrd.img.old lib64 media opt root sbin srv tmp var vmlinuz.old
boot etc initrd.img lib lost+found mnt proc run snap sys usr vmlinuz
root@dockserver:/# pwd
/
root@dockserver:/# cd root
root@dockserver:~# ls
apptest
root@dockserver:~# cd apptests
-bash: cd: apptests: No such file or directory
root@dockserver:~# cd apptest
root@dockserver:~/apptest# docker-compose build --no-cache
db uses an image, skipping
Building app
Step 1/25 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/25 : RUN apk update
---> Running in 6e793c6fc927
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
Removing intermediate container 6e793c6fc927
---> 2c91986587cc
Step 3/25 : RUN apk add nodejs
---> Running in 6e34c7477f1d
(1/4) Installing c-ares (1.15.0-r0)
(2/4) Installing nghttp2-libs (1.40.0-r0)
(3/4) Installing libuv (1.34.0-r0)
(4/4) Installing nodejs (12.15.0-r1)
Executing busybox-1.31.1-r9.trigger
OK: 54 MiB in 41 packages
Removing intermediate container 6e34c7477f1d
---> 4eeafaa96fd6
Step 4/25 : ADD Gemfile Gemfile
---> 49729789fc8c
Step 5/25 : ADD Gemfile.lock Gemfile.lock
---> d0cdf801747b
Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Running in 5a039972961e
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
(1/89) Installing bash (5.0.11-r1)
Executing bash-5.0.11-r1.post-install
(2/89) Installing binutils (2.33.1-r0)
(3/89) Installing libmagic (5.37-r1)
(4/89) Installing file (5.37-r1)
(5/89) Installing isl (0.18-r0)
(6/89) Installing libgomp (9.2.0-r3)
(7/89) Installing libatomic (9.2.0-r3)
(8/89) Installing mpfr4 (4.0.2-r1)
(9/89) Installing mpc1 (1.1.0-r1)
(10/89) Installing gcc (9.2.0-r3)
(11/89) Installing musl-dev (1.1.24-r0)
(12/89) Installing libc-dev (0.7.2-r0)
(13/89) Installing g++ (9.2.0-r3)
(14/89) Installing make (4.2.1-r2)
(15/89) Installing fortify-headers (1.1-r0)
(16/89) Installing build-base (0.5-r1)
(17/89) Installing libcurl (7.67.0-r0)
(18/89) Installing expat (2.2.9-r1)
(19/89) Installing pcre2 (10.34-r1)
(20/89) Installing git (2.24.1-r0)
(21/89) Installing libxau (1.0.9-r0)
(22/89) Installing libbsd (0.10.0-r0)
(23/89) Installing libxdmcp (1.1.3-r0)
(24/89) Installing libxcb (1.13.1-r0)
(25/89) Installing libx11 (1.6.9-r0)
(26/89) Installing libxext (1.3.4-r0)
(27/89) Installing libbz2 (1.0.8-r1)
(28/89) Installing libpng (1.6.37-r1)
(29/89) Installing freetype (2.10.1-r0)
(30/89) Installing libuuid (2.34-r1)
(31/89) Installing fontconfig (2.13.1-r2)
(32/89) Installing lcms2 (2.9-r1)
(33/89) Installing libltdl (2.4.6-r7)
(34/89) Installing xz-libs (5.2.4-r0)
(35/89) Installing libxml2 (2.9.10-r2)
(36/89) Installing imagemagick-libs (7.0.9.7-r0)
(37/89) Installing libxrender (0.9.10-r3)
(38/89) Installing pixman (0.38.4-r0)
(39/89) Installing cairo (1.16.0-r2)
(40/89) Installing libblkid (2.34-r1)
(41/89) Installing libmount (2.34-r1)
(42/89) Installing pcre (8.43-r0)
(43/89) Installing glib (2.62.4-r0)
(44/89) Installing dbus-libs (1.12.16-r2)
(45/89) Installing avahi-libs (0.7-r4)
(46/89) Installing nettle (3.5.1-r0)
(47/89) Installing p11-kit (0.23.18.1-r0)
(48/89) Installing libtasn1 (4.15.0-r0)
(49/89) Installing libunistring (0.9.10-r0)
(50/89) Installing gnutls (3.6.10-r0)
(51/89) Installing cups-libs (2.2.12-r1)
(52/89) Installing jbig2dec (0.17-r0)
(53/89) Installing libjpeg-turbo (2.0.4-r0)
(54/89) Installing tiff (4.1.0-r0)
(55/89) Installing ghostscript (9.50-r0)
(56/89) Installing libde265 (1.0.3-r0)
(57/89) Installing x265-libs (3.2.1-r0)
(58/89) Installing libheif (1.6.0-r0)
(59/89) Installing libcroco (0.6.13-r1)
(60/89) Installing shared-mime-info (1.15-r0)
(61/89) Installing gdk-pixbuf (2.40.0-r0)
(62/89) Installing libxft (2.3.3-r0)
(63/89) Installing fribidi (1.0.8-r0)
(64/89) Installing graphite2 (1.3.13-r1)
(65/89) Installing harfbuzz (2.6.4-r0)
(66/89) Installing pango (1.44.7-r0)
(67/89) Installing librsvg (2.46.4-r0)
(68/89) Installing libwebp (1.0.3-r0)
(69/89) Installing imagemagick (7.0.9.7-r0)
(70/89) Installing mariadb-common (10.4.12-r0)
(71/89) Installing libaio (0.3.112-r1)
(72/89) Installing linux-pam (1.3.1-r1)
(73/89) Installing mariadb (10.4.12-r0)
Executing mariadb-10.4.12-r0.pre-install
(74/89) Installing mysql (10.4.12-r0)
(75/89) Installing mariadb-client (10.4.12-r0)
(76/89) Installing mysql-client (10.4.12-r0)
(77/89) Installing openssl-dev (1.1.1d-r3)
(78/89) Installing mariadb-connector-c (3.1.6-r0)
(79/89) Installing mariadb-connector-c-dev (3.1.6-r0)
(80/89) Installing mariadb-embedded (10.4.12-r0)
(81/89) Installing mariadb-dev (10.4.12-r0)
(82/89) Installing openssh-keygen (8.1_p1-r0)
(83/89) Installing libedit (20191211.3.1-r0)
(84/89) Installing openssh-client (8.1_p1-r0)
(85/89) Installing openssh-sftp-server (8.1_p1-r0)
(86/89) Installing openssh-server-common (8.1_p1-r0)
(87/89) Installing openssh-server (8.1_p1-r0)
(88/89) Installing openssh (8.1_p1-r0)
(89/89) Installing tzdata (2019c-r0)
Executing busybox-1.31.1-r9.trigger
Executing fontconfig-2.13.1-r2.trigger
Executing shared-mime-info-1.15-r0.trigger
Executing gdk-pixbuf-2.40.0-r0.trigger
OK: 522 MiB in 130 packages
Removing intermediate container 5a039972961e
---> 45fa50662b11
Step 7/25 : RUN gem install bundler:2.1.4
---> Running in 84d4e0fba052
Successfully installed bundler-2.1.4
1 gem installed
Removing intermediate container 84d4e0fba052
---> be0891857b89
Step 8/25 : RUN apk add --no-cache build-base
---> Running in 6b332a1b3e36
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
OK: 522 MiB in 130 packages
Removing intermediate container 6b332a1b3e36
---> d47967cf0bc3
Step 9/25 : RUN gem install mysql2
---> Running in 93561d2752bf
Building native extensions. This could take a while...
Successfully installed mysql2-0.5.3
1 gem installed
Removing intermediate container 93561d2752bf
---> b4b0fe088108
Step 10/25 : RUN gem install ffi
---> Running in 4fecfbc9124e
Building native extensions. This could take a while...
Successfully installed ffi-1.12.2
1 gem installed
Removing intermediate container 4fecfbc9124e
---> 3ab8f0f2609c
Step 11/25 : RUN gem install nokogiri
---> Running in c994b8d3fcba
Successfully installed mini_portile2-2.4.0
Building native extensions. This could take a while...
Successfully installed nokogiri-1.10.8
2 gems installed
Removing intermediate container c994b8d3fcba
---> d8ebe7ff0ca2
Step 12/25 : RUN bundle install
---> Running in bb61d6e63772
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/............
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Fetching rake 12.3.3
Installing rake 12.3.3
Fetching concurrent-ruby 1.1.6
Installing concurrent-ruby 1.1.6
Fetching i18n 1.6.0
Installing i18n 1.6.0
Fetching minitest 5.12.2
Installing minitest 5.12.2
Fetching thread_safe 0.3.6
Installing thread_safe 0.3.6
Fetching tzinfo 1.2.5
Installing tzinfo 1.2.5
Fetching activesupport 5.2.3
Installing activesupport 5.2.3
Fetching builder 3.2.3
Installing builder 3.2.3
Fetching erubi 1.9.0
Installing erubi 1.9.0
Using mini_portile2 2.4.0
Fetching nokogiri 1.10.4
Installing nokogiri 1.10.4 with native extensions
Fetching rails-dom-testing 2.0.3
Installing rails-dom-testing 2.0.3
Fetching crass 1.0.4
Installing crass 1.0.4
Fetching loofah 2.3.0
Installing loofah 2.3.0
Fetching rails-html-sanitizer 1.2.0
Installing rails-html-sanitizer 1.2.0
Fetching actionview 5.2.3
Installing actionview 5.2.3
Fetching rack 2.0.7
Installing rack 2.0.7
Fetching rack-test 1.1.0
Installing rack-test 1.1.0
Fetching actionpack 5.2.3
Installing actionpack 5.2.3
Fetching nio4r 2.5.2
Installing nio4r 2.5.2 with native extensions
Fetching websocket-extensions 0.1.4
Installing websocket-extensions 0.1.4
Fetching websocket-driver 0.7.1
Installing websocket-driver 0.7.1 with native extensions
Fetching actioncable 5.2.3
Installing actioncable 5.2.3
Fetching globalid 0.4.2
Installing globalid 0.4.2
Fetching activejob 5.2.3
Installing activejob 5.2.3
Fetching mini_mime 1.0.2
Installing mini_mime 1.0.2
Fetching mail 2.7.1
Installing mail 2.7.1
Fetching actionmailer 5.2.3
Installing actionmailer 5.2.3
Fetching activemodel 5.2.3
Installing activemodel 5.2.3
Fetching arel 9.0.0
Installing arel 9.0.0
Fetching activerecord 5.2.3
Installing activerecord 5.2.3
Fetching mimemagic 0.3.3
Installing mimemagic 0.3.3
Fetching marcel 0.3.3
Installing marcel 0.3.3
Fetching activestorage 5.2.3
Installing activestorage 5.2.3
Fetching public_suffix 4.0.1
Installing public_suffix 4.0.1
Fetching addressable 2.7.0
Installing addressable 2.7.0
Fetching io-like 0.3.0
Installing io-like 0.3.0
Fetching archive-zip 0.12.0
Installing archive-zip 0.12.0
Fetching bindex 0.8.1
Installing bindex 0.8.1 with native extensions
Fetching msgpack 1.3.1
Installing msgpack 1.3.1 with native extensions
Fetching bootsnap 1.4.5
Installing bootsnap 1.4.5 with native extensions
Using bundler 2.1.4
Fetching byebug 11.0.1
Installing byebug 11.0.1 with native extensions
Fetching regexp_parser 1.6.0
Installing regexp_parser 1.6.0
Fetching xpath 3.2.0
Installing xpath 3.2.0
Fetching capybara 3.29.0
Installing capybara 3.29.0
Fetching childprocess 2.0.0
Installing childprocess 2.0.0 with native extensions
Fetching chromedriver-helper 2.1.1
Installing chromedriver-helper 2.1.1
Fetching coffee-script-source 1.12.2
Installing coffee-script-source 1.12.2
Fetching execjs 2.7.0
Installing execjs 2.7.0
Fetching coffee-script 2.4.1
Installing coffee-script 2.4.1
Fetching method_source 0.9.2
Installing method_source 0.9.2
Fetching thor 1.0.1
Installing thor 1.0.1
Fetching railties 5.2.3
Installing railties 5.2.3
Fetching coffee-rails 4.2.2
Installing coffee-rails 4.2.2
Fetching ffi 1.11.1
Installing ffi 1.11.1 with native extensions
Fetching jbuilder 2.9.1
Installing jbuilder 2.9.1
Fetching rb-fsevent 0.10.3
Installing rb-fsevent 0.10.3
Fetching rb-inotify 0.10.0
Installing rb-inotify 0.10.0
Fetching ruby_dep 1.5.0
Installing ruby_dep 1.5.0
Fetching listen 3.1.5
Installing listen 3.1.5
Using mysql2 0.5.3
Fetching puma 3.12.1
Installing puma 3.12.1 with native extensions
Fetching sprockets 3.7.2
Installing sprockets 3.7.2
Fetching sprockets-rails 3.2.1
Installing sprockets-rails 3.2.1
Fetching rails 5.2.3
Installing rails 5.2.3
Fetching rubyzip 1.2.4
Installing rubyzip 1.2.4
Fetching sass-listen 4.0.0
Installing sass-listen 4.0.0
Fetching sass 3.7.4
Installing sass 3.7.4
Fetching tilt 2.0.10
Installing tilt 2.0.10
Fetching sass-rails 5.1.0
Installing sass-rails 5.1.0
Fetching selenium-webdriver 3.142.4
Installing selenium-webdriver 3.142.4
Fetching turbolinks-source 5.2.0
Installing turbolinks-source 5.2.0
Fetching turbolinks 5.2.1
Installing turbolinks 5.2.1
Fetching uglifier 4.2.0
Installing uglifier 4.2.0
Fetching web-console 3.7.0
Installing web-console 3.7.0
Bundle complete! 16 Gemfile dependencies, 76 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0

Post-install message from chromedriver-helper:

+--------------------------------------------------------------------+
| |
| NOTICE: chromedriver-helper is deprecated after 2019-03-31. |
| |
| Please update to use the 'webdrivers' gem instead. |
| See https://github.com/flavorjones/chromedriver-helper/issues/83 |
| |
+--------------------------------------------------------------------+

Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

- If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

- If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

- For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Removing intermediate container bb61d6e63772
---> 764763402f13
Step 13/25 : ENV RAILS_ROOT ./apptest
---> Running in c103eace9e6d
Removing intermediate container c103eace9e6d
---> 3898210909b1
Step 14/25 : COPY . /apptest
---> beec6d4e9379
Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Running in 1c87e08e0696
Removing intermediate container 1c87e08e0696
 ---> 9f0ef9b6fc6f
Step 16/25 : WORKDIR $RAILS_ROOT
---> Running in e4464ce8e6c4
Removing intermediate container e4464ce8e6c4
---> ccf6c302d898
Step 17/25 : ENV RAILS_ENV='production'
---> Running in 1dab4142f3fc
Removing intermediate container 1dab4142f3fc
---> 961c78f3bcdc
Step 18/25 : ENV RACK_ENV='production'
---> Running in 8921e2db9a95
Removing intermediate container 8921e2db9a95
---> 3c099fc93eb4
Step 19/25 : ENV PORT 3000
---> Running in ffede831e114
Removing intermediate container ffede831e114
---> 150c46f4d26f
Step 20/25 : COPY Gemfile Gemfile
---> 269f1f6435af
Step 21/25 : COPY Gemfile.lock Gemfile.lock
---> e3bd8b4f022b
Step 22/25 : COPY . .
---> a35c25a2a103
Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in e269497c045a
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T05:01:12.668223 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T05:01:12.669489 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T05:01:12.712380 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T05:01:12.713494 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container e269497c045a
---> d75090ae6b63
Step 24/25 : EXPOSE 3000
---> Running in ce4d05e80297
Removing intermediate container ce4d05e80297
---> d554d7f71dd5
Step 25/25 : CMD ["bundle", "exec", "puma", "-C", "-e production", "config/puma.rb"]
---> Running in 3ba510caad79
Removing intermediate container 3ba510caad79
---> 908405b7c067
Successfully built 908405b7c067
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Running in a7e511a3ba99
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
libapr1 libaprutil1 libgdbm6
Suggested packages:
gdbm-l10n
The following NEW packages will be installed:
apache2-utils libapr1 libaprutil1 libgdbm6
0 upgraded, 4 newly installed, 0 to remove and 9 not upgraded.
Need to get 495 kB of archives.
After this operation, 1157 kB of additional disk space will be used.
Get:1 http://deb.debian.org/debian buster/main amd64 libapr1 amd64 1.6.5-1+b1 [102 kB]
Get:2 http://deb.debian.org/debian buster/main amd64 libgdbm6 amd64 1.18.1-4 [64.7 kB]
Get:3 http://deb.debian.org/debian buster/main amd64 libaprutil1 amd64 1.6.1-4 [91.8 kB]
Get:4 http://deb.debian.org/debian buster/main amd64 apache2-utils amd64 2.4.38-3+deb10u3 [236 kB]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 495 kB in 0s (16.1 MB/s)
Selecting previously unselected package libapr1:amd64.
(Reading database ... 7203 files and directories currently installed.)
Preparing to unpack .../libapr1_1.6.5-1+b1_amd64.deb ...
Unpacking libapr1:amd64 (1.6.5-1+b1) ...
Selecting previously unselected package libgdbm6:amd64.
Preparing to unpack .../libgdbm6_1.18.1-4_amd64.deb ...
Unpacking libgdbm6:amd64 (1.18.1-4) ...
Selecting previously unselected package libaprutil1:amd64.
Preparing to unpack .../libaprutil1_1.6.1-4_amd64.deb ...
Unpacking libaprutil1:amd64 (1.6.1-4) ...
Selecting previously unselected package apache2-utils.
Preparing to unpack .../apache2-utils_2.4.38-3+deb10u3_amd64.deb ...
Unpacking apache2-utils (2.4.38-3+deb10u3) ...
Setting up libapr1:amd64 (1.6.5-1+b1) ...
Setting up libgdbm6:amd64 (1.18.1-4) ...
Setting up libaprutil1:amd64 (1.6.1-4) ...
Setting up apache2-utils (2.4.38-3+deb10u3) ...
Processing triggers for libc-bin (2.28-10) ...
Removing intermediate container a7e511a3ba99
---> 5c3f0cdd8127
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Running in 7efb6bdc6153
Removing intermediate container 7efb6bdc6153
---> 6b15004829b8
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Running in 2873286aa011
Removing intermediate container 2873286aa011
 ---> 4090a6f3b9f1
Step 5/9 : RUN mkdir log
 ---> Running in ef5eed41e998
Removing intermediate container ef5eed41e998
 ---> b461f916c2a0
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> 3e9d6bdd15f4
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Running in f45b93d062da
Removing intermediate container f45b93d062da
---> 0b6276d8f270
Step 8/9 : EXPOSE 80
---> Running in c94a6cdbf9c8
Removing intermediate container c94a6cdbf9c8
---> 2ad3563fb90d
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Running in 78c2a69515b7
Removing intermediate container 78c2a69515b7
---> 5338e7d50868
Successfully built 5338e7d50868
Successfully tagged apptest_web:latest
root@dockserver:~/apptest# docker-compose up -d
Creating network "apptest_default" with the default driver
Creating apptest_db_1 ...
Creating apptest_db_1 ... done
Creating apptest_app_1 ...
Creating apptest_app_1 ... done
Creating apptest_web_1 ...
Creating apptest_web_1 ... done
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
b2adeb1d6245 mysql:5.7.18 "docker-entrypoint.s…" 30 seconds ago Up 29 seconds 0.0.0.0:3306->3306/tcp apptest_db_1
root@dockserver:~/apptest# docker-compose down
Stopping apptest_db_1 ... done
Removing apptest_web_1 ... done
Removing apptest_app_1 ... done
Removing apptest_db_1 ... done
Removing network apptest_default
root@dockserver:~/apptest# docker-compose build
db uses an image, skipping
Building app
Step 1/25 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/25 : RUN apk update
---> Using cache
---> 2c91986587cc
Step 3/25 : RUN apk add nodejs
---> Using cache
---> 4eeafaa96fd6
Step 4/25 : ADD Gemfile Gemfile
---> Using cache
---> 49729789fc8c
Step 5/25 : ADD Gemfile.lock Gemfile.lock
---> Using cache
---> d0cdf801747b
Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Using cache
---> 45fa50662b11
Step 7/25 : RUN gem install bundler:2.1.4
---> Using cache
---> be0891857b89
Step 8/25 : RUN apk add --no-cache build-base
---> Using cache
---> d47967cf0bc3
Step 9/25 : RUN gem install mysql2
---> Using cache
---> b4b0fe088108
Step 10/25 : RUN gem install ffi
---> Using cache
---> 3ab8f0f2609c
Step 11/25 : RUN gem install nokogiri
---> Using cache
---> d8ebe7ff0ca2
Step 12/25 : RUN bundle install
---> Using cache
---> 764763402f13
Step 13/25 : ENV RAILS_ROOT ./apptest
---> Using cache
---> 3898210909b1
Step 14/25 : COPY . /apptest
---> Using cache
---> beec6d4e9379
Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Using cache
 ---> 9f0ef9b6fc6f
Step 16/25 : WORKDIR $RAILS_ROOT
---> Using cache
---> ccf6c302d898
Step 17/25 : ENV RAILS_ENV='production'
---> Using cache
---> 961c78f3bcdc
Step 18/25 : ENV RACK_ENV='production'
---> Using cache
---> 3c099fc93eb4
Step 19/25 : ENV PORT 3000
---> Using cache
---> 150c46f4d26f
Step 20/25 : COPY Gemfile Gemfile
---> Using cache
---> 269f1f6435af
Step 21/25 : COPY Gemfile.lock Gemfile.lock
---> Using cache
---> e3bd8b4f022b
Step 22/25 : COPY . .
---> Using cache
---> a35c25a2a103
Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Using cache
---> d75090ae6b63
Step 24/25 : EXPOSE 3000
---> Using cache
---> d554d7f71dd5
Step 25/25 : CMD ["bundle", "exec", "puma", "-C", "-e production", "config/puma.rb"]
---> Using cache
---> 908405b7c067
Successfully built 908405b7c067
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Using cache
---> 5c3f0cdd8127
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Using cache
---> 6b15004829b8
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Using cache
 ---> 4090a6f3b9f1
Step 5/9 : RUN mkdir log
 ---> Using cache
 ---> b461f916c2a0
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> Using cache
 ---> 3e9d6bdd15f4
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Using cache
---> 0b6276d8f270
Step 8/9 : EXPOSE 80
---> Using cache
---> 2ad3563fb90d
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Using cache
---> 5338e7d50868
Successfully built 5338e7d50868
Successfully tagged apptest_web:latest
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
root@dockserver:~/apptest# docker-compose up -d
Creating network "apptest_default" with the default driver
Creating apptest_db_1 ...
Creating apptest_db_1 ... done
Creating apptest_app_1 ...
Creating apptest_app_1 ... done
Creating apptest_web_1 ...
Creating apptest_web_1 ... done
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
76e8d412af73 mysql:5.7.18 "docker-entrypoint.s…" 6 seconds ago Up 5 seconds 0.0.0.0:3306->3306/tcp apptest_db_1
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# cd docker
root@dockserver:~/apptest/docker# ls
app db.env web
root@dockserver:~/apptest/docker# cd app
root@dockserver:~/apptest/docker/app# ls
Dockerfile
root@dockserver:~/apptest/docker/app# nano Dockerfile
root@dockserver:~/apptest/docker/app# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
76e8d412af73 mysql:5.7.18 "docker-entrypoint.s…" 4 minutes ago Up 4 minutes 0.0.0.0:3306->3306/tcp apptest_db_1
root@dockserver:~/apptest/docker/app# docker-compose down
Stopping apptest_db_1 ... done
Removing apptest_web_1 ... done
Removing apptest_app_1 ... done
Removing apptest_db_1 ... done
Removing network apptest_default
root@dockserver:~/apptest/docker/app# docker-compose build
db uses an image, skipping
Building app
Step 1/24 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/24 : RUN apk update
---> Using cache
---> 2c91986587cc
Step 3/24 : RUN apk add nodejs
---> Using cache
---> 4eeafaa96fd6
Step 4/24 : ADD Gemfile Gemfile
---> Using cache
---> 49729789fc8c
Step 5/24 : ADD Gemfile.lock Gemfile.lock
---> Using cache
---> d0cdf801747b
Step 6/24 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Using cache
---> 45fa50662b11
Step 7/24 : RUN gem install bundler:2.1.4
---> Using cache
---> be0891857b89
Step 8/24 : RUN apk add --no-cache build-base
---> Using cache
---> d47967cf0bc3
Step 9/24 : RUN gem install mysql2
---> Using cache
---> b4b0fe088108
Step 10/24 : RUN gem install ffi
---> Using cache
---> 3ab8f0f2609c
Step 11/24 : RUN gem install nokogiri
---> Using cache
---> d8ebe7ff0ca2
Step 12/24 : RUN bundle install
---> Using cache
---> 764763402f13
Step 13/24 : ENV RAILS_ROOT ./apptest
---> Using cache
---> 3898210909b1
Step 14/24 : COPY . /apptest
---> 64281cd86fdc
Step 15/24 : RUN mkdir -p $RAILS_ROOT
 ---> Running in 369d1b4eff39
Removing intermediate container 369d1b4eff39
 ---> 63baa65affa4
Step 16/24 : WORKDIR $RAILS_ROOT
---> Running in 526281d4cd6c
Removing intermediate container 526281d4cd6c
---> cf29a3b91a19
Step 17/24 : ENV RAILS_ENV='production'
---> Running in 4a394068ae88
Removing intermediate container 4a394068ae88
---> 978e719b5e27
Step 18/24 : ENV RACK_ENV='production'
---> Running in c2a64262b0ba
Removing intermediate container c2a64262b0ba
---> 47c037faad28
Step 19/24 : ENV PORT 3000
---> Running in 0bff18d26fcb
Removing intermediate container 0bff18d26fcb
---> d127b1da8e0e
Step 20/24 : COPY Gemfile Gemfile
---> e0253230169a
Step 21/24 : COPY Gemfile.lock Gemfile.lock
---> e87db2b65a01
Step 22/24 : COPY . .
---> 07204049d18d
Step 23/24 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in 2655a5cb10b4
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T05:14:20.997116 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T05:14:20.998407 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T05:14:21.061949 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T05:14:21.063046 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container 2655a5cb10b4
---> 07483c94dc4f
Step 24/24 : EXPOSE 3000
---> Running in 2c642f4d5ac5
Removing intermediate container 2c642f4d5ac5
---> e84ed2a6a3fb
Successfully built e84ed2a6a3fb
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Using cache
---> 5c3f0cdd8127
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Using cache
---> 6b15004829b8
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Using cache
 ---> 4090a6f3b9f1
Step 5/9 : RUN mkdir log
 ---> Using cache
 ---> b461f916c2a0
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> Using cache
 ---> 3e9d6bdd15f4
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Using cache
---> 0b6276d8f270
Step 8/9 : EXPOSE 80
---> Using cache
---> 2ad3563fb90d
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Using cache
---> 5338e7d50868
Successfully built 5338e7d50868
Successfully tagged apptest_web:latest
root@dockserver:~/apptest/docker/app# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
root@dockserver:~/apptest/docker/app# docker-compose up
Creating network "apptest_default" with the default driver
Creating apptest_db_1 ...
Creating apptest_db_1 ... done
Creating apptest_app_1 ...
Creating apptest_app_1 ... done
Creating apptest_web_1 ...
Creating apptest_web_1 ... done
Attaching to apptest_db_1, apptest_app_1, apptest_web_1
db_1 | Initializing database
db_1 | 2020-02-20T05:14:43.112364Z 0 [Warning] TIMESTAMP with implicit DEFAULT value is deprecated. Please use --explicit_defaults_for_timestamp server option (see documentation for more details).
db_1 | 2020-02-20T05:14:43.443847Z 0 [Warning] InnoDB: New log files created, LSN=45790
db_1 | 2020-02-20T05:14:43.503401Z 0 [Warning] InnoDB: Creating foreign key constraint system tables.
db_1 | 2020-02-20T05:14:43.567703Z 0 [Warning] No existing UUID has been found, so we assume that this is the first time that this server has been started. Generating a new UUID: e76b028b-539f-11ea-92a9-0242ac1e0002.
db_1 | 2020-02-20T05:14:43.570180Z 0 [Warning] Gtid table is not ready to be used. Table 'mysql.gtid_executed' cannot be opened.
db_1 | 2020-02-20T05:14:43.570698Z 1 [Warning] root@localhost is created with an empty password ! Please consider switching off the --initialize-insecure option.
db_1 | 2020-02-20T05:14:44.405733Z 1 [Warning] 'user' entry 'root@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:44.405763Z 1 [Warning] 'user' entry 'mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:44.405777Z 1 [Warning] 'db' entry 'sys mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:44.405790Z 1 [Warning] 'proxies_priv' entry '@ root@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:44.405815Z 1 [Warning] 'tables_priv' entry 'sys_config mysql.sys@localhost' ignored in --skip-name-resolve mode.
app_1 | Switch to inspect mode.
app_1 |
web_1 | 2020/02/20 05:14:44 [emerg] 1#1: host not found in upstream "app:3000" in /etc/nginx/conf.d/default.conf:2
web_1 | nginx: [emerg] host not found in upstream "app:3000" in /etc/nginx/conf.d/default.conf:2
apptest_app_1 exited with code 0
apptest_web_1 exited with code 1
db_1 | Database initialized
db_1 | Initializing certificates
db_1 | Generating a 2048 bit RSA private key
db_1 | .......+++
db_1 | ...............................+++
db_1 | unable to write 'random state'
db_1 | writing new private key to 'ca-key.pem'
db_1 | -----
db_1 | Generating a 2048 bit RSA private key
db_1 | ........+++
db_1 | ...............+++
db_1 | unable to write 'random state'
db_1 | writing new private key to 'server-key.pem'
db_1 | -----
db_1 | Generating a 2048 bit RSA private key
db_1 | ...........................................................+++
db_1 | ...........................+++
db_1 | unable to write 'random state'
db_1 | writing new private key to 'client-key.pem'
db_1 | -----
db_1 | Certificates initialized
db_1 | MySQL init process in progress...
db_1 | 2020-02-20T05:14:46.967800Z 0 [Warning] TIMESTAMP with implicit DEFAULT value is deprecated. Please use --explicit_defaults_for_timestamp server option (see documentation for more details).
db_1 | 2020-02-20T05:14:46.969608Z 0 [Note] mysqld (mysqld 5.7.18) starting as process 89 ...
db_1 | 2020-02-20T05:14:46.973036Z 0 [Note] InnoDB: PUNCH HOLE support available
db_1 | 2020-02-20T05:14:46.973393Z 0 [Note] InnoDB: Mutexes and rw_locks use GCC atomic builtins
db_1 | 2020-02-20T05:14:46.973557Z 0 [Note] InnoDB: Uses event mutexes
db_1 | 2020-02-20T05:14:46.973702Z 0 [Note] InnoDB: GCC builtin **atomic_thread_fence() is used for memory barrier
db_1 | 2020-02-20T05:14:46.973844Z 0 [Note] InnoDB: Compressed tables use zlib 1.2.3
db_1 | 2020-02-20T05:14:46.974017Z 0 [Note] InnoDB: Using Linux native AIO
db_1 | 2020-02-20T05:14:46.974453Z 0 [Note] InnoDB: Number of pools: 1
db_1 | 2020-02-20T05:14:46.974746Z 0 [Note] InnoDB: Using CPU crc32 instructions
db_1 | 2020-02-20T05:14:46.976648Z 0 [Note] InnoDB: Initializing buffer pool, total size = 128M, instances = 1, chunk size = 128M
db_1 | 2020-02-20T05:14:46.985532Z 0 [Note] InnoDB: Completed initialization of buffer pool
db_1 | 2020-02-20T05:14:46.988275Z 0 [Note] InnoDB: If the mysqld execution user is authorized, page cleaner thread priority can be changed. See the man page of setpriority().
db_1 | 2020-02-20T05:14:47.000088Z 0 [Note] InnoDB: Highest supported file format is Barracuda.
db_1 | 2020-02-20T05:14:47.009599Z 0 [Note] InnoDB: Creating shared tablespace for temporary tables
db_1 | 2020-02-20T05:14:47.010112Z 0 [Note] InnoDB: Setting file './ibtmp1' size to 12 MB. Physically writing the file full; Please wait ...
db_1 | 2020-02-20T05:14:47.040336Z 0 [Note] InnoDB: File './ibtmp1' size is now 12 MB.
db_1 | 2020-02-20T05:14:47.041905Z 0 [Note] InnoDB: 96 redo rollback segment(s) found. 96 redo rollback segment(s) are active.
db_1 | 2020-02-20T05:14:47.042432Z 0 [Note] InnoDB: 32 non-redo rollback segment(s) are active.
db_1 | 2020-02-20T05:14:47.043115Z 0 [Note] InnoDB: Waiting for purge to start
db_1 | 2020-02-20T05:14:47.093869Z 0 [Note] InnoDB: 5.7.18 started; log sequence number 2535558
db_1 | 2020-02-20T05:14:47.094741Z 0 [Note] Plugin 'FEDERATED' is disabled.
db_1 | 2020-02-20T05:14:47.100907Z 0 [Note] Found ca.pem, server-cert.pem and server-key.pem in data directory. Trying to enable SSL support using them.
db_1 | 2020-02-20T05:14:47.101792Z 0 [Warning] CA certificate ca.pem is self signed.
db_1 | 2020-02-20T05:14:47.101591Z 0 [Note] InnoDB: Loading buffer pool(s) from /var/lib/mysql/ib_buffer_pool
db_1 | 2020-02-20T05:14:47.103885Z 0 [Note] InnoDB: Buffer pool(s) load completed at 200220 5:14:47
db_1 | 2020-02-20T05:14:47.111282Z 0 [Warning] 'user' entry 'root@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:47.111775Z 0 [Warning] 'user' entry 'mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:47.112039Z 0 [Warning] 'db' entry 'sys mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:47.112207Z 0 [Warning] 'proxies_priv' entry '@ root@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:47.113634Z 0 [Warning] 'tables_priv' entry 'sys_config mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:47.119378Z 0 [Note] Event Scheduler: Loaded 0 events
db_1 | 2020-02-20T05:14:47.119993Z 0 [Note] mysqld: ready for connections.
db_1 | Version: '5.7.18' socket: '/var/run/mysqld/mysqld.sock' port: 0 MySQL Community Server (GPL)
db_1 | 2020-02-20T05:14:47.120332Z 0 [Note] Executing 'SELECT \* FROM INFORMATION_SCHEMA.TABLES;' to get a list of tables using the deprecated partition engine. You may use the startup option '--disable-partition-engine-check' to skip this check.
db_1 | 2020-02-20T05:14:47.120495Z 0 [Note] Beginning of list of non-natively partitioned tables
db_1 | 2020-02-20T05:14:47.130824Z 0 [Note] End of list of non-natively partitioned tables
db_1 | Warning: Unable to load '/usr/share/zoneinfo/iso3166.tab' as time zone. Skipping it.
db_1 | Warning: Unable to load '/usr/share/zoneinfo/leap-seconds.list' as time zone. Skipping it.
db_1 | Warning: Unable to load '/usr/share/zoneinfo/zone.tab' as time zone. Skipping it.
db_1 | 2020-02-20T05:14:49.472193Z 5 [Warning] 'user' entry 'root@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:49.472757Z 5 [Warning] 'user' entry 'mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:49.473202Z 5 [Warning] 'db' entry 'sys mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:49.473488Z 5 [Warning] 'proxies_priv' entry '@ root@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:49.473824Z 5 [Warning] 'tables_priv' entry 'sys_config mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 |
db_1 | 2020-02-20T05:14:49.477084Z 0 [Note] Giving 0 client threads a chance to die gracefully
db_1 | 2020-02-20T05:14:49.477419Z 0 [Note] Shutting down slave threads
db_1 | 2020-02-20T05:14:49.477678Z 0 [Note] Forcefully disconnecting 0 remaining clients
db_1 | 2020-02-20T05:14:49.477922Z 0 [Note] Event Scheduler: Purging the queue. 0 events
db_1 | 2020-02-20T05:14:49.478204Z 0 [Note] Binlog end
db_1 | 2020-02-20T05:14:49.479216Z 0 [Note] Shutting down plugin 'ngram'
db_1 | 2020-02-20T05:14:49.479504Z 0 [Note] Shutting down plugin 'BLACKHOLE'
db_1 | 2020-02-20T05:14:49.479756Z 0 [Note] Shutting down plugin 'partition'
db_1 | 2020-02-20T05:14:49.480020Z 0 [Note] Shutting down plugin 'ARCHIVE'
db_1 | 2020-02-20T05:14:49.480257Z 0 [Note] Shutting down plugin 'INNODB_SYS_VIRTUAL'
db_1 | 2020-02-20T05:14:49.480490Z 0 [Note] Shutting down plugin 'INNODB_SYS_DATAFILES'
db_1 | 2020-02-20T05:14:49.480732Z 0 [Note] Shutting down plugin 'INNODB_SYS_TABLESPACES'
db_1 | 2020-02-20T05:14:49.480946Z 0 [Note] Shutting down plugin 'INNODB_SYS_FOREIGN_COLS'
db_1 | 2020-02-20T05:14:49.481227Z 0 [Note] Shutting down plugin 'INNODB_SYS_FOREIGN'
db_1 | 2020-02-20T05:14:49.481470Z 0 [Note] Shutting down plugin 'INNODB_SYS_FIELDS'
db_1 | 2020-02-20T05:14:49.481688Z 0 [Note] Shutting down plugin 'INNODB_SYS_COLUMNS'
db_1 | 2020-02-20T05:14:49.481913Z 0 [Note] Shutting down plugin 'INNODB_SYS_INDEXES'
db_1 | 2020-02-20T05:14:49.482115Z 0 [Note] Shutting down plugin 'INNODB_SYS_TABLESTATS'
db_1 | 2020-02-20T05:14:49.482310Z 0 [Note] Shutting down plugin 'INNODB_SYS_TABLES'
db_1 | 2020-02-20T05:14:49.482519Z 0 [Note] Shutting down plugin 'INNODB_FT_INDEX_TABLE'
db_1 | 2020-02-20T05:14:49.482715Z 0 [Note] Shutting down plugin 'INNODB_FT_INDEX_CACHE'
db_1 | 2020-02-20T05:14:49.482899Z 0 [Note] Shutting down plugin 'INNODB_FT_CONFIG'
db_1 | 2020-02-20T05:14:49.483111Z 0 [Note] Shutting down plugin 'INNODB_FT_BEING_DELETED'
db_1 | 2020-02-20T05:14:49.483361Z 0 [Note] Shutting down plugin 'INNODB_FT_DELETED'
db_1 | 2020-02-20T05:14:49.483575Z 0 [Note] Shutting down plugin 'INNODB_FT_DEFAULT_STOPWORD'
db_1 | 2020-02-20T05:14:49.483791Z 0 [Note] Shutting down plugin 'INNODB_METRICS'
db_1 | 2020-02-20T05:14:49.483858Z 0 [Note] Shutting down plugin 'INNODB_TEMP_TABLE_INFO'
db_1 | 2020-02-20T05:14:49.483865Z 0 [Note] Shutting down plugin 'INNODB_BUFFER_POOL_STATS'
db_1 | 2020-02-20T05:14:49.483869Z 0 [Note] Shutting down plugin 'INNODB_BUFFER_PAGE_LRU'
db_1 | 2020-02-20T05:14:49.483871Z 0 [Note] Shutting down plugin 'INNODB_BUFFER_PAGE'
db_1 | 2020-02-20T05:14:49.483874Z 0 [Note] Shutting down plugin 'INNODB_CMP_PER_INDEX_RESET'
db_1 | 2020-02-20T05:14:49.483877Z 0 [Note] Shutting down plugin 'INNODB_CMP_PER_INDEX'
db_1 | 2020-02-20T05:14:49.483880Z 0 [Note] Shutting down plugin 'INNODB_CMPMEM_RESET'
db_1 | 2020-02-20T05:14:49.483883Z 0 [Note] Shutting down plugin 'INNODB_CMPMEM'
db_1 | 2020-02-20T05:14:49.483886Z 0 [Note] Shutting down plugin 'INNODB_CMP_RESET'
db_1 | 2020-02-20T05:14:49.483888Z 0 [Note] Shutting down plugin 'INNODB_CMP'
db_1 | 2020-02-20T05:14:49.483891Z 0 [Note] Shutting down plugin 'INNODB_LOCK_WAITS'
db_1 | 2020-02-20T05:14:49.483894Z 0 [Note] Shutting down plugin 'INNODB_LOCKS'
db_1 | 2020-02-20T05:14:49.483897Z 0 [Note] Shutting down plugin 'INNODB_TRX'
db_1 | 2020-02-20T05:14:49.484584Z 0 [Note] Shutting down plugin 'InnoDB'
db_1 | 2020-02-20T05:14:49.484768Z 0 [Note] InnoDB: FTS optimize thread exiting.
db_1 | 2020-02-20T05:14:49.485504Z 0 [Note] InnoDB: Starting shutdown...
db_1 | 2020-02-20T05:14:49.586188Z 0 [Note] InnoDB: Dumping buffer pool(s) to /var/lib/mysql/ib_buffer_pool
db_1 | 2020-02-20T05:14:49.586498Z 0 [Note] InnoDB: Buffer pool(s) dump completed at 200220 5:14:49
db_1 | 2020-02-20T05:14:51.107157Z 0 [Note] InnoDB: Shutdown completed; log sequence number 12139844
db_1 | 2020-02-20T05:14:51.109244Z 0 [Note] InnoDB: Removed temporary tablespace data file: "ibtmp1"
db_1 | 2020-02-20T05:14:51.109682Z 0 [Note] Shutting down plugin 'MRG_MYISAM'
db_1 | 2020-02-20T05:14:51.109881Z 0 [Note] Shutting down plugin 'MyISAM'
db_1 | 2020-02-20T05:14:51.110043Z 0 [Note] Shutting down plugin 'CSV'
db_1 | 2020-02-20T05:14:51.110192Z 0 [Note] Shutting down plugin 'MEMORY'
db_1 | 2020-02-20T05:14:51.110360Z 0 [Note] Shutting down plugin 'PERFORMANCE_SCHEMA'
db_1 | 2020-02-20T05:14:51.110527Z 0 [Note] Shutting down plugin 'sha256_password'
db_1 | 2020-02-20T05:14:51.110817Z 0 [Note] Shutting down plugin 'mysql_native_password'
db_1 | 2020-02-20T05:14:51.111183Z 0 [Note] Shutting down plugin 'binlog'
db_1 | 2020-02-20T05:14:51.112879Z 0 [Note] mysqld: Shutdown complete
db_1 |
db_1 |
db_1 | MySQL init process done. Ready for start up.
db_1 |
db_1 | 2020-02-20T05:14:51.347377Z 0 [Warning] TIMESTAMP with implicit DEFAULT value is deprecated. Please use --explicit_defaults_for_timestamp server option (see documentation for more details).
db_1 | 2020-02-20T05:14:51.349233Z 0 [Note] mysqld (mysqld 5.7.18) starting as process 1 ...
db_1 | 2020-02-20T05:14:51.354711Z 0 [Note] InnoDB: PUNCH HOLE support available
db_1 | 2020-02-20T05:14:51.355240Z 0 [Note] InnoDB: Mutexes and rw_locks use GCC atomic builtins
db_1 | 2020-02-20T05:14:51.355517Z 0 [Note] InnoDB: Uses event mutexes
db_1 | 2020-02-20T05:14:51.355714Z 0 [Note] InnoDB: GCC builtin **atomic_thread_fence() is used for memory barrier
db_1 | 2020-02-20T05:14:51.355973Z 0 [Note] InnoDB: Compressed tables use zlib 1.2.3
db_1 | 2020-02-20T05:14:51.356393Z 0 [Note] InnoDB: Using Linux native AIO
db_1 | 2020-02-20T05:14:51.356959Z 0 [Note] InnoDB: Number of pools: 1
db_1 | 2020-02-20T05:14:51.357555Z 0 [Note] InnoDB: Using CPU crc32 instructions
db_1 | 2020-02-20T05:14:51.359738Z 0 [Note] InnoDB: Initializing buffer pool, total size = 128M, instances = 1, chunk size = 128M
db_1 | 2020-02-20T05:14:51.368576Z 0 [Note] InnoDB: Completed initialization of buffer pool
db_1 | 2020-02-20T05:14:51.371681Z 0 [Note] InnoDB: If the mysqld execution user is authorized, page cleaner thread priority can be changed. See the man page of setpriority().
db_1 | 2020-02-20T05:14:51.384315Z 0 [Note] InnoDB: Highest supported file format is Barracuda.
db_1 | 2020-02-20T05:14:51.402109Z 0 [Note] InnoDB: Creating shared tablespace for temporary tables
db_1 | 2020-02-20T05:14:51.402660Z 0 [Note] InnoDB: Setting file './ibtmp1' size to 12 MB. Physically writing the file full; Please wait ...
db_1 | 2020-02-20T05:14:51.443398Z 0 [Note] InnoDB: File './ibtmp1' size is now 12 MB.
db_1 | 2020-02-20T05:14:51.444822Z 0 [Note] InnoDB: 96 redo rollback segment(s) found. 96 redo rollback segment(s) are active.
db_1 | 2020-02-20T05:14:51.445277Z 0 [Note] InnoDB: 32 non-redo rollback segment(s) are active.
db_1 | 2020-02-20T05:14:51.445933Z 0 [Note] InnoDB: Waiting for purge to start
db_1 | 2020-02-20T05:14:51.496440Z 0 [Note] InnoDB: 5.7.18 started; log sequence number 12139844
db_1 | 2020-02-20T05:14:51.497279Z 0 [Note] Plugin 'FEDERATED' is disabled.
db_1 | 2020-02-20T05:14:51.503689Z 0 [Note] Found ca.pem, server-cert.pem and server-key.pem in data directory. Trying to enable SSL support using them.
db_1 | 2020-02-20T05:14:51.504493Z 0 [Warning] CA certificate ca.pem is self signed.
db_1 | 2020-02-20T05:14:51.504281Z 0 [Note] InnoDB: Loading buffer pool(s) from /var/lib/mysql/ib_buffer_pool
db_1 | 2020-02-20T05:14:51.508393Z 0 [Note] Server hostname (bind-address): '_'; port: 3306
db_1 | 2020-02-20T05:14:51.510470Z 0 [Note] IPv6 is available.
db_1 | 2020-02-20T05:14:51.510771Z 0 [Note] - '::' resolves to '::';
db_1 | 2020-02-20T05:14:51.511020Z 0 [Note] Server socket created on IP: '::'.
db_1 | 2020-02-20T05:14:51.512269Z 0 [Note] InnoDB: Buffer pool(s) load completed at 200220 5:14:51
db_1 | 2020-02-20T05:14:51.517597Z 0 [Warning] 'user' entry 'root@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:51.518070Z 0 [Warning] 'user' entry 'mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:51.518345Z 0 [Warning] 'db' entry 'sys mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:51.518590Z 0 [Warning] 'proxies_priv' entry '@ root@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:51.521440Z 0 [Warning] 'tables_priv' entry 'sys_config mysql.sys@localhost' ignored in --skip-name-resolve mode.
db_1 | 2020-02-20T05:14:51.527534Z 0 [Note] Event Scheduler: Loaded 0 events
db_1 | 2020-02-20T05:14:51.528182Z 0 [Note] mysqld: ready for connections.
db_1 | Version: '5.7.18' socket: '/var/run/mysqld/mysqld.sock' port: 3306 MySQL Community Server (GPL)
db_1 | 2020-02-20T05:14:51.528591Z 0 [Note] Executing 'SELECT _ FROM INFORMATION_SCHEMA.TABLES;' to get a list of tables using the deprecated partition engine. You may use the startup option '--disable-partition-engine-check' to skip this check.
db_1 | 2020-02-20T05:14:51.528890Z 0 [Note] Beginning of list of non-natively partitioned tables
db_1 | 2020-02-20T05:14:51.540657Z 0 [Note] End of list of non-natively partitioned tables
^CGracefully stopping... (press Ctrl+C again to force)
Stopping apptest_db_1 ... done
root@dockserver:~/apptest/docker/app# docker-compose down
Removing apptest_web_1 ... done
Removing apptest_app_1 ... done
Removing apptest_db_1 ... done
Removing network apptest_default
root@dockserver:~/apptest/docker/app# docker-compose build
db uses an image, skipping
Building app
Step 1/24 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/24 : RUN apk update
---> Using cache
---> 2c91986587cc
Step 3/24 : RUN apk add nodejs
---> Using cache
---> 4eeafaa96fd6
Step 4/24 : ADD Gemfile Gemfile
---> Using cache
---> 49729789fc8c
Step 5/24 : ADD Gemfile.lock Gemfile.lock
---> Using cache
---> d0cdf801747b
Step 6/24 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Using cache
---> 45fa50662b11
Step 7/24 : RUN gem install bundler:2.1.4
---> Using cache
---> be0891857b89
Step 8/24 : RUN apk add --no-cache build-base
---> Using cache
---> d47967cf0bc3
Step 9/24 : RUN gem install mysql2
---> Using cache
---> b4b0fe088108
Step 10/24 : RUN gem install ffi
---> Using cache
---> 3ab8f0f2609c
Step 11/24 : RUN gem install nokogiri
---> Using cache
---> d8ebe7ff0ca2
Step 12/24 : RUN bundle install
---> Using cache
---> 764763402f13
Step 13/24 : ENV RAILS_ROOT ./apptest
---> Using cache
---> 3898210909b1
Step 14/24 : COPY . /apptest
---> Using cache
---> 64281cd86fdc
Step 15/24 : RUN mkdir -p $RAILS_ROOT
 ---> Using cache
 ---> 63baa65affa4
Step 16/24 : WORKDIR $RAILS_ROOT
---> Using cache
---> cf29a3b91a19
Step 17/24 : ENV RAILS_ENV='production'
---> Using cache
---> 978e719b5e27
Step 18/24 : ENV RACK_ENV='production'
---> Using cache
---> 47c037faad28
Step 19/24 : ENV PORT 3000
---> Using cache
---> d127b1da8e0e
Step 20/24 : COPY Gemfile Gemfile
---> Using cache
---> e0253230169a
Step 21/24 : COPY Gemfile.lock Gemfile.lock
---> Using cache
---> e87db2b65a01
Step 22/24 : COPY . .
---> Using cache
---> 07204049d18d
Step 23/24 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Using cache
---> 07483c94dc4f
Step 24/24 : EXPOSE 3000
---> Using cache
---> e84ed2a6a3fb
Successfully built e84ed2a6a3fb
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Using cache
---> 5c3f0cdd8127
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Using cache
---> 6b15004829b8
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Using cache
 ---> 4090a6f3b9f1
Step 5/9 : RUN mkdir log
 ---> Using cache
 ---> b461f916c2a0
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> Using cache
 ---> 3e9d6bdd15f4
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Using cache
---> 0b6276d8f270
Step 8/9 : EXPOSE 80
---> Using cache
---> 2ad3563fb90d
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Using cache
---> 5338e7d50868
Successfully built 5338e7d50868
Successfully tagged apptest_web:latest
root@dockserver:~/apptest/docker/app# docker-compose build --no-cache
db uses an image, skipping
Building app
Step 1/24 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/24 : RUN apk update
---> Running in d333f78d9e20
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
Removing intermediate container d333f78d9e20
---> 7da7eeaa4694
Step 3/24 : RUN apk add nodejs
---> Running in 1bed143d01fc
(1/4) Installing c-ares (1.15.0-r0)
(2/4) Installing nghttp2-libs (1.40.0-r0)
(3/4) Installing libuv (1.34.0-r0)
(4/4) Installing nodejs (12.15.0-r1)
Executing busybox-1.31.1-r9.trigger
OK: 54 MiB in 41 packages
Removing intermediate container 1bed143d01fc
---> 9363ed25a642
Step 4/24 : ADD Gemfile Gemfile
---> 77566c9f4013
Step 5/24 : ADD Gemfile.lock Gemfile.lock
---> c146a3d0a737
Step 6/24 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Running in a1869a4ad467
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
(1/89) Installing bash (5.0.11-r1)
Executing bash-5.0.11-r1.post-install
(2/89) Installing binutils (2.33.1-r0)
(3/89) Installing libmagic (5.37-r1)
(4/89) Installing file (5.37-r1)
(5/89) Installing isl (0.18-r0)
(6/89) Installing libgomp (9.2.0-r3)
(7/89) Installing libatomic (9.2.0-r3)
(8/89) Installing mpfr4 (4.0.2-r1)
(9/89) Installing mpc1 (1.1.0-r1)
(10/89) Installing gcc (9.2.0-r3)
(11/89) Installing musl-dev (1.1.24-r0)
(12/89) Installing libc-dev (0.7.2-r0)
(13/89) Installing g++ (9.2.0-r3)
(14/89) Installing make (4.2.1-r2)
(15/89) Installing fortify-headers (1.1-r0)
(16/89) Installing build-base (0.5-r1)
(17/89) Installing libcurl (7.67.0-r0)
(18/89) Installing expat (2.2.9-r1)
(19/89) Installing pcre2 (10.34-r1)
(20/89) Installing git (2.24.1-r0)
(21/89) Installing libxau (1.0.9-r0)
(22/89) Installing libbsd (0.10.0-r0)
(23/89) Installing libxdmcp (1.1.3-r0)
(24/89) Installing libxcb (1.13.1-r0)
(25/89) Installing libx11 (1.6.9-r0)
(26/89) Installing libxext (1.3.4-r0)
(27/89) Installing libbz2 (1.0.8-r1)
(28/89) Installing libpng (1.6.37-r1)
(29/89) Installing freetype (2.10.1-r0)
(30/89) Installing libuuid (2.34-r1)
(31/89) Installing fontconfig (2.13.1-r2)
(32/89) Installing lcms2 (2.9-r1)
(33/89) Installing libltdl (2.4.6-r7)
(34/89) Installing xz-libs (5.2.4-r0)
(35/89) Installing libxml2 (2.9.10-r2)
(36/89) Installing imagemagick-libs (7.0.9.7-r0)
(37/89) Installing libxrender (0.9.10-r3)
(38/89) Installing pixman (0.38.4-r0)
(39/89) Installing cairo (1.16.0-r2)
(40/89) Installing libblkid (2.34-r1)
(41/89) Installing libmount (2.34-r1)
(42/89) Installing pcre (8.43-r0)
(43/89) Installing glib (2.62.4-r0)
(44/89) Installing dbus-libs (1.12.16-r2)
(45/89) Installing avahi-libs (0.7-r4)
(46/89) Installing nettle (3.5.1-r0)
(47/89) Installing p11-kit (0.23.18.1-r0)
(48/89) Installing libtasn1 (4.15.0-r0)
(49/89) Installing libunistring (0.9.10-r0)
(50/89) Installing gnutls (3.6.10-r0)
(51/89) Installing cups-libs (2.2.12-r1)
(52/89) Installing jbig2dec (0.17-r0)
(53/89) Installing libjpeg-turbo (2.0.4-r0)
(54/89) Installing tiff (4.1.0-r0)
(55/89) Installing ghostscript (9.50-r0)
(56/89) Installing libde265 (1.0.3-r0)
(57/89) Installing x265-libs (3.2.1-r0)
(58/89) Installing libheif (1.6.0-r0)
(59/89) Installing libcroco (0.6.13-r1)
(60/89) Installing shared-mime-info (1.15-r0)
(61/89) Installing gdk-pixbuf (2.40.0-r0)
(62/89) Installing libxft (2.3.3-r0)
(63/89) Installing fribidi (1.0.8-r0)
(64/89) Installing graphite2 (1.3.13-r1)
(65/89) Installing harfbuzz (2.6.4-r0)
(66/89) Installing pango (1.44.7-r0)
(67/89) Installing librsvg (2.46.4-r0)
(68/89) Installing libwebp (1.0.3-r0)
(69/89) Installing imagemagick (7.0.9.7-r0)
(70/89) Installing mariadb-common (10.4.12-r0)
(71/89) Installing libaio (0.3.112-r1)
(72/89) Installing linux-pam (1.3.1-r1)
(73/89) Installing mariadb (10.4.12-r0)
Executing mariadb-10.4.12-r0.pre-install
(74/89) Installing mysql (10.4.12-r0)
(75/89) Installing mariadb-client (10.4.12-r0)
(76/89) Installing mysql-client (10.4.12-r0)
(77/89) Installing openssl-dev (1.1.1d-r3)
(78/89) Installing mariadb-connector-c (3.1.6-r0)
(79/89) Installing mariadb-connector-c-dev (3.1.6-r0)
(80/89) Installing mariadb-embedded (10.4.12-r0)
(81/89) Installing mariadb-dev (10.4.12-r0)
(82/89) Installing openssh-keygen (8.1_p1-r0)
(83/89) Installing libedit (20191211.3.1-r0)
(84/89) Installing openssh-client (8.1_p1-r0)
(85/89) Installing openssh-sftp-server (8.1_p1-r0)
(86/89) Installing openssh-server-common (8.1_p1-r0)
(87/89) Installing openssh-server (8.1_p1-r0)
(88/89) Installing openssh (8.1_p1-r0)
(89/89) Installing tzdata (2019c-r0)
Executing busybox-1.31.1-r9.trigger
Executing fontconfig-2.13.1-r2.trigger
Executing shared-mime-info-1.15-r0.trigger
Executing gdk-pixbuf-2.40.0-r0.trigger
OK: 522 MiB in 130 packages
Removing intermediate container a1869a4ad467
---> 98e5ddeebdb6
Step 7/24 : RUN gem install bundler:2.1.4
---> Running in e50b3d96ab8e
Successfully installed bundler-2.1.4
1 gem installed
Removing intermediate container e50b3d96ab8e
---> 6c0097104f77
Step 8/24 : RUN apk add --no-cache build-base
---> Running in 1bade0891b52
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
OK: 522 MiB in 130 packages
Removing intermediate container 1bade0891b52
---> 23f9a81fbd92
Step 9/24 : RUN gem install mysql2
---> Running in abcbc7d9f997
Building native extensions. This could take a while...
Successfully installed mysql2-0.5.3
1 gem installed
Removing intermediate container abcbc7d9f997
---> dbf878ef9bbd
Step 10/24 : RUN gem install ffi
---> Running in d07cdd6201a9
Building native extensions. This could take a while...
Successfully installed ffi-1.12.2
1 gem installed
Removing intermediate container d07cdd6201a9
---> c28b31c899c6
Step 11/24 : RUN gem install nokogiri
---> Running in be510689c7e2
Successfully installed mini_portile2-2.4.0
Building native extensions. This could take a while...
Successfully installed nokogiri-1.10.8
2 gems installed
Removing intermediate container be510689c7e2
---> 3823fcf8d5a8
Step 12/24 : RUN bundle install
---> Running in a5caba5ee7e0
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/............
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Fetching rake 12.3.3
Installing rake 12.3.3
Fetching concurrent-ruby 1.1.6
Installing concurrent-ruby 1.1.6
Fetching i18n 1.6.0
Installing i18n 1.6.0
Fetching minitest 5.12.2
Installing minitest 5.12.2
Fetching thread_safe 0.3.6
Installing thread_safe 0.3.6
Fetching tzinfo 1.2.5
Installing tzinfo 1.2.5
Fetching activesupport 5.2.3
Installing activesupport 5.2.3
Fetching builder 3.2.3
Installing builder 3.2.3
Fetching erubi 1.9.0
Installing erubi 1.9.0
Using mini_portile2 2.4.0
Fetching nokogiri 1.10.4
Installing nokogiri 1.10.4 with native extensions
Fetching rails-dom-testing 2.0.3
Installing rails-dom-testing 2.0.3
Fetching crass 1.0.4
Installing crass 1.0.4
Fetching loofah 2.3.0
Installing loofah 2.3.0
Fetching rails-html-sanitizer 1.2.0
Installing rails-html-sanitizer 1.2.0
Fetching actionview 5.2.3
Installing actionview 5.2.3
Fetching rack 2.0.7
Installing rack 2.0.7
Fetching rack-test 1.1.0
Installing rack-test 1.1.0
Fetching actionpack 5.2.3
Installing actionpack 5.2.3
Fetching nio4r 2.5.2
Installing nio4r 2.5.2 with native extensions
Fetching websocket-extensions 0.1.4
Installing websocket-extensions 0.1.4
Fetching websocket-driver 0.7.1
Installing websocket-driver 0.7.1 with native extensions
Fetching actioncable 5.2.3
Installing actioncable 5.2.3
Fetching globalid 0.4.2
Installing globalid 0.4.2
Fetching activejob 5.2.3
Installing activejob 5.2.3
Fetching mini_mime 1.0.2
Installing mini_mime 1.0.2
Fetching mail 2.7.1
Installing mail 2.7.1
Fetching actionmailer 5.2.3
Installing actionmailer 5.2.3
Fetching activemodel 5.2.3
Installing activemodel 5.2.3
Fetching arel 9.0.0
Installing arel 9.0.0
Fetching activerecord 5.2.3
Installing activerecord 5.2.3
Fetching mimemagic 0.3.3
Installing mimemagic 0.3.3
Fetching marcel 0.3.3
Installing marcel 0.3.3
Fetching activestorage 5.2.3
Installing activestorage 5.2.3
Fetching public_suffix 4.0.1
Installing public_suffix 4.0.1
Fetching addressable 2.7.0
Installing addressable 2.7.0
Fetching io-like 0.3.0
Installing io-like 0.3.0
Fetching archive-zip 0.12.0
Installing archive-zip 0.12.0
Fetching bindex 0.8.1
Installing bindex 0.8.1 with native extensions
Fetching msgpack 1.3.1
Installing msgpack 1.3.1 with native extensions
Fetching bootsnap 1.4.5
Installing bootsnap 1.4.5 with native extensions
Using bundler 2.1.4
Fetching byebug 11.0.1
Installing byebug 11.0.1 with native extensions
Fetching regexp_parser 1.6.0
Installing regexp_parser 1.6.0
Fetching xpath 3.2.0
Installing xpath 3.2.0
Fetching capybara 3.29.0
Installing capybara 3.29.0
Fetching childprocess 2.0.0
Installing childprocess 2.0.0 with native extensions
Fetching chromedriver-helper 2.1.1
Installing chromedriver-helper 2.1.1
Fetching coffee-script-source 1.12.2
Installing coffee-script-source 1.12.2
Fetching execjs 2.7.0
Installing execjs 2.7.0
Fetching coffee-script 2.4.1
Installing coffee-script 2.4.1
Fetching method_source 0.9.2
Installing method_source 0.9.2
Fetching thor 1.0.1
Installing thor 1.0.1
Fetching railties 5.2.3
Installing railties 5.2.3
Fetching coffee-rails 4.2.2
Installing coffee-rails 4.2.2
Fetching ffi 1.11.1
Installing ffi 1.11.1 with native extensions
Fetching jbuilder 2.9.1
Installing jbuilder 2.9.1
Fetching rb-fsevent 0.10.3
Installing rb-fsevent 0.10.3
Fetching rb-inotify 0.10.0
Installing rb-inotify 0.10.0
Fetching ruby_dep 1.5.0
Installing ruby_dep 1.5.0
Fetching listen 3.1.5
Installing listen 3.1.5
Using mysql2 0.5.3
Fetching puma 3.12.1
Installing puma 3.12.1 with native extensions
Fetching sprockets 3.7.2
Installing sprockets 3.7.2
Fetching sprockets-rails 3.2.1
Installing sprockets-rails 3.2.1
Fetching rails 5.2.3
Installing rails 5.2.3
Fetching rubyzip 1.2.4
Installing rubyzip 1.2.4
Fetching sass-listen 4.0.0
Installing sass-listen 4.0.0
Fetching sass 3.7.4
Installing sass 3.7.4
Fetching tilt 2.0.10
Installing tilt 2.0.10
Fetching sass-rails 5.1.0
Installing sass-rails 5.1.0
Fetching selenium-webdriver 3.142.4
Installing selenium-webdriver 3.142.4
Fetching turbolinks-source 5.2.0
Installing turbolinks-source 5.2.0
Fetching turbolinks 5.2.1
Installing turbolinks 5.2.1
Fetching uglifier 4.2.0
Installing uglifier 4.2.0
Fetching web-console 3.7.0
Installing web-console 3.7.0
Bundle complete! 16 Gemfile dependencies, 76 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0

Post-install message from chromedriver-helper:

+--------------------------------------------------------------------+
| |
| NOTICE: chromedriver-helper is deprecated after 2019-03-31. |
| |
| Please update to use the 'webdrivers' gem instead. |
| See https://github.com/flavorjones/chromedriver-helper/issues/83 |
| |
+--------------------------------------------------------------------+

Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

- If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

- If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

- For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Removing intermediate container a5caba5ee7e0
---> 9b7e78633a2a
Step 13/24 : ENV RAILS_ROOT ./apptest
---> Running in 1b2977009fbe
Removing intermediate container 1b2977009fbe
---> 4c0d547311d0
Step 14/24 : COPY . /apptest
---> 4e9925ed16b4
Step 15/24 : RUN mkdir -p $RAILS_ROOT
 ---> Running in e22445f3f40c
Removing intermediate container e22445f3f40c
 ---> 3ce1c7da910d
Step 16/24 : WORKDIR $RAILS_ROOT
---> Running in 795467e49f55
Removing intermediate container 795467e49f55
---> 7f8b05cdea5f
Step 17/24 : ENV RAILS_ENV='production'
---> Running in 0578197d8aa8
Removing intermediate container 0578197d8aa8
---> d446b0195d90
Step 18/24 : ENV RACK_ENV='production'
---> Running in 755a3052a133
Removing intermediate container 755a3052a133
---> a206598443aa
Step 19/24 : ENV PORT 3000
---> Running in 00519381d965
Removing intermediate container 00519381d965
---> 5ef78c5d7cee
Step 20/24 : COPY Gemfile Gemfile
---> 0d609c5e1676
Step 21/24 : COPY Gemfile.lock Gemfile.lock
---> 3f7744ef4697
Step 22/24 : COPY . .
---> 4cc6795a2c1e
Step 23/24 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in c42dc2df086f
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T05:26:54.538632 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T05:26:54.539900 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T05:26:54.604793 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T05:26:54.605866 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container c42dc2df086f
---> 6851060b0edf
Step 24/24 : EXPOSE 3000
---> Running in 22d44f1238b1
Removing intermediate container 22d44f1238b1
---> a7f87b1a2aef
Successfully built a7f87b1a2aef
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Running in f02079baf7c6
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
libapr1 libaprutil1 libgdbm6
Suggested packages:
gdbm-l10n
The following NEW packages will be installed:
apache2-utils libapr1 libaprutil1 libgdbm6
0 upgraded, 4 newly installed, 0 to remove and 9 not upgraded.
Need to get 495 kB of archives.
After this operation, 1157 kB of additional disk space will be used.
Get:1 http://deb.debian.org/debian buster/main amd64 libapr1 amd64 1.6.5-1+b1 [102 kB]
Get:2 http://deb.debian.org/debian buster/main amd64 libgdbm6 amd64 1.18.1-4 [64.7 kB]
Get:3 http://deb.debian.org/debian buster/main amd64 libaprutil1 amd64 1.6.1-4 [91.8 kB]
Get:4 http://deb.debian.org/debian buster/main amd64 apache2-utils amd64 2.4.38-3+deb10u3 [236 kB]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 495 kB in 0s (22.9 MB/s)
Selecting previously unselected package libapr1:amd64.
(Reading database ... 7203 files and directories currently installed.)
Preparing to unpack .../libapr1_1.6.5-1+b1_amd64.deb ...
Unpacking libapr1:amd64 (1.6.5-1+b1) ...
Selecting previously unselected package libgdbm6:amd64.
Preparing to unpack .../libgdbm6_1.18.1-4_amd64.deb ...
Unpacking libgdbm6:amd64 (1.18.1-4) ...
Selecting previously unselected package libaprutil1:amd64.
Preparing to unpack .../libaprutil1_1.6.1-4_amd64.deb ...
Unpacking libaprutil1:amd64 (1.6.1-4) ...
Selecting previously unselected package apache2-utils.
Preparing to unpack .../apache2-utils_2.4.38-3+deb10u3_amd64.deb ...
Unpacking apache2-utils (2.4.38-3+deb10u3) ...
Setting up libapr1:amd64 (1.6.5-1+b1) ...
Setting up libgdbm6:amd64 (1.18.1-4) ...
Setting up libaprutil1:amd64 (1.6.1-4) ...
Setting up apache2-utils (2.4.38-3+deb10u3) ...
Processing triggers for libc-bin (2.28-10) ...
Removing intermediate container f02079baf7c6
---> 316c8ca77b5a
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Running in d5d6f4e76cc0
Removing intermediate container d5d6f4e76cc0
---> 0250287866c7
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Running in 1db06e882bcf
Removing intermediate container 1db06e882bcf
 ---> 8fdd29fa0dcd
Step 5/9 : RUN mkdir log
 ---> Running in 64211d0ee76a
Removing intermediate container 64211d0ee76a
 ---> 8406e24dd95e
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> cffadca2f0ac
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Running in a963b69599ed
Removing intermediate container a963b69599ed
---> a0dcbe4149c7
Step 8/9 : EXPOSE 80
---> Running in 317e02337ace
Removing intermediate container 317e02337ace
---> 4c61be3afbe2
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Running in d71167ac81c3
Removing intermediate container d71167ac81c3
---> 264bd4155d72
Successfully built 264bd4155d72
Successfully tagged apptest_web:latest
root@dockserver:~/apptest/docker/app# packet_write_wait: Connection to 157.245.211.227 port 22: Broken pipe
imac-de-william:apptest williamromero\$ ssh root@157.245.211.227
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 4.15.0-66-generic x86_64)

- Documentation: https://help.ubuntu.com
- Management: https://landscape.canonical.com
- Support: https://ubuntu.com/advantage

System information as of Thu Feb 20 06:04:27 UTC 2020

System load: 0.0 Users logged in: 1
Usage of /: 45.2% of 24.06GB IP address for eth0: 157.245.211.227
Memory usage: 21% IP address for eth1: 10.132.7.149
Swap usage: 0% IP address for docker0: 172.17.0.1
Processes: 89

105 packages can be updated.
58 updates are security updates.

Last login: Thu Feb 20 04:09:04 2020 from 190.148.52.47
root@dockserver:~# ls
apptest
root@dockserver:~# cd apptest
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# cd docker
root@dockserver:~/apptest/docker# ls
app db.env web
root@dockserver:~/apptest/docker# cd ..
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# cd config
root@dockserver:~/apptest/config# ls
application.rb cable.yml database.yml environments locales routes.rb spring.rb
boot.rb credentials.yml.enc environment.rb initializers puma.rb secrets.yml storage.yml
root@dockserver:~/apptest/config# nano puma.rb
root@dockserver:~/apptest/config# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
root@dockserver:~/apptest/config# cd ..
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# cd docker
root@dockserver:~/apptest/docker# ls
app db.env web
root@dockserver:~/apptest/docker# cd app
root@dockserver:~/apptest/docker/app# ls
Dockerfile
root@dockserver:~/apptest/docker/app# nano Dockerfile
root@dockserver:~/apptest/docker/app# cd ..
root@dockserver:~/apptest/docker# ls
app db.env web
root@dockserver:~/apptest/docker# cd ..
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# docker-compose build --no-cache
db uses an image, skipping
Building app
Step 1/25 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/25 : RUN apk update
---> Running in 5486606ae5ad
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
Removing intermediate container 5486606ae5ad
---> bb31048b5943
Step 3/25 : RUN apk add nodejs
---> Running in f9cec415bf19
(1/4) Installing c-ares (1.15.0-r0)
(2/4) Installing nghttp2-libs (1.40.0-r0)
(3/4) Installing libuv (1.34.0-r0)
(4/4) Installing nodejs (12.15.0-r1)
Executing busybox-1.31.1-r9.trigger
OK: 54 MiB in 41 packages
Removing intermediate container f9cec415bf19
---> 4c31ccc1cc36
Step 4/25 : ADD Gemfile Gemfile
---> 248009b6ff32
Step 5/25 : ADD Gemfile.lock Gemfile.lock
---> a95fee19d191
Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Running in 73022a8789b4
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main]
v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community]
OK: 11264 distinct packages available
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
(1/89) Installing bash (5.0.11-r1)
Executing bash-5.0.11-r1.post-install
(2/89) Installing binutils (2.33.1-r0)
(3/89) Installing libmagic (5.37-r1)
(4/89) Installing file (5.37-r1)
(5/89) Installing isl (0.18-r0)
(6/89) Installing libgomp (9.2.0-r3)
(7/89) Installing libatomic (9.2.0-r3)
(8/89) Installing mpfr4 (4.0.2-r1)
(9/89) Installing mpc1 (1.1.0-r1)
(10/89) Installing gcc (9.2.0-r3)
(11/89) Installing musl-dev (1.1.24-r0)
(12/89) Installing libc-dev (0.7.2-r0)
(13/89) Installing g++ (9.2.0-r3)
(14/89) Installing make (4.2.1-r2)
(15/89) Installing fortify-headers (1.1-r0)
(16/89) Installing build-base (0.5-r1)
(17/89) Installing libcurl (7.67.0-r0)
(18/89) Installing expat (2.2.9-r1)
(19/89) Installing pcre2 (10.34-r1)
(20/89) Installing git (2.24.1-r0)
(21/89) Installing libxau (1.0.9-r0)
(22/89) Installing libbsd (0.10.0-r0)
(23/89) Installing libxdmcp (1.1.3-r0)
(24/89) Installing libxcb (1.13.1-r0)
(25/89) Installing libx11 (1.6.9-r0)
(26/89) Installing libxext (1.3.4-r0)
(27/89) Installing libbz2 (1.0.8-r1)
(28/89) Installing libpng (1.6.37-r1)
(29/89) Installing freetype (2.10.1-r0)
(30/89) Installing libuuid (2.34-r1)
(31/89) Installing fontconfig (2.13.1-r2)
(32/89) Installing lcms2 (2.9-r1)
(33/89) Installing libltdl (2.4.6-r7)
(34/89) Installing xz-libs (5.2.4-r0)
(35/89) Installing libxml2 (2.9.10-r2)
(36/89) Installing imagemagick-libs (7.0.9.7-r0)
(37/89) Installing libxrender (0.9.10-r3)
(38/89) Installing pixman (0.38.4-r0)
(39/89) Installing cairo (1.16.0-r2)
(40/89) Installing libblkid (2.34-r1)
(41/89) Installing libmount (2.34-r1)
(42/89) Installing pcre (8.43-r0)
(43/89) Installing glib (2.62.4-r0)
(44/89) Installing dbus-libs (1.12.16-r2)
(45/89) Installing avahi-libs (0.7-r4)
(46/89) Installing nettle (3.5.1-r0)
(47/89) Installing p11-kit (0.23.18.1-r0)
(48/89) Installing libtasn1 (4.15.0-r0)
(49/89) Installing libunistring (0.9.10-r0)
(50/89) Installing gnutls (3.6.10-r0)
(51/89) Installing cups-libs (2.2.12-r1)
(52/89) Installing jbig2dec (0.17-r0)
(53/89) Installing libjpeg-turbo (2.0.4-r0)
(54/89) Installing tiff (4.1.0-r0)
(55/89) Installing ghostscript (9.50-r0)
(56/89) Installing libde265 (1.0.3-r0)
(57/89) Installing x265-libs (3.2.1-r0)
(58/89) Installing libheif (1.6.0-r0)
(59/89) Installing libcroco (0.6.13-r1)
(60/89) Installing shared-mime-info (1.15-r0)
(61/89) Installing gdk-pixbuf (2.40.0-r0)
(62/89) Installing libxft (2.3.3-r0)
(63/89) Installing fribidi (1.0.8-r0)
(64/89) Installing graphite2 (1.3.13-r1)
(65/89) Installing harfbuzz (2.6.4-r0)
(66/89) Installing pango (1.44.7-r0)
(67/89) Installing librsvg (2.46.4-r0)
(68/89) Installing libwebp (1.0.3-r0)
(69/89) Installing imagemagick (7.0.9.7-r0)
(70/89) Installing mariadb-common (10.4.12-r0)
(71/89) Installing libaio (0.3.112-r1)
(72/89) Installing linux-pam (1.3.1-r1)
(73/89) Installing mariadb (10.4.12-r0)
Executing mariadb-10.4.12-r0.pre-install
(74/89) Installing mysql (10.4.12-r0)
(75/89) Installing mariadb-client (10.4.12-r0)
(76/89) Installing mysql-client (10.4.12-r0)
(77/89) Installing openssl-dev (1.1.1d-r3)
(78/89) Installing mariadb-connector-c (3.1.6-r0)
(79/89) Installing mariadb-connector-c-dev (3.1.6-r0)
(80/89) Installing mariadb-embedded (10.4.12-r0)
(81/89) Installing mariadb-dev (10.4.12-r0)
(82/89) Installing openssh-keygen (8.1_p1-r0)
(83/89) Installing libedit (20191211.3.1-r0)
(84/89) Installing openssh-client (8.1_p1-r0)
(85/89) Installing openssh-sftp-server (8.1_p1-r0)
(86/89) Installing openssh-server-common (8.1_p1-r0)
(87/89) Installing openssh-server (8.1_p1-r0)
(88/89) Installing openssh (8.1_p1-r0)
(89/89) Installing tzdata (2019c-r0)
Executing busybox-1.31.1-r9.trigger
Executing fontconfig-2.13.1-r2.trigger
Executing shared-mime-info-1.15-r0.trigger
Executing gdk-pixbuf-2.40.0-r0.trigger
OK: 522 MiB in 130 packages
Removing intermediate container 73022a8789b4
---> 88b99150f987
Step 7/25 : RUN gem install bundler:2.1.4
---> Running in 816ea4a2eb1b
Successfully installed bundler-2.1.4
1 gem installed
Removing intermediate container 816ea4a2eb1b
---> 45cc9c906551
Step 8/25 : RUN apk add --no-cache build-base
---> Running in 116be0834c9b
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
OK: 522 MiB in 130 packages
Removing intermediate container 116be0834c9b
---> 3c1120c7e6a0
Step 9/25 : RUN gem install mysql2
---> Running in ac23752d6073
Building native extensions. This could take a while...
Successfully installed mysql2-0.5.3
1 gem installed
Removing intermediate container ac23752d6073
---> efc3376215ba
Step 10/25 : RUN gem install ffi
---> Running in 90ca5a7bf72e
Building native extensions. This could take a while...
Successfully installed ffi-1.12.2
1 gem installed
Removing intermediate container 90ca5a7bf72e
---> 26a792829132
Step 11/25 : RUN gem install nokogiri
---> Running in 436be1963240
Successfully installed mini_portile2-2.4.0
Building native extensions. This could take a while...
Successfully installed nokogiri-1.10.8
2 gems installed
Removing intermediate container 436be1963240
---> 6d5646e2af23
Step 12/25 : RUN bundle install
---> Running in 6bea65ad6cf1
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/............
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Fetching rake 12.3.3
Installing rake 12.3.3
Fetching concurrent-ruby 1.1.6
Installing concurrent-ruby 1.1.6
Fetching i18n 1.6.0
Installing i18n 1.6.0
Fetching minitest 5.12.2
Installing minitest 5.12.2
Fetching thread_safe 0.3.6
Installing thread_safe 0.3.6
Fetching tzinfo 1.2.5
Installing tzinfo 1.2.5
Fetching activesupport 5.2.3
Installing activesupport 5.2.3
Fetching builder 3.2.3
Installing builder 3.2.3
Fetching erubi 1.9.0
Installing erubi 1.9.0
Using mini_portile2 2.4.0
Fetching nokogiri 1.10.4
Installing nokogiri 1.10.4 with native extensions
Fetching rails-dom-testing 2.0.3
Installing rails-dom-testing 2.0.3
Fetching crass 1.0.4
Installing crass 1.0.4
Fetching loofah 2.3.0
Installing loofah 2.3.0
Fetching rails-html-sanitizer 1.2.0
Installing rails-html-sanitizer 1.2.0
Fetching actionview 5.2.3
Installing actionview 5.2.3
Fetching rack 2.0.7
Installing rack 2.0.7
Fetching rack-test 1.1.0
Installing rack-test 1.1.0
Fetching actionpack 5.2.3
Installing actionpack 5.2.3
Fetching nio4r 2.5.2
Installing nio4r 2.5.2 with native extensions
Fetching websocket-extensions 0.1.4
Installing websocket-extensions 0.1.4
Fetching websocket-driver 0.7.1
Installing websocket-driver 0.7.1 with native extensions
Fetching actioncable 5.2.3
Installing actioncable 5.2.3
Fetching globalid 0.4.2
Installing globalid 0.4.2
Fetching activejob 5.2.3
Installing activejob 5.2.3
Fetching mini_mime 1.0.2
Installing mini_mime 1.0.2
Fetching mail 2.7.1
Installing mail 2.7.1
Fetching actionmailer 5.2.3
Installing actionmailer 5.2.3
Fetching activemodel 5.2.3
Installing activemodel 5.2.3
Fetching arel 9.0.0
Installing arel 9.0.0
Fetching activerecord 5.2.3
Installing activerecord 5.2.3
Fetching mimemagic 0.3.3
Installing mimemagic 0.3.3
Fetching marcel 0.3.3
Installing marcel 0.3.3
Fetching activestorage 5.2.3
Installing activestorage 5.2.3
Fetching public_suffix 4.0.1
Installing public_suffix 4.0.1
Fetching addressable 2.7.0
Installing addressable 2.7.0
Fetching io-like 0.3.0
Installing io-like 0.3.0
Fetching archive-zip 0.12.0
Installing archive-zip 0.12.0
Fetching bindex 0.8.1
Installing bindex 0.8.1 with native extensions
Fetching msgpack 1.3.1
Installing msgpack 1.3.1 with native extensions
Fetching bootsnap 1.4.5
Installing bootsnap 1.4.5 with native extensions
Using bundler 2.1.4
Fetching byebug 11.0.1
Installing byebug 11.0.1 with native extensions
Fetching regexp_parser 1.6.0
Installing regexp_parser 1.6.0
Fetching xpath 3.2.0
Installing xpath 3.2.0
Fetching capybara 3.29.0
Installing capybara 3.29.0
Fetching childprocess 2.0.0
Installing childprocess 2.0.0 with native extensions
Fetching chromedriver-helper 2.1.1
Installing chromedriver-helper 2.1.1
Fetching coffee-script-source 1.12.2
Installing coffee-script-source 1.12.2
Fetching execjs 2.7.0
Installing execjs 2.7.0
Fetching coffee-script 2.4.1
Installing coffee-script 2.4.1
Fetching method_source 0.9.2
Installing method_source 0.9.2
Fetching thor 1.0.1
Installing thor 1.0.1
Fetching railties 5.2.3
Installing railties 5.2.3
Fetching coffee-rails 4.2.2
Installing coffee-rails 4.2.2
Fetching ffi 1.11.1
Installing ffi 1.11.1 with native extensions
Fetching jbuilder 2.9.1
Installing jbuilder 2.9.1
Fetching rb-fsevent 0.10.3
Installing rb-fsevent 0.10.3
Fetching rb-inotify 0.10.0
Installing rb-inotify 0.10.0
Fetching ruby_dep 1.5.0
Installing ruby_dep 1.5.0
Fetching listen 3.1.5
Installing listen 3.1.5
Using mysql2 0.5.3
Fetching puma 3.12.1
Installing puma 3.12.1 with native extensions
Fetching sprockets 3.7.2
Installing sprockets 3.7.2
Fetching sprockets-rails 3.2.1
Installing sprockets-rails 3.2.1
Fetching rails 5.2.3
Installing rails 5.2.3
Fetching rubyzip 1.2.4
Installing rubyzip 1.2.4
Fetching sass-listen 4.0.0
Installing sass-listen 4.0.0
Fetching sass 3.7.4
Installing sass 3.7.4
Fetching tilt 2.0.10
Installing tilt 2.0.10
Fetching sass-rails 5.1.0
Installing sass-rails 5.1.0
Fetching selenium-webdriver 3.142.4
Installing selenium-webdriver 3.142.4
Fetching turbolinks-source 5.2.0
Installing turbolinks-source 5.2.0
Fetching turbolinks 5.2.1
Installing turbolinks 5.2.1
Fetching uglifier 4.2.0
Installing uglifier 4.2.0
Fetching web-console 3.7.0
Installing web-console 3.7.0
Bundle complete! 16 Gemfile dependencies, 76 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0

Post-install message from chromedriver-helper:

+--------------------------------------------------------------------+
| |
| NOTICE: chromedriver-helper is deprecated after 2019-03-31. |
| |
| Please update to use the 'webdrivers' gem instead. |
| See https://github.com/flavorjones/chromedriver-helper/issues/83 |
| |
+--------------------------------------------------------------------+

Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

- If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

- If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

- For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Removing intermediate container 6bea65ad6cf1
---> c03f66341ee9
Step 13/25 : ENV RAILS_ROOT ./apptest
---> Running in 6980bd94249b
Removing intermediate container 6980bd94249b
---> c2c79b3a9c55
Step 14/25 : COPY . /apptest
---> 54ad3967de07
Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Running in 4540eb0432e7
Removing intermediate container 4540eb0432e7
 ---> 488b6783aee6
Step 16/25 : WORKDIR $RAILS_ROOT
---> Running in cb3d9f50bf4c
Removing intermediate container cb3d9f50bf4c
---> b311d5b3ecb2
Step 17/25 : ENV RAILS_ENV='production'
---> Running in 9a7bf52a2cb2
Removing intermediate container 9a7bf52a2cb2
---> b546b3caa8c8
Step 18/25 : ENV RACK_ENV='production'
---> Running in 3a69e147a755
Removing intermediate container 3a69e147a755
---> 77ac75dddcdf
Step 19/25 : ENV PORT 3000
---> Running in 1dab1ca749a8
Removing intermediate container 1dab1ca749a8
---> 5099716b2ea7
Step 20/25 : COPY Gemfile Gemfile
---> 7afa33b0a708
Step 21/25 : COPY Gemfile.lock Gemfile.lock
---> 624ce8911252
Step 22/25 : COPY . .
---> 526083ff23d8
Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in bc5592c1a6bd
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T06:11:45.306590 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T06:11:45.307775 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T06:11:45.373024 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T06:11:45.374170 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container bc5592c1a6bd
---> 38bf025ed4fb
Step 24/25 : EXPOSE 3000
---> Running in 7eb2c1c37421
Removing intermediate container 7eb2c1c37421
---> ff485da3e3c3
Step 25/25 : CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]
---> Running in 9a258048ddb9
Removing intermediate container 9a258048ddb9
---> 8c60cf08ba5d
Successfully built 8c60cf08ba5d
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Running in 8b8dd6a22723
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
libapr1 libaprutil1 libgdbm6
Suggested packages:
gdbm-l10n
The following NEW packages will be installed:
apache2-utils libapr1 libaprutil1 libgdbm6
0 upgraded, 4 newly installed, 0 to remove and 9 not upgraded.
Need to get 495 kB of archives.
After this operation, 1157 kB of additional disk space will be used.
Get:1 http://deb.debian.org/debian buster/main amd64 libapr1 amd64 1.6.5-1+b1 [102 kB]
Get:2 http://deb.debian.org/debian buster/main amd64 libgdbm6 amd64 1.18.1-4 [64.7 kB]
Get:3 http://deb.debian.org/debian buster/main amd64 libaprutil1 amd64 1.6.1-4 [91.8 kB]
Get:4 http://deb.debian.org/debian buster/main amd64 apache2-utils amd64 2.4.38-3+deb10u3 [236 kB]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 495 kB in 0s (22.2 MB/s)
Selecting previously unselected package libapr1:amd64.
(Reading database ... 7203 files and directories currently installed.)
Preparing to unpack .../libapr1_1.6.5-1+b1_amd64.deb ...
Unpacking libapr1:amd64 (1.6.5-1+b1) ...
Selecting previously unselected package libgdbm6:amd64.
Preparing to unpack .../libgdbm6_1.18.1-4_amd64.deb ...
Unpacking libgdbm6:amd64 (1.18.1-4) ...
Selecting previously unselected package libaprutil1:amd64.
Preparing to unpack .../libaprutil1_1.6.1-4_amd64.deb ...
Unpacking libaprutil1:amd64 (1.6.1-4) ...
Selecting previously unselected package apache2-utils.
Preparing to unpack .../apache2-utils_2.4.38-3+deb10u3_amd64.deb ...
Unpacking apache2-utils (2.4.38-3+deb10u3) ...
Setting up libapr1:amd64 (1.6.5-1+b1) ...
Setting up libgdbm6:amd64 (1.18.1-4) ...
Setting up libaprutil1:amd64 (1.6.1-4) ...
Setting up apache2-utils (2.4.38-3+deb10u3) ...
Processing triggers for libc-bin (2.28-10) ...
Removing intermediate container 8b8dd6a22723
---> cf65e2011274
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Running in 1fa3a2cbb65f
Removing intermediate container 1fa3a2cbb65f
---> 3057ddc6bb31
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Running in 71d1789b61cc
Removing intermediate container 71d1789b61cc
 ---> 55b44985e29b
Step 5/9 : RUN mkdir log
 ---> Running in 4b882910fca1
Removing intermediate container 4b882910fca1
 ---> c99c6682b2be
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> 5df400b5d1a8
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Running in da281934efe8
Removing intermediate container da281934efe8
---> 707e3ef27877
Step 8/9 : EXPOSE 80
---> Running in 331cf109293a
Removing intermediate container 331cf109293a
---> 9d9a96cf5960
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Running in 111d44e6200e
Removing intermediate container 111d44e6200e
---> 20f810128657
Successfully built 20f810128657
Successfully tagged apptest_web:latest
root@dockserver:~/apptest# docker-compose up -d
Creating network "apptest_default" with the default driver
Creating apptest_db_1 ...
Creating apptest_db_1 ... done
Creating apptest_app_1 ...
Creating apptest_app_1 ... done
Creating apptest_web_1 ...
Creating apptest_web_1 ... done
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
abc06a1853b2 apptest_web "nginx -g 'daemon of…" 3 seconds ago Up 2 seconds 0.0.0.0:80->80/tcp apptest_web_1
a42d6a3cbe8d apptest_app "bundle exec puma -C…" 5 seconds ago Up 3 seconds 0.0.0.0:3000->3000/tcp apptest_app_1
2c4e2c400165 mysql:5.7.18 "docker-entrypoint.s…" 5 seconds ago Up 4 seconds 0.0.0.0:3306->3306/tcp apptest_db_1
root@dockserver:~/apptest# docker run -it apptest_web
2020/02/20 06:13:00 [emerg] 1#1: host not found in upstream "app:3000" in /etc/nginx/conf.d/default.conf:2
nginx: [emerg] host not found in upstream "app:3000" in /etc/nginx/conf.d/default.conf:2
failed to resize tty, using default size
root@dockserver:~/apptest# docker run -it apptest_app
Puma starting in single mode...

- Version 3.12.1 (ruby 2.5.7-p206), codename: Llamas in Pajamas
- Min threads: 5, max threads: 5
- Environment: production
  ! Unable to load application: ArgumentError: Missing `secret_key_base` for 'production' environment, set this string with `rails credentials:edit`
  bundler: failed to load command: puma (/usr/local/bundle/bin/puma)
  ArgumentError: Missing `secret_key_base` for 'production' environment, set this string with `rails credentials:edit`
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:585:in `validate_secret_key_base' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:432:in`secret_key_base'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:176:in `key_generator' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:205:in`message_verifier'
  /usr/local/bundle/gems/activestorage-5.2.3/lib/active_storage/engine.rb:81:in `block (2 levels) in <class:Engine>' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:69:in`block in execute_hook'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:62:in `with_execution_control' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:67:in`execute_hook'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:52:in `block in run_load_hooks' /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:51:in`each'
  /usr/local/bundle/gems/activesupport-5.2.3/lib/active_support/lazy_load_hooks.rb:51:in `run_load_hooks' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application/finisher.rb:75:in`block in <module:Finisher>'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:32:in `instance_exec' /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:32:in`run'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:61:in `block in run_initializers' /usr/local/lib/ruby/2.5.0/tsort.rb:228:in`block in tsort_each'
  /usr/local/lib/ruby/2.5.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component' /usr/local/lib/ruby/2.5.0/tsort.rb:431:in`each_strongly_connected_component_from'
  /usr/local/lib/ruby/2.5.0/tsort.rb:349:in `block in each_strongly_connected_component' /usr/local/lib/ruby/2.5.0/tsort.rb:347:in`each'
  /usr/local/lib/ruby/2.5.0/tsort.rb:347:in `call' /usr/local/lib/ruby/2.5.0/tsort.rb:347:in`each_strongly_connected_component'
  /usr/local/lib/ruby/2.5.0/tsort.rb:226:in `tsort_each' /usr/local/lib/ruby/2.5.0/tsort.rb:205:in`tsort_each'
  /usr/local/bundle/gems/railties-5.2.3/lib/rails/initializable.rb:60:in `run_initializers' /usr/local/bundle/gems/railties-5.2.3/lib/rails/application.rb:361:in`initialize!'
  /apptest/config/environment.rb:5:in `<top (required)>' config.ru:3:in`require_relative'
  config.ru:3:in `block in <main>' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in`instance_eval'
  /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in `initialize' config.ru:in`new'
  config.ru:in `<main>' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in`eval'
  /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in `new_from_string' /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:40:in`parse_file'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/configuration.rb:320:in `load_rackup' /usr/local/bundle/gems/puma-3.12.1/lib/puma/configuration.rb:245:in`app'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/runner.rb:147:in `load_and_bind' /usr/local/bundle/gems/puma-3.12.1/lib/puma/single.rb:98:in`run'
  /usr/local/bundle/gems/puma-3.12.1/lib/puma/launcher.rb:186:in `run' /usr/local/bundle/gems/puma-3.12.1/lib/puma/cli.rb:80:in`run'
  /usr/local/bundle/gems/puma-3.12.1/bin/puma:10:in `<top (required)>' /usr/local/bundle/bin/puma:23:in`load'
  /usr/local/bundle/bin/puma:23:in `<top (required)>' root@dockserver:~/apptest# docker-compose stop Stopping apptest_web_1 ... done Stopping apptest_db_1 ... done root@dockserver:~/apptest# docker-compose down Removing apptest_web_1 ... done Removing apptest_app_1 ... done Removing apptest_db_1 ... done Removing network apptest_default root@dockserver:~/apptest# ls Gemfile README.md app config db docker lib package.json storage tmp yarn.lock Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor root@dockserver:~/apptest# cd docker root@dockserver:~/apptest/docker# ls app db.env web root@dockserver:~/apptest/docker# cd ap -bash: cd: ap: No such file or directory root@dockserver:~/apptest/docker# cd app root@dockserver:~/apptest/docker/app# ls Dockerfile root@dockserver:~/apptest/docker/app# nano Dockerfile root@dockserver:~/apptest/docker/app# docker ps CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES root@dockserver:~/apptest/docker/app# docker-compose build --no-cache db uses an image, skipping Building app Step 1/25 : FROM ruby:2.5-alpine ---> cbd297d70a23 Step 2/25 : RUN apk update ---> Running in b3781db0315f fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main] v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community] OK: 11264 distinct packages available Removing intermediate container b3781db0315f ---> e9cb5ae4e0a8 Step 3/25 : RUN apk add nodejs ---> Running in f3224d212509 (1/4) Installing c-ares (1.15.0-r0) (2/4) Installing nghttp2-libs (1.40.0-r0) (3/4) Installing libuv (1.34.0-r0) (4/4) Installing nodejs (12.15.0-r1) Executing busybox-1.31.1-r9.trigger OK: 54 MiB in 41 packages Removing intermediate container f3224d212509 ---> 123bcbba9422 Step 4/25 : ADD Gemfile Gemfile ---> ad7a4e5750ef Step 5/25 : ADD Gemfile.lock Gemfile.lock ---> 9da05b179fc8 Step 6/25 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick ---> Running in a944f6b22228 fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz v3.11.3-73-g095aa9b9d4 [http://dl-cdn.alpinelinux.org/alpine/v3.11/main] v3.11.3-74-gdd165531a7 [http://dl-cdn.alpinelinux.org/alpine/v3.11/community] OK: 11264 distinct packages available fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz (1/89) Installing bash (5.0.11-r1) Executing bash-5.0.11-r1.post-install (2/89) Installing binutils (2.33.1-r0) (3/89) Installing libmagic (5.37-r1) (4/89) Installing file (5.37-r1) (5/89) Installing isl (0.18-r0) (6/89) Installing libgomp (9.2.0-r3) (7/89) Installing libatomic (9.2.0-r3) (8/89) Installing mpfr4 (4.0.2-r1) (9/89) Installing mpc1 (1.1.0-r1) (10/89) Installing gcc (9.2.0-r3) (11/89) Installing musl-dev (1.1.24-r0) (12/89) Installing libc-dev (0.7.2-r0) (13/89) Installing g++ (9.2.0-r3) (14/89) Installing make (4.2.1-r2) (15/89) Installing fortify-headers (1.1-r0) (16/89) Installing build-base (0.5-r1) (17/89) Installing libcurl (7.67.0-r0) (18/89) Installing expat (2.2.9-r1) (19/89) Installing pcre2 (10.34-r1) (20/89) Installing git (2.24.1-r0) (21/89) Installing libxau (1.0.9-r0) (22/89) Installing libbsd (0.10.0-r0) (23/89) Installing libxdmcp (1.1.3-r0) (24/89) Installing libxcb (1.13.1-r0) (25/89) Installing libx11 (1.6.9-r0) (26/89) Installing libxext (1.3.4-r0) (27/89) Installing libbz2 (1.0.8-r1) (28/89) Installing libpng (1.6.37-r1) (29/89) Installing freetype (2.10.1-r0) (30/89) Installing libuuid (2.34-r1) (31/89) Installing fontconfig (2.13.1-r2) (32/89) Installing lcms2 (2.9-r1) (33/89) Installing libltdl (2.4.6-r7) (34/89) Installing xz-libs (5.2.4-r0) (35/89) Installing libxml2 (2.9.10-r2) (36/89) Installing imagemagick-libs (7.0.9.7-r0) (37/89) Installing libxrender (0.9.10-r3) (38/89) Installing pixman (0.38.4-r0) (39/89) Installing cairo (1.16.0-r2) (40/89) Installing libblkid (2.34-r1) (41/89) Installing libmount (2.34-r1) (42/89) Installing pcre (8.43-r0) (43/89) Installing glib (2.62.4-r0) (44/89) Installing dbus-libs (1.12.16-r2) (45/89) Installing avahi-libs (0.7-r4) (46/89) Installing nettle (3.5.1-r0) (47/89) Installing p11-kit (0.23.18.1-r0) (48/89) Installing libtasn1 (4.15.0-r0) (49/89) Installing libunistring (0.9.10-r0) (50/89) Installing gnutls (3.6.10-r0) (51/89) Installing cups-libs (2.2.12-r1) (52/89) Installing jbig2dec (0.17-r0) (53/89) Installing libjpeg-turbo (2.0.4-r0) (54/89) Installing tiff (4.1.0-r0) (55/89) Installing ghostscript (9.50-r0) (56/89) Installing libde265 (1.0.3-r0) (57/89) Installing x265-libs (3.2.1-r0) (58/89) Installing libheif (1.6.0-r0) (59/89) Installing libcroco (0.6.13-r1) (60/89) Installing shared-mime-info (1.15-r0) (61/89) Installing gdk-pixbuf (2.40.0-r0) (62/89) Installing libxft (2.3.3-r0) (63/89) Installing fribidi (1.0.8-r0) (64/89) Installing graphite2 (1.3.13-r1) (65/89) Installing harfbuzz (2.6.4-r0) (66/89) Installing pango (1.44.7-r0) (67/89) Installing librsvg (2.46.4-r0) (68/89) Installing libwebp (1.0.3-r0) (69/89) Installing imagemagick (7.0.9.7-r0) (70/89) Installing mariadb-common (10.4.12-r0) (71/89) Installing libaio (0.3.112-r1) (72/89) Installing linux-pam (1.3.1-r1) (73/89) Installing mariadb (10.4.12-r0) Executing mariadb-10.4.12-r0.pre-install (74/89) Installing mysql (10.4.12-r0) (75/89) Installing mariadb-client (10.4.12-r0) (76/89) Installing mysql-client (10.4.12-r0) (77/89) Installing openssl-dev (1.1.1d-r3) (78/89) Installing mariadb-connector-c (3.1.6-r0) (79/89) Installing mariadb-connector-c-dev (3.1.6-r0) (80/89) Installing mariadb-embedded (10.4.12-r0) (81/89) Installing mariadb-dev (10.4.12-r0) (82/89) Installing openssh-keygen (8.1_p1-r0) (83/89) Installing libedit (20191211.3.1-r0) (84/89) Installing openssh-client (8.1_p1-r0) (85/89) Installing openssh-sftp-server (8.1_p1-r0) (86/89) Installing openssh-server-common (8.1_p1-r0) (87/89) Installing openssh-server (8.1_p1-r0) (88/89) Installing openssh (8.1_p1-r0) (89/89) Installing tzdata (2019c-r0) Executing busybox-1.31.1-r9.trigger Executing fontconfig-2.13.1-r2.trigger Executing shared-mime-info-1.15-r0.trigger Executing gdk-pixbuf-2.40.0-r0.trigger OK: 522 MiB in 130 packages Removing intermediate container a944f6b22228 ---> 185dde634373 Step 7/25 : RUN gem install bundler:2.1.4 ---> Running in 191edd29fbb9 Successfully installed bundler-2.1.4 1 gem installed Removing intermediate container 191edd29fbb9 ---> 8b116d6fb1b6 Step 8/25 : RUN apk add --no-cache build-base ---> Running in cf2f26dba630 fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz OK: 522 MiB in 130 packages Removing intermediate container cf2f26dba630 ---> bccf6671d2d5 Step 9/25 : RUN gem install mysql2 ---> Running in 4a90e3d9853f Building native extensions. This could take a while... Successfully installed mysql2-0.5.3 1 gem installed Removing intermediate container 4a90e3d9853f ---> 229c48c6dee7 Step 10/25 : RUN gem install ffi ---> Running in 0e714d0cd776 Building native extensions. This could take a while... Successfully installed ffi-1.12.2 1 gem installed Removing intermediate container 0e714d0cd776 ---> 3912ee41e94d Step 11/25 : RUN gem install nokogiri ---> Running in 984c39d09e3d Successfully installed mini_portile2-2.4.0 Building native extensions. This could take a while... Successfully installed nokogiri-1.10.8 2 gems installed Removing intermediate container 984c39d09e3d ---> 105d47e8ca3f Step 12/25 : RUN bundle install ---> Running in 1fd5b639b380 The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run`bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`. Fetching gem metadata from https://rubygems.org/............ Fetching gem metadata from https://rubygems.org/. Resolving dependencies... Fetching rake 12.3.3 Installing rake 12.3.3 Fetching concurrent-ruby 1.1.6 Installing concurrent-ruby 1.1.6 Fetching i18n 1.6.0 Installing i18n 1.6.0 Fetching minitest 5.12.2 Installing minitest 5.12.2 Fetching thread_safe 0.3.6 Installing thread_safe 0.3.6 Fetching tzinfo 1.2.5 Installing tzinfo 1.2.5 Fetching activesupport 5.2.3 Installing activesupport 5.2.3 Fetching builder 3.2.3 Installing builder 3.2.3 Fetching erubi 1.9.0 Installing erubi 1.9.0 Using mini_portile2 2.4.0 Fetching nokogiri 1.10.4 Installing nokogiri 1.10.4 with native extensions Fetching rails-dom-testing 2.0.3 Installing rails-dom-testing 2.0.3 Fetching crass 1.0.4 Installing crass 1.0.4 Fetching loofah 2.3.0 Installing loofah 2.3.0 Fetching rails-html-sanitizer 1.2.0 Installing rails-html-sanitizer 1.2.0 Fetching actionview 5.2.3 Installing actionview 5.2.3 Fetching rack 2.0.7 Installing rack 2.0.7 Fetching rack-test 1.1.0 Installing rack-test 1.1.0 Fetching actionpack 5.2.3 Installing actionpack 5.2.3 Fetching nio4r 2.5.2 Installing nio4r 2.5.2 with native extensions Fetching websocket-extensions 0.1.4 Installing websocket-extensions 0.1.4 Fetching websocket-driver 0.7.1 Installing websocket-driver 0.7.1 with native extensions Fetching actioncable 5.2.3 Installing actioncable 5.2.3 Fetching globalid 0.4.2 Installing globalid 0.4.2 Fetching activejob 5.2.3 Installing activejob 5.2.3 Fetching mini_mime 1.0.2 Installing mini_mime 1.0.2 Fetching mail 2.7.1 Installing mail 2.7.1 Fetching actionmailer 5.2.3 Installing actionmailer 5.2.3 Fetching activemodel 5.2.3 Installing activemodel 5.2.3 Fetching arel 9.0.0 Installing arel 9.0.0 Fetching activerecord 5.2.3 Installing activerecord 5.2.3 Fetching mimemagic 0.3.3 Installing mimemagic 0.3.3 Fetching marcel 0.3.3 Installing marcel 0.3.3 Fetching activestorage 5.2.3 Installing activestorage 5.2.3 Fetching public_suffix 4.0.1 Installing public_suffix 4.0.1 Fetching addressable 2.7.0 Installing addressable 2.7.0 Fetching io-like 0.3.0 Installing io-like 0.3.0 Fetching archive-zip 0.12.0 Installing archive-zip 0.12.0 Fetching bindex 0.8.1 Installing bindex 0.8.1 with native extensions Fetching msgpack 1.3.1 Installing msgpack 1.3.1 with native extensions Fetching bootsnap 1.4.5 Installing bootsnap 1.4.5 with native extensions Using bundler 2.1.4 Fetching byebug 11.0.1 Installing byebug 11.0.1 with native extensions Fetching regexp_parser 1.6.0 Installing regexp_parser 1.6.0 Fetching xpath 3.2.0 Installing xpath 3.2.0 Fetching capybara 3.29.0 Installing capybara 3.29.0 Fetching childprocess 2.0.0 Installing childprocess 2.0.0 with native extensions Fetching chromedriver-helper 2.1.1 Installing chromedriver-helper 2.1.1 Fetching coffee-script-source 1.12.2 Installing coffee-script-source 1.12.2 Fetching execjs 2.7.0 Installing execjs 2.7.0 Fetching coffee-script 2.4.1 Installing coffee-script 2.4.1 Fetching method_source 0.9.2 Installing method_source 0.9.2 Fetching thor 1.0.1 Installing thor 1.0.1 Fetching railties 5.2.3 Installing railties 5.2.3 Fetching coffee-rails 4.2.2 Installing coffee-rails 4.2.2 Fetching ffi 1.11.1 Installing ffi 1.11.1 with native extensions Fetching jbuilder 2.9.1 Installing jbuilder 2.9.1 Fetching rb-fsevent 0.10.3 Installing rb-fsevent 0.10.3 Fetching rb-inotify 0.10.0 Installing rb-inotify 0.10.0 Fetching ruby_dep 1.5.0 Installing ruby_dep 1.5.0 Fetching listen 3.1.5 Installing listen 3.1.5 Using mysql2 0.5.3 Fetching puma 3.12.1 Installing puma 3.12.1 with native extensions Fetching sprockets 3.7.2 Installing sprockets 3.7.2 Fetching sprockets-rails 3.2.1 Installing sprockets-rails 3.2.1 Fetching rails 5.2.3 Installing rails 5.2.3 Fetching rubyzip 1.2.4 Installing rubyzip 1.2.4 Fetching sass-listen 4.0.0 Installing sass-listen 4.0.0 Fetching sass 3.7.4 Installing sass 3.7.4 Fetching tilt 2.0.10 Installing tilt 2.0.10 Fetching sass-rails 5.1.0 Installing sass-rails 5.1.0 Fetching selenium-webdriver 3.142.4 Installing selenium-webdriver 3.142.4 Fetching turbolinks-source 5.2.0 Installing turbolinks-source 5.2.0 Fetching turbolinks 5.2.1 Installing turbolinks 5.2.1 Fetching uglifier 4.2.0 Installing uglifier 4.2.0 Fetching web-console 3.7.0 Installing web-console 3.7.0 Bundle complete! 16 Gemfile dependencies, 76 gems now installed. Use`bundle info [gemname]` to see where a bundled gem is installed.
  Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0

Post-install message from chromedriver-helper:

+--------------------------------------------------------------------+
| |
| NOTICE: chromedriver-helper is deprecated after 2019-03-31. |
| |
| Please update to use the 'webdrivers' gem instead. |
| See https://github.com/flavorjones/chromedriver-helper/issues/83 |
| |
+--------------------------------------------------------------------+

Post-install message from sass:

Ruby Sass has reached end-of-life and should no longer be used.

- If you use Sass as a command-line tool, we recommend using Dart Sass, the new
  primary implementation: https://sass-lang.com/install

- If you use Sass as a plug-in for a Ruby web framework, we recommend using the
  sassc gem: https://github.com/sass/sassc-ruby#readme

- For more details, please refer to the Sass blog:
  https://sass-lang.com/blog/posts/7828841

Removing intermediate container 1fd5b639b380
---> aa4335b2543f
Step 13/25 : ENV RAILS_ROOT ./apptest
---> Running in 2d5a3ff744ba
Removing intermediate container 2d5a3ff744ba
---> 94550e8e8fc7
Step 14/25 : COPY . /apptest
---> 47be7afe07de
Step 15/25 : RUN mkdir -p $RAILS_ROOT
 ---> Running in 3230cf12a70c
Removing intermediate container 3230cf12a70c
 ---> b6a03ed0f7e1
Step 16/25 : WORKDIR $RAILS_ROOT
---> Running in 52675e498930
Removing intermediate container 52675e498930
---> b29c876c1c15
Step 17/25 : ENV RAILS_ENV='production'
---> Running in 56151fbc1b8e
Removing intermediate container 56151fbc1b8e
---> f71f2ba546fb
Step 18/25 : ENV RACK_ENV='production'
---> Running in 63bd406bb816
Removing intermediate container 63bd406bb816
---> ab061fd91552
Step 19/25 : ENV PORT 3000
---> Running in 9ca797d17ddf
Removing intermediate container 9ca797d17ddf
---> a4fe160390c9
Step 20/25 : COPY Gemfile Gemfile
---> fa1f69db2a1d
Step 21/25 : COPY Gemfile.lock Gemfile.lock
---> 06d35df7f5b3
Step 22/25 : COPY . .
---> cfdf15c74f76
Step 23/25 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in 5a7dc86b0b11
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T06:20:50.087282 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T06:20:50.088515 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T06:20:50.157287 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T06:20:50.158397 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container 5a7dc86b0b11
---> f82af1d56f3b
Step 24/25 : EXPOSE 3000
---> Running in 053f7d44101b
Removing intermediate container 053f7d44101b
---> e7cc08711925
Step 25/25 : CMD ["SECRET_KEY_BASE=1", "RAILS_ENV=production", "bundle", "exec", "puma", "-C", "config/puma.rb"]
---> Running in 26fb74c1e833
Removing intermediate container 26fb74c1e833
---> 3ffab28229dc
Successfully built 3ffab28229dc
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Running in 74b3322b9176
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
libapr1 libaprutil1 libgdbm6
Suggested packages:
gdbm-l10n
The following NEW packages will be installed:
apache2-utils libapr1 libaprutil1 libgdbm6
0 upgraded, 4 newly installed, 0 to remove and 9 not upgraded.
Need to get 495 kB of archives.
After this operation, 1157 kB of additional disk space will be used.
Get:1 http://deb.debian.org/debian buster/main amd64 libapr1 amd64 1.6.5-1+b1 [102 kB]
Get:2 http://deb.debian.org/debian buster/main amd64 libgdbm6 amd64 1.18.1-4 [64.7 kB]
Get:3 http://deb.debian.org/debian buster/main amd64 libaprutil1 amd64 1.6.1-4 [91.8 kB]
Get:4 http://deb.debian.org/debian buster/main amd64 apache2-utils amd64 2.4.38-3+deb10u3 [236 kB]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 495 kB in 0s (1523 kB/s)
Selecting previously unselected package libapr1:amd64.
(Reading database ... 7203 files and directories currently installed.)
Preparing to unpack .../libapr1_1.6.5-1+b1_amd64.deb ...
Unpacking libapr1:amd64 (1.6.5-1+b1) ...
Selecting previously unselected package libgdbm6:amd64.
Preparing to unpack .../libgdbm6_1.18.1-4_amd64.deb ...
Unpacking libgdbm6:amd64 (1.18.1-4) ...
Selecting previously unselected package libaprutil1:amd64.
Preparing to unpack .../libaprutil1_1.6.1-4_amd64.deb ...
Unpacking libaprutil1:amd64 (1.6.1-4) ...
Selecting previously unselected package apache2-utils.
Preparing to unpack .../apache2-utils_2.4.38-3+deb10u3_amd64.deb ...
Unpacking apache2-utils (2.4.38-3+deb10u3) ...
Setting up libapr1:amd64 (1.6.5-1+b1) ...
Setting up libgdbm6:amd64 (1.18.1-4) ...
Setting up libaprutil1:amd64 (1.6.1-4) ...
Setting up apache2-utils (2.4.38-3+deb10u3) ...
Processing triggers for libc-bin (2.28-10) ...
Removing intermediate container 74b3322b9176
---> d3d9227c8092
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Running in 341008ed903b
Removing intermediate container 341008ed903b
---> 6cf45bd827e0
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Running in 6e5b62f73c2f
Removing intermediate container 6e5b62f73c2f
 ---> 5f133ad7a38a
Step 5/9 : RUN mkdir log
 ---> Running in 104f85c408e0
Removing intermediate container 104f85c408e0
 ---> ed5f2af3e25a
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> 7bbf98e3ec0f
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Running in 7d677d46faa3
Removing intermediate container 7d677d46faa3
---> cbb89b05b570
Step 8/9 : EXPOSE 80
---> Running in 0440efdaef64
Removing intermediate container 0440efdaef64
---> ade9ef27e410
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Running in df17d9fd1ad7
Removing intermediate container df17d9fd1ad7
---> cb159621db73
Successfully built cb159621db73
Successfully tagged apptest_web:latest
root@dockserver:~/apptest/docker/app# docker-compose up -d
Creating network "apptest_default" with the default driver
Creating apptest_db_1 ...
Creating apptest_db_1 ... done
Creating apptest_app_1 ...
Creating apptest_app_1 ... error

ERROR: for apptest_app_1 Cannot start service app: OCI runtime create failed: container_linux.go:345: starting container process caused "exec: \"SECRET_KEY_BASE=1\": executable file not found in \$PATH": unknown

ERROR: for app Cannot start service app: OCI runtime create failed: container_linux.go:345: starting container process caused "exec: \"SECRET_KEY_BASE=1\": executable file not found in $PATH": unknown
ERROR: Encountered errors while bringing up the project.
root@dockserver:~/apptest/docker/app# pwd
/root/apptest/docker/app
root@dockserver:~/apptest/docker/app# ls
Dockerfile  Dockerfile.save  Dockerfile~
root@dockserver:~/apptest/docker/app# nano Dockerfile
root@dockserver:~/apptest/docker/app# ls
Dockerfile  Dockerfile.save  Dockerfile~
root@dockserver:~/apptest/docker/app# rm Dockerfile.save
root@dockserver:~/apptest/docker/app# ls
Dockerfile  Dockerfile~
root@dockserver:~/apptest/docker/app# rm Dockerfile~
root@dockserver:~/apptest/docker/app# ls
Dockerfile
root@dockserver:~/apptest/docker/app# cd ..
root@dockserver:~/apptest/docker# ls
app  db.env  web
root@dockserver:~/apptest/docker# cd ..
root@dockserver:~/apptest# ls
Gemfile       README.md  app  config     db       docker              lib  package.json  storage  tmp     yarn.lock
Gemfile.lock  Rakefile   bin  config.ru  db-data  docker-compose.yml  log  public        test     vendor
root@dockserver:~/apptest# docker-compose build
db uses an image, skipping
Building app
Step 1/26 : FROM ruby:2.5-alpine
 ---> cbd297d70a23
Step 2/26 : RUN apk update
 ---> Using cache
 ---> e9cb5ae4e0a8
Step 3/26 : RUN apk add nodejs
 ---> Using cache
 ---> 123bcbba9422
Step 4/26 : ADD Gemfile Gemfile
 ---> Using cache
 ---> ad7a4e5750ef
Step 5/26 : ADD Gemfile.lock Gemfile.lock
 ---> Using cache
 ---> 9da05b179fc8
Step 6/26 : RUN apk update &&     apk add --no-cache     tzdata git make     build-base bash openssh     mysql     mysql-client     mysql-dev      imagemagick
 ---> Using cache
 ---> 185dde634373
Step 7/26 : RUN gem install bundler:2.1.4
 ---> Using cache
 ---> 8b116d6fb1b6
Step 8/26 : RUN apk add --no-cache build-base
 ---> Using cache
 ---> bccf6671d2d5
Step 9/26 : RUN gem install mysql2
 ---> Using cache
 ---> 229c48c6dee7
Step 10/26 : RUN gem install ffi
 ---> Using cache
 ---> 3912ee41e94d
Step 11/26 : RUN gem install nokogiri
 ---> Using cache
 ---> 105d47e8ca3f
Step 12/26 : RUN bundle install
 ---> Using cache
 ---> aa4335b2543f
Step 13/26 : ENV RAILS_ROOT ./apptest
 ---> Using cache
 ---> 94550e8e8fc7
Step 14/26 : COPY . /apptest
 ---> 65d684d9bf76
Step 15/26 : RUN mkdir -p $RAILS_ROOT
---> Running in c1a13da16ebf
Removing intermediate container c1a13da16ebf
---> ce9f42848a4d
Step 16/26 : WORKDIR $RAILS_ROOT
 ---> Running in 7cd0b90d74cc
Removing intermediate container 7cd0b90d74cc
 ---> 034c96cbe2e7
Step 17/26 : ENV RAILS_ENV='production'
 ---> Running in 4171f94ba752
Removing intermediate container 4171f94ba752
 ---> 5d922ba51abe
Step 18/26 : ENV RACK_ENV='production'
 ---> Running in d4c32e213f6f
Removing intermediate container d4c32e213f6f
 ---> 05ee22599503
Step 19/26 : ENV PORT 3000
 ---> Running in cab0bee44ae0
Removing intermediate container cab0bee44ae0
 ---> 0fc1366d1143
Step 20/26 : ENV SECRET_KEY_BASE=f9e612c0c13733da9cd8d3b5a90e4410b039526ae8f407734070aa99e15c9cd3d87380622c502f85883468ff18ee1ed72f6482b70022b220e08d8572b0e68c0e
 ---> Running in 4df493a0594d
Removing intermediate container 4df493a0594d
 ---> 2c62b6fe2099
Step 21/26 : COPY Gemfile Gemfile
 ---> 2bde4e43c58c
Step 22/26 : COPY Gemfile.lock Gemfile.lock
 ---> b626438288eb
Step 23/26 : COPY . .
 ---> 217d9927ce52
Step 24/26 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
 ---> Running in 9115d2d97def
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T06:25:20.165050 #1]  INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T06:25:20.166281 #1]  INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T06:25:20.236966 #1]  INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T06:25:20.238116 #1]  INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container 9115d2d97def
 ---> 8151ff1bb8cf
Step 25/26 : EXPOSE 3000
 ---> Running in 9fe7bb3ad89a
Removing intermediate container 9fe7bb3ad89a
 ---> d367deafdef6
Step 26/26 : CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]
 ---> Running in b2ddf931b8ce
Removing intermediate container b2ddf931b8ce
 ---> 11660b61a2cf
Successfully built 11660b61a2cf
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
 ---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
 ---> Using cache
 ---> d3d9227c8092
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
 ---> Using cache
 ---> 6cf45bd827e0
Step 4/9 : WORKDIR $RAILS_ROOT
---> Using cache
---> 5f133ad7a38a
Step 5/9 : RUN mkdir log
---> Using cache
---> ed5f2af3e25a
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
---> Using cache
---> 7bbf98e3ec0f
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
 ---> Using cache
 ---> cbb89b05b570
Step 8/9 : EXPOSE 80
 ---> Using cache
 ---> ade9ef27e410
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
 ---> Using cache
 ---> cb159621db73
Successfully built cb159621db73
Successfully tagged apptest_web:latest
root@dockserver:~/apptest# docker-compose up -d
apptest_db_1 is up-to-date
Recreating apptest_app_1 ... 
Recreating apptest_app_1 ... done
Creating apptest_web_1 ... 
Creating apptest_web_1 ... done
root@dockserver:~/apptest# docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                    NAMES
f5b90274b92f        apptest_web         "nginx -g 'daemon of…"   5 seconds ago       Up 4 seconds        0.0.0.0:80->80/tcp       apptest_web_1
9a38ba422cf4        apptest_app         "bundle exec puma -C…"   6 seconds ago       Up 5 seconds        0.0.0.0:3000->3000/tcp   apptest_app_1
210dac65a3d8        mysql:5.7.18        "docker-entrypoint.s…"   4 minutes ago       Up 4 minutes        0.0.0.0:3306->3306/tcp   apptest_db_1
root@dockserver:~/apptest# docker-compose exec app bundle exec rake db:create db:schema:loadCreated database 'apptest'
-- create_table("posts", {:options=>"ENGINE=InnoDB DEFAULT CHARSET=utf8", :force=>:cascade})
   -> 0.0364s
root@dockserver:~/apptest# exit
logout
Connection to 157.245.211.227 closed.
imac-de-william:apptest williamromero$ l
bash: l: command not found
imac-de-william:apptest williamromero$ ls
Gemfile                 app                     db                      lib                     public                  vendor
Gemfile.lock            bin                     db-data                 log                     storage                 yarn.lock
README.md               config                  docker                  node_modules            test
Rakefile                config.ru               docker-compose.yml      package.json            tmp
imac-de-william:apptest williamromero$ ssh root@157.245.211.227
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 4.15.0-66-generic x86_64)

- Documentation: https://help.ubuntu.com
- Management: https://landscape.canonical.com
- Support: https://ubuntu.com/advantage

System information as of Thu Feb 20 07:24:36 UTC 2020

System load: 0.0
Usage of /: 59.4% of 24.06GB
Memory usage: 52%
Swap usage: 0%
Processes: 100
Users logged in: 1
IP address for eth0: 157.245.211.227
IP address for eth1: 10.132.7.149
IP address for docker0: 172.17.0.1
IP address for br-89588f3cc44b: 192.168.0.1

- Canonical Livepatch is available for installation.
  - Reduce system reboots and improve kernel security. Activate at:
    https://ubuntu.com/livepatch

57 packages can be updated.
0 updates are security updates.

**_ System restart required _**
Last login: Thu Feb 20 06:04:28 2020 from 190.148.52.47
root@dockserver:~# ls
apptest
root@dockserver:~# cd apptest
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Gemfile
        modified:   config/puma.rb
        modified:   docker-compose.yml
        modified:   docker/app/Dockerfile

no changes added to commit (use "git add" and/or "git commit -a")
root@dockserver:~/apptest# git remote -v update && git status
Fetching origin
POST git-upload-pack (677 bytes)
remote: Enumerating objects: 11, done.
remote: Counting objects: 100% (11/11), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 6 (delta 3), reused 6 (delta 3), pack-reused 0
Unpacking objects: 100% (6/6), done.
From https://github.com/williamromero/apptest
0d2a267..04dda9d master -> origin/master
= [up to date] dependabot/bundler/loofah-2.4.0 -> origin/dependabot/bundler/loofah-2.4.0
= [up to date] dependabot/bundler/puma-3.12.2 -> origin/dependabot/bundler/puma-3.12.2
= [up to date] dependabot/bundler/rack-2.2.2 -> origin/dependabot/bundler/rack-2.2.2
= [up to date] dependabot/bundler/rubyzip-1.3.0 -> origin/dependabot/bundler/rubyzip-1.3.0
On branch master
Your branch is behind 'origin/master' by 1 commit, and can be fast-forwarded.
(use "git pull" to update your local branch)

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Gemfile
        modified:   config/puma.rb
        modified:   docker-compose.yml
        modified:   docker/app/Dockerfile

no changes added to commit (use "git add" and/or "git commit -a")
root@dockserver:~/apptest# git stash save "Cambios en la configuracion para entorno de produccion"

\*\*\* Please tell me who you are.

Run

git config --global user.email "you@example.com"
git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'root@dockserver.(none)')
Cannot save the current index state
root@dockserver:~/apptest# git config --global user.email "williamromerovela@gmail.com"
root@dockserver:~/apptest# git config --global user.name "William Romero"
root@dockserver:~/apptest# git stash save "Cambios en la configuracion para entorno de produccion"
Saved working directory and index state On master: Cambios en la configuracion para entorno de produccion
root@dockserver:~/apptest# git remote -v update && git status
Fetching origin
From https://github.com/williamromero/apptest
= [up to date] master -> origin/master
= [up to date] dependabot/bundler/loofah-2.4.0 -> origin/dependabot/bundler/loofah-2.4.0
= [up to date] dependabot/bundler/puma-3.12.2 -> origin/dependabot/bundler/puma-3.12.2
= [up to date] dependabot/bundler/rack-2.2.2 -> origin/dependabot/bundler/rack-2.2.2
= [up to date] dependabot/bundler/rubyzip-1.3.0 -> origin/dependabot/bundler/rubyzip-1.3.0
On branch master
Your branch is behind 'origin/master' by 1 commit, and can be fast-forwarded.
(use "git pull" to update your local branch)

nothing to commit, working tree clean
root@dockserver:~/apptest# git pull
Updating 0d2a267..04dda9d
Fast-forward
docker-compose.yml | 1 +
docker/app/Dockerfile | 3 ++-
2 files changed, 3 insertions(+), 1 deletion(-)
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
root@dockserver:~/apptest# git stash list
stash@{0}: On master: Cambios en la configuracion para entorno de produccion
root@dockserver:~/apptest# git stash apply @{0}
'@{0}' is not a stash-like commit
root@dockserver:~/apptest# git stash apply 0
Auto-merging docker/app/Dockerfile
CONFLICT (content): Merge conflict in docker/app/Dockerfile
Auto-merging docker-compose.yml
root@dockserver:~/apptest# nano docker/app/Dockerfile
root@dockserver:~/apptest# nano docker/app/Dockerfile
root@dockserver:~/apptest# git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
(use "git reset HEAD <file>..." to unstage)

        modified:   Gemfile
        modified:   config/puma.rb
        modified:   docker-compose.yml

Unmerged paths:
(use "git reset HEAD <file>..." to unstage)
(use "git add <file>..." to mark resolution)

        both modified:   docker/app/Dockerfile

root@dockserver:~/apptest# nano docker-compose.yml
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# ls
Gemfile README.md app config db docker lib package.json storage tmp yarn.lock
Gemfile.lock Rakefile bin config.ru db-data docker-compose.yml log public test vendor
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
f5b90274b92f apptest_web "nginx -g 'daemon of…" About an hour ago Up About an hour 0.0.0.0:80->80/tcp apptest_web_1
9a38ba422cf4 apptest_app "bundle exec puma -C…" About an hour ago Up About an hour 0.0.0.0:3000->3000/tcp apptest_app_1
210dac65a3d8 mysql:5.7.18 "docker-entrypoint.s…" About an hour ago Up About an hour 0.0.0.0:3306->3306/tcp apptest_db_1
root@dockserver:~/apptest# docker-compose down
Stopping apptest_web_1 ... done
Stopping apptest_app_1 ... done
Stopping apptest_db_1 ... done
Removing apptest_web_1 ... done
Removing apptest_app_1 ... done
Removing apptest_db_1 ... done
Removing network apptest_default
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
root@dockserver:~/apptest# docker-compose build
db uses an image, skipping
Building app
Step 1/26 : FROM ruby:2.5-alpine
---> cbd297d70a23
Step 2/26 : RUN apk update
---> Using cache
---> e9cb5ae4e0a8
Step 3/26 : RUN apk add nodejs
---> Using cache
---> 123bcbba9422
Step 4/26 : ADD Gemfile Gemfile
---> Using cache
---> ad7a4e5750ef
Step 5/26 : ADD Gemfile.lock Gemfile.lock
---> Using cache
---> 9da05b179fc8
Step 6/26 : RUN apk update && apk add --no-cache tzdata git make build-base bash openssh mysql mysql-client mysql-dev imagemagick
---> Using cache
---> 185dde634373
Step 7/26 : RUN gem install bundler:2.1.4
---> Using cache
---> 8b116d6fb1b6
Step 8/26 : RUN apk add --no-cache build-base
---> Using cache
---> bccf6671d2d5
Step 9/26 : RUN gem install mysql2
---> Using cache
---> 229c48c6dee7
Step 10/26 : RUN gem install ffi
---> Using cache
---> 3912ee41e94d
Step 11/26 : RUN gem install nokogiri
---> Using cache
---> 105d47e8ca3f
Step 12/26 : RUN bundle install
---> Using cache
---> aa4335b2543f
Step 13/26 : ENV RAILS_ROOT ./apptest
---> Using cache
---> 94550e8e8fc7
Step 14/26 : COPY . /apptest
---> 851170d3bb08
Step 15/26 : RUN mkdir -p $RAILS_ROOT
 ---> Running in 38788a2853e2
Removing intermediate container 38788a2853e2
 ---> cf83cf5da0bf
Step 16/26 : WORKDIR $RAILS_ROOT
---> Running in 171f139c9b80
Removing intermediate container 171f139c9b80
---> 602894615e95
Step 17/26 : ENV RAILS_ENV='production'
---> Running in b04a0e77f7f2
Removing intermediate container b04a0e77f7f2
---> fecfa8685074
Step 18/26 : ENV RACK_ENV='production'
---> Running in b8d4bd543d6a
Removing intermediate container b8d4bd543d6a
---> 0245908c92d8
Step 19/26 : ENV PORT 3000
---> Running in 4dda62d5b57e
Removing intermediate container 4dda62d5b57e
---> 74087038daa0
Step 20/26 : ENV SECRET_KEY_BASE=f9e612c0c13733da9cd8d3b5a90e4410b039526ae8f407734070aa99e15c9cd3d87380622c502f85883468ff18ee1ed72f6482b70022b220e08d8572b0e68c0e
---> Running in 158b9e51bfd9
Removing intermediate container 158b9e51bfd9
---> d94c2ff9a786
Step 21/26 : COPY Gemfile Gemfile
---> aca2531bafa8
Step 22/26 : COPY Gemfile.lock Gemfile.lock
---> d0b04a76c8bb
Step 23/26 : COPY . .
---> 7d3a3d128104
Step 24/26 : RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile
---> Running in 1c676174165e
Yarn executable was not detected in the system.
Download Yarn at https://yarnpkg.com/en/docs/install
I, [2020-02-20T07:41:39.852091 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js
I, [2020-02-20T07:41:39.853373 #1] INFO -- : Writing /apptest/public/assets/application-5b9a89e2a2a4fd5130145fa31b84267a9d9ec37b48a782dcfd88dbc717e56f66.js.gz
I, [2020-02-20T07:41:39.894970 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css
I, [2020-02-20T07:41:39.896031 #1] INFO -- : Writing /apptest/public/assets/application-35729bfbaf9967f119234595ed222f7ab14859f304ab0acc5451afb387f637fa.css.gz
Removing intermediate container 1c676174165e
---> 05dca3d5d2fa
Step 25/26 : EXPOSE 3000
---> Running in 072ea5429627
Removing intermediate container 072ea5429627
---> d4ff323cca8f
Step 26/26 : CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]
---> Running in 95f01a59a109
Removing intermediate container 95f01a59a109
---> 83e543cb4890
Successfully built 83e543cb4890
Successfully tagged apptest_app:latest
Building web
Step 1/9 : FROM nginx
---> 2073e0bcb60e
Step 2/9 : RUN apt-get update -qq && apt-get -y install apache2-utils
---> Using cache
---> d3d9227c8092
Step 3/9 : ENV RAILS_ROOT /var/www/app_name
---> Using cache
---> 6cf45bd827e0
Step 4/9 : WORKDIR $RAILS_ROOT
 ---> Using cache
 ---> 5f133ad7a38a
Step 5/9 : RUN mkdir log
 ---> Using cache
 ---> ed5f2af3e25a
Step 6/9 : COPY docker/web/nginx.conf /tmp/docker.nginx
 ---> Using cache
 ---> 7bbf98e3ec0f
Step 7/9 : RUN envsubst '$RAILS_ROOT' < /tmp/docker.nginx > /etc/nginx/conf.d/default.conf
---> Using cache
---> cbb89b05b570
Step 8/9 : EXPOSE 80
---> Using cache
---> ade9ef27e410
Step 9/9 : CMD [ "nginx", "-g", "daemon off;" ]
---> Using cache
---> cb159621db73
Successfully built cb159621db73
Successfully tagged apptest_web:latest
root@dockserver:~/apptest# docker-compose up -
Creating network "apptest_default" with the default driver
ERROR: No such service: -
root@dockserver:~/apptest# ^C
root@dockserver:~/apptest# docker-compose up -d
Creating apptest_db_1 ...
Creating apptest_db_1 ... done
Creating apptest_app_1 ...
Creating apptest_app_1 ... done
Creating apptest_web_1 ...
Creating apptest_web_1 ... done
root@dockserver:~/apptest# docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
0f923e8b8964 apptest_web "nginx -g 'daemon of…" 6 seconds ago Up 4 seconds 0.0.0.0:80->80/tcp apptest_web_1
c75c7735a494 apptest_app "bundle exec puma -p…" 7 seconds ago Up 6 seconds 0.0.0.0:3000->3000/tcp apptest_app_1
cced66cffa94 mysql:5.7.18 "docker-entrypoint.s…" 8 seconds ago Up 7 seconds 0.0.0.0:3306->3306/tcp apptest_db_1
root@dockserver:~/apptest# git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
(use "git reset HEAD <file>..." to unstage)

        modified:   Gemfile
        modified:   config/puma.rb
        modified:   docker-compose.yml

Unmerged paths:
(use "git reset HEAD <file>..." to unstage)
(use "git add <file>..." to mark resolution)

        both modified:   docker/app/Dockerfile

root@dockserver:~/apptest# git add .
root@dockserver:~/apptest# git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
(use "git reset HEAD <file>..." to unstage)

        modified:   Gemfile
        modified:   config/puma.rb
        modified:   docker-compose.yml
        modified:   docker/app/Dockerfile

root@dockserver:~/apptest# git commit -m "Added modifications on docker files"
[master 66fb666] Added modifications on docker files
4 files changed, 6 insertions(+), 2 deletions(-)
root@dockserver:~/apptest# git push -u origin master
Username for 'https://github.com': williamromerovela@gmail.com
Password for 'https://williamromerovela@gmail.com@github.com':
Counting objects: 9, done.
Compressing objects: 100% (8/8), done.
Writing objects: 100% (9/9), 918 bytes | 918.00 KiB/s, done.
Total 9 (delta 6), reused 0 (delta 0)
remote: Resolving deltas: 100% (6/6), completed with 6 local objects.
remote:
remote: GitHub found 4 vulnerabilities on williamromero/apptest's default branch (1 high, 1 moderate, 2 low). To find out more, visit:
remote: https://github.com/williamromero/apptest/network/alerts
remote:
To https://github.com/williamromero/apptest.git
04dda9d..66fb666 master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
root@dockserver:~/apptest#
