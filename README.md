# AED3 - TP3: Backup-compactado

## Descrição do que foi realizado
  Foi implementada apenas uma classe nova (MenuLZW), utilizada para o menu para compactar de descompactar os arquivos de livros. A principal razão da classe ter sido desenvolvida da forma que está, é tentar simular e mostrar que quanto maior a parte do arquivo carregado em memória para a compactação, menor será o arquivo de backup, pois a utilização do dicionário durante a compaatação é maior. Sendo assim, a compactação e feita de duas formas diferentes, uma carregando o arquivo inteiro em memória e aplicando o LZW, já o outro, pegando 'x' bytes fixos do arquivo de cada vez e aplicando o LZW de parte em parte, na tentativa de simlular um arquivo grande e memória para ler o arquivo limitada. Os arquivos compactados são guardados em pastas separadas para o arquivo inteiro, backup, e arquivo compactado por partes, backup2, cujo nome das pastas(versão) é a data e horário na qual o método foi iniciado.
  já na descompactação foi feita de forma semelhante, o usuário escolhe a opção da versão que deseja recuperar os arquivos e os dois métodos de descompactação e feita. Além de imprimir o tamanho de cada arquivo compactado, no final é mostrada a proporção de quanto o backup feito por partes é maior que o arquivo compactado inteiro, podendo assim ser analisado de forma mais clara que quanto maior parte do arquivo carregado em memória melhor o uso do LZW pois a repetição dos bytes se torna mais frequente.
  Também na descompactação dos arquivos, são escritos em pastas de dados diferentes, uma na pasta "dados" que é original do projeto e outra na pasta "dados2". Este prossedimento foi feito para mostrar a integridade dos dados presente nos dois métodos de leitura de arquivos utilizados.
  No menu (classe "Principal") foi adicionada a opção para acesso do menu de backup.
Os métodos criados na nova classe para atender as especificações do projeto foram:
#### Para compactar os arquivos:
 CompactarArquivos: Método simplesmente usado para criar os diretórios caso não exista e chamar os métodos para compactação.
 metodo1_compactar: método que lê o arquivo de forma integral e aplica o LZW.
 metodo2_compactar: método que lê o arquivo uma quantidade fixa de bytes de cada vez aplicando o LZW em cada. trecho.

#### Para descompactar os arquivos:
  DescompactarArquivos: Semelhante as compactarArquivos mas listando os backups para o usuário escolher qual versão deseja recuperar.
 metodo1_descompactar: método que lê o arquivo de forma integral a partir da pasta "backup" e aplica o LZW para descompactar.
 metodo2_descompactar: método que lê o arquivo a partir da pasta "backup2" aplicando o LZW a partir de cada trecho compactado.Também no final mostra a relação de quanto uma compactação é maior que a outra, como já foi explicado anteriormente. (Observação: Não se sabe se o método para identificar estes trechos compactados é o correto, mas como ele funcionou com todos os arquivos compactados foi decidido deixar dessa forma)

#### Experiência do grupo
  A lógica do LZW não é complicada, e como na teoria, quanto maior o arquivo em memória maior a chance de repetições e, portanto maior o uso do dicionário criado, o que proporciona redução do tamanho do arquivo em comparação com o original. Já na aplicação, como apontado anteriormente, na descompactação dos arquivos feita em partes, não se sabe se a lógica foi aplicada de forma correta, apesar do resultado ser correto em todos os caso em que foi aplicado.

#### Perguntas objetivas sobre o projeto(chacklist):

 * Há uma rotina de compactação usando o algoritmo LZW para fazer backup dos arquivos?
	Sim.
 * Há uma rotina de descompactação usando o algoritmo LZW para recuperação dos arquivos?
	Sim.
 * O usuário pode escolher a versão a recuperar?
	Sim, é mostrada as lista das vesões e o usuário pode escolher qual deseja recuperar.
 * Qual foi a taxa de compressão alcançada por esse backup? (Compare o tamanho dos arquivos compactados com os arquivos originais)
	A taxa é calculada e mostrada durante a execução da compactação o quanto o arquivo compactado é menor que o original.
 * O trabalho está funcionando corretamente?
	Sim.
 * O trabalho está completo?
	Sim.
 * O trabalho é original e não a cópia de um trabalho de um colega?
	Sim.

