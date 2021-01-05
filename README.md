# NORMINETTE_VM_INSTALL

For people who struggle to install the new norminette on the VM, here are the steps I had to do (from a virgin VM).

Please share whichever problem you've faced in the "issues" section.


Installing Python3.7 and making an alias and symbolic link to define python3 as python3.7 :
```sudo apt update -y
sudo apt install python3.7
echo "alias python3='python3.7'" >> ~/.zshrc
sudo ln -sf /usr/bin/python3.7 /usr/bin/python3
source ~/.zshrc
```


Installing norminette and requirements :
```sudo git clone https://github.com/42School/norminette.git
cd ./norminette
pip3 install -r requirements.txt
sudo -H pip3 install --upgrade setuptools
pip3 install importlib.metadata
sudo -H python3 setup.py install
```


Changing the alias of norminette :
```
sed -i '/alias norminette=/d' ~/.zshrc
echo "alias norminette='norminette'" >> ~/.zshrc
source ~/.zshrc
```


Check your version :
```norminette --version
norminette 2.52```
