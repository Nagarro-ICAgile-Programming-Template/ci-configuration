# ci-configuration

This repository contains build shared worksflows for all repositories in the template. 

## Available workflows

- .github/workflows/dotnet.yml: a job to checkout, build an test a .NET solution
- .github/workflows/maven.yml: a job to checkout, build an test a .NET solution

## How to call

This is an example how to call the .NET github actions in your yml file.

`
jobs:  
  call-dotnet-job:  
    uses: Nagarro-ICAgile-Programming-Template/04-refactoring-bingo/.github/workflows/dotnet.yml@main
`
