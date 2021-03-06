# Before ML
***To do a good job, an artisan needs the best tools.*** Before embarking on a machine learning project, we first need to set up a suitable development environment. In this section, I will describe the preparations that are made before a machine learning project is carried out. For example, acquiring a GPU, installing CUDA, configuring Miniconda and other tasks. Let's get started!

### GPU
You may ask me if I really need a GPU to train machine learning? The answer is **YES**.This graph shows how fast GPU is compared with CPU.

![avatar](/GPU-SSL-Jupyter/gpu.png)

As you can see that GPU is 82x faster than CPU. So, it is way faster to train a modal with GPU compared with CPU. There are lots of GPU provider you can rend from. So, i am gonna leave it here and you can choose whatever GPU provider you like. 

### SSH Remote Connection
After you having a GPU(ECS), you may consider how to use it in a proper way. Here is my suggestion. If you are using Mac, for example, try `ssh [name]@[public IP]` in your terminal. and than you will be ased to enter the password of your ecs. Do it and you will finish the connection part. If you encounter any question here, search 'linux ssh usage' at google. 

### Linux
You are still facing black terminal GUI, right? Don't worry, Let's set up the environment first and than I will give you a powerful pick. Alright, let me introduction a few linux terms so that you can play with it in the terminal. 
- `sudo` gives you the right as a root user.
- `apt-get` is a package management tool in Ubuntu that can be used to install and uninstall packages, to upgrade packages, and to upgrade the system to a new version.
- `wget` is a tool for downloading files, which is used at the command line. It is an essential tool for Linux users, we often have to download some software or restore backups from a remote server to the local server.

### CUDA
It provides an easy interface to GPU programming, and CUDA-based programming can be used to build GPU computing-based applications that take advantage of the GPUs' parallel computing engine to solve more complex computing challenges more efficiently. Go to the official website of CUDA and choose the right version and use wget to download in you ecs.

![avatar](/GPU-SSL-Jupyter/CUDA.png)

### Miniconda
'*Miniconda is a free minimal installer for conda. It is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages, including pip, zlib and a few others. Use the conda install command to install 720+ additional conda packages from the Anaconda repository.*' Go to the official website of Miniconda and choose the right version and use wget to download in you ecs.

- use `conda create` to build a new environment.
- use `conda activate` to activate the environment you have just built.
- use `conda install` to install packages you need.

![avatar](/GPU-SSL-Jupyter/miniconda.png)

### Pytorch
Pytorch is a Python-based scientific computing package that uses the power of a graphics processing unit. It is also one of the preferred deep learning research platforms built to provide maximum flexibility and speed. It is known to offer two top-level features: tensor computing with powerful GPU acceleration support and building deep neural networks on a tape-based automated programming system.
Go to the official website of Pytorch and choose the right version and use pip to download in you ecs.

![avatar](/GPU-SSL-Jupyter/pytorch.png)

### Jupyter Notebook
Jupyter Notebook is a program that opens as a web page and allows you to write and run code directly on the web page, with the results displayed directly under the code block. If you need to write documentation during the programming process, you can do so directly on the same page, making it easy to provide timely instructions and explanations. In short, Jupyter Notebook is a server to let you avoid the black terminal and show the content at frontend nicely with the help of ssh port mapping.

Remember the `ssh [name]@[public IP]` thing? Here we gonna add something in it. Try `ssh -L 8888:locallhost:8888 [name]@[public IP]` before you connect to ecs. This time, we aso connect to the ecs, however, we add a port mapping. What is it? It means the service at port 8888 in your ecs is mapped at your local port 8888. So, if you go to your browser and call 8888 after you have started your jupyter in ecs, you can see a nice interface shown up! ***Congratulations!***