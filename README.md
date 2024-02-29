# Docker "hello world" different runtimes tests

![Images size](./.img/images.png?raw=true)

For test the most slim images where taken (C was built from scratch)


## Docker build without and with cache
### JS: 
```
docker build -t node-hello-world .
[+] Building 5.7s (7/7) FINISHED   
docker build -t node-hello-world .
[+] Building 0.5s (7/7) FINISHED
```

### Python: 
```
docker build -t python-hello-world .
[+] Building 5.0s (7/7) FINISHED  
docker build -t python-hello-world .
[+] Building 0.7s (7/7) FINISHED
```

### BUN: 
```
docker build -t bun-hello-world .
[+] Building 14.3s (7/7) FINISHED  
docker build -t bun-hello-world .
[+] Building 0.7s (7/7) FINISHED 
```

### JAVA
```
docker build -t java-hello-world .
[+] Building 20.8s (7/7) FINISHED
docker build -t java-hello-world .
[+] Building 0.7s (7/7) FINISHED 
```

### C
```
docker build -t c-hello-world .
[+] Building 0.2s (5/5) FINISHED
docker build -t c-hello-world .
[+] Building 0.1s (5/5) FINISHED
```

## Benchmarking
### JS: 
```
$ time docker run node-hello-world
> Hello, world!
> docker run node-hello-world  0.00s user 0.03s system 4% cpu 0.708 total
$ time docker run node-hello-world
> Hello, world!
> docker run node-hello-world  0.03s user 0.00s system 3% cpu 0.797 total
$ time docker run node-hello-world
> Hello, world!
> docker run node-hello-world  0.00s user 0.03s system 4% cpu 0.702 total
$ time docker run node-hello-world
> Hello, world!
> docker run node-hello-world  0.00s user 0.03s system 4% cpu 0.648 total
```

### Python
```
$ time docker run python-hello-world
> Hello, world!
> docker run python-hello-world  0.00s user 0.03s system 4% cpu 0.677 total
$ time docker run python-hello-world
> Hello, world!
> docker run python-hello-world  0.02s user 0.01s system 4% cpu 0.692 total
$ time docker run python-hello-world
> Hello, world!
> docker run python-hello-world  0.00s user 0.03s system 5% cpu 0.624 total
$ time docker run python-hello-world
> Hello, world!
> docker run python-hello-world  0.01s user 0.01s system 4% cpu 0.694 total
```
### BUN: 
```
$ time docker run bun-hello-world
> Hello world
> docker run bun-hello-world  0.01s user 0.02s system 4% cpu 0.723 total
$ time docker run bun-hello-world
> Hello world
> docker run bun-hello-world  0.00s user 0.03s system 4% cpu 0.761 total
$ time docker run bun-hello-world
> Hello world
> docker run bun-hello-world  0.00s user 0.03s system 5% cpu 0.600 total
$ time docker run bun-hello-world
> Hello world
> docker run bun-hello-world  0.02s user 0.02s system 4% cpu 0.690 total
```

### JAVA
```
$ time docker run java-hello-world
> Hello, World!
> docker run java-hello-world  0.03s user 0.00s system 2% cpu 1.154 total
$ time docker run java-hello-world
> Hello, World!
> docker run java-hello-world  0.00s user 0.03s system 2% cpu 1.138 total
$ time docker run java-hello-world
> Hello, World!
> docker run java-hello-world  0.00s user 0.03s system 2% cpu 1.052 total
$ time docker run java-hello-world
> Hello, World!
> docker run java-hello-world  0.02s user 0.01s system 2% cpu 1.074 total
```

### C
```
$ time docker run c-hello-world
> Hello, world!
> docker run c-hello-world  0.00s user 0.03s system 4% cpu 0.671 total
$ time docker run c-hello-world
> Hello, world!
> docker run c-hello-world  0.00s user 0.03s system 4% cpu 0.651 total
$ time docker run c-hello-world
> Hello, world!
> docker run c-hello-world  0.02s user 0.02s system 4% cpu 0.726 total
$ time docker run c-hello-world
> Hello, world!
> docker run c-hello-world  0.01s user 0.02s system 4% cpu 0.671 total
```

#### To compile C code, run
```
musl-gcc -o hello -static -flto hello.c
```
