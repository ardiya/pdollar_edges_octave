# Modified [pdollar/edges](https://github.com/pdollar/edges) to run under Octave

This modification is tested under debian 9.0, with Octave 5.1(Lower version of octave might segfault)

This repo will contain .mex files needed for linux distribution so you can skip the .mex generation process and go on install

## (Optional) Compile cpp to mex
```
cd private
for item in edgesDetectMex.cpp edgesNmsMex.cpp spDetectMex.cpp edgeBoxesMex.cpp;
    do mkoctfile --mex -DMATLAB_MEX_FILE $item;
done
cd ..
```

## (Optional) [Copy](https://github.com/ardiya/BSR_bench_octave/blob/master/benchmarks/correspondPixels.mex) / [Create](https://github.com/ardiya/BSR_bench_octave) correspondPixels.mex
Then put it under `private/` folder

## Install (Add path to octave)
Run following commands in `octave`
```octave
addpath(pwd)
addpath(strcat(pwd, "/private"))
savepath
```
