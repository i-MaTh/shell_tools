# 1.PCM2WAV
```
input_dir=$1

for f in $(ls ${input_dir}); do 
    echo "Processing $f"
    sox -t raw -c 1 -e signed-integer -b 16 -r 16000 ${input_dir}/$f ${input_dir}/$(echo $f | cut -d . -f1).wav
done
```
