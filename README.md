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

## 3.Tensorboard
```
port=1024
netstat -nap | grep ${port} | grep LISTEN | awk '{print $7}' | awk -F '/' '{prinnt "kill -9 "$1}' | sh
tensorboard --port ${port} --logdir new_name:events_logdir
```

