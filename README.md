# Bash Commands
Frequently used commands summary

## Linux System
 ```Bash
sbatch --nodes=1 --time=01:00:00 --partition=hour --mail-user=hong.xu@psi.ch --job-name=clean-folder /das/work/p12/p12926/codes_Hong/submit_whatever_to_slurm.py python fltp_sin_empty_folders_clean.py

grep '-c' /das/work/p12/p12926/tomcat_20181128_t18d/*/logs/*.cla

find /das/work/p12/p12926/tomcat*t17c*/disk1/disk1/t17c*/ -type d -name "sino_fltp*" -exec rm -r "{}" \;

```

## GPU System
 ```Bash
 ssh -Y afs_account@ra.psi.ch
 salloc --account=gpu -p gpu -t 7-00:00:00
 ssh -Y ra-gpu-001
 
 #create env for GPU system
conda create --prefix /das/work/p12/p12196/PythonEnv/tfgpu36 tensorflow-gpu=1.14.0 python=3.6
source activate /das/work/p12/p12196/PythonEnv/tfgpu36

 # Set only one GPU visible to tensorflow
os.environ["CUDA_VISIBLE_DEVICES"]="0"  #Could be GPU card number 0, or 1, 2, 3

```

## beamtime t18e
 ```Bash

python /das/work/p12/p12926/codes_Hong/pyScript_t18e/reconstructor_multiscan_angles_Hong.py -Di /das/work/p16/p16830/tomcat_20181205_t18e/t18e_T202_60C_30Sc_2_/t18e_T202_60C_30Sc_2_.h5 -recType pag -recFormat 0 -pixelMask /das/work/p12/p12926/codes_Hong/pyScript_t18e/maskFull4_t18e.DMP -leftCut 0 -rightCut 0 -centOfRot 1023 -x c1023_Centest -firstScan 1 -lastScan 1
```
