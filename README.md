# road-of-fishing
Collect small tips learned every day as a programmer.

* TypeScript
    * object literal specify type: https://github.com/brickmaker/road-of-fishing/blob/master/articles/typescript.md#obj-type

* JavaScript
    * get float decimal part of number: https://stackoverflow.com/a/4512317
    * Monkeypatching: https://www.audero.it/blog/2016/12/05/monkey-patching-javascript/
    * React
        * hooks update state depend in previous state: https://reactjs.org/docs/hooks-reference.html#functional-updates (in Note)

* PYTHON
    * `for-else` clause: https://docs.python.org/3/tutorial/controlflow.html#break-and-continue-statements-and-else-clauses-on-loops
    * sort with indices(useful in OJ): https://stackoverflow.com/a/6422754
    * run script with path error: add `__init__.py` under directory, and in script file add sys path: `sys.path.append(os.path.dirname(os.path.dirname(os.path.dirname(__file__))))`
    * string to list of chars: not `s.split()` or `s.split('')`, use `list(s)`
    * bisect for binary search: https://github.com/brickmaker/road-of-fishing/blob/master/articles/python-bisect.md
    * jupyter notebook
        * jupyter notebook add venv kernel: https://janakiev.com/til/jupyter-virtual-envs/
        * matplotlib use svg draw chart: https://stackoverflow.com/a/36622238
        * import things from other notebooks: https://github.com/brickmaker/road-of-fishing/blob/master/articles/jupyter-notebook.md#import-another

* HTML&CSS
    * css disable mouse event on DOM element: https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events
    * change webpage to gray: `filter: gray`. https://zhuanlan.zhihu.com/p/146884498
    * insert DOM element as first child: https://stackoverflow.com/a/43838105

* WebGL
    * click object detection: https://github.com/brickmaker/road-of-fishing/blob/master/articles/webgl-click-detection.md

* Observable
    * Observable - JavaScript相互转换：https://github.com/brickmaker/road-of-fishing/blob/master/articles/observable-javascript.md
* GLSL
    * Loop statement in GLSL not support dynamic value directly: http://learnwebgl.brown37.net/12_shader_language/glsl_control_structures.html#iteration

* WSL
    * WSL python3 配置： https://github.com/brickmaker/road-of-fishing/blob/master/articles/wsl-python.md
    * windows-wsl git使用问题: https://github.com/brickmaker/road-of-fishing/blob/master/articles/wsl-git.md

* Linux
    * ssh key config: https://github.com/brickmaker/road-of-fishing/blob/master/articles/linux.md#ssh-key
    * scp upload file: https://github.com/brickmaker/road-of-fishing/blob/master/articles/linux.md#scp-upload
    * zip and unzip file: https://github.com/brickmaker/road-of-fishing/blob/master/articles/linux.md#zip-unzip
    * run in background: https://unix.stackexchange.com/a/148698

* MacOS
    * disable internal keyboard when using other keyboard: Use Karabiner-Elements. Preferences > Devices > Advanced > Disable the build-in keyboard while...
    * space quicklook plugins: https://github.com/sindresorhus/quick-look-plugins

* Windows
    * windows boot `bootsafe64_ev.sys` 签名错误：https://icecoland.com/2018/01/12/bootsafe64ev-sys/

* VSCode
    * open without previous project: https://stackoverflow.com/a/36797180
    * python virtualenv powershell terminal 无法运行active script: https://stackoverflow.com/a/18713789
* Vim
    * open and close folds: https://vim.fandom.com/wiki/Folding
    * jump to next blank line: `}` https://vi.stackexchange.com/a/10829

* Ridiculous problems
   * git clone protocol 'https' not supported: https://stackoverflow.com/a/55985462

* tools
    * git
        * git proxy setting: https://stackoverflow.com/questions/783811/getting-git-to-work-with-a-proxy-server
        * update update with upstream(origin repo): https://www.neonscience.org/git-setup-remote
    * homebrew
        * homebrew cannot load such file...: https://stackoverflow.com/questions/54848319/homebrew-broken-cannot-load-such-file-vendor-bundle-bundler-setup-loaderr/54978161#54978161
    * 软件源
        * ubuntu软件源：https://mirror.tuna.tsinghua.edu.cn/help/ubuntu/
        * pypi源：https://mirror.tuna.tsinghua.edu.cn/help/pypi/
        * npm源：https://github.com/8788/blog/issues/7
        * homebrew源：https://mirror.tuna.tsinghua.edu.cn/help/homebrew/

* OS Configs
    * VPN WiFi无法连接：https://github.com/brickmaker/road-of-fishing/blob/master/articles/vpn-wifi.md

* LaTeX
    * windows latex vscode 中文：https://zhuanlan.zhihu.com/p/43133114


* NICHES
    * C++11 is formal named C++0x: https://stackoverflow.com/questions/9538701/what-is-the-difference-between-c0x-and-c11

## Rule of tips

1. Link with one line description
2. Write on own? put in `/articles` and use link
3. Bottom-up. Categorize if and only if needed
