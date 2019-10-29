## Dockerize composer


* create executable composer by
```
touch /usr/local/bin/composer
chmod +x /usr/local/bin/composer
```
then paste the following contents

```
#/bin/bash

docker run --rm -v $(pwd):/app  composer:latest $@
```