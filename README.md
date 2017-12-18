# Techdoc-ja examples

## Requirements

- node v9.3.0
- Gitbook version 3.2.2
- RedPen 1.10.1
- textlint v10.0.0
- AWS CLI 1.14.11
- Java 1.8.0_131
- graphviz 2.38.0 (20140413.2041)

or

Docker image `dai0304/docker-techdoc-ja`

## Command examples

### build commands

```
$ gitbook install
$ gitbook serve
$ gitbook build . _book/html
$ gitbook pdf . _book/techdoc-example.pdf
```

### test command

```
$ find ./content -name "*.md" -type f | xargs redpen -l 0 -L ja -f markdown -c ./config/redpen-conf.xml
$ textlint --config ./config/textlint.json ./content
```

### deploy command

```
$ aws s3 sync _book s3://example-bucket --delete
```

### login to docker container

```
$ docker run --rm -it -v $(pwd):/root/workspace -w /root/workspace dai0304/docker-techdoc-ja bash
```
