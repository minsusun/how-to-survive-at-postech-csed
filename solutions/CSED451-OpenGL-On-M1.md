# breif introduction of installing and setting OpenGL environment

**OpenGL(pre-installed) + glew + glm + freeglut on XCode**

(I think you can use vscode with some configurations or cmake and make but i didn't try)

- OpenGL is deprecated since M1 comes with metal API
- But OpenGL is stil installed with XCode libraries
- So we gonna use that

### Brew

(search on internet for installing brew on mac)

```shell
brew install glew glm freeglut
```

### XCode

1. create empty command line project
2. go to project setting ( double-click your project's name on the left side(Project Navigator) )
3. TARGETS -> your project name (on left side)
4. general menu -> Frameworks and Libraries and add followings
    - GLUT / OpenGL
    - glew / glm / freeglut -> you need to add them with Add other... -> Add files...
        - glew: `/opt/homebrew/Cellar/glew/<your version>/lib/libGLEW.dylib`, do not embed
        - glm: `/opt/homebrew/Cellar/glm/<your version>/lib/libglm.dylib`, do not embed
        - freeglut: `opt/homebrew/Cellar/freeglut/<your version>/lib/libglut.dylib`, do not embed
5. build settings -> search paths
    - header search paths
        - `/opt/homebrew/Cellar/glew/<your version>/include`, recursive
        - `/opt/homebrew/Cellar/glm/<your version>/include`, recursive
        - `/opt/homebrew/Cellar/freeglut/<your version>/include`, recursive
    - library search paths (it will be already added but just for some cases)
        - `/opt/homebrew/Cellar/glew/<your version>/lib`, recursive
        - `/opt/homebrew/Cellar/glm/<your version>/lib`, recursive
        - `/opt/homebrew/Cellar/freeglut/<your version>/lib`, recursive

6. now go build