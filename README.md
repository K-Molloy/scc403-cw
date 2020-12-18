# SCC 403 - Coursework

Please note the automl section will only run on UNIX based configurations due to python limitations.

## Installation
The script itself needs no installation, just copy it with the rest of the files in your working directory.
Alternatively you could use git clone
<pre>
sudo apt-get update && sudo apt-get install git && git clone https://github.com/K-Molloy/scc403-cw.git
</pre>

First performing the following commands. All are REQUIRED or errors will occur :)
<pre>
sudo apt-get update && sudo apt-get install git gcc build-essential swig python3-pip python3-virtualenv python3-dev
cd scc403-cw
pip install virtualenv
virtualenv venv -p /usr/bin/python3.8
source venv/bin/activate
curl https://raw.githubusercontent.com/K-Molloy/scc403-cw/master/requirements.txt | xargs -n 1 -L 1 pip install
</pre>

### Main
You will need various packages
Required
- build-essential
- python3dev
Optional
- pip
- virtualenv

<pre>
cd main && python3 ./bin/main.py -d ./data/SCC403CWWeatherData.txt
</pre>

For your convenience, all assets are already saved in `\doc` but generating will simply put everything in `\bin` to avoid confustion. 
This is then converted into hdf5 for the AutoML section using
<pre>
python3 ./bin/hdf-converter.py
</pre> 
N.B it seemed pointless implementing full infrastructure for this simple function

### AutoML
Again, this code is largely based upon a codebase from github user Motoratt

Installation is based upon Python3.8, please reconfigure virtualenv initialisation for your own python version.
You will need various packages
Required
- gcc
- build-essential
- swig
- python3dev
Optional Packages
- pip
- virtualenv

You can run this section with the following command :)
<pre>
cd scc403-cw/automl && python3 ./bin/zeroconf.py -d ./data/df_final.h5 > results.txt
</pre>
