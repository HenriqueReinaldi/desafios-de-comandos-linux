### Solução problema 1 (B):

    tar -xf challenges.tar.gz

### Solução problema 2 (B):

    cd challenges/

### Solução problema 3 (B):

    dir challenges

### Solução problema 4 (B):

    mkdir foo

### Solução problema 5 (I):

    mkdir -p foo/bar/1/2/3

### Solução problema 6 (B):

    rm -rf foo

### Solução problema 7 (B):

    echo "Hello World"

### Solução problema 8 (B):

    echo "Hello World" > hello.txt

### Solução problema 9 (B):

    touch empty.txt

### Solução problema 10 (B):

    rm empty.txt

### Solução problema 11 (I):

    > empty.txt

### Solução problema 12 (I):

    > printf "" > empty.txt

### Solução problema 13 (B):

    cp hello.txt goodbye.txt

### Solução problema 14 (B):

    mv goodbye.txt hello_copy.txt

### Solução problema 15 (I):

    diff hello.txt hello_copy.txt

### Solução problema 16 (B):

    cat hello.txt hello_copy.txt > 2_hellos.txt

### Solução problema 17 (B):

    pwd

### Solução problema 18 (B):

    ls -l challenges

### Solução problema 19 (B):

    printf "(text)" | sudo tee -a challenges/restricted.txt

### Solução problema 20 (B):

    ./challenges/hello_executable