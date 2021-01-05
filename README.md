# NORMINETTE_VM_INSTALL

Still working on it, don't destroy your computer please...

For people who struggle to install the new norminette on the VM, here are the steps I had to do :

Installing Python3.7 and making an alias and symbolic link to define python3 as python3.7
```sudo apt update -y
sudo apt install python3.7
echo "alias\ python3='python3.7'" >> ~/.zshrc
sudo rm /usr/bin/python3
sudo ln -s /usr/bin/python3.7 /usr/bin/python3
source ~/.zshrc
```

Installing norminette and requirements
```sudo git clone https://github.com/42School/norminette.git
cd ./norminette
pip3 install -r requirements.txt
sudo -H pip3 install --upgrade setuptools
pip3 install importlib.metadata
sudo -H python3 setup.py install
```

Changing the alias of norminette
```
sed -i '/alias\ norminette=/d' ~/.zshrc
echo "alias\ norminette='norminette'" >> ~/.zshrc
source ~/.zshrc
```
