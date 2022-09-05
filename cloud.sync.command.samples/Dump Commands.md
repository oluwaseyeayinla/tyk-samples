
## Windows Commands

### Prerequisite

```
VER = <version number>
docker pull tykio/tyk-sync:v%VER%
```


### Dump
CD into your target directory and brimg up the command prompt



```
docker run ^
--rm --mount type=bind,source="%cd%",target=/opt/tyk-sync/tmp ^
tykio/tyk-sync:v%VER% dump ^
-d <dashboard-endpoint> ^
-s <dashboard-secret> ^
-t="./tmp"
```