## 1.PCM2WAV
```
input_dir=$1

for f in $(ls ${input_dir}); do 
    echo "Processing $f"
    sox -t raw -c 1 -e signed-integer -b 16 -r 16000 ${input_dir}/$f ${input_dir}/$(echo $f | cut -d . -f1).wav
done
```

## 2.Resampling wav
```
sox -t wav ${input_wav_filepath} "-G" "-r" "16000" "-b" "16" "-c" "1" ${output_wav_filepath}
```

## 3.m4a2wav
```
avconv -i ${input_wav_filepath} ${output_wav_filepath}
```

## 4. shell list
```
speaker_list=(
xiaoming
xiaohong
)

for speaker in ${speaker_list[*]};do
    echo $speaker
done
```

## 5.Tensorboard
```
port=1024
netstat -nap | grep ${port} | grep LISTEN | awk '{print $7}' | awk -F '/' '{prinnt "kill -9 "$1}' | sh
tensorboard --port ${port} --logdir new_name:events_logdir
```

## 6.Random copy
```
ls | shuf -n 100 | xargs -i cp {} ${output_dir}
```

## 7.Batch remove file
```
 for speaker_name in $(ls ${root_dir});do
     outdir=path
     ls $outdir | wc -l
     for file in $(ls ${outdir})};do
         if [[ $file = *.txt ]];then
             echo "delete $outdir/$file"
             rm -rf $outdir/$file
         fi
     done
 done
```



