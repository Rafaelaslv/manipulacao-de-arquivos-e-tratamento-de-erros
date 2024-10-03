Minhas anotações sobre Manipulação de arquivos e tratamento de erros.

---

Uma das vantagens do Python é a possibilidade de trabalhar de maneira eficaz com manipulação de arquivos locais ou em nuvem, caso o seu script esteja rodando em alguma página web. Seja da forma que for, a manipulação de arquivos com Python é algo extremamente simples de fazer e consideravelmente útil.

Por meio as funções de manipulação de arquivos, você consegue:

Manipular arquivos locais;
Mover, inserir, excluir arquivos de pastas ou diretórios;
Manipular conteúdos de arquivos;
Importar conteúdos de arquivos da Web;

Algo bastante utilizado com Python é a automação de determinadas tarefas como a realização de back-ups em dispositivos externos ou até mesmo a manipulação de arquivos mediante determinadas ações pré-programadas.

Falaremos sobre manipulação de arquivos, sejam eles em Nuvem/na WEB/na internet ou arquivos no nosso computador(manipulação de arquivos locais).

A manipulação de arquivos no Python é muito masi simples quando comparado à algumas outras linguagens.

QUANDO FALAMOS MANIPULAÇÃO DE ARQUIVOS EM NUVEM, NÃO É QUE VAMOS MEXER EM UM ARQUIVO QUE ESTÁ NA INTERNET, MAS IREMOS ACESSAR PÁGINAS WEB, PUXAR ARQUIVOS PARA DENTRO DO NOSSO COMPUTADOR/APLICAÇÃO EM PYTHON E O ARQUIVO FICARÁ SALVO EM NOSSO COMPUTADOR COMO SE ESTIVÉSSEMOS ACESSANDO ELE NA INTERNET, MAS NA VERDADE APENAS PUXAMOS.

E ISSO É MUITO INTERESSANTE PARA QUEM FAZ ANÁLISE DE DADOS, VOCÊ PODE FAZER UM ALGORITMO QUE VASCULHA A INTERNET INTEIRA EM BUSCA DE ARQUIVOS COM UMA CERTA ESTRUTURA, VAI TRAZNEDO ESSES ARQUIVOS, VAI ALOCANDO EM UM DATA WAREHOUSE/EM UMA ARMAZÉM DE DADOS E DEPOIS VOCÊ PODE RODAR UMA APLICAÇÃO DE ETL PARA VOCÊ PODER FILTRAR INFORMAÇÕES, MENSURAR DADOS, ...

---

### COMO MANIPULAR ARQUIVOS LOCAIS

Como já vimos anteriormente, existem funções específicas para praticamente tudo em Python e claro, existem funções para lidar com arquivos. Uma dessas funções é a open(), responsável por abrir um arquivo e iniciar todos os métodos necessários para realizar praticamente qualquer ação. Caso o arquivo não possa ser aberto, um erro é exibido em tela.

Antes de interagir com os arquivos é importante que você conheça algumas regras de permissões padrões.

,

---

O ERRO ACABA ACONTECENDO SE VOCÊ ERRAR ALGUMA SINTAXE, MAS EM RELAÇÃO À EXCEÇÃO CONSEGUIMOS BLINDAR O ALGORITMO PARA QUE ISSO NÃO ACONTEÇA.

---

O COMANDO PARA MANIPULAR ARQUIVOS EM PYTHON É O: open("teste.txt", "") - open + caminho do arquivo entre aspas + o que quero fazer com esse arquivo)

TEMOS ALGUMAS POSSIBILIDADES DE PERMISSÕES PARA QUANDO VOCÊ ESTIVER TRABALHANDO COM A MANIPULAÇÃO DE ARQUIVOS LOCALMENTE:

R - Raad
W - Write (adiciona algo ao final do arquivo)
X - eXecute

A - Append (acrescentar/adicionar algo)
NÃO SÃO NATIVOS: PERMITE ESCREVER UM ARQUIVO, MAS BASEADO EM BINÁRIOS.
R+ (PERMITE LER O ARQUIVO E ESCREVER)
WB

---

A PALAVRA open É PADRÃO, NÃO IMPORTA SE VOCÊ QUER ABRIR ou FECHAR.

PARA CRIAR UM ARQUIVO CHAMADO teste.txt:

open("teste.txt", "x")

---

conteudo = open("arquivo.txt", "a")
conteudo.write("Uma linha qualquer\n")
conteudo.write("Segunda linha\n")


COMANDO DE QUEBRA DE LINHA: \n

---

É IMPORTANTE APÓS AO ABRIR A CONEXÃO COM O BANCO DE DADOS, É IMPORTANTE FECHAR:

conteudo.close()

PARA IMPRIMIR O QUE ESTÁ ESCRITO DENTRO DO ARQUIVO:

print(conteudo.read())
print(conteudo.readline())

---

### MANIPULAÇÃO DE ARQUIVOS EM NUVEM

PARA QUEM QUER TRABALHAR COM CIÊNCIA DE DADOS, É INTERESSANTE LER ARQUIVOS DA INTERNET.

A BIBLIOTECA requests NÃO ESTÁ DENTRO DO PACOTE PYTHON, ENTÃO TEMOS QUE BAIXAR USANDO O COMANDO pip:

pip install requests

---

PARA UTILIZAR A BIBLIOTECA TEMOS QUE IMPORTAR ELA PARA DENTRO DA NOSSA APLICAÇÃO.

E PARA FAZER A LEITURA DE ALGUM ARQUIVO DA INTERNET, VAMOS CRIAR UMA VARIÁVEL CHAMADA ler E ELA RECEBERÁ A BIBLIOTECA request + get PARA APONTARM,OS O CAMINHO DO ARQUIVO QUE QUERO PEGAR.

E PARA BUSCAR ARQUIVOS DO TIPO TEXTO PROCURAMOS POR: arquivo filetype.txt

E PARA BUSCAR ARQUIVOS DO TIPO PDF PROCURAMOS POR: arquivo filetype.pdf

PARA LER OS DADOS DO ARQUIVO VAMOS UTILIZAR print(ler) que é o nome da variável.

import requests
ler = requests.get("https://wiki.sj.ifsc.edu.br/images/4/4a/Ecoshower.txt")
print(ler)

---

PARA SALVAR/MANIPULAR O ARQUIVO:

arquivo2.txt é o nome do arquivo que será gerado por mim com o conteúdo que está sendo puxado da internet.
wb - conseguirá escrever algo em modo binário
e será interpretada como uma variável chamada arquivo

with open("arquivo2.txt", wb") as arquivo:
    arquivo.write(ler.content) - VOU ESCREVER DENTRO DO ARQUIVO, O CONTEÚDO QUE ESTIVER DENTRO DA VARIÁVEL ler.

---

### ERROS E COMO TRATÁ-LOS

ERRO GERALMENTE É ORIGINADO A PARTIR DE UMA SINTAXE INCORRETA.

UMA FALHA NÃO IRÁ PROPRIAMENTE GERAR ALGUM AVISO NA TELA, MAS SE COMPORTARÁ DE UMA MANEIRA INESPERADA/O ALGORITMO SE COMPORTARÁ DE UMA MANEIRA DIFERENTE DAQUILO PARA QUAL ELE FOI PROJETADO.

ECEMPLO DE FALHA:

QUERO QUE O ALGORITMO SOME 3 + 4 E DEPOIS MULTIPLIQUE POR 2.

incorreto:
a = 3 + 4 * 2
correto:
a = (3 + 4) * 2

EXEMPLO DE ERRO:

incorreto:
a = 1 + "2"

SERÁ MOPSTRADO QUE VOCÊ QUER SOMAR UM INTEIRO COM STRING.

---

PARA RESOLVER OS ERROS, VOCÊ PODE COPIAR O TIPO DO ERRO E PESQUISAR NO GOOGLE.

A MAIOR PARTE DOS RESULTADOS DE PROGRAMAÇÃO, ENCONTRAREMOS NO stackoveflow.

O INPUT É PARA STRING, ENTÃO A STRING NÃO VAI ACEITAR SER SOMADA COM ALGUM NÚMERO.

ENTÃO USAREMOS O CASTING PARA CONVERTER O NÚMERO PARA INTEIRO.

---

PARA BUSCAR DETERMINADO TERMO DENTRO DO SITE DO PYTHON:

"unsupported operand type(s)" site:https://www.python.org

---

### O QUE SÃO EXCEÇÕES















