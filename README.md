# Build detector

![](https://banners.beyondco.de/Build%20Detector.png?theme=light&packageManager=&packageName=docker+pull+neo9sas%2Fbuild-detector&pattern=architect&style=style_1&description=Smart+CLI+utility+to+simplify+CI%2FCD+builds&md=1&showWatermark=1&fontSize=100px&images=play)

Build detector is a small CLI written in Bash which aims to simplify CI/CD. It automatically detects and (possible)
build a given project using Docker/Buildpack/custom rule.


## Usage

```bash
# Only detect the project.
docker run --rm -v ~/Code/my-working-dir:/data neo9devops/build-detector build-detector detect --working-dir /data

# Detect and build the project.
docker run --rm -v ~/Code/my-working-dir:/data neo9devops/build-detector build-detector build --working-dir /data --registry $REGISTRY
```

### Help

```bash
Build detector.

This small utility aims to help building or detecting a project
using its framework.

Global options:

--working-dir=WORKING_DIR     Define the working directory.

Commands:

> build-detector detect [ --working-dir= ]

Output detection information in JSON.

> build-detector build  [ --working-dir= , --dockerfile=, --registry= ]

Detect and build the project by detecting the underlying framework.
You can optionnaly use a custom Dockerfile to build it (if not empty).
--dockerfile and --registry are optionals but you will need to parse
ouput in order to manually push the image to the registry.
```

## License
[MIT](https://choosealicense.com/licenses/mit/)
