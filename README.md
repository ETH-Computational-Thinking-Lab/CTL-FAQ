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

### python with arguments


Contents of file demo1.py

*Run this python code from the vscode TERMINAL like:*

*python demo.py 3 100 1.0*

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


