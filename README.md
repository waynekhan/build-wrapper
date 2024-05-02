# README

```text
brew install cmake

PROJECT_KEY=$(basename "`pwd`") && \
  rm -rf build-wrapper* build_wrapper* && \
  wget $SONAR_HOST_URL/static/cpp/build-wrapper-macosx-x86.zip && \
  unzip build-wrapper-macosx-x86.zip && \
  chmod +x ./build-wrapper-macosx-x86/build-wrapper-macosx-x86 && \
  ./build-wrapper-macosx-x86/build-wrapper-macosx-x86 --out-dir build_wrapper_output_directory make && \
  sonar-scanner \
    -Dsonar.host.url=$SONAR_HOST_URL \
    -Dsonar.projectKey=$PROJECT_KEY \
    -Dsonar.cfamily.build-wrapper-output=build_wrapper_output_directory \
  -X
```
