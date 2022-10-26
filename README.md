# Lab B
## Introdução
Pretende-se desenvolver uma aplicação que permita gerar percursos a pé e de bicicleta dentro de um parque biológico. A aplicação disponibiliza informação sobre o preço total a pagar pelo percurso selecionado.
O parque biológico é constituído por vários pontos de interesses, pontos esses que estão conectados caminhos, os caminhos podem ser percorridos em qualquer sentido, no entanto existem caminhos que não permitem a circulação de bicicletas. Cada conexão tem um custo, e uma distância associada.
Cada percurso inicia e termina num ponto do parque e este é pago em função disso. O utilizador poderá por optar pelo percurso mais curto, ou o mais barato.
## Nível 1
* Crie a Classe PontoInteresse que representa um Local no Mapa
* Crie a Classe Conexao que representa um troço de caminho que liga dois pontos.
  Uma Conexão guarda a seguinte informação:
  * ID
  * Navegabilidade (boolean)
  * Custo
  * Distancia
* Crie a classe MapManager que será responsável por gerir os percursos no parque
  * Adicione uma instância de GraphEdgeList com nome map, que será manipulada posteriormente, de forma a que permita guardar o mapa lido.
  * Implemente os métodos que permitam adicionar um novo Ponto no mapa
  * Implemente os métodos que permitam adicionar um nova conexão no mapa
 
 # Nivel 2
 O mapa do parque deve ser configurável, através de um ficheiro de texto com o seguinte formato:
 *     n_pontos
 *     id_ponto, ponto
      ...
 *     n_conexoes
 *     id_c, nconexao, id_ponto1, id_ponto2, navegabilidade, custo, distancia
      ...
( disponibiliza-se um ficheiro mapa1.txt como exemplo)

Cada placeholder contém um valor de acordo com a seguinte descrição:
* n_pontos: número de pontos de interesse marcados no mapa; dita também quantos pontos são descritos em seguida no ficheiro – valor inteiro;
* id_ponto: identificador do ponto do mapa – valor inteiro;
* ponto: nome do ponto do mapa – texto;
* n_conexoes: número de conexoes marcadas no mapa; dita também quantas conexões são descritas de seguida no ficheiro – valor inteiro;
* id_c: identificador da conexao do mapa – valor inteiro;
* conexao – nome da conexão - texto;
* id_ponto1 e id_ponto2: identificadores dos pontos que a conexão liga, no caso de ser uma ponte, esta só pode ser atravessada no sentido do ponto1 para o ponto2 – valores inteiros, cujos pontos já foram definidos no início do ficheiro.
* navegabilidade: true se for passível de atravessar de bicicleta, false, caso contrário – um dos seguintes valores {“true”, “false”};
* custo: custo (€) para a travessia dessa conexão – valor inteiro >= 0;
* distancia: distância (m) associada a atravessar essa conexão – valor inteiro >= 0;

# Nivel 3

Implementar os seguintes métodos na classe MapManager.
- Método que dado um ponto de interesse, mostrar todos as conexões que se podem tomar a partir desse local
- Método que dado dois pontos calcular o número de conexões diretas que existem entre esses dois locais.
- Método para determinar se existem pontos isolados no mapa.
- Método que devolve quais as conexões onde é possível andar de bicicleta.

# Nivel 4
Implemente um método baseado no algoritmo de Dijkstra que dado um ponto de origem e um ponto de destino, o tipo de percurso (a pé ou de bicicleta) e o aspeto a otimizar (custo ou distancia), calcule o custo total do percurso, a distancia total e os troços percorridos.

# Nivel 5
Implemente em modo consola, uma user-interface (com menus) que permita testar os níveis 1-4: Nomeadamente
1. carregar um ficheiro
2. ver informação sobre o mapa
  * número de Locais
    * número de caminhos
    * número de caminhos onde podem circular bicicletas
  * Pontos isolados no mapa
3. Dado um Local determinar todos as conexões possível tomar a partir daquele local.
4. Calcular um caminho dado o ponto de origem e chegada, o aspeto a optimizar (custo o distancia) e o tipo de percurso (a pé ou de bicicleta). Deverá mostra a seguinte informação:
  * Custo; Distancia e conexões percorridas.
