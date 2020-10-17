# TTS

Setting up festvox TTS

http://www.festvox.org/festival/index.html

## Local Installation (Ubuntu)

### clone the repository
git clone https://github.com/ranuzz/tts_festvox.git

### change directory 
cd tts_festvox/

### download packages
cd packages/ <br />
wget http://www.festvox.org/packed/festival/2.5/speech_tools-2.5.0-release.tar.gz <br />
wget http://www.festvox.org/packed/festival/2.5/festival-2.5.0-release.tar.gz <br />
wget http://www.festvox.org/packed/festival/2.5/festlex_CMU.tar.gz <br />
wget http://www.festvox.org/packed/festival/2.5/festlex_OALD.tar.gz <br />
wget http://www.festvox.org/packed/festival/2.5/festlex_POSLEX.tar.gz <br />
wget http://www.festvox.org/packed/festival/2.5/voices/festvox_cmu_indic_hin_ab_cg.tar.gz <br />
wget http://www.festvox.org/packed/festival/2.5/voices/festvox_cmu_us_slt_cg.tar.gz <br />
wget http://www.festvox.org/packed/festival/2.5/voices/festvox_kallpc16k.tar.gz <br />

### Extract packages
cd .. <br />
tar -xvzf packages/speech_tools-2.5.0-release.tar.gz <br />
tar -xvzf packages/festival-2.5.0-release.tar.gz <br />
tar -xvzf packages/festlex_CMU.tar.gz <br />
tar -xvzf packages/festlex_OALD.tar.gz <br />
tar -xvzf packages/festlex_POSLEX.tar.gz <br />
tar -xvzf packages/festvox_cmu_indic_hin_ab_cg.tar.gz <br />
tar -xvzf packages/festvox_kallpc16k.tar.gz <br />
tar -xvzf packages/festvox_cmu_us_slt_cg.tar.gz <br />

### make sure build essentials are present
sudo apt-get update <br />
sudo apt-get install build-essential <br />
sudo apt-get install libncurses5-dev libncursesw5-dev <br />

### compile speech_tools
cd speech_tools <br />
./configure <br />
make <br />

### compile festival
cd ../festival/ <br />
./configure <br />
make <br />

### ref
http://www.festvox.org/docs/manual-2.4.0/festival_6.html#Installation


## site setting

vim festival/lib/siteinit.scm

add (set! voice_default 'voice_cmu_indic_hin_ab_cg)

## text2wave command

 festival/bin/text2wave sample.txt -o sample.wav
 

## Python setup

### pre-requisite
python 3.5+ <br />
sudo apt-get install python3-pip <br />
sudo apt-get install python3-venv <br />
sudo apt-get install libsndfile1 <br />

### create virtual environment

python3 -m venv .env

### activate environment

source .env/bin/activate

### install python dependencies

pip3 install -r requirements.txt

