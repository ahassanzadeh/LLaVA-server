# LLaVA-server

Serves LLaVA inference using an HTTP server. Supports batched inference and caches the embeddings for each image in order to produce multiple responses per image more efficiently.

## Usage
1. Clone this repository and navigate to LLaVA folder
```bash
git clone https://github.com/haotian-liu/LLaVA.git
cd LLaVA
```

1.5 Install Miniconda  

``` Shell
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -rf ~/miniconda3/miniconda.sh

~/miniconda3/bin/conda init bash
~/miniconda3/bin/conda init zsh

```

The restart the terminal session. 


2. Install LLava Package
```Shell
conda create -n llava python=3.10 -y
conda activate llava
pip install --upgrade pip  # enable PEP 660 support
pip install -e .
```

3. Install LLava server packages
4. 
 
```bash
gunicorn "app:create_app()"
```
You must modify `gunicorn.conf.py` to change the number of GPUs.
