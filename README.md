# Bash Commands
Frequently used commands summary

## Linux System
 ```Bash
sbatch --nodes=1 --time=01:00:00 --partition=hour --mail-user=hong.xu@psi.ch --job-name=clean-folder /das/work/p12/p12926/codes_Hong/submit_whatever_to_slurm.py python fltp_sin_empty_folders_clean.py

grep '-c' /das/work/p12/p12926/tomcat_20181128_t18d/*/logs/*.cla

find /das/work/p12/p12926/tomcat*t17c*/disk1/disk1/t17c*/ -type d -name "sino_fltp*" -exec rm -r "{}" \;

du -h --max-depth=1 | sort -hr

rsync -r -v --dry-run --include='t19a*T30*/' --include='t19a*T30*/*.*' --exclude='*' /sls/TOMCAT/Data10/e12926/disk15/ /das/work/p12/p12926/tomcat_20190828_t19a/

```

## Nvidia GPU | tensorflow-gpu System
 ```Bash
 #get a gpu node on RA cluster
 ssh -Y afs_account@ra.psi.ch
 salloc --account=gpu -p gpu -t 7-00:00:00
 ssh -Y ra-gpu-001
 
 #mornitoring GPU performance/utility
 watch -d -n 0.5 nvidia-smi
 
 #create env for GPU system
module load psi-python36/4.4.0
conda search -c anaconda tensorflow-gpu
conda create --prefix /das/work/p12/p12196/PythonEnv/tfgpu36 tensorflow-gpu==1.14.0 python=3.6
source activate /das/work/p12/p12196/PythonEnv/tfgpu36
conda list

 # Set only one GPU visible to tensorflow
os.environ["CUDA_VISIBLE_DEVICES"]="0"  #Could be GPU card number 0, or 1, 2, 3

```
## Jupyter on Mac
 ```Bash

conda create -n p37tf python=3.7
conda activate p37tf
conda install jupyter notebook
conda install tensorflow==1.13.1 scipy==1.1.0 pillow
conda install -c anaconda ipykernel
python -m ipykernel install --user --name=py37tf #TO get  new env available in jupyter
jupyter #type in command line

```
%matplotlib inline
%config InlineBackend.figure_format = 'retina'
```
$$
y = \frac{a}{b+c}
$$
```
%%timeit  #for whole cell
def func():
%timeit func()  #for a func 

## beamtime t18e
 ```Bash

python /das/work/p12/p12926/codes_Hong/pyScript_t18e/reconstructor_multiscan_angles_Hong.py -Di /das/work/p16/p16830/tomcat_20181205_t18e/t18e_T202_60C_30Sc_2_/t18e_T202_60C_30Sc_2_.h5 -recType pag -recFormat 0 -pixelMask /das/work/p12/p12926/codes_Hong/pyScript_t18e/maskFull4_t18e.DMP -leftCut 0 -rightCut 0 -centOfRot 1023 -x c1023_Centest -firstScan 1 -lastScan 1
```
