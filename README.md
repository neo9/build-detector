# Build Detector

![Build Detector](https://banners.beyondco.de/Build%20Detector.png?theme=light&packageManager=&packageName=docker+pull+neo9sas%2Fbuild-detector&pattern=architect&style=style_1&description=Smart+CLI+utility+to+simplify+CI%2FCD+builds&md=1&showWatermark=1&fontSize=100px&images=play)

Build Detector is a small CLI written in Bash that aims to simplify CI/CD by automatically detecting the build environment for a given project using Docker, Buildpack, or custom rules.

## Usage

Build Detector is primarily designed to be used within a Tekton task. However, you can also test it locally by setting up the following environment variables:

### Environment Variables

1. `PARAMS_BRANCH_OVERRIDE`: Override the detected branch name for the project. If the value matches the regular expression `^v([0-9]+\.){0,2}(\*|[0-9]+)([-,a-z,0-9]*)$`, it is considered a tag.

2. `PARAMS_BUILD_FORMAT_OVERRIDE`: Override the detected build format for the project. This variable allows you to specify a custom build format.

3. `PARAMS_BUILD_TOOL_OVERRIDE`: Override the detected build tool for the project. This variable allows you to specify a custom build tool.

4. `PARAMS_CHART_NAME_OVERRIDE`: Override the detected Helm chart name for the project. This variable allows you to specify a custom Helm chart name.

5. `PARAMS_CHART_VERSION_OVERRIDE`: Override the detected Helm chart version for the project. This variable allows you to specify a custom Helm chart version.

6. `PARAMS_DEPLOY_ENABLED`: When set to "true", indicates that the project should be deployed.

7. `PARAMS_DIRECTORY`: Specify the directory to search for the project's build files. The build detector will look for files like `Dockerfile`, `build.gradle`, `pom.xml`, and `package.json` in this directory.

8. `PARAMS_DOCKERFILE_OVERRIDE`: Override the default Dockerfile path. This variable allows you to specify a custom Dockerfile location.

9. `OUTPUT_PATH`: Specify the directory where the build-detector.json output file will be saved. Defaults to the current directory if not set.

10. `OUTPUT_NAME`: Specify the name of the output file (build-detector.json). Defaults to "build-detector.json" if not set.

## License

Build Detector is open-source software licensed under the MIT License. You can find the full license text in the [LICENSE](https://choosealicense.com/licenses/mit/) file.
