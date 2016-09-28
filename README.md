# docker-image_optim
A Dockerfile that builds every version of the best command line apps and then image_optim to rule them all

## credits
95% of this Dockerfile it's [rhardih](https://github.com/rhardih)'s work.

## changes
* creating more layers, so if you need to test different versions you can avoid full rebuilds.
* Versions have been bumped, and ordered alphabetically

## How To Use
```
docker run --rm -ti \
  # Add whatever image directory you like
  # -v $(cd && cd images && pwd):/images/ \
  -v $(pwd)/config:/root/.config/ \
  colthreepv/docker-image_optim sh
```

Then a simple `cd /images && image_optim -r .` would optimize all the images in the mounted path.

## How to Build
`docker build -t image_optim .`
and (after a while) you can run your custom-built image
```
docker run --rm -ti \
  # Add whatever image directory you like
  # -v $(cd && cd images && pwd):/images/ \
  -v $(pwd)/config:/root/.config/ \
  docker-image_optim sh
```

## configs
A demo configuration (LOSSY!) can be found in config/image_optim.yml, all the options are [listed here](http://www.rubydoc.info/gems/image_optim/)
