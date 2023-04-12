1. Criar um arquivo hello.html
<html>
  <body>
    <h1>Alô Mundo!</h1>
  </body>
</html>

2. Adicionar o arquivo ao repositório
3. Criar um branch chamado Estilo
4. Adicionar neste branch o arquivo estilo.css

h1 {
  color: red;
}

5. Alterar o arquivo hello.html com as modificações abaixo.
<html>
  <head>
    <link type="text/css" rel="stylesheet" media="all" href="estilo.css" />
  </head>
  <body>
    <h1>Alô Mundo!</h1>
  </body>
</html>

6. Adicionar o arquivo ao repositório e faça um commit
      git add hello.html
      git commit -m "Hello.html Atualizado"

7. Volte para o branch master e verifique que o arquivo hello.html não possui a folha de estilo
      git checkout master
      cat hello.html
      
8. Crie um arquivo README.txt
        Arquivo com conteúdos instrucionais  

9. Volte para branch Estilo
      atualize o arquivo READM.txt

10. Volte para o branch master e faça o commit das mudanças do arquivo README.txt
      git checkout master
      git add README.TXT
      git commit -m "Added README"
      
11. Use o git log para ver os branchs

12. Mescle os branchs - execute
      git checkout style
      git merge master
      
13. As modificações no branch master conflitaram com as modificações do Estilo?

14. Volte para o branch master executando git checkout master

15. Faça as alterações no arquivo hello.html removendo os estilos
<html>
  <head>
    <!-- no style -->
  </head>
  <body>
    <h1>Alô Mundo! Paz e saúde!</h1>
  </body>
</html>

16. Use o git log para visualizar os branchs

17. Volte para o branch Estilo e faça um merge dele com um novo master.

18. O que você encontra no interior do arquivo hello.html?

19. Resolva o conflito manualmente, adicionando os conteúdos perdidos.

<html>
  <head>
    <link type="text/css" rel="stylesheet" media="all" href="estilo.css" />
  </head>
  <body>
    <h1>Alô Mundo! Paz, saúde e alegria!</h1>
  </body>
</html>

20. Faça o commit da alterações

git add hello.html 
git commit -m "Merged Master conflito corrigido."

A partir deste ponto, vamos precisamos voltar no repositório no momento antes do primeiro merge e então repetir os mesmos passos realocando  ao invés de fundindo (merged).

Resetar o branch Estilo para o ponto anterior ao primeiro merge.

21. Use o comando reset para voltar o branch para um estado anterior.
git checkout Estilo

22. veja o log dos branchs e os hash dos arquivos.

23. Observe pelos dados que o commit Atualizado hello.html foi o último no branch Estilo anterior ao merging.

Vamos resetar o branch Estilo para esse commit.

24. Resete (ou Redefina) o branch Estilo com o comando abaixo:
git reset --hard <hash>

O resultado do comando abaixo é algo parecido com
$ git reset --hard 07a2a46
HEAD is now at 07a2a46 Atualizado hello.html

25. Cheque o branch com o git log
Procure pelo log do branch Estilo. Não devem existir commits de merge no histórico

26. Reset (ou redefina) o branch master para um ponto anterior ao commit conflitante
git checkout master

27. Veja o log

28. O commit "Added README" está imediatamente anterior ao modo interativo conflitante a ser adicionado.
Agora precisamos resetar o branch master para o commit "Added README"

      git reset --hard <hash>

29. Veja o histórico (log). Ele deve parecer como se tivéssemos retrocedido o repositório para um ponto no tempo anterior a qualquer merge.

30. Então nós voltamos no histórico até antes do primeiro merge e queremos realocar as mudanças do master para o nosso branch Estilo.
      git checkout Estilo
      git rebase master
      
31. Nós mantivemos nosso branch style atualizado em relação ao branch master (usando rebase), mas agora vamos fundir as modificações de volta no master. Execute:
git checkout master
git merge Estilo

32. Confira os logs