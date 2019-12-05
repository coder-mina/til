## Bash script

  * hello.sh
  * chmod 700 hello.sh
  * ./hello.sh
  * ex) ffmpeg -i movie.mov -vcodec copy -acodec copy out.mp4 (convert mov to mp4)

## Conda

* conda create -n "kim" python=3.5, conda create --name tf_gpu tensorflow-gpu
* source activate "kim"
* conda env list
* conda env remove -n kim
* conda install -c anaconda tensorflow-gpu

## GPU

* track GPU usage: Nvidia-smi -l 1

