# Bulk change repository tool

Use these scripts to create pull requests and propose changes to multiple GitHub repositories. This 
is useful when making similar changes across multiple GitHub repositories. 

### Prerequisites

- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [GitHub CLI](https://cli.github.com/manual/installation) - You must authenticate from the 
  command line before using.
  
### Procedure
  
1.  Customize the [global-step1.sh](global-step1.sh) script with the path to your GitHub 
    repositories. For example:
    
    ```git clone git@github.com:joel-hamill/bulk-change-tool.git```
    
1.  From your terminal, run the script to clone the repos. ```./global-step1.sh```

1.  Make changes to multiple GitHub repositories. For example, to search for "thethe" and replace with "the:

    ```find . -name '*.rst' -print0 | xargs -0 sed -i "" "s/thethe/the/g"```
 
1.  Customize the [global-step2.sh](global-step2.sh) script with your information and
    commit and push your change to GitHub. For example:

    ```
    cd bulk-change-tool && git add filename && git checkout -b branchname \
    && git commit -m "commit message" && \
    git push origin HEAD && gh pr create --title "commit message" --fill 
    ```

