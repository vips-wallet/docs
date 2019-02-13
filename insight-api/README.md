# VIPSTARCOIN insight-api documents

## introduction

This document is [vipstarcoin-api](https://github.com/vips-wallet/vipstarcoin-api) endpoint document.

## usage

### preview

#### use CLI

```
npm install -g snowboard@1.8.13 --unsafe-perm
git clone https://github.com/vips-wallet/docs.git
cd docs/insight-api
snowboard http md/ja.md

# open http://localhost:8088/ in your browser
```

#### use Docker

```
git clone https://github.com/vips-wallet/docs.git
cd docs/insight-api
docker-compose -f docker-compose-http.yml up -d

# open http://localhost:3000/ in your browser
```

### generate html

#### use CLI

```
npm install -g snowboard@1.8.13 --unsafe-perm
git clone https://github.com/vips-wallet/docs.git
cd docs/insight-api
snowboard html -o html/ja.html md/ja.md
```

#### use Docker

```
git clone https://github.com/vips-wallet/docs.git
cd docs/insight-api
docker-compose -f docker-compose-html.yml up
docker-compose -f docker-compose-html.yml down
```

## license

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.en)

## author

- 海野山猿 (Yamazaru Umino)
- ましろ (white)
