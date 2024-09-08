# DIO - Trilha .NET - Fundamentos
www.dio.me

## Desafio de projeto
Para este desafio, você precisará usar seus conhecimentos adquiridos no módulo de fundamentos, da trilha .NET da DIO.

## Contexto
Você foi contratado para construir um sistema para um estacionamento, que será usado para gerenciar os veículos estacionados e realizar suas operações, como por exemplo adicionar um veículo, remover um veículo (e exibir o valor cobrado durante o período) e listar os veículos.

## Proposta
Você precisará construir uma classe chamada "Estacionamento", conforme o diagrama abaixo:
![Diagrama de classe estacionamento](diagrama_classe_estacionamento.png)

A classe contém três variáveis, sendo:

**precoInicial**: Tipo decimal. É o preço cobrado para deixar seu veículo estacionado.

**precoPorHora**: Tipo decimal. É o preço por hora que o veículo permanecer estacionado.

**veiculos**: É uma lista de string, representando uma coleção de veículos estacionados. Contém apenas a placa do veículo.

A classe contém três métodos, sendo:

**AdicionarVeiculo**: Método responsável por receber uma placa digitada pelo usuário e guardar na variável **veiculos**.

**RemoverVeiculo**: Método responsável por verificar se um determinado veículo está estacionado, e caso positivo, irá pedir a quantidade de horas que ele permaneceu no estacionamento. Após isso, realiza o seguinte cálculo: **precoInicial** * **precoPorHora**, exibindo para o usuário.

**ListarVeiculos**: Lista todos os veículos presentes atualmente no estacionamento. Caso não haja nenhum, exibir a mensagem "Não há veículos estacionados".

Por último, deverá ser feito um menu interativo com as seguintes ações implementadas:
1. Cadastrar veículo
2. Remover veículo
3. Listar veículos
4. Encerrar


## Solução
**TODO: Pedir para o usuário digitar uma placa (ReadLine) e adicionar na lista "veiculos"**


Explicação: Nesse desafio adicionei um Console.WriteLine para informar o usuário em que irá ser pedido à ele informar a placa do veículo, a linha seguinte (string line = Console.ReadLine();) contém exatamente esse comando de permitir o usuário digitar algo no qual, nesse caso é a placa do veículo que deseja estacionar no estacionamento.

Console.WriteLine("\nDigite a placa do veículo para estacionar:");
string line = Console.ReadLine();


**TODO(EXTRA): Verifica caso o veículo já está estacionado**


Explicação: Esse foi um código adicionado por mim que é facultativo para o funcionamento do projeto. No código abaixo é feita uma verificação caso o veículo em que o usuário informou (código informado acima) já está adicionado ao estacionamento ao array de veículos aonde é armazenado todos os veículos previamente adicionados pelo usuário ao estacionamento. Caso o veículo informado já estiver estacionado, é retornado ao usuáio que Console.WriteLine("\nEsse veículo já está estacionado, verifique caso informou a placa corretamente."); mas caso o veículo não esteja estacionado, o programa segue normalmente permitindo adicionar a placa informada pelo usuário ao array de veículos.

  if (veiculos.Contains(line))
  {
      Console.WriteLine("\nEsse veículo já está estacionado, verifique caso informou a placa corretamente.");
  }
  else
  {
      veiculos.Add(line);
  }
}


**TODO: Pedir para o usuário digitar a quantidade de horas que o veículo permaneceu estacionado,**


Explicação: Através do Console.ReadLine(); o usuário consegue informar a quantidade de horas em que o veículo no qual deseja tirar do estacionamente permaneceu dentro dele. O Console.WriteLine("\nDigite a quantidade de horas que o veículo permaneceu estacionado:"); permite o usuário entender o que deve ser informado ao programa.

Console.WriteLine("\nDigite a quantidade de horas que o veículo permaneceu estacionado:");
string informa_horas = Console.ReadLine();


**TODO: Realizar o seguinte cálculo: "precoInicial + precoPorHora * horas" para a variável valorTotal**


Explicação: Tendo como referência o desafio acima (Pedir para o usuário digitar a quantidade de horas que o veículo permaneceu estacionado), o int.Tryparse(informa_horas out horas) irá substituir o valor literal armazenado no int horas = 0 para a conversão da string armazenada no informa_horas para um número inteiro (int), após a conversão e armazenamento da no novo valor de horas irá ser feito o caculo do preço total à ser pago pelo motorista, através do código decimal valorTotal = (horas * precoPorHora) + precoInicial;, no qual apresenta que o valorTotal irá ser igual ao número de horas vezes o preço por hora adicionado ao preço inicial fixo pago pelo motorista.

int horas = 0;
int.TryParse(informa_horas, out horas);

decimal valorTotal = (horas * precoPorHora) + precoInicial;



**TODO: Remover a placa digitada da lista de veículos**


Explicação: Através do veiculos.Remove(); é possível remover uma varíavel armazenada dentro do array, nesse caso, a placa em que o usuário deseja remover.

veiculos.Remove(placa);


**TODO: Realizar um laço de repetição, exibindo os veículos estacionados**


Explicação: O laço de repetição é feito através do código foreach (string i in veiculos) {Console.WriteLine(i);}, que possibilita que seja mostrado no terminal os elementos dentro da array veiculos, aonde i é a váriavel contadora que irá permitir que seja feita a busca pelas varíaveis armazenadas dentro do array, até que a útilma variável seja apresentada no terminal, concluido assim o laço de repetição.


foreach (string i in veiculos)
{
Console.WriteLine(i);
}
}
else
{
Console.WriteLine("\nNão há veículos estacionados.");
}
