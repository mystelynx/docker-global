# docker-global

## base image

```
docker run --rm -i -t -v $PWD:/src mystelynx/docker-global
```

`/src` is a working directory.

## gtags

```
docker run --rm -i -t -v $PWD:/src --entrypoint gtags mystelynx/docker-global --gtagslabel=pygments -v
```

generate GTAGS, GRTAGS, GPATHS in the container. (share with local by `-v`)

## global

```
docker run --rm -i -t -v $PWD:/src mystelynx/docker-global -ax -t Hello
```

use `global` installed in the container or on local system.

