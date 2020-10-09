# CPSC4300/6300-001 PS02

You can check out this problem set in two ways: 
  1. From your Jupyter Notebook nbgrader's Assignments menu.
  1. From the github classroom URL.
  
To develop a good software development practice, the following workflow is highly recommended.

## step 1. Get the code
``` 
mkdir -p ~/cpsc6300-001
cd ~/cpsc6300-001
git clone git@github.com:cpsc6300/ps02-<your-github-account>.git ps02-work
nbgrader fetch_assignment ps02
```
## step 2: work on the assignment
You could work on your assignment under any environment. However, the Login VM environment is recommended because that is the enviornment we have tested the solution and are confident that all required packages have been properly installed in the courses/cpsc6300 Python environment. 

## step 3: commit the assignment to your git repo
```
cd ~/cpsc6300-001/ps01-work
git add part_a.ipynb part_b.ipynb
git commit -m "commit completed assignment"
git push
```

## step 4: sync the notebooks from git-work to ps02
```
cd ~/cpsc6300-001
rsync -av ps02-work/*.ipynb ps02/
```
## step 5: validate
```
cd ~/cpsc6300-001
for part in ps02/*.ipynb; do nbgrader validate $part; done
```
## step 6: submit the assignment
```
cd ~/cpsc6300-001
nbgrader submit ps02
```  

# Start a Jupyter Notebook Server on a Login VM

The following recipe applies when you start a Jupyter notebook server on a Login VM at the first time. You can skip any step you have done and directly go to the step that needs to be done.

  0. Connect to Clemson VPN if your computer on an off-campus network.
  1. Request a Login VM at https://www.palmetto.clemson.edu/loginvm/ (Links to an external site.) using the LoginVM-CPSC6300 template.
  2. Use ssh to connect the VM assigned to you.
  3. Create the folder ~/.jupyter  using the command: mkdir -p .jupyter
  4. Copy the nbgrader_config.py file from the course's shared folder into ~/.jupyter/ using the command:  rsync -av /zfs/courses/CPSC6300/files/nbgrader_config.py  ~/.jupyter/
  5. Start a screen session (see https://linuxize.com/post/how-to-use-linux-screen/ (Links to an external site.) for screen usage) using the command: screen
  6. Create a password for your Jupyter Notebook using the command: module load courses/cpsc6300; jupyter-notebook password
  7. Start the Jupyter notebook using the command: /zfs/courses/CPSC6300/bin/start-cpsc6300-jupyter
  8. Open a browser in you local computer and paste the URL in the output from step 7. Bookmark this URL.
  9. Detach the screen using the key sequence Ctrl-a + Ctrl-d to detach from the screen session.
  
Later on, you can simple open the url in your local computer to access the notebook.

In case you need to restart your notebook server, try the following steps:

  1. Connect your Login VM and restore your previous screen session (use command: `screen -r`). 
  2. Use key combination `CTRL`+`C` to terminate previous Jupyter Notebook session. 
  3. Use command `ps aux | grep -i jupyter` to find if the Jupyter is actually terminated. If not, use the command `kill -9 <jupyter-nodebook-server'spid>` to terminate the process.
  4. Start a new Jupyter Notebook Server session: /zfs/courses/CPSC6300/bin/start-cpsc6300-jupyter
  
# Code of Honors

You can discuss with your classmates or ask your TA about a particular question. However, you SHOULD NOT give your source file to anyone or accept a source file from anyone. If you have collaborated with someone, please acknowledge in the front.
