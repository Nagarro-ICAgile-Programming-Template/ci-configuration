# CI repository for shared workflows

This repository contains build shared worksflows for all repositories in the template. 

## Available workflows

### .NET

The shared workflow is available via `.github/workflows/dotnet.yml` It contains a job to checkout, build an test a .NET solution. The build provides an .NET environment for version 6.0.

```
jobs:  
  call-dotnet-job:
    uses: Nagarro-ICAgile-Programming-Template/04-refactoring-bingo/.github/workflows/dotnet.yml@main
    secrets: inherit
```

### Java

The shared workflow is available via `.github/workflows/maven.yml` It contains a job to checkout, build an test a Java project. The build provides an environment for with Java 17 runtime.

```
jobs:  
  call-maven-job:
    uses: Nagarro-ICAgile-Programming-Template/04-refactoring-bingo/.github/workflows/maven.yml@main
    secrets: inherit
```

## Directory layout and naming conventions

The workflows need a specific directory layout to be reused. Take care that the names are case-sensitve.

```
+ my-repo
  + csharp
    mysolution.sln
  + java
    pom.xml
```

For the .NET build there must be a solution file in the root of the `csharp` directory. You can take any name for your solution and project folders.

In the root of your `java` directory there must be a `pom.xml'. The structure should follow common Maven rules.
