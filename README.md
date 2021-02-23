# NORMINETTE_VM_INSTALL

Here is a guideline to install the new norminette on the VM. Please follow the steps one line at a time. Don't continue if you get an error.

If you think this is not the right way to do it or if you've faced other problems, please tell me in the "issues" section.


Install Python3.7 : (if you have an error with "dpkg", close and reopen your VM)
```
sudo apt update -y
sudo apt install python3.7
```

Make an alias and symbolic link to define python3 as python3.7 :
```
echo "alias python3='python3.7'" >> ~/.zshrc
sudo ln -sf /usr/bin/python3.7 /usr/bin/python3
source ~/.zshrc
```

Check your version : 
```
python3 -V
    Python 3.7.x
```

Install norminette and requirements :
```
sudo git clone https://github.com/42School/norminette.git
cd ./norminette
pip3 install -r requirements.txt
sudo -H pip3 install --upgrade setuptools
pip3 install importlib.metadata
sudo -H python3 setup.py install
```

Comment the alias of norminette V2: (you still have the reference to the V2 in the .zshrc if you want to switch back)
```
sed -i -e s/"alias norminette="/"# alias norminette="/g ~/.zshrc
source ~/.zshrc
```

Check your version : (if your version is not 3.0 or above, close and reopen your terminal and try again)
```
norminette --version
    norminette 3.x
```


Thanks to cdai and mescande for the help
