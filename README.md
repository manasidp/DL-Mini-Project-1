# DL-Mini-Project-1

In this zipped folder I am uploading the following files:
project1_model.py : This is our Resnet model 
project1_model.pt : The modified weights of our model
main.py: File used to run the model 
self_eval.py : File provided by professor to run locally 
util.py : for running main.py file as it uses progress bar

The self_eval.py file has been modified with the normalization method we used.
The model has been saved using the command professor mentioned since we used data parallelization.
The earlier problem was also due to the function not being named project1_model() in the project1_model.py file.
All this was resolved and an accuracy of 94.7 % was achieved on self_eval.py 

We ran our program using sbatch file.
In the file along with GPU specification, we ran the main.py file as follows

#!/bin/bash
#SBATCH --nodes=1
#SBATCH --ntasks-per-node=1
#SBATCH --cpus-per-task=1
#SBATCH --time=8:00:00
#SBATCH --mem=16GB
#SBATCH --gres=gpu
#SBATCH --job-name=manasijob
#SBATCH --output=manasieval.out

  
module load amber/openmpi/intel/20.06;
module load anaconda3/2020.07;
source /share/apps/anaconda3/2020.07/etc/profile.d/conda.sh;
conda activate ../penv;
python3 ./main.py

You can similarly run self_eval.py file by replacing the python execution line.

python3 ./self_eval.py
