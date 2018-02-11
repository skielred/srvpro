## SRVPro
This is forked from [moecube/srvpro](https://github.com/moecube/srvpro) in an
attempt to host my own YGOPro server supporting YGOPRO2, Link monsters and MR4.

## Installation (Debian)

Building mercury233/ygopro server
```bash
sudo apt-get update

sudo apt-get install premake4 liblua5.2-dev libirrlicht-dev mesa-common-dev libglu1-mesa-dev libfreetype6-dev

sudo ln -s /usr/lib/x86_64-linux-gnu/liblua5.2.so /usr/lib/liblua.so

git clone https://github.com/mercury233/ygopro.git -b server --recursive
cd ygopro
premake4 gmake
cd ocgcore && git checkout master && cd ..
cd script && git checkout master && cd ..
cd build && make config=release && cd ..
ln -s bin/release/ygopro .
strip ygopro
mkdir -p replay
cd ..
```

Downloading srvpro
```bash
git clone https://github.com/skielred/srvpro
cd srvpro
npm install
ln -s ../ygopro .
```

Starting srvpro
```bash
node ygopro-server.js
```
