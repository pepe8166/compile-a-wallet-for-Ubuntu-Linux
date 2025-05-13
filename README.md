````markdown
🚀 To compile a wallet for **Ubuntu Linux** on **Ubuntu Server 22.04**, follow this single continuous guide:

🔄 First, update your system:

```bash
sudo apt-get update && sudo apt-get upgrade -y
````

📦 Then install the required dependencies:

```bash
sudo apt-get install make automake cmake curl g++-multilib libtool binutils-gold bsdmainutils pkg-config python3 patch bison -y
```

📁 Create a directory to hold the source code:

```bash
cd ~/
mkdir source_code
cd source_code
```

🌐 Download the Pepe3 source code:

```bash
wget "https://dl.walletbuilders.com/download?customer=f0579c48bb63bd0c8a64297876a42fcb05630a49e7f9a82d94&filename=pepe3-source.tar.gz" -O pepe3-source.tar.gz
```

🗂️ Extract the archive:

```bash
tar -xzvf pepe3-source.tar.gz
```

💻 For **64-bit systems**:

```bash
PATH=$(echo "$PATH" | sed -e 's/:\/mnt.*//g')
cd depends
make HOST=x86_64-pc-linux-gnu
cd ..
```

🛠️ Compile the wallet:

```bash
./autogen.sh
CONFIG_SITE=$PWD/depends/x86_64-pc-linux-gnu/share/config.site ./configure --prefix=/
make
```

🧹 Optional clean-up after build:

```bash
make clean
```

💻 For **32-bit systems**:

```bash
PATH=$(echo "$PATH" | sed -e 's/:\/mnt.*//g')
cd depends
make HOST=i686-pc-linux-gnu
cd ..
```

🛠️ Compile the wallet:

```bash
./autogen.sh
CONFIG_SITE=$PWD/depends/i686-pc-linux-gnu/share/config.site ./configure --prefix=/
make
```

📦 The compiled wallet (Qt GUI) will be in the directory `src/qt`, and the command-line tools like `pepe3d`, `pepe3-cli`, and `pepe3-tx` will be in the directory `src`.

```
```
