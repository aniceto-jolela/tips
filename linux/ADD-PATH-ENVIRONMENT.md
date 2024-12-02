# ADD PATH ENVIRONMENT - UBUNTU


###

Here are two ways to add `your_path` to your PATH:


### 1. Using ~/.bashrc` (recommended): ✳️

```bash
	echo 'export PATH=$PATH:your_path' >> ~/.bashrc
	source ~/.bashrc
```

### 2. Using `~/.profile`: ✳️


```bash
	echo 'export PATH=$PATH:your_path' >> ~/.profile
	source ~/.profile
```

> . Verify the path is added:

```bash
	echo $PATH
```
#
#
ex.: your_path =  /usr/local/go/bin