# Sub Module Usage

Git repos generically use submodules to store all thier dependancies. As for as I can tell, they are used a bit like python packages. i.e "install" the submodule and then one shall have acess to everything in it. This is shown below:

``` mermaid

stateDiagram-v2

  State RepoA {
      [*] --> SourceA
      SourceA --> RepoB
      [*] --> RepoB

      State RepoB {
        [*] --> SourceB
        SourceB --> RepoC
        [*] --> RepoC

        State RepoC {
            [*] --> [*]
        }
      }
  }

```

## Adding a Submodule

1. Git 
