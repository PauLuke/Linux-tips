To use the auto-generated subtitles on Shotcut on Linux you have to provide whisper.cpp and a ggml model. Here is how you install it:

## 1. First clone the repository:
```
git clone https://github.com/ggml-org/whisper.cpp.git
```

## 2. Navigate to the new directory:
```
cd whisper.cpp
```

## 3. Then, download one of the Whisper [models](https://github.com/ggml-org/whisper.cpp/blob/master/models/README.md) converted in ggml format. For example:
```
sh ./models/download-ggml-model.sh base.en
```

## 4. Now build the project
```
cmake -B build
```
```
cmake --build build --config Release
```

## How to transcribe an audio file:
```
./build/bin/whisper-cli -f samples/jfk.wav
```
