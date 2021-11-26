## Stack Ignore 

### Overview
When a new stack instance gets created, the stack author might not want to include every file in the stack repo to get cloned in the target repo. For example some of the CI/CD workflow/script used for testing the stack itself don't need to be included in the target repo. Inclusion of such files might even cause the new stack instance repo to have badly configured workflows. To solve this issue, the stack author can include a .stackignore file in the root folder of the repo. This file is similar in format to .gitignore file used by git. In this file the stack author can provide paths of files which do not need to be cloned to the target repo. 

### Stack Ignore syntax
The .stackignore file will use the glob pattern used by the .gitignore file. An example .stackignore file can look something like following 

```
# Example stack ignore file
/.github/
/.stackignore
**/test.yml

```

### Pattern format 
We are starting with support for a subset of .gitignore format. 

- A blank line matches no files. It can be used for readability. 
- A comment line begins with # character and is ignored. 
- / is used as path separater. 

More details on .gitignore format can be found [here](https://git-scm.com/docs/gitignore)
