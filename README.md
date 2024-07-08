# CI repository for shared workflows

This repository contains build shared worksflows for all repositories in the template. 

## Available workflows

### .NET

The shared workflow is available via `.github/workflows/dotnet.yml` It contains a job to checkout, build an test a .NET solution. The build provides an .NET environment for version 6.0.

```
jobs:  
  call-dotnet-job:
    uses: Nagarro-ICAgile-Programming-Template/04-refactoring-bingo/.github/workflows/dotnet.yml@main
```

### Java

The shared workflow is available via `.github/workflows/maven.yml` It contains a job to checkout, build an test a Java project. The build provides an environment for with Java 17 runtime.

```
jobs:  
  call-maven-job:
    uses: Nagarro-ICAgile-Programming-Template/04-refactoring-bingo/.github/workflows/maven.yml@main
```

## Directory layout and naming conventions

The workflows need a specific dirctory layout to be reused. Take care that the names are case-sensitve.

```
+ my-repo
  + csharp
    mysolution.sln
  + java
    pom.xml
```

For the .NET build there must be a solution file in the root of the `csharp` directory. You can tanke any name for your solution.

In the root of your `java` directory there must be a `pom.xml'. The structure should follow common Maven rules.

<div
    <ul id="repoList"></ul>

    <script>
        const orgName = 'Nagarro-ICAgile-Programming-Template'; // replace with your GitHub organization name
        const token = 'YOUR_PERSONAL_ACCESS_TOKEN'; // replace with your GitHub personal access token

        fetch(`https://api.github.com/orgs/${orgName}/repos`, {
            headers: {
                'Authorization': `token ${token}`
            }
        })
        .then(response => response.json())
        .then(data => {
            const ul = document.getElementById('repoList');
            data.forEach(repo => {
                const li = document.createElement('li');
                li.textContent = repo.name;
                ul.appendChild(li);
            });
        })
        .catch(error => console.error('Error:', error));
    </script>
</div>
