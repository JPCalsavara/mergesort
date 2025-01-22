# Mergesort
![image](https://img.shields.io/badge/Programming-brightgreen?style=plastic&logo=c%2B%2B)

Trabalho prático desenvolvido para a disciplina de Sistemas Operacionais - TT304, da Faculdade de Tecnologia da Unicamp.

Grupo: 2Threads

Discentes: Hitallo Alves Teles Azevedo / João Pedro Leite Calsavara

Docente: André Leon S. Gradvohl

<a target="_blank" href="https://youtu.be/-b-9yzjy3Eg">Vídeo explicando o projeto detalhadamente</a>

## Descrição do problema
Este programa em C processa múltiplos arquivos de entrada, cada um contendo uma lista de inteiros desordenados (um em cada linha), utilizando threads. Ele realiza a leitura e ordenação simultânea dos arquivos, armazenando o resultado em um arquivo de saída. A implementação visa medir o impacto do aumento de threads no tempo de execução. 

## Instruções para executar o projeto 
O projeto foi desenvolvido utilizando linguagem C pura e a biblioteca POSIX threads para manipulação das threads. Portanto, para a execução do programa, é pré requisito que o sistema operacional seja baseado em Linux.


Com o terminal aberto e o GIT devidamente instalado, execute o comando a seguir para clonar o repositório.
```
  git clone https://github.com/hitalloazevedo/mergesort
```

Abrindo o repositório
```
cd mergesort
```

Compilando o programa
```
make
```

Executando o programa
```
./mergesort <T> <F1> <F2> <F3> -o <OF>
```
##### Argumentos
\<T\>: quantidade de threads que o programa irá utilizar. <br>
\<Fn\>: Nome do arquivo de entrada, deve incluir a extensão do arquivo.<br>
-o: Indica que o próximo argumento será o nome do arquivo de saída.<br>
\<OF\>: Nome do arquivo de saída, deve incluir a extensão do arquivo.

<strong>Após a execução do programa, o programa irá gerar um arquivo de saida que estará localizado em `/mergesort/outputs`.</strong>

#### Configurações essenciais para uma execução correta
Os arquivos de entrada com os valores inteiros devem estar localizados em `/mergesort/inputs`. <br>
É recomendado que as extensões dos arquivos de entrada e saída sejam `.dat` ou `.txt`.

## Experimentos
#### Configuração das amostras de teste
- 5 arquivos
- 1000 inteiros ordenados de forma decrescente
#### Configuração dos casos de teste
- 1 thread
- 2 threads
- 4 threads
- 8 threads

Cada teste utilizou a amostra pré definida e diferentes quantidades de threads. Para cada quantidade de thread foi realizada 5 execuções, com os tempos de execução foi calculada a média aritmética.

#### Executando os casos de teste
Testes com 1 thread

`./casodeteste1.sh` ou `bash casodeteste1.sh`

Testes com 2 threads

`./casodeteste2.sh` ou `bash casodeteste2.sh`

Testes com 4 threads

`./casodeteste3.sh` ou `bash casodeteste3.sh`

Testes com 5 threads

`./casodeteste4.sh` ou `bash casodeteste4.sh`

## Resultados
Os tempos de execução estão numa escala de microssegundos. (1 microssegundo == 10⁻⁶ segundo)

1 thread
|Thread 1|Tempo Total|
| -       | -        |
| 60     | 75        |

2 threads
|Thread 1|Thread 2|Tempo total|
| -       | -        | -|
| 33     | 33        | 106 |

4 threads
|Thread 1|Thread 2|Thread 3|Thread 4| Tempo total |
| -       | -        | -|-|-|
| 14     | 16        |13| 14|107|

8 threads
|Thread 1|Thread 2|Thread 3|Thread 4|Thread 5|Thread 6|Thread 7|Thread 8| Tempo total |
| -       | -        | -|-|-|-|-|-|-|
| 7     | 8        |8    |   8        |   9        |        8 |    8       |     8        | 130 |

## Resultados
Esses resultados indicam que, embora o uso de múltiplas threads tenha permitido a execução paralela de tarefas, o tempo total não diminuiu proporcionalmente com o aumento no número de threads. A configuração com 1 thread apresentou o menor tempo total, enquanto o uso de 8 threads resultou em um tempo total mais elevado.
Esses dados mostram que a sobrecarga de gerenciamento de múltiplas threads aumenta com o número de threads, o que, em alguns casos, pode anular os ganhos de paralelismo. Isso sugere que, para tarefas de I/O e processamento leve, um número menor de threads pode oferecer um desempenho mais eficiente.
