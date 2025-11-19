**\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ lesson 1 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**



bash



pwd -> path of working directory (caminho de pastas)



mkdir -> criar diretoria



mkdir dir1/dir2 -> criar várias diretorias



-v -> aprece mensagem a explicar a ação



ls -> list (apenas da diretoria que estamos)



ls -R -> mostar todos os contuédos dentro das diretorias



-R -> Recursive



cd dir2 -> chance directory



cd .. -> andar para trás



cd - -> volta para a diretoria onde estava (ctrl + z)



cd dir2/dir3 -> entrar na pasta dir3 sem ter de entrar na pasta dir 2 primeiro



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ lesson 2 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_





TAB -> pressionar tab mostra as possibilidades que temos enquanto escrevermos o commando



touch file1.txt -> criar ficheiro txt/mudar a timestamp de um ficheiro existente



dir -> mostar conteudos das directorias



clear -> limpar linha de commandos



echo "menssagem" -> imprimir "menssagem" na linha de commando



echo "UA" > file1.txt  -> enviar menssagem para o ficheiro e apaga o conteudo já existente no ficheiro



echo "UA2" >> file1.txt  -> adicionar menssagem para o ficheiro sem apagar o conteudo do ficheiro



cat file1.txt -> ver contuedo do ficheiro



head -2 file1.txt -> ver as primeiras 2 linhas ficheiro



tail -2 file1.txt -> ver as ultimas 2 linhas do ficheiro



stat file1.txt -> mostra estatisticas sobre feicheiro



stat dir1 -> mostra estatisticas sobre diretorias e ficheiros



ls -all -> mostra todo o conteudo da pasta



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ lesson 3 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



du -> mostra o espaço do disco que está a ser usado



du -h -> mostra o espaço do disco que está a ser usado "numa linguagem legivel"



du -xh ~ -> mostra o espaço do disco que está a ser usado e a diretoria completa



du --max-depth 2 ~ -> mostra o espaço do disco que está a ser usado e a diretoria até a uma profundidade de 2



cp -v file1.txt dir2 -> copia o ficheiro "file1.txt" para a diretoria "dir2"



cp -v file1.txt dir2/file2.txt -> copia o fichiero para a diretoria e muda o nome ao mesmo tempo



cp -vr dir2/\*.txt dir2/dir3 -> copia todos os ficheiros que acabam com ".txt" da dir2 para a dir3



cp -vr dir2/dir3 . -> copia a diretoria dir3 para a diretoria dir2



md5sum file1.txt -> ler grandes ficheiros ou ficheiros com conteudo binários (também mostra a "chave de identidade" do ficheiro)



mv hello.txt dir2/dir3/dir4/hi.txt -> move o ficheiro "hello.txt" para a dir4 e muda o nome do ficheiro para "hi.txt" (ctrl-x)



mv dir2/\*.txt dir5 -> move todos os ficheiros que acabam em ".txt" para a diretoria "dir5"



mv dir5 dir50 -> alterar o nome da diretoria de "dir5" para "dir50"



ln  dir2/dir3/dir4/hi.txt hello -> criar um link para o ficheiro "hi.txt" chamado "hello"



--->>> explicação:Um hard link é quando dois nomes diferentes apontam para o mesmo inode (especie de “cartão de identidade”),

e um soft link funciona mais como um atalho.<<<---



ln -s  dir2/dir3/dir4/hi.txt  softlink -> criar um softlink



rm -i file2.txt -> remove o ficheiro (yes to delete -> "y")



rm -ri dir50/\* -> remove a diretoria



rm -rf junk/\* -> remove a diretoria "junk" sem mensagem de confirmação



rmdir  dir50 -> remove diretoria vazia (sem ficheiros ect…)







**||--------------------------------** Aula 3 --------------------------------**||**





\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ lesson 4 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



ps -> mostra os processos a serem excutados no momento



sleep 60 \& -> coloca o Sistema a dormir ("\&" faz com que o processo corra em background)



kill 12345 -> termina o processo (12345 é o "id" do processo)



kill -9 12345 -> em caso de o programa não terminar usar "-9" para forçar



killall sleep -> termina todos os processos com o nome "sleep"



killall -u webminal -> termina todos os processos do utilizador "webminal"



killall -w find -> verifica se algum dos processos eliminados está ainda ativo (apenas devolve um valor se não encontrar nenhum processo)



pidof bash -> devolve o id de todos os processos que estão a correr como "bash"



pidof -s bash -> devolve apenas o id de um processo que está a correr como "bash"

nice -n 19 sleep 30 \& -> executa o programa sleep 30 em segundo plano com prioridade muito baixa (sendo 19 a prioridade mais baixa)

renice -n 19 12345 -> alterar a prioridade num processo já está a corer (sendo "12345" o id do processo)



renice +1 -u webminal -> muda a prioridade de precesso que já estão a corer para 1 (do utilizador "webminal")



top -> para visualizar o precesso que estão decorrer no momento (para sair "q")



pstree -> mostra uma "arvore" de processos



pstree -p -> mostra o id dos processos



time ls -l -> mostra o tempo que o comando "ls" demorou a executar



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ lesson 5 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_





grep "Linux" hello -> procura por palavras ou linhas, neste caso "Linux", no ficheiro "hello"



grep -r "Hello" . -> procura a palavra "Hello", em várias diretorias e ficheiros



grep -i 'lINUX' hello -> o atributo "-i" faz com que o commando grep deixe de ser case sensitive



grep -n "linux" hello -> mostra as linhas onde a palavra se encontra



grep -v 'world' hello -> mostra as linhas que não cores pondem à palavra "world"



wc -L hello -> explicação do site: (To count no.of words,lines and character on a file use wc hello title: wc

thus wc counts lines/words/bytes in a file. first field is no.of lines , second column is no.of words and third column denotes no.of bytes.)



echo -e "yha/yhe" >> linux.txt -> "-e" faz com o echo interprete os caracteres especiais, como \\n, \\t, etc.

Ou seja, permite usar sequências de escape dentro das aspas.



cut -f1 -d' ' new.txt -> cortar/extrair a primeira coluna



paste hello new.txt -> combina as linhas dos ficheiros



paste -s hello new.txt -> para colar um linha de cada vez



sort new.txt -> para organizar um ficheiro



diff hello linux.txt -> cara comprar ficheiros



diff3 hello new.txt linux.txt -> comprar 3 ficheiros





\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ lesson 6 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



dirname dir2/dir3/dir4/hi.txt -> remove o nome do ficheiro e mostra só a parte do caminho (as pastas onde o ficheiro está).



basename dir2/dir3/dir4/hi.txt -> remove ad diretorias e mostra apenas a utlima entrada (neste caso "hi.txt")



chmod -v 666 file1.txt -> muda as permições de acesso ao ficheiro (neste caso muda para rw-rw-rw, 1ª parcela: Owner, 2ª parcela: Group, 3ª parcela: others users) 



chmod a+rw file1.txt -> "a" aplica a todos (owner, group e others) "+rw" adiciona a permissão de escrita(w) e leitura(r) \[todos os utilizadores podem ler e escrever no ficheiro]



chmod a-rw file1.txt -> faz o oposto de "chmod a+rw file1.txt" (tira as permissões de leitura e escrita a todos)



chmod -R 644 ~/chmod\_dir -> aplica as permissões 644 a tudo dentro da pasta "chmod\_dir" (6 = rw, 4=r)



chown root file1.txt -> muda o owner do ficheiro (nest caso para "root")



chown root:staff file1.txt -> muda o owner para "root" e o group para "staff



chown root:staff -R ~/dir2 -> muda o dono e o grupo em todos os ficheiros e subpastas dentro de "dir2"



chown --from=webminal:webminal root:staff -R ~/dir2 -> muda os ficheiros que pretence a webminal:webminal para o novo dono root e grupo staff



chgrp root file1.txt -> muda só o grupo do ficheiro



chgrp -hR root dir2 -> -R → recursivo (altera dentro de subpastas) | -h → muda também os links simbólicos (não apenas os ficheiros “reais”)







