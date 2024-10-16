# Computational Thinking Lab - link list and FAQ

### link list 

1. anaconda installation: https://www.youtube.com/watch?v=xfAcErzOKN4
2. VS Code installation with python integration: https://www.youtube.com/watch?v=HvAjnpA6mlA
3. VS Code introduction: https://www.youtube.com/watch?v=UuwlySU7Hjg
4. git in VS Code: https://www.youtube.com/watch?v=i_23KUAEtUM
5. introduction to merge conflicts: https://www.youtube.com/watch?v=HosPml1qkrg
6. working with github classroom in VS Code: https://www.youtube.com/watch?v=iqW_yzZkU_8
7. (advanced) github classroom in the command line: https://www.youtube.com/watch?v=jXpT8eOzzCM
8. introduction to markdown: https://www.markdownguide.org/getting-started/
9. ... 

### problems with python errors

Please see <a href="https://github.com/CTL-PROJECTS/python-errors">this page</a>.

### problems with git pull/push from within vscode (git log error)

Open a terminal within vscode and execute the following commands to manually pull and push (instead of using the vscode commit buttom)

          git add .
          git pull
          git commit -m "test"
          git push

### problems with git (Mac users)

To check if your git installation operates properly with VS code, open VS code. Open a Terminal window from the menu bar (top). Enter: git --version. If an error message occurs, enter: git. This will install git. Afterwards, you may enter: git --version again to verify the installation. Then proceed with the two 'git config --global' items

          git config --global user.name "XXX"
          git config --global user.email XXX@YYY

### problems with git (Windows users)

To check if your git installation operates properly with VS code, open VS code. Open a Terminal window from the menu bar (top). Enter: git --version. If an error message occurs, enter: conda -V into the Terminal. If this gives an error as well, enter: conda activate. Then enter: git --version. If this gives an error, enter: conda install git. This will install git. Afterwards, you may enter: git --version again to verify the installation. Then proceed with the two 'git config --global' items

          git config --global user.name "XXX"
          git config --global user.email XXX@YYY

If you continue having trouble, open the command palette in VS code using crtl-shift+P and select or type 'python: Select Interpreter'. Switch the interpreter to 'base' from conda, which is the correct environment. 

If the above does not solve your problem, you might have installed Anaconda without leaving the checkbox 'ADD TO PATH' checked. We propose you deinstall and install Anaconda again, and this time keep the box checked. 

### How to check if setup is complete

1. login to www.github.com. click your github symbol. Check your profile. Check if you are member of the CTL organization and member of a group. If not, contact us.
2. start vscode, click on your accounts symbol, check if you are logged in to your github account from vscode, or log in.
3. vscode: click on Terminal. Execute: python --version (enter), git --version (enter) to see if python and git are installed. If not, install python (install miniconda that carries python) and install git via *conda install git* or *pip install git* from the TERMINAL.
4. vscode: File, close folder, then click on GitHub symbol. You should see your classroom folder. If not, install vscode extension *Github classroom*.
5. vscode: In the classroom folder, open assignment. You should see a README.md. To see the rendered version of the README.md source code, click on the split screen symbol (top right)
6. vscode: You should see a triangle in the top right corner of your vscode screen (if not, install vscode extension *python*, or click on the settings wheel in vscode, check settings). 
7. vscode: Open a python file or create a new one, press the triangle. The code should execute, output printed to 'OUTPUT'.
8. vscode: There should be a Live Share buttom in the menu (if not, install *vscode live share* extension)
9. vscode: Having modified files, click the Source Control symbol from the menu bar. Stage changes, commit changes (with message), synchronize.
10. github: find your repository, check if files have been updated there.

### Common problems with github, python and git

1. Avoid blanks in directory, file and user names. Avoid minus characters (-) in python file names (if you have a blank in your username, you cannot use the GitHub symbol in vscode to open your classroom folder, but have to *Open folder*, and *clone repository* using the repository code available from your repository at the GitHub website)
2. Save your python file before committing changes and leave a message in the Commit window before committing. Afterwards press *Synchronize*
3. Configure git (in vscode TERMINAL or another terminal), using the above-mentioned 'git config --global' items
4. Check if git is installed from within vscode. Open a Terminal in vscode, type
          git --version
5. Start vscode from anaconda, i.e., start the anaconda navigator first, then click the vscode logo in anaconda
5. In the vscode terminal type
          git add .
          git commit -m "message"
          git pull
          git push


### git conflicts

1. In the TERMINAL window type: [git mergetool](https://www.git-scm.com/docs/git-mergetool)
2. In the TERMINAL window type: git config pull.rebase true
3. If you see at the bottom top left of your vscode that you are not in *main*, click on this word (like *main+* or similar) and choose *main*.
4. If you see *main (rebase)* in the bottom top left corner of vscode, and if 3. did not help, delete the whole github-ctl-... folder (usually within your user directory) or move it away if you did important changes. Then restart vscode, click the Github symbol, mouse over *open folder* behind the classroom directory, click this *open folder*, and you should retrieve and see all files that exist at your GitHub (website) repository.

### Problems with anaconda + vscode + numpy/matplotlib

It seems many of you installed anaconda earlier to use Jupyter, and didn't install miniconda. If so, it is eventually not possible to install numpy or other missing packages. The following (1.) was reported to work, the remaining 2. to 5. are additional ideas. 

1. Start vscode: Go to the wheel / Settings. Search for: *terminal.integrated.shell.window*. Choose *Command prompt*. 
   Still in vscode -> wheel -> setting: Search for *terminal.integrated.defaultProfile.windows*. Choose *Command prompt*. 
   Still in vscode -> wheel -> setting: Search for conda. See "in Python: Conda Path" and add your personal: c:\Users\username\anaconda3\condabin.
   Try to use *pip install numpy* or *conda install numpy* from the vscode TERMINAL. If this still does not work, under Windows, click the windows symbol (bottom left)     -> Settings -> search for path -> Edit the system environment variables -> find the *path* environment and Edit it -> add your anaconda installation path, and also     the ...\anaconda\condabin directory path to your paths. Save the new settings. 

2. Start anaconda, In anaconda, open the anaconda command prompt and type: code <return>. This might start vscode with the correct settings. 
3. Start anaconda, click on the vscode logo, and if it does not exist, or does not work, go to *File* (anaconda, top left), *Preferences* and add the path to the *vscode* item inside *Preferences*. Save, and click the vscode symbol again. 
4. If this does not work. Close anaconda. Try to find out where anaconda or anaconda3 is located on your disk, and search the directory condabin within the anaconda location. Write down this path or copy it. Start vscode. Click the wheel (last item in the menu bar) and choose *Settings*. In the search field that opened, type in *conda*. You should see this
    
         Python: Conda Path
         Path to the conda executable to use for activation (version ...).
Add the c:\...\anaconda\condabin directory path into this field. 
    
5. If this didn't work, start vscode, go to the TERMINAL, and type: python --version. If you get an error message, and because you have python already installed via anaconda, the path to your anaconda installation is not known to your system. Under Windows, click the windows symbol (bottom left) -> Settings -> search for path -> Edit the system environment variables -> find the *path* environment and Edit it -> add your anaconda installation path, and also the ...\anaconda\condabin directory path to your paths. Save the new settings, open vscode, and type again *python --version* to your vscode TERMINAL.
   
5. If this does not work, we will probably recommend uninstalling anaconda, then installing miniconda, and then installing the jupyter extension in vscode. This way you can use *conda install numpy* or *pip install numpy* from the vscode TERMINAL and also use jupyter from within vscode. 
    
6. We will be extremely happy receiving your feedback. 

### installing ffmpeg under windows
          
You do not necessarily install ffmpeg to create videos from a collection of image files. But if you wish to do so, we are aware of a successful installation under windows 10 using the sources available from [this site](https://www.geeksforgeeks.org/how-to-install-ffmpeg-on-windows/).
          
### python with arguments


Contents of file demo1.py

*Run this python code from the vscode TERMINAL (or from a linux shell or a windows command prompt) as:*

*python demo1.py 3 100 1.0*

*python demo1.py go*

    import numpy as np
    import sys
    
    print("len(sys.argv) = ",len(sys.argv))
    print("sys.argv[0]   = ",sys.argv[0])

    def myfunction(N):
        print("myfunction was called with N =",N)
        A = np.array((2,2),dtype=float)

    if len(sys.argv)-1==3:
        dim = sys.argv[1]
        N = sys.argv[2]  
        T = sys.argv[3] 
        print("dim = ",dim," N =",N," T =",T)
        myfunction(N)
    elif len(sys.argv)-1==1 and sys.argv[1]=='go':
        dim = 3
        N = 100
        T = 1.0
        print("dim = ",dim," N =",N," T =",T)
        myfunction(N)
    else:
        print("required arguments: dim N T")
        
        
 Contents of file demo2.py
 
 *Run this python code using the vscode triangle, or from the vscode TERMINAL as: python demo2.py*
    
    import demo1 as M
    
    M.myfunction(200)


