Seja bem-vindo aos desafios de Python, onde você encontra desafios que envolvem tarefas executadas no dia a dia de um
programador.

Desafio 1

Esse desafio envolve a leitura de um arquivo, manipulacão dos dados do mesmo para gerar as respostas desejadas e
finalmente o salvamento dos dados manipulados num novo arquivo. Para facilitar a implementaćão do desafio vamos
descrever quais passos devem ser seguidos e assim facilitar a compreesão das atvidades que devem ser realizadas.

O arquivo em questão possui dados de pacientes contendo informacões como peso, altura e tipo sanguíneo. O objeto do
desafio é ler o conteúdo do arquivo e calcular as médias dos pesos e das alturas, contar os tipos sanguíneos para cada
tipo e escrever esses valores num arquivo de saída. Seguem abaixo uma descricão das etapas que podem ser seguidas para
a finalizacão do desafio.

Para finalizarmos essa tarefa precisamos:

1: abrir o arquivo

O arquivo dados_pacientes.csv é do tipo csv (comma separated value), ou seja, arquivo separado por vírgula, mais
especificamente "ponto e vírgula" no nosso exemplo e possui 3 colunas: peso, altura e tipo sanguíneo. Segue abaixo o
exemplo de uma linha:

    85.6;177;A+

Aqui nós vamos ler o arquivo linha por linha e salvar o conteúdo da linha com texto (string) em uma lista. Abaixo é
mostrado um exemplo de valores de entrada seguido de sua respectiva saída:

85.60;177;A+      ["85.60;177;A+",
72.47;165;B+  =>   "72.47;165;B+",
90.00;172;AB-      "90.00;172;AB-"]

Se o arquivo tiver 3 linhas então a nossa lista terá tamanho 3.

PS: utilize gerenciadores de contexto (context manager) para fazer essa abertura. Você vai encontrar
informacões sobre gerenciadores de contexto nesses links: https://acervolima.com/gerenciador-de-contexto-em-python/ e
https://www.pythonmorsels.com/what-is-a-context-manager/

PS2: não se esqueca de remover o caracter de linha nova \n que fica no final de cada linha do arquivo

2: Quebrando os valores de texto salvos na lista do item 1

Nessa etapa nós iremos ler o conteúdo da nossa lista um por um, separaremos os itens e salvaremos num dicionário (dict)
onde as chaves serão "peso", "altura" e "tipo_sangue". Devemos também converter os valores de peso e altura para float
e int sucessivamente. Segue abaixo um exemplo dessa etapa:

["85.60;177;A+",        [{"altura": 85.6, "peso": 177, "tipo_sangue": "A+"},
 "72.47;165;B+",  =>     {"altura": 72.47, "peso": 165, "tipo_sangue": "B+"},
 "90.00;172;AB-"]        {"altura": 90.0, "peso": 172, "tipo_sangue": "AB-"}]

3: Implementar a funcão de cálculo da média:

Aqui vamos implementar uma funcão que calcula a média dos valores, ou seja, faremos uma soma de todos os valores e
dividiremos pela sua quantidade. Aqui se sugere passar como atributo uma lista com somente valores numéricos.

4: Contagem de tipo sanguíneo:

Nessa fase faremos uma contagem por tipo e salvaremos o resultado num dicionário (dict), ou seja, para cada tipo
sanguíneo encontrados na lista gerada no ítem 2 nós faremos uma contagem e a chave do dicionário será o tipo sanguíneo.
Ex:

[{"altura": 85.6, "peso": 177, "tipo_sangue": "A+"},
 {"altura": 72.47, "peso": 165, "tipo_sangue": "B-"},  =>  {"A+": 2, "B-": 1}
 {"altura": 90.0, "peso": 172, "tipo_sangue": "A+"}]

5: Salvando os resultados em um arquivo

Salve os valores das médias das alturas e pesos num arquivo .txt em linhas separadas. Ex:

82.5
172
{"A+": 2, "B-": 1}