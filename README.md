# NebulaNexCoin
# A .gitignore file létrehozása
echo "target/" > .gitignore
echo "*.log" >> .gitignore
#.github/workflows/ci.ymlname: CI

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up JDK 11
      uses: actions/setup-java@v1
      with:
        java-version: '11'
    - name: Build with Maven
      run: mvn clean install
