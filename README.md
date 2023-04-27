Simulação de Atendimento
Esse é um código em Python para simular o atendimento de uma fila de clientes em um estabelecimento. A simulação é feita usando a biblioteca SimPy.

Funcionamento do código
O código é composto pela classe Atendimento, que representa o sistema de atendimento em si. Essa classe possui os seguintes atributos:

env: o ambiente de simulação do SimPy
num_atendentes: o número de atendentes disponíveis no sistema
taxa_chegada: a taxa média de chegada de clientes no sistema
tempo_atendimento: o tempo médio de atendimento de cada cliente
fila: uma lista que representa a fila de espera dos clientes
atendentes: uma lista que representa quais atendentes estão ocupados com cada cliente
A classe também possui os seguintes métodos:

gera_chegada: método para gerar o tempo até a chegada do próximo cliente, seguindo uma distribuição exponencial
gera_tempo_atendimento: método para gerar o tempo de atendimento de um cliente, seguindo uma distribuição exponencial
chegada_cliente: método para simular a chegada de um novo cliente no sistema
execucao_atendimento: método para simular o atendimento de um cliente no sistema
Além disso, o código também tem um trecho para verificar se um cliente desistiu da fila. Esse trecho de código ainda não está completo e precisa ser ajustado.

Como usar o código
Para usar o código, basta criar uma instância da classe Atendimento e rodar a simulação usando o ambiente do SimPy. Por exemplo:

scss
Copy code
env = simpy.Environment()
atendimento = Atendimento(env, num_atendentes=2, taxa_chegada=0.5, tempo_atendimento=5.0)
env.run(until=100)
Nesse exemplo, a simulação roda por 100 unidades de tempo (minutos, horas, etc.) e tem dois atendentes disponíveis, uma taxa média de chegada de 0.5 clientes por unidade de tempo e um tempo médio de atendimento de 5 unidades de tempo.

Ao final da simulação, é possível criar um dataframe com as informações dos clientes usando o seguinte código:

bash
Copy code
df = pd.DataFrame(atendimento.clientes)
Esse dataframe contém as seguintes colunas:

nome: nome do cliente
hora_chegada: hora em que o cliente chegou no sistema
hora_atendimento: hora em que o cliente foi atendido
tempo_espera: tempo que o cliente esperou na fila antes de ser atendido
Melhorias a serem feitas
O código atual ainda precisa de algumas melhorias para se tornar mais completo e realista. Algumas possíveis melhorias são:

Adicionar um contador para o número de clientes que desistiram da fila
Adicionar uma opção para definir um tempo máximo de espera na fila
Melhorar a saída de dados para incluir informações sobre o número de clientes que desistiram da fila e o tempo médio de espera
Autor
Esse código foi desenvolvido por Dheiver.
