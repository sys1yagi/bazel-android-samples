# Setup 

## Generate BUILD file

AS generate `build` directory automatically. 
`build` directory and `BUILD` file collide in the case-insensitive environment.
So, avoid the collision by the following flow。

```sh
chmod +x setup_build_file.sh
./gradlew clean
./setup_build_file.sh
```

It generate a symbolic link of `BUILD_FILE`.
