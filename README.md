# svg-placeholder

## install dependencies

- https://github.com/fogleman/primitive
- https://github.com/technopagan/sqip


- `go` to get/run primitive
- `primitive` to convert images to svg/gif
- `imagequick` to support gif
- `ffmpeg` to convert to mp4/webm
- `sqip` to automate SVG with blur creation
- `serve` to serve files

```shell
brew install go ffmpeg imagemagick
go get -u github.com/fogleman/primitive
echo 'export PATH="${HOME}/go/bin:$PATH"' >> ~/.bash_profile
source ~/.bash_profile
npm install -g serve sqip
```

## generate svg & webp preview
```shell
sqip -o assets/prag.svg assets/prag.jpg
cwebp -q 0 -resize 0 100 assets/prag.jpg -o assets/prag.webp
```

## generate gif -> video
```shell
primitive -i assets/pontus.jpg -o assets/pontus.gif -n 100
ffmpeg -i assets/pontus.gif assets/pontus.mp4
ffmpeg -i assets/pontus.gif -c vp9 -b:v 0 -crf 41 assets/pontus.webm
```

## serve site
```shell
serve
```
