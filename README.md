# slowed&reverb
Takes an audio file and a gif, outputs a slowed+reverb video (e.g http://tiny.cc/iprlez)
### NOTE!!! IT ONLY TAKES MP3!!!!!

### Setup 
install python 3 
install sox by homebrew or macports

## Linux & Mac
```
$ brew install sox
$ pip install -r requirements.txt
```

### Usage

```
$ python slowed-reverb.py -a <mp3 file> -g <gif file> -o <mp4 output>

e.g.
$ python slowed-reverb.py -a song.mp3 -g video.gif -o output.mp4
```

### Docker Setup

```
// install [docker] (https://www.docker.com/)

// build the docker image
$ docker build -t slowed-reverb:latest .

// move your files to the shared directory (shared between the docker container and your system)
$ mv /path/to/mp3 shared
$ mv /path/to/gif shared
```

### Usage

```
// run docker container
$ docker run -it --rm --name slowed-reverb --mount type=bind,source=$(PWD)/shared,target=/usr/src/app/shared slowed-reverb:latest -a <mp3 file> -g <gif file> -o <mp4 output>

e.g.
$ docker run -it --rm --name slowed-reverb --mount type=bind,source=$(PWD)/shared,target=/usr/src/app/shared slowed-reverb:latest -a shared/sample.mp3 -g shared/sample.gif -o shared/sample-output.mp4
```
