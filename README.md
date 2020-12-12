# SCC 403 - Coursework - Linux Section

## Installation
The script itself needs no installation, just copy it with the rest of the files in your working directory.
Alternatively you could use git clone
<pre>
sudo apt-get update && sudo apt-get install git && git clone https://github.com/K-Molloy/scc403-cw-linux.git
</pre>

### Happy path installation on Ubuntu 18.04LTS
<pre>
sudo apt-get update && sudo apt-get install git gcc build-essential swig python-pip virtualenv python3-dev
git clone https://github.com/K-Molloy/scc403-cw-linux.git
pip install virtualenv
virtualenv venv -p /usr/bin/python3.6
source zeroconf/bin/activate
curl https://raw.githubusercontent.com/K-Molloy/scc403-cw-linux/master/requirements.txt | xargs -n 1 -L 1 pip install
git clone https://github.com/K-Molloy/scc403-cw-linux.git
cd scc403-cw-linux/ && python ./bin/zeroconf.py -d ./data/df_final.h5 > results.txt
</pre>