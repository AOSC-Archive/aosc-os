Major Objectives
------------------

- Nothing special for July, a test for monthly cycle. ✓

Pakreq (Package Requests)
-----------------------------

This section lists all the new packages requested by community members, these packages are made available when this wave of updates is ready.

- Fritzing (IRC/Telegram). ✓
- gti (rwos/gti; IRC/Telegram). ✓
- RSpamD (IRC/Telegram). ✓
- Virt-What (IRC/Telegram). ✓
- BSDiff (IRC/Telegram). ✓
- Telegram-Purple (IRC/Telegram). ✓
- fzf (IRC/Telegram). ✓
- GNOME Wave Cleaner (IRC/Telegram). ✓
- Pulp (IRC/Telegram). ✓
- Teeworlds DDraceNetwork mod (IRC/Telegram). ✓
- libnetfilter-queue (IRC/Telegram). ✓
- xattr (PyPI; IRC/Telegram). ✓
- Screenruler (IRC/Telegram). ✓
- Magic-Wormhole (for file transfer; IRC/Telegram). ✓
- Anki (#657). ✓
- GNU Radio (IRC/Telegram). ✓
- ACBS (IRC/Telegram). ✓
- dump1090 (IRC/Telegram). ✓
- Vivaldi FFmpeg Plugin (IRC/Telegram). ✓

Unresolved/Delayed Pakreqs
------------------------------

These package requests are delayed, and thus will not be made available yet this month - reasons for which are listed below.

- Nginx-RTMP (IRC/Telegram).
	- Building into Nginx may need further discussion.

*Note: Most pakreqs filed after July 1st were not processed, this was due to a discussed change regarding deadlines for pakreqs. From August, all pakreqs filed before Day 20 will be processed, however, packagers could still delay a certain pakreq filed close to that date if they find the request difficult to meet.*

Updreq (Update Requests)
---------------------------

This section lists all updates to existing packages requested by community members, these package updates are made by request and are made available when this wave of updates is ready.

None processed this month.

*Note: This is a new request format introduced since AOSCC 2017 (mid-July), thus not to be processed in this cycle.*

Unresolved/Delayed Updreqs
------------------------------

None this month.

Optreq (Optimisation Requests)
----------------------------------

This section lists all optimisation to existing packages requested by community members, these package updates are made by request and are made available when this wave of updates is ready.

None processed this month.

*Note: This is a new request format introduced since AOSCC 2017 (mid-July), thus not to be processed in this cycle.*

Unresolved/Delayed Optreqs
------------------------------

None this month.

Security Issues
-----------------

This section lists all security updates made throughout the month (**not** made available monthly, but at availability).

- AOSA-2017-0045: Update Unrar to 5.5.5 (CVE-2012-6706). ✓
- AOSA-2017-0046: Update LibGCrypt to 1.7.8 (CVE-2017-7526). ✓
- AOSA-2017-0047: Update Perl DBD::MySQL to (CVE-2017-10789). ✓
- AOSA-2017-0048: Update SQLite to 3.19.2-1 (CVE-2017-10989). ✓
- AOSA-2017-0049: Update KMail and MessageLib to 17.04.2 (CVE-2017-9604). ✓
- AOSA-2017-0050: Update Mpg123 to 1.25.2 (CVE-2017-11126). ✓
- AOSA-2017-0051: Update Evince to 3.24.0-1 (CVE-2017-1000083). ✓
- AOSA-2017-0052: Update SPICE libraries to 0.12.8-1 (CVE-2017-7506). ✓
- AOSA-2017-0053: Update ImageMagick to 6.9.8+10 (CVE-2017-11352). ✓
- AOSA-2017-0054: Update GraphicsMagick to 1.3.25-4 (CVE-2017-11403). ✓
- AOSA-2017-0055: Update Open VMware Tools to 10.1.5-2 (CVE-2015-5191). ✓
- AOSA-2017-0056: Update Linux Kernel and Linux Kernel LTS branch (CVE-2017-7541). ✓

General Issues
----------------

This section lists all issues/bugs reported by community members, and are made available as a part of this wave of update.

- Fixed upgrading/replacement installation of adapta (IRC/Telegram). ✓
- FeelUOwn requires root to launch (IRC/Telegram). ✓
- Fixed missing dependency `libidn2` in `apt` (IRC/Telegram). ✓
- Fixed Deluge segmentation faults with errors in relation to Boost's Python bindings (IRC/Telegram). ✓
	- Libtorrent-Rasterbar currently has issue with Python 3 bindings to Boost. ✓
	- Dropped Epour for now. ✓
- NSS now includes libpkix again (IRC/Telegram). ✓
- Nim now includes sources (IRC/Telegram). ✓
- Fixed incorrect permission/mode of `apt-fast` Zsh completion files (IRC/Telegram). ✓
- Fixed missing dependencies `snappy` and `glu` in `qemu` (IRC/Telegram). ✓
- Fixed missing dependency `imchooser` in `ibus` (IRC/Telegram). ✓
- Fixed misisng dependency `pcre2` in `qt-5` (IRC/Telegram). ✓
- Fixed a typo in NetworkManager, zh_CN: "wireless network" translated as "invalid network" (IRC/Telegram). ✓
- Fixed invocation of Git::SVN by appending `subversion` to `git` dependencies (IRC/Telegram). ✓

Unresolved/Delayed Issues
-----------------------------

- Fixed an issue where Intel's driver for LibVA failed to initialise.
- Plasma desktop may fail to initialise due to a crash in libQt5Qml with a function pointer offset (`SIBGUS`).
	- Original bug report: https://bugreports.qt.io/browse/QTBUG-61522.
	- Working patch: https://codereview.qt-project.org/#/c/198278/.
	- This fix will be pushed as a `bugfix` branch commit in August.
- KInfoCenter may crash on devices with no PCI bus.
	- Bug reported at https://bugs.kde.org/show_bug.cgi?id=382979 by Icenowy Zheng.

Other Changes
---------------

Other changes are non-bugfix changes made to packages, or packages dropped from the community repository - effective in this wave of update. Users should take note.

- PHP 5.x is now dropped for it's no longer being maintained, `php` is now a transitional package for `php7`, which no longer provides PHP 5.x. ✓
- Minetest (`minetest`) and Minetest Game Data (`minetest-game`) are now merged as `minetest`. ✓

Delayed Changes
-----------------

These changes are not made due to various reasons, these could include lack of testing or major unresolved bugs found in the testing period (Day 20-25).

- NetworkManager is now using `systemd-resolved` for DNS resolver configuration, DNSSEC supported where available.

General Updates
-----------------

This section lists all changes made, and effective with this wave of update - including all issues, requests, and changes mentioned above, and additionally all version updates and rebuilds (if necessary). This section **excludes** all changes made to the `bugfix` branch, as they are not made available in a monthly fashion but irregularly as necessary, they will be listed below in a separate section.

This section is essentially a (slightly edited for reference) list of Git commits made to the `staging` (testing) branch of our ABBS tree. This list is chronologically sorted, with oldest commits on top.

ac5344ef9 atom: update to 1.18.0 (amd64)
7cade1e60 vim: update to 8.0.0691
179605623 shadowsocks-libev: update to 3.0.7
4d24af9aa nodejs: update to 8.1.3 (out of LTS), npm to 5.0.4
506727a07 youtube-dl: update to 2017.06.25 (noarch)
4d2dccbaf you-get: update to 0.4.750 (noarch)
2e548f25f boinc: update to 7.8.0
0cb429cd1 fsharp: update to 4.1.19
cc17ce2de polkit: add itstool files
a79aa262d fwupd: update to 0.9.4
95ccb8c94 packagekit: update to 1.1.6
0ad3c101c webkitgtk: fix build on arm64
c26d44a88 appstream-glib: update to 0.7.0
41be19f7b tilix: update to 1.6.1
640820d69 minetest: update to 0.4.16
7bb07cfc3 minetest-game: update to 0.4.16 (noarch)
024104013 nvchecker: update to 0.4.4 (noarch)
a2468f9d8 adwaita-qt: update to 1.0
3290fc167 sqlmap: update to 1.1.6 (noarch)
a34abc750 nghttp2: update to 1.23.1
8f979c1a1 ostree: update to 2017.7
8568d9ef3 bash-completion: update to 2.6 (noarch)
48205ec9a x264: fix LTO linking (amd64)
1c35baf78 mkvtoolnix: update to 11.0.0
cadb7a241 tlp: update to 1.0
7b0df15a6 rustc: update to 1.18.0
3d4f22b74 oregano: update to 0.84.6
985051820 elvish: update to 0.8
cd9d66b21 phoronix-test-suite: update to 7.2.1 (noarch)
10f0e7e7e qt-5: update to 5.9.1
d6ca356a1 ppsspp: update to 1.4.2
d37e00a76 calibre: update to 3.2.1
89b641cc4 playonlinux: update to 4.2.12
5386ddeec winetricks: update to 20170614 (noarch)
7b9568955 mate-themes: update to 3.22.12
2584f8f8b leatherman: update to 1.0.0
179b8178a ruby-bundler: update to 1.15.1 (noarch)
b9df15009 emscripten: update to 1.37.15
bb0bcd080 git: update to 2.13.2
80dcfa45f lollypop: update tbleo 0.9.240 (noarch)
7b9ca5521 libgit2: update to 0.26.0
86b714abf tmux: update to 2.5
f83761efb metasploit: update to 4.14.28 (noarch)
736b799da adapta: update to 3.91.0.145
61a86bba1 sqlite: update to 3.19.3
e676e45e0 apsw: update to 3.19.3
69cae6639 syncthing: update to 0.14.31
a382fe273 april: new, 0.0.1a4 (noarch)
99ed398da aiozmq: new, 0.7.1 (noarch)
c1fa5f6d3 fuzzywuzzy: new, 0.5.1
6795cfd33 marshmallow: new, 2.13.5 (noarch)
ce9046285 fuocore: new, 0.0.5a5 (noarch)
d7c587b37 feeluown: update to 9.5 (noarch)
073373cd6 qtox: update to 1.10.2
40b51cad0 beets: update to 1.4.5 (noarch)
05da5b7c1 flatpak: update to 0.9.7
c3248e4d8 openimageio: update to 1.7.15
dd06f158e blender: rebuild for openimageio
3d52d1560 openimageio: add luxrays break; fix build
6960e500e luxrays: rebuild for openimageio
5fd99ee14 luxrender: rebuild for openimageio
858c0c8b5 xdg-desktop-portal: update to 0.8
9529ac30a xdg-desktop-portal-gtk: update to 0.7
cbaef8459 memcached: update to 1.4.38
99b89dae3 zrtpcpp: update to 4.6.6
43d243d92 vapoursynth: update to 38
6b1a89df3 taisei: update to 20170601 (git)
d35d33498 slop: update to 6.3.45
34127906a maim: update to 5.4.63
33f5bf2a5 kaffeine: update to 2.0.10
a4ff24de7 guake: new, 0.8.10 (noarch)
61582ccf9 retext: update to 7.0.1 (noarch)
adbf33c51 meson: update to 0.41.1 (noarch)
7ad6e5845 pcap-dnsproxy: update to 0.4.9.1
0e7d05f5f yubikey-manager: update to 0.4.0 (noarch)
21d447601 mutagen: update to 1.38 (noarch)
3d13dfcfb flask: update to 0.12.2 (noarch)
cd7d93bd0 ipython: update to 6.1.0 (noarch)
7e76bf9e8 ffmpeg: update to 3.3.2
43acd566e c-ares: update to 1.13.0
e4634c24a ardour: update to 5.10
0bacde72c libass{,+32}: update to 0.13.7
88094dba2 tor: update to 0.3.0.9
bec308e0e mongodb-tools: update to 3.4.5
0238c375d fonttools: update to 3.13.1 (noarch)
144b5ac6e lumina: update to 1.3.0p1
7e11afcf9 brave-browser: update to 0.17.13 (amd64)
bfa356e5b musicbox: update to 0.2.4.1
2d26beac1 iperf3: update to 3.2
6786e5bbb logrotate: update to 3.12.3
9d74a0d13 libuv: update to 1.12.0
ee12ca6ec inxi: update to 2.3.23
ff19cccae firefox: update to 54.0.1
795834b5e thunderbird: update to 52.2.1
9c73ff396 ffmpeg: add numactl to all arch
19db5e59b mpv: add uchardet dep
1e2a31dfc ncmpcpp: update to 0.8
1ae111491 gtkd: update to 3.6.5
1f151d2c3 xed: update to 1.4.4
dbbae87da cinnamon-desktop: update to 3.4.2
fff1b2f92 cinnamon-translations: update to 3.4.3 (noarch)
3259af419 cinnamon-settings-daemon: update to 3.4.2
1a3fe476e cinnamon-session: update to 3.4.1
46d0ff538 cinnamon-screensaver: update to 3.4.1
adc26904f nemo: update to 3.4.5
d6ed0ba73 cjs: update to 3.4.2
48b6e6a8c cinnamon: update to 3.4.3
75deb96bd blueberry: update to 1.1.15 (noarch)
fd98c4d90 gst-transcoder: update to 1.10.1
7ce32c678 libsass: update to 3.4.5
b7ee26ec2 sassc: update to 3.4.5
1c7ae4b46 glmark2: update to 20170629
5fccfe3b8 libpinyin: update to 2.0.91
62644ba8e fcitx-libpinyin: rebuild for libpinyin
d4e144cfc ibus-libpinyin: rebuild for libpinyin
c57e98248 hhvm: update to 3.20.2
0f0df5c75 linux-kernel: add patch to fix some lenovo ideapads' wifi rfkill blocked issues
655df07b4 fcitx-cloudpinyin: update to 20170610
c0100cdfa tint2: update to 0.14.6
52399e78d dmd: update to 2.074.1
54d26d44b libbytesize: new 0.10
a79c01f1c volume-key: new, 0.3.9
d2f356464 libblockdev: new, 2.9
5ecef6013 pywbem: new, 0.10.0 (noarch)
60d3f6d06 libstoragemgmt: new, 1.4.0
19df3cec4 udisks-2: update to 2.7.0
e54545410 gogglesmm: update to 1.1.9
1fa0fa4a7 brial: update to 1.0.1
dff0c1626 darktable: update to 2.2.5
3f6313bc5 libva: update to 1.8.3
4dd20d68a libva-intel-driver: update to 1.8.3
9b16bf896 groovy: update to 2.4.12
15c5f63ee tensorflow: update to 1.2.1 (GFW block)
e35f7e18f mpd: update to 0.20.9
2db9cb116 bazel: update to 0.5.2 (amd64)
e53c6642d xreader: update to 1.4.4
26277653b xviewer: update to 1.4.3
16236ed1a slick-greeter: update to 1.0.8
855e13182 lightdm-settings: update to 1.1.1 (noarch)
27a653e4c tslib: update to 1.11
e1c6c4a8d tigervnc: update to 1.8.0
b6675842f protobuf: update to 3.3.2
e68bdd752 lantern: update to 3.7.3 (amd64)
7ee2b397e snappy: update to 1.1.5
31e221942 hiera: update to 3.4.0 (noarch)
d98ca0af3 diffutils: update to 3.6
9eafdc221 libmicrohttpd: update to 0.9.55
cce8567de gdb: update to 8.0
6cfb81382 gradle: update to 3.5.1
dd1a8e5c4 glpk: update to 4.62
a6a9bc03d automake: update to 1.15.1 (noarch)
64f9331c9 gsl: update to 2.4
ebebcfe8f arts: rebuild for gsl
617276ae2 astrometry.net: rebuild for gsl
6d884be13 asymptote: rebuild for gsl
d15665cb0 bogofilter: rebuild for gsl
51289d3d5 calligra: rebuild for gsl
0ab5312ff cvxopt: rebuild for gsl
a1055632c dieharder: rebuild for gsl
1cba5d216 enblend-enfuse: rebuild for gsl
2968515ad gsl: remove geogebra breakage
10aed2c65 giac: rebuild for gsl
54a048435 inkscape: rebuild for gsl
8e5a7d937 krita: rebuild for gsl
2aeaf3a65 libindi: rebuild for gsl
d3fc83127 pspp: rebuild for gsl
cca9e31c2 snd: rebuild for gsl
bf4f9276e step: rebuild for gsl
890b95979 unifont: update to 10.0.03
828f94e7f grub: update to unifont 10.0.03
f4fd65f4f texinfo: update to 6.3
08709456b nano: update to 2.8.5
86a3de8ca screen: update to 4.6.0
edeb4d66e gnome-recipes: update to 1.4.6
8fd4b9225 pango{,+32}: update to 1.40.6
6aa1abec5 networkmanager: fix typo in zh_CN
3b5005195 gnome-maps: update to 3.24.3
0eac64317 gnome-online-accounts: update to 3.24.1
5ec3c2438 shotwell: update to 0.26.2
4f2c643be libgweather: update to 3.24.1
5e01fec53 bijiben: update to 3.24.0
ff0ca458d gnome-todo: update to 3.24.2
8d51f50e6 gnome-calendar: update to 3.24.3
f906e0eb9 latexila: update to 3.24.2
26708269d libepoxy: update to 1.4.3
867cdd62a gnome-tweak-tool: update to 3.24.1
d39a71801 network-manager-applet: update to 1.8.2
2a600c4be gjs: update to 1.48.5
6e7dca042 libgnome-games-support: update to 1.2.2
417d7decb evolution-data-server: update to 3.24.3
f974d2270 evolution: update to 3.24.3
57031d410 groups/gstreamer-1-0: update to 1.12.1
22fc0217a minetest: merge in game data
12b7d44e7 gtk-3{,+32}: update to 3.22.16
6987aafec unicode-ucd: update to 10.0.0+5.0 (noarch)
f082dcd9b gucharmap: update to 10.0.0
a82401de0 totem-pl-parser: update to 3.10.8
5a8aad212 gom: update to 0.3.3
d5d6d864d nautilus-sendto: update to 3.8.5
84c9d1251 glibmm: update to 2.52.0
1424e96ed gtkmm-3: update to 3.22.1
c4764b76e mutter: update to 3.24.3
8d380949b vala: update to 0.36.4
22ace6809 tracker: update to 1.12.1
fafc14371 libwnck-3: update to 3.24.0
eb189ab30 girl: update to 0.4.0 (rewrite, epoch)
83a9ac1d3 libbsd: update to 0.8.5
1f0dc0344 dbus{,+32}: update to 1.10.20
7ffb564fd xkeyboard-config: update to 2.21 (noarch)
73315a8bb mesa: update to 17.1.4
82ffd57b4 tumbler: update to 0.1.32
ea732d2ed garcon: update to 0.6.1
6f1b0ae92 xfce4-xkb-plugin: update to 0.8.0
169115278 xfdesktop: update to 4.12.4
2f3c0f2a3 thunar: update to 1.6.12
fd282bb7d apt: update to 1.4.6
a8eced850 keyring: update to 10.4.0 (noarch)
2481271bf pytest: update to 3.1.2 (noarch)
93e6d15cc setuptools: update to 36.0.1 (noarch)
d0dcefa44 unidecode: update to 0.04.21 (noarch)
e8fc3bec4 stevedore: update to 1.23.0 (noarch)
881ea1b89 lttng-ust: update to 2.9.1
3540f49a1 linux-firmware: update to 20170622 (noarch)
6056008c9 mono: update to 5.4.0.56
7951bb82c nss: update to 3.31; enable pkix
acfe9cb01 libfilezilla: update to 0.9.2
e0cb5a2c1 filezilla: update to 3.26.2
890438e68 mercurial: update to 4.2.1
5fd822ecc strongswan: update to 5.5.3
e3de48562 nmap: update to 7.50
3df7f3df7 cherrytree: update to 0.38.1 (noarch)
291a85eef php: mark transitional for php7 (noarch)
7c775308e php7: update to 7.1.6
c268a0838 xf86-video-intel: update to 20170607 (amd64)
684a3b197 mutt: update to 1.8.3
f5dfe14b6 sudo: update to 1.8.20p2
2cf65c73c sbcl: update to 1.3.19
f6acb4c55 android-platform-tools: update to 7.1.2r17
8607fd7e3 openldap: update to 2.4.45
6e0f2210d gnutls: update to 3.5.13
ff6267146 unbound: update to 1.6.4
f5d917d20 libtasn1: update to 4.12
0da796dfc maxima: update to 5.40.0
5b1879681 wxmaxima: update to 17.05.1
aab6e43dc npth: update to 1.5
aa2b7dac1 erlang: update to 20.0
52fa2e48c cups-filters: update to 1.14.1
bb908e08d i3lock: update to 2.9.1
e8936544a libinput: update to 1.7.3
b4baba72a acpica-unix: update to 20170629
58d5f4a48 btrfs-progs: update to 4.11.1
4e9312b92 fontconfig{,+32}: update to 2.12.3
b06c15f12 libatomic-ops: update to 7.6.0
de7a48e7a qmmp: update to 1.1.9
5957225a9 py: update to 1.4.34 (noarch)
c90c73eff ethtool: update to 4.11
2a4eabd5a pv: update to 1.6.6
dc7b7f36f mbedtls: update to 2.5.1
2333e2f35 babl: update to 0.1.28
cf5b04f88 skk-jisyo: update to 20170625 (noarch)
ada7d73f0 quiterss: update to 0.18.6
fd750e8ec gsoap: update to 2.8.48
20681d695 haproxy: update to 1.7.7
016c77c18 qbittorrent: update to 3.3.13
6d5e69c0f simgear: update to 2017.2.1
f01b7cf15 flightgear: update to 2017.2.1
e548be61d veracrypt: update to 1.20
ed0d89e13 hplip: update to 3.17.6
2cd599027 inziu-iosevka-fonts: update to 1.13.0 (noarch)
f31e1d45a iosevka-fonts: update to 1.13.1 (noarch)
027ece883 iosevka-slab-fonts: update to 1.13.1 (noarch)
7d96d0953 webkit2gtk: update to 2.16.5
102f4c9d5 mariadb: update to 10.2.6
ddbb6cfed powertop: update to 2.9
d1e35c89d xf86-input-wacom: update to 0.35.0
83183f7dd opera: update to 46.0.2597.32 (amd64)
8e24b6fc3 numpy: update to 1.13.0
db97cb62b samba: update to 4.6.5
e10d84369 xterm: update to 330
3d1a26340 mobile-broadband-provider-info: update to 20170602 (noarch)
22d6b3358 flask-security: update to 3.0.0 (noarch)
3f173bb1d django: update to 1.11.2 (noarch)
a00194332 freeplane: update to 1.5.21 (noarch)
07841faab openvpn: update to 2.4.3
60d1e8e25 fasm: update to 1.71.63 (noarch)
40aae1d01 snd: update to 17.5
3580dd402 stellarium: update to 0.16.0
8cb0a9aa3 gnome-mpv: update to 0.12
1ba86960d jmol: update to 14.19.1 (noarch)
e69f50d81 qt5ct: update to 0.33
32ba92015 smplayer: update to 17.6.0
10d51d649 weechat: update to 1.9
e5879e9cd feh: update to 2.19
cbb6f874c groups/certbot: update to 0.15.0 (noarch)
5cf4aebc3 flashplayer-ppapi: update to 26.0.0.131 (amd64)
34017b4a3 mate-control-center: update to 1.18.2
25f836dd5 mate-media: update to 1.18.1
d5cce7c6d qt-5: fix WebKit version reference
17331b979 digikam: update to 5.6.0
86ad6ab69 krita: update to 3.1.4
37d91a940 mate-panel: update to 1.18.3
4477e4833 util-linux: update to 2.30
1df75fd76 parallel: update to 20170622 (noarch)
0b7feb5da os-prober: update to 1.76
ebf7d5c9a chardet: update to 3.0.4 (noarch)
e2c225537 requests: update to 2.18.1 (noarch)
fa171067b afl: update to 2.44b
63f11f552 pbr: update to 3.1.1 (noarch)
3a1fe7256 pcsclite: update to 1.8.22
563ebf64e alsa-lib{,+32}: update to 1.1.4.1
ea5befe0a picocom: add, 2.2
e7b27283e portmidi: add
95b366f24 portmidi: add missing builddeps
ee655211d mixxx: new package
fdd83d5fb manaplus: update to 1.7.6.24
7a7f6b720 nvidia{,+32}: update to 384.47 (amd64)
529144f54 nodejs: remove an excess symlink
c93109a1e papirus-icon-theme: update to 20170701 (noarch)
26d3b573f android-udev: update to 20170612 (noarch)
c5c2d2764 google-chrome: update to 59.0.3071.115 (amd64)
2f0527efd anbox: update to 20170620 (amd64)
069cb2d56 chromium: update to 59.0.3071.115
e7f3dab61 libreoffice: update to 5.3.4.2
237866656 certifi: new, 2017.4.17 (noarch)
75734bd1e setuptools: add certifi dep (noarch)
fa0e568fd requests: add certifi, idna dep (noarch)
59d8b6c53 idna: update to 2.5 (noarch)
365499aac groups/kf5: update to 5.35.0
9c23e5393 groups/plasma: update to 5.10.3
fa05b8acc groups/kde-applications: update to 17.04.2
55b4753dd telegram-desktop: upgrade to 1.1.10
842095e7d qtractor: upgrade to 0.8.3
fb011fb8d git: add subversion as dep
add0518db qemu: add dep glu and snappy
582ac5a9a apt-fast: fix permission on zsh/bash completion (noarch)
ef604127c nim: refurbish build script, include compiler source
2e676886f epour: drop for now
c40cfaa78 libtorrent-rasterbar: use Python 2
2c637afdd deluge: rebuild for libtorrent
68ceb9014 apt: add libidn2 dep
bc6f31ca3 fritzing: new, 0.9.3b
37d3f3029 gti: new, 1.6.1
181270645 fann: new, 20151129
deef5c6be rspamd: new, 1.6.1
ab27e2043 virt-what: new, 1.15
3a93c7190 bsdiff: new, 4.3
30f733d1a telegram-purple: new, 1.3.1
c10e57d1e fzf: new, 0.16.8
b8c17ae71 kcptun: update to 20170525
aae71795f boost: disable LTO to avoid some vtables error
f094589d1 privoxy: fix config read
cf2501cbd qwtplot3d: new, 0.2.7
7654cc3a4 go: rebuild for broken package due to GFW
1d363ae38 qwt5: new, 5.2.3
a87118e70 pyqwt: new, 5.2.0
63027a167 libuhd: new, 003.010.001.001
57a9771b2 gnuradio: new, FTBFS
33978b8e2 jpegoptim: new, 1.4.4
97fcd601a gwc: new, 0.21+19
13b0ce303 pulp: new, 1.6.6
727519ce8 teeworlds: conflicts ddnet, clean up
365901d27 ddnet: new, 10.6.4
b4a69909c wireshark: update to 2.2.7
470ecf41c libnetfilter-queue: new, 1.0.2
12c8c250a xattr: update to 0.9.2
abd6f60ff ruby-pkg-config: new, 1.2.3 (noarch)
9c73679af ruby-native-package-installer: new, 1.0.4 (noarch)
6e3dbf1d8 ruby-cairo: new, 1.15.9
fbd6e7b97 gnuradio: fix build
2eda8a7cd ruby-text: new, 1.3.0 (noarch)
dd05b121e ruby-locale: new, 2.1.2 (noarch)
1086ac4c5 ruby-gettext: new, 3.2.3 (noarch)
0d046495b ruby-glib2: new, 3.1.7
d0b1f3afc ruby-gobject-introspection: new, 3.1.7
d4a2ff37a ruby-cairo-gobject: new, 3.1.7
48e400cbd ruby-pango: new, 3.1.7
73aaf227f ruby-gio2: new, 3.1.7
ac7aac3a3 ruby-gdk-pixbuf2: new, 3.1.7
cd3f88bab ruby-atk: new, 3.1.7
bfcf6162e ruby-gtk2: new, 3.1.7
d679080d3 screenruler: new, 0.9.6 (noarch)
c68b7c67e gnuradio: move flag adjustment to prepare
04bd3d958 pygame: new, 1.9.3
79692288c pyaudio: new, 0.2.11
53eeddbf5 beautifulsoup: new, 3.2.1 (noarch)
b839ffd6c anki: new, 2.0.43 (noarch); fix #657
59ab9c46e pygeoip: new, 1.3.2
81d9269de txtorcon: new, 0.19.3 (noarch)
dbeb74675 tqdm: new, 4.14.0
1cdb8f0ea hkdf: new, 0.0.3 (noarch)
8703b4fc6 spake2: new, 0.7 (noarch)
9c76d1d49 pynacl: new, 1.1.2
e427281fc humanize: new, 0.5.1 (noarch)
a2aa2f1ec txaio: new, 2.8.0 (noarch)
78771f34f autobahn: new, 17.6.2 (noarch)
f91110842 ipaddress: update to 1.0.18 (noarch)
3e44e1f69 twisted: update to 17.5.0
d047e6c40 hyperlink: new, 17.2.1 (noarch)
3b6928d5a twisted: add hyperlink dep
6789265a0 automat: update to 0.6.0 (noarch)
56abfdb61 magic-wormhole: new, 0.10.2
2fd121a41 snappy: use CMake to fix sover
da1f76add ed: drop alternative priority to 10
000054f93 ruby-pkg-config: bump EPOCH for a mistake
c5b723240 anki: add httplib2 dep
9f80baffe snappy: add missing so symlink
40daf665b netease-cloud-music: update to 1.0.0+2
ee32a7056 ilibrtlsdr: new package
4b8775612 hackrf: new package
3c17818aa fixes for librtlsdr and hackRF
10d200cc6 mdp: add, 1.0.9
ebfab97c5 acbs: new, 20170417 (noarch)
ab45d777b bladerf: new package
e48f6394e bladerf: fix PKGNAME and add version vars
b6ec82e08 networkmanger: disable resolvconf binding; fix #667
c0038a867 systemd: update to 234
2f4424685 qt-5: fix build
90ba9813e mesa: add libunwind to dep, llvm to builddep
088224d76 neovim: move xclip to dep
14aa27f72 libgit2: add breakage
c695130d1 pygit2: update to 0.26.0 (libgit2)
f1ae7f398 libgit2-glib: rebuild (libgit2)
0166bb190 libgit2: add geany-plugins breakage
041663b35 geany-plugins: rebuild (libgit2)
f86dcb3e7 regex: new, 2017.07.11
05e8fd0a1 calibre: add regex to dep
7943e7345 Revert "qt-5: fix build"
77af0ffe5 ppsspp: workaround build on armv8
5f48e0e5b libdbusmenu: update to 16.04.0
65d527e44 libdbusmenu-qt: update to 0.9.3+16.04.20160218
1dbd09ea5 menumaker: update to 0.99.10
ca9a69eea vivaldi-ffmpeg-codecs: new, 59.0.3071.104
fa97c2947 mesa: more features for arm*
3397a2866 taisei: enable LTO to fix build
3a0d77176 dump1090: new package
75ab4dae3 vivaldi-ffmpeg-codecs: corrected autobuild define's file name typo
bfd8655b0 vivaldi-ffmpeg-codecs: corrected the dependency name typo
3bb42bbd9 mariadb: add compat symlink and options from Fedora
5966e675b autobuild3: update to 20170718 (noarch)
ff96fae1f acbs: update to 20170725 (noarch)
953d44956 tor: arm64 build support
732e83464 calligra: limit vc to amd64
59ee871b9 ki18n: fix header support for Qt 5.9.1 (rebuild all)
ff90ad51e firefox: pull in some fixes from Fedora (rebuild all)
1fc915d38 kactivities4-runtime: fix build (no rebuild)
ec71c47d1 firefox: fix autobuild/patch
95ae2499f libkolab{,xml}: fix src links (no rebuild)
020c1bc25 kdepim-runtime: disable libkolab on non-amd64
daa7ca668 telepathy-qt: disable tests (no rebuild)
e24978025 libkdegames: fix src link and build (no rebuild)
debc04910 firefox: remove inappropriate flags (armel, arm64)
ea40f2cfa apt: fix src link (no rebuild)
b84b9b398 openscenegraph: fix build (no rebuild)
8df0c665b libdbusmenu: fix the dependency for gtk-2
6830cf7c8 wireshark: fix src link

Delayed Updates
-----------------

These changes listed in the paragraph below are changes intended but not implemented according to the original schedule for this month's updates.

- ceph: update to version 12.1.0
- linux-kernel: update for univt, unifont 10.0.30
- tensorflow: update to 1.2.1 

These changes are made to the `staging` (or main testing branch) **after** Day 25 and are thus excluded from this month's update.

1028a9a7e linux-kernel-lts: remove useless autobuild/patch
36e375622 linux-kernel-lts: upgrade to 4.9.38
0b6362ca4 linux+kernel+lts: bump VER for 4.9.38
348586760 linux-kernel: drop patch 0010 rtl8723bs drv
c0f077767 linux-kernel: drop patches 10* arm
ac1ac0ea8 linux-kernel: upgrade patch uksm to 4.12
f9799c25c linux-kernel: port patch 0019 to 4.12 manually
6459ec592 linux-kernel: update amd64, mips* config to 4.12
1a07e031d linux-kernel: re-gen exfat-nofuse patch for 4.12
d2d0a3473 linux-kernel: upgrade to 4.12.3
77af87db1 linux+kernel: bump VER for 4.12.3
03adc8e71 linux-kernel-lts: re-gen patch 0016 for Kernel 4.9
38a35cacc linux-kernel-lts: upgrade to 4.9.39
09c4df86e linux+kernel+lts: bump VER for 4.9.39
74cdf113e linux-kernel: remove useless autobuild/patch
cbdd8cdf9 accuraterip-checksum: new, 1.4
5e5b91058 pycdio: new 0.20
43634f1a2 whipper: new, 0.5.1
8fbbc70dd broadcom-wl: new, 6.30.223.271
0bcddf5ea epub2txt: upgrade to 0.1.4.20170701
203edc0c9 zynaddsubfx: bump to 3.0.2 
2e0798dd3 wildmidi: bump to 0.4.1
d98c09f26 freepats: fix source url (freepats classic gus pack)
3865f9f31 freepats2: new package
8da4a52b1 32subsystem: should only compile on amd64
659e5fc49 wine: upgrade to 2.13
f18c4eb2d icewm: new, 1.4.1
a4f672a46 icewm-themes: new, 1.2.26
0bd133c03 juffed: new, 0.10-85-g5ba17f9-11
0199ccc85 icewm: no unnecessary bump rel
aea9d0a10 tea: new, 44.1.0
6a5753b90 trojita: new, 0.7
25588edae trojita: fix the cmake parameter for qmake
8e9f40a2e icewm: fix the sources' permission problem during packaging
e01fad050 juffed: add lost dependency "qscintilla", and make it using Qt5
c5a8ae573 juffed: fix qscintilla no found problem
f7574cb34 juffed: fix the line break typo caused by GNU nano in the qscintilla patch
6078b99fd tea: change the source tarball upstream
0027abd3b tea: change "make install" parameter from DESTDIR to INSTALL_ROOT
16a9593a4 v2ray: new, 2.33.1
a7f8bc8bf v2ray: change the architecture checking method
a383b2a02 v2ray: fix some mistake in build script
88f09d5e9 v2ray: add a new systemd service file
318bef10d azpainter: update to 2.0.6, fix the translation problem in 2.0.6
1e36c7e86 azpainter, v2ray, icewm, icewm-themes: Add missing quotations
3c2edf752 funcsigs: upgrade to 1.0.2, fix upstream link
da36a2b36 nbd: new, 3.16.1
f1d086859 nbd: fix systemd service file installation

Bugfix Updates
----------------

These updates were committed and made available to AOSC OS throughout the month as bug fix updates, and could contain major functionality improvements and security updates, the list below, like those listed in the two sections above, is a list of Git commits made to this particular branch (again, slightly edited for reference).

c7f442bb1 cyanberry-config: update to 0.1.2 (noarch)
9a7dd708c libgcrypt{,+32}: update to 1.7.8 (security); fix #671
7d004ff46 unrar: update to 5.5.5 (security); fix #670
3175e02f8 perl-dbd-mysql: update to 4.043 (security); fix #673
ef97fdb98 Corrected a package dependency typo in the package "abiword". (User Report)
c1f7a149c abiword: bump REL for bugfix
1f6b4aeab firmware-wifi-ap6212: update to contain both a0 and a1
83dd03959 linux-kernel: fix typo in post-action scripts
5be47e120 linux-kernel-libre: fix typo in post-action scripts
5222e3263 linux-kernel: WTF is this?
00b2eac7a linux-kernel-libre: I was like ??????
cfdf50dde sqlite: fix CVE-2017-10989; fix #674 (security)
dcb24ccf6 pinentry: fix dep
33a5f3815 wireshark: add speex dep
87e8886ab shadow: fix #676
2ce852dd9 mpg123{,+32}: update to 1.25.2 (security); fix #677
bb35cd78c evince: fix CVE-2017-1000083; fix #679
23102959e spice: fix CVE-2017-7506; fix #680
6193775ca graphicsmagick: fix CVE-2017-11403; fix #682
6c5d2b328 grub: remove patch 10009 (revert #451)
7a9f7ad87 grub: bump REL for rebuild
bbcf79ac1 smartmontools: add ConditionVirtualization to systemd unit
212b93dcf speech-dispatcher: disable shadow build
d8ac7cf5d speech-dispatcher: bump REL for rebuild
ec2da357c mesa: add libunwind to dep, llvm to builddep
eafdca48a evince: rebuild for build failure
2d54b2072 firmware-wifi-ap6212: change build to reflect armbian directory structure change
b0251a6e7 modemmanager: fix build and dell plugin linkage
b0076ab32 open-vm-tools: security update; fix #686 (amd64)
a27cd7bee linux-kernel: hotfix #687
5448de665 linux-kernel: hotfix #687
bdd70f804 linux-kernel-libre: hotfix for liberal broadcom #687

Problems sir?
---------------

- Report any issue to our [Issues](https://github.com/AOSC-Dev/aosc-os-abbs/issues) page.

Or alternatively...

- Find us on the #aosc IRC channel, Telegram group information will be provided if requested on IRC.
- Send us an e-mail at [discussions@lists.aosc.io](mailto:discussions@lists.aosc.io).
