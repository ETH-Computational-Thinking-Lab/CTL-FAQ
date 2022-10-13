# Computational Thinking Lab - FAQ

### Group forming

If you cannot find a place in any of the existing groups and want to create a new group, while the maximum number of groups has been reached already, or if you have already joined a team but couldn‘t see any identifiers and therefore skipped the process and have no access to your repository, please contact [Martin](https://polyphys.mat.ethz.ch/group/people/person-detail.mk.html).

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

1. Avoid blanks in directory, file and user names. Avoid minus characters (-) in python file names. 

### Problem with anaconda + vscode + numpy/matplotlib

It seems many of you installed anaconda earlier to use Jupyter, and didn't install miniconda. If so, it is eventually not possible to install numpy or other missing packages. We do not know yet a solution to this problem, but most likely the following could help: 

0. Start vscode: Go to the wheel / Settings. Search for: terminal.integrated.shell.window. Choose *Command prompt*. 
   Then go to the wheel, search conda, in Python: Conda Path c:\Users\username\anaconda3\condabin

1. Start anaconda, In anaconda, open the anaconda command prompt and type: code <return>. This might start vscode with the correct settings. 
3. If this does not work. Close anaconda. Try to find out where anaconda or anaconda3 is located on your disk, and search the directory condabin within the anaconda location. Write down this path or copy it. Start vscode. Click the wheel (last item in the menu bar) and choose *Settings*. In the search field that opened, type in *conda*. You should see this
    
         Python: Conda Path
         Path to the conda executable to use for activation (version ...).
Add the c:\...\anaconda\condabin directory path into this field. 
    
4. If this didn't work, start vscode, go to the TERMINAL, and type: python --version. If you get an error message, and because you have python already installed via anaconda, the path to your anaconda installation is not known to your system. Under Windows, click the windows symbol (bottom left) -> Settings -> search for path -> Edit the system environment variables -> find the *path* environment and Edit it -> add your anaconda installation path, and also the ...\anaconda\condabin directory path to your paths. Save the new settings, open vscode, and type again *python --version* to your vscode TERMINAL.
   
4. If this does not work, we will probably recommend uninstalling anaconda, then installing miniconda, and then installing the jupyter extension in vscode. This way you can use *conda install numpy* or *pip install numpy* from the vscode TERMINAL and also use jupyter from within vscode. 
    
5. We will be extremely happy receiving your feedback. 

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


