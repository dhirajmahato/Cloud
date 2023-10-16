1. Create Project directory
  ```
    mkdir project_name
    cd project_name
  ```
2. connect with git version control directory in local directory
  ```
    git init
    git add README.md   /  git add.  # for all files 
    git status # to check staging area
    git commit -m "first commit"
    git branch -M main
    git remote add origin git@github.com:dhirajmahato/dm_streamlit.git
    git push -u origin main
  ```
2. create project environment
```
    python3 -m venv myenv
    source myenv/bin/activate

    check package manager **pip**
      pip --version
      python3 -m pip install --upgrade pip # if pip not installed in virtual environment
```
3. Create requirements
```
    pip install -r requirements.txt
```
