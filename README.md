# C/C++ setup for vs code

[![Author](https://img.shields.io/badge/Auther---Ullas-blu)](https://img.shields.io/badge/Auther---Ullas-blu?utm_source=github.com&utm_medium=campaign&utm_content=button&utm_campaign=dmhendricks%2Ffile-icon-vectors)

Table Of Content

- [General info](#general-info)
- [SetUp](#setup)

## General info

what is a workspace ?

A Visual Studio Code `workspace` is the collection of one or more folders that are opened in a VS Code window (instance)

The best part:
__The concept of a workspace enables VS Code to: Configure settings that only apply to a specific folder or folders but not others.__

The `code .` command opens VS Code in the current working folder, which becomes your `workspace`.

In a workspace:

settings as well as **debugging** and **task** configurations are stored at the root in a `.vscode` folder with file
`c_cpp_properties.json`, `task.json`, `launch.json`.

You can even create it using **Command Palette** key combination `Ctrl+Shift+P`

## SetUp

1. Install [MinGW](https://osdn.net/projects/mingw/releases/) or [MinGW-w64](http://mingw-w64.org/doku.php) or [TDM gcc](https://jmeubank.github.io/tdm-gcc/)

    inshort:

    Now the difference between **MinGW, MinGW-w64, TDM GCC**

    - MingGW is only for 32 bit-program\
    !which can be run on 64 bit as well *(not all(there are tricks as well))*

    - MinGW-w64 is a newer which has the ability to support 32 & 64 bit

    - The MinGW distribution also doesn't use posix emulation to access threads in Windows (unlike MinGW-w64 or TDM64)

    - The TDM-gcc compiler also seems to implement the latest gcc version faster than the other projects.

    Its totally up to you according to your project

    - If you want to use the older graphics.h then go for **MingW**
    - If your working with something like **SFML** or **SDL**( Go for *TDM GCC* ) & **OPENCV** ( Go for *MinGW-w64* )

        Set environemnt variable\
        Search for Edit environment variables.\
        In **User variable** click on Path & New path of compiler bin folder.\
        select OK and save and exit

        Check from the terminal by the command

        ```bash
            g++ --version
            or
            gcc -v
        ```

2. Install `C/C++ extension for VS Code` from vs code extension tab or key `Ctrl+Shift+X`

    - Now Configure environemnt by command pallet **CTRL+Shift+P** type >c/c++: Edit Configurations (JSON) this will generate *c_cpp_properties.json* file

    - For task.json same in the command pallet type >tasks: Configure Task then select the task g++ for cpp file this will generate *task.json* file

3. That's it... Now create main.cpp in workspace

    ```cpp
        #include <iostream>
        using namespace std;
        int main(){
            cout<<"Hola Amigooo";
            return 0;
        }   
    ```

    - After that to create executable or to run the program just use the key command `Ctrl+Shift+B` **eso está todo hecho** means that's all... done

4. You can take it to the next level by modifying task.json

    - You can give the arguments
    - Specify where to build the .exe
    - ...
