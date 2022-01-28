
To initialize a new tutorial, 
    PROJECT_NAME=my_project
    git clone https://github.com/pprados/git-for-tutorial.git $PROJECT_NAME &&\
    cd $PROJECT_NAME &&\
    rm -rf .git &&\
    git init --template tutorial_git && \
    rm -rf tutorial_git && \
    git branch

Then, you have two branch:
    - `soluce` with the descriptions, exercises and solutions
    - `student` the student branch

When you commit the branch `soluce`, the branch `student` in synchronized.
But, to remove the response, you must add a file `./purge.sh`
with command to remove the solutions:

    #!/bin/sh
    git rm -rf --ignore-unmatch -q ext1/soluce.md
̀
Now, every time you push, the `main` branch is pushed to, but after 
the purge step.