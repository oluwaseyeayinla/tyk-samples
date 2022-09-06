
## Windows Commands

### Prerequisite

```
VER = <version number>
docker pull tykio/tyk-sync:v%VER%
```


### Dump command
CD into your target directory and brimg up the command prompt

```
docker run ^
--rm --mount type=bind,source="%cd%",target=/opt/tyk-sync/tmp ^
tykio/tyk-sync:v%VER% dump ^
-d <dashboard-endpoint> ^
-s <dashboard-secret> ^
-t="./tmp"
```


### Sync Command
```
docker run ^
--rm --mount type=bind,source="%cd%",target=/opt/tyk-sync/tmp ^
tykio/tyk-sync:v1.2.1 sync ^
-b "refs/heads/master" https://github.com/oluwaseyeayinla/tyk-samples.git ^
-d https://worldwide-alpaca-adm.aws-use1.cloud-ara.tyk.io/ ^
-o 61fd63e8a35fd4000162ed94 ^
-p "./tmp" ^
-s c0b882b1616f4efa72f7c35effff19dc
```

```
docker run ^
--rm --mount type=bind,source="%cd%",target=/opt/tyk-sync/tmp ^
tykio/tyk-sync:v1.2.1 sync ^
-b "refs/heads/master" https://github.com/oluwaseyeayinla/tyk-samples.git ^
-d https://worldwide-alpaca-adm.aws-use1.cloud-ara.tyk.io/ ^
-p "./tmp" ^
-s c0b882b1616f4efa72f7c35effff19dc
```