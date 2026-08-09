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

    -p é curto de --parents, ou seja, cria parentes como necessário.

### Solução problema 6 (B):

    rm -rf foo

    -r -> recursivo (vai entrando em pastas)
    -f -> force     (deleta tudo na força (sem perguntar e ignorando erros))


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

    flag -y pode ser usada para ver melhor as diferenças

### Solução problema 16 (B):

    cat hello.txt hello_copy.txt > 2_hellos.txt

    cat é abreviação de concatenate

### Solução problema 17 (B):

    pwd

    print working directory

### Solução problema 18 (B):

    ls -l challenges

    -l significa long, (dê-me mais informações!)
    ls = list

### Solução problema 19 (B):

    printf "(text)" | sudo tee -a challenges/restricted.txt

    sudo = superuser do
    -a = append


### Solução problema 20 (B):

    ./challenges/hello_executable

### Solução problema 21 (B):

    chmod +x challenges/challenge_20
    ./challenges/challenge_20


    chmod = changemode
    + adiciona
    - remove
    x r w -> execute read write (separar por virgula +w,+r,+x)

### Solução problema 22 (B):

    gcc challenges/compile_me.c -o challenges/compile_me
    ./challenges/compile_me

### Solução problema 23 (A):

    ./challenges/redirect &> output.txt

    &> redireciona tudo (stdout + stderr), > só stdout

### Solução problema 24 (B):

    date

### Solução problema 25 (B):

    top

### Solução problema 26 (B):

    nproc

### Solução problema 27 (B):

    lsb_release -a

### Solução problema 28 (B):

    grep -rl "You found the needle"

### Solução problema 29 (B):

    cat challenges/people.csv | head -25

### Solução problema 30 (B):

    cat challenges/people.csv | tail -25

### Solução problema 31 (I):

    diff challenges/greeting1.txt challenges/greeting2.txt -y

### Solução problema 32 (I):

    printf "Hello "; sleep 5; printf "world! \n"

### Solução problema 33 (I):

    dd if=/dev/zero of=challenges/zeros bs=1M count=1

    data description (disk destroyer) -> le e escreve
    if = input file
    of = output file


### Solução problema 34 (I):

    dd if=/dev/random of=challenges/random bs=1M count=2

### Solução problema 35 (I):

    wc -l README.txt

    wordcount 
    -l = linhas

### Solução problema 36 (B):

    tac README.txt

    concatenate = cat
    etanetacnoc = tac (bizarro)

### Solução problema 37 (I):

    cut -d',' -f2 challenges/people.csv | tail -n +2

### Solução problema 38 (A):

    cut -d',' -f2 challenges/people.csv | tail -n +2 | sort -u | wc -l

### Solução problema 39 (A):

    o cara pensou que mogava mas eu tinha percebido o problema,
    " | tail -n +2" serve pra resolver isso, (tudo da linha 2 (incluso) pra baixo)

### Solução problema 40 (A):

    cut -d',' -f2 challenges/people.csv | sed '1d'

    set = stream editor
    '1d' = 1 delete // deletar linha 1

### Solução problema 41 (A):

    time { cut -d',' -f2 challenges/people.csv | tail -n +2 > /dev/null ; } ; time { cut -d',' -f2 challenges/people.csv | sed '1d' > /dev/null ; }

    /dev/null tem NADA

### Solução problema 42 (A):

    cut -d',' -f4 challenges/people.csv | tail -n +2 | grep Josiah | wc -l

### Solução problema 43 (I):

    find challenges/ -maxdepth 1 -type f | wc -l

### Solução problema 44 (I):

    find challenges/ -maxdepth 1 -type d | tail -n +2 | wc -l

    cortei o primeiro pq é ele mesmo, mas não sei se esse sempre é o caso

### Solução problema 45 (I):

    find challenges/ -type f -name "*deleteme*" -delete

    glob (qualquer coisa deleteme qualquer coisa)

### Solução problema 46 (I):

    grep -rl "You found the needle" . | xargs sed -i 's/You found the needle in the haystack!/The needle has been removed./g'

    xargs usa o resultado do comando anterior como argumentos pro proximo comando
    (caminhos onde tem "string") -> stream editor -inplace (velho, novo)

### Solução problema 47 (A):

    sed 's/,/|/g' challenges/people.csv > challenges/people_pipe.csv

### Solução problema 48 (A):

    find . -type f ! -path "./file001.rand" -exec cmp -s "file001.rand" {} \; -print

### Solução problema 49 (A):

    touch supercalifragilisticexpialidocious.txt
    rm !$

    !$ pega o ultimo argumento do ultimo comando (supercalrigosfatrous.txt)

### Solução problema 50 (A):

    touch {a..c}-{1..3}.txt

### BONUS:

    você tem dois comandos para: 
        1. repetir a criação dos arquivos do problema 50
        2. criar mais um conjunto de arquivos, só que dessa vez invertido (N-L.txt)

        3. o primeiro comando deve ter menos de 45 caracteres
        4. o segundo comando deve ter menos de 20 caracteres


    b(){ eval touch "{$1..$2}-{$3..$4}.txt";}
    b 1 3 a c;b a c 1 3