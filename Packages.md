# Setup GIM Controller

Getting version

    lsb_release -a

Install cockpit

    . /etc/os-release
    sudo apt install -t ${VERSION_CODENAME}-backports cockpit


Install ISC dhcp server

    sudo apt update

    sudo apt install isc-dhcp-server

Install MongoDB 

    sudo apt update

    sudo apt upgrade

    wget -qO-  https://www.mongodb.org/static/pgp/server-4.4.asc | sudo tee /etc/apt/trusted.gpg.d/mongodb-archive-keyring.asc

    echo "deb [signed-by=/etc/apt/trusted.gpg.d/mongodb-archive-keyring.asc arch=arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list

update again

    sudo apt update

    sudo apt-get install -y mongodb-org

start mongo db in systemd:

    sudo systemctl start mongod

    sudo systemctl status mongod

You can optionally ensure that MongoDB will start following a system reboot by issuing the following command:

    sudo systemctl enable mongod

Start a mongo shell

    mongo

    