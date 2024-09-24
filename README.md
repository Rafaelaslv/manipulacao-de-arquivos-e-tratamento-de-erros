Minhas anotações sobre Manipulação de arquivos e tratamento de erros.

---

Falaremos sobre manipulação de arquivos, sejam eles em Nuvem/na WEB/na internet ou arquivos no nosso computador(manipulação de arquivos locais).

A manipulação de arquivos no Python é muito masi simples quando comparado à algumas outras linguagens.

QUANDO FALAMOS MANIPULAÇÃO DE ARQUIVOS EM NUVEM, NÃO É QUE VAMOS MEXER EM UM ARQUIVO QUE ESTÁ NA INTERNET, MAS IREMOS ACESSAR PÁGINAS WEB, PUXAR ARQUIVOS PARA DENTRO DO NOSSO COMPUTADOR/APLICAÇÃO EM PYTHON E O ARQUIVO FICARÁ SALVO EM NOSSO COMPUTADOR COMO SE ESTIVÉSSEMOS ACESSANDO ELE NA INTERNET, MAS NA VERDADE APENAS PUXAMOS.

E ISSO É MUITO INTERESSANTE PARA QUEM FAZ ANÁLISE DE DADOS, VOCÊ PODE FAZER UM ALGORITMO QUE VASCULHA A INTERNET INTEIRA EM BUSCA DE ARQUIVOS COM UMA CERTA ESTRUTURA, VAI TRAZNEDO ESSES ARQUIVOS, VAI ALOCANDO EM UM DATA WAREHOUSE/EM UMA ARMAZÉM DE DADOS E DEPOIS VOCÊ PODE RODAR UMA APLICAÇÃO DE ETL PARA VOCÊ PODER FILTRAR INFORMAÇÕES, MENSURAR DADOS, ...

---

O ERRO ACABA ACONTECENDO SE VOCÊ ERRAR ALGUMA SINTAXE, MAS EM RELAÇÃO À EXCEÇÃO CONSEGUIMOS BLINDAR O ALGORITMO PARA QUE ISSO NÃO ACONTEÇA.

---

O COMANDO PARA MANIPULAR ARQUIVOS EM PYTHON É O: open("teste.txt", "") - open + caminho do arquivo entre aspas + o que quero fazer com esse arquivo)

TEMOS ALGUMAS POSSIBILIDADES DE PERMISSÕES PARA QUANDO VOCÊ ESTIVER TRABALHANDO COM A MANIPULAÇÃO DE ARQUIVOS LOCALMENTE:

R - Raad
W - Write
X - eXecute

A - Append (acrescentar/adicionar algo)
NÃO SÃO NATIVOS: PERMITE ESCREVER UM ARQUIVO, MAS BASEADO EM BINÁRIOS.
R+
WB

---

A PALAVRA open É PADRÃO, NÃO IMPORTA SE VOCÊ QUER ABRIR ou FECHAR.

PARA CRIAR UM ARQUIVO CHAMADO teste.txt:

open("teste.txt", "x")

---

conteudo = open("arquivo.txt", "a")
conteudo.write("Uma linha qualquer\n")
conteudo.write("Segunda linha\n")

---














