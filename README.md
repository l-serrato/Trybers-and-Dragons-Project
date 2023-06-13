# Projeto Trybers and Dragons

<strong>O que foi desenvolvido</strong>

  Para este projeto, você deverá aplicar os princípios da arquitetura `SOLID` e os princípios de `POO` em uma estrutura de jogos de interpretação de papéis, mais conhecidos como jogos `RPG` (_Role Playing Game_).

  ---
  
  # Requisitos

### 1 - Criação da classe `Race`

No universo de Trybers and Dragons - T&D, quase todos os seres racionais têm uma raça e, embora todas as raças de personagens sejam humanoides, cada uma tem as suas particularidades.

A raça influencia desde a aparência geral até fatores como longevidade média, talento em determinadas habilidades ou mesmo a presença de algum sentido mais aguçado nos habitantes desse universo.

Para entender melhor um pouco da incrível diversidade que temos e as características únicas de algumas das raças de T&D, vamos começar nossa jornada com a missão de **criar a classe abstrata `Race`**.

Para que você tenha sucesso nesta *quest*, é importante saber que:

- O arquivo deve ser criado no diretório `src/Races/` e se chamar `Race.ts`;
- A classe `Race` deve ter os atributos privados: `name` e `dexterity`, ambos inicializados em seu **construtor**;
  - O atributo `name` dever ser do tipo `string`;
  - O atributo `dexterity` dever ser do tipo `number`;
  - `name` e `dexterity` devem ser recebidos como parâmetros e inicializados no construtor.
- Os atributos da classe `Race` podem ser lidos, mas não podem ser alterados:
  - `name` deve retornar o tipo `string`;
  - `dexterity` deve retornar o tipo `number`.
- A classe `Race` deve ter um **método estático** chamado `createdRacesInstances`, que retorna um `number`;
  - Esse número corresponde à quantidade de **instâncias criadas a partir das classes estendidas** da classe `Race`;
  - Cada raça terá seu número máximo de instâncias, **que será definido dentro de cada classe especializada**;
  - Na classe `Race`, o método deve lançar um erro com a mensagem `Not implemented`.
- A classe `Race` deve ter um **getter abstrato** chamado `maxLifePoints` que retorna um `number`;
  - Esse número corresponde à quantidade máxima de pontos de vida da raça;
  - Cada raça terá seu número máximo de pontos, **que será definido dentro de cada classe especializada**;
  - Na classe `Race` **deve estar apenas a assinatura do método**.

---

### 2 - Criação das classes que herdam de `Race`
  
Já foi dito anteriormente que há uma diversidade de raças neste universo e agora chegou a hora de você saber mais a respeito de algumas delas. Nesta segunda *quest*, você irá criar classes para quatro raças que existem no mundo de T&D.

Antes de prosseguir com a missão, é muito importante saber que:

- Os arquivos devem ser criados no diretório `src/Races/`;
- Todas as raças devem estender da classe abstrata `Race`;
- As classes `Dwarf`, `Elf`, `Halfling` e `Orc` devem ser criadas em arquivos com exatamente esses nomes.
- Cada raça deve possuir um número máximo de pontos de vida (`maxLifePoints`), que deve ser inicializado em seu **construtor**:
  - A raça `Dwarf` deve receber `80` pontos de vida;
  - A raça `Elf` deve receber `99` pontos de vida;
  - A raça `Halfling` deve receber `60` pontos de vida;
  - A raça `Orc` deve receber `74` pontos de vida.
- Não se esqueça de implementar o(s) método(s) necessário(s) após estender a classe abstrata `Race`;
- Não se esqueça de fazer a sobrescrita (`override`) do(s) método(s) necessário(s).
  
---

### 3 - Criação da interface `Energy`
  
Energia é um atributo vital para a maioria dos seres. No contexto de `Trybers and Dragons`, a energia gasta ao se andar, nadar, escalar ou lutar é chamada de *"stamina"* .
Contudo, esse universo também abriga seres capazes de usar magia. Nesses casos, a energia gasta é chamada de *"mana"*.

Sua próxima missão é tornar possível o uso destes dois tipos de energia:  *"stamina"* e *"mana"*. Para isso:

- Crie uma `interface` chamada `Energy`, para isso:
  - Crie o arquivo `Energy.ts` na raiz do diretório `src/`.
  - A interface deverá possuir os atributos:
    - `type_`, do tipo `EnergyType`;
      - Esse novo tipo ~~pode~~ deve receber os valores: `'mana'` ou `'stamina'`;
      - O tipo `EnergyType` também deve ser exportado.
    - `amount`, do tipo `number`.
  
---

### 4 - Criação da classe `Archetype`
  
Dentro do nosso universo, os seres têm talentos especiais e cada um desses talentos tem o seu nome dentro de T&D.
Aqui vamos ter alguns atributos super legais e necessários, que representarão o nome, a potência do seu ataque especial e o custo energético para utilizá-lo. Por isso, sua próxima *quest* será **criar a classe abstrata `Archetype`**.

Para que você tenha sucesso nesta *quest*, é importante saber que:

- O arquivo `Archetype.ts` deve ser criado no diretório `src/Archetypes/`;
- A classe `Archetype` deve ter os atributos privados: `name`, `special`, `cost`, que serão inicializados em seu **construtor**;
  - O atributo `name` dever ser do tipo `string`;
  - O atributo `special` dever ser do tipo `number`;
  - O atributo `cost` dever ser do tipo `number`;
  - `name` deve ser recebido como parâmetro e inicializado no construtor;
  - `special` e `cost` devem ser apenas inicializados no construtor com o valor `0`.
- Os atributos da classe `Archetype` podem ser lidos, mas não podem ser alterados:
  - `name` deve retornar o tipo `string`;
  - `special` deve retornar o tipo `number`;
  - `cost` deve retornar o tipo `number`.
- A classe `Archetype` deve ter um **método estático** chamado `createdArchetypeInstances` que retorna um `number`:
  - Esse número corresponde à quantidade de **instâncias criadas a partir das classes estendidas** da classe abstrata `Archetype`;
  - Cada arquétipo terá seu número máximo de instâncias, **que será definido dentro de suas classes especializadas**;
  - Na classe abstrata `Archetype`, o método deve apenas lançar um erro com a mensagem `Not implemented`.
- A classe `Archetype` deve ter um **getter abstrato** chamado `energyType` que retorna uma `EnergyType`:
  - Esse tipo EnergyType corresponde ao tipo de energia que este arquétipo deve ter. *(`mana` ou `stamina`)*
  - Cada arquétipo terá o seu tipo de energia, **que será definido dentro de suas classes especializadas**;
  - A classe abstrata `Archetype` **deve conter apenas a assinatura do método**.

---

### 5 - Criação de classes que herdam de `Archetype`
  
Como você pode imaginar, há diversos arquétipos diferentes no mundo de *Trybers and Dragons*, cada um com as suas peculiaridades e alinhamentos.
Agora, chegou a hora de você conhecer alguns desses arquétipos. E o que poderia ser melhor para isso do que criar classes para eles?
Para isto, atenção às instruções a seguir:

- Os arquivos devem ser criados no diretório `src/Archetypes/`;
- Todos os arquétipos devem estender da classe abstrata `Archetype`.
- No momento, vamos nos ater a quatro arquétipos muito comuns aos seres deste universo: (eles devem estar em quatro arquivos com os mesmos nomes)
  - `Mage`;
  - `Necromancer`; 
  - `Warrior`;
  - `Ranger`.
- Cada arquétipo possui a habilidade de causar danos em seus inimigos de forma diferente, e essa habilidade deve ser inicializada em seu **construtor**
  - Os arquétipos `Mage` e `Necromancer` causam dano por meio de magia, através do uso de `mana`;
  - Os arquétipos `Warrior` e `Ranger` causam dano por meio de sua força, usando `stamina`.
- Não se esqueça de implementar o(s) método(s) necessário(s) após estender a classe abstrata `Archetype`;
- Não se esqueça de fazer a sobrescrita (`override`) do(s) método(s) necessário(s);

---

### 6 - Crie a interface `Fighter`
  
Um universo tão rico e cheio de diferentes seres, com diferentes alinhamentos, convicções e personalidades pode não ser um lugar sempre amigável. Por isso, seus habitantes têm que ser capazes de se defender ou de inventar artimanhas para se livrarem de brigas, confusões e armadilhas. Sendo assim, podemos dizer que todos os seres de T&D são, em essência, lutadores.

Para fixar bem esse conceito, preparamos para você a missão especial de criar a interface `Fighter`. Mas não se preocupe! Não deixaremos você dar mais nem um passo sem as informações necessárias para tirar isso de letra! Observe as orientações abaixo:

- Crie uma `interface` chamada `Fighter`;
- O arquivo `Fighter.ts` deve ser criado no diretório `src/Fighter/`;
- A interface deverá possuir os atributos:
  - `lifePoints`, do tipo `number`;
  - `strength`, do tipo `number`;
  - `defense`, do tipo `number`;
  - `energy`, do tipo `Energy`.
- A interface deverá possuir os métodos:
  - `attack()`, que recebe um `enemy` do tipo `Fighter` como parâmetro e não possui retorno (`void`);
  - `special()`, que recebe um `enemy` do tipo `Fighter` como parâmetro e não possui retorno (`void`);
  - `levelUp()`, que não recebe parâmetro e não possui retorno (`void`);
  - `receiveDamage()`, que recebe um `attackPoints` do tipo `number` como parâmetro e retorne um `number`.
  
---

### 7 - Crie a classe `Character`

Maravilha! Agora já temos tanto as nossas raças quanto os nossos arquétipos e interfaces definidos. Mas antes de sair por aí entrando em tavernas e calabouços, temos outra *quest*: **criar uma personagem**!

Cada personagem será composta tanto por uma raça quanto por um arquétipo. Essa classe reunirá um conjunto de características que terão o poder de fazer desse ser o mais único possível. Além disso, personagens devem possuir tudo o que se espera de alguém que luta.

As dicas para completar essa *quest* são: 

- O arquivo deve ser criado na raiz do diretório `src/` e se chamar `Character.ts`;
- A classe deve implementar a interface `Fighter`;
- A classe `Character` deve ter os atributos privados: `race`, `archetype`, `maxLifePoints`, `lifePoints`, `strength`, `defense`, `dexterity` e `energy`, todos inicializados em seu **construtor**;
  - O atributo `race` deve ser do tipo `Race`;
  - O atributo `archetype` deve ser do tipo `Archetype`;
  - O atributo `maxLifePoints` deve ser do tipo `number`;
  - O atributo `lifePoints` deve ser do tipo `number`;
  - O atributo `strength` deve ser do tipo `number`;
  - O atributo `defense` deve ser do tipo `number`;
  - O atributo `dexterity` deve ser do tipo `number`;
  - O atributo `energy` deve ser do tipo `Energy`;
  - O atributo `name` deve ser recebido como parâmetro no construtor e deve ser usado para dar nome à sua personagem.
  - Devem ser inicializados no construtor:
    - `dexterity` com um valor aleatório de no mínimo 1 e no máximo 10 pontos;
    - `race` por padrão com uma instância de `Elf` (A destreza de `Elf` deve ser a mesma definida em `dexterity`);
    - `archetype` por padrão com uma instância de `Mage`;
    - `maxLifePoints` por padrão com metade do `maxLifePoints` da raça instanciada;
    - `lifePoints` por padrão com o mesmo valor de `maxLifePoints` da classe;
    - `strength`, `defense` com valores aleatórios de no mínimo 1 e no máximo 10 pontos;
    - `energy` por padrão:
      - `type_` com o mesmo valor do arquétipo instanciado;
      - `amount` com um valor aleatório de no mínimo 1 e no máximo 10 pontos.
- Os atributos da classe `Character` podem ser lidos mas não podem ser alterados:
  - `race` deve retornar o tipo `Race`;
  - `archetype` deve retornar o tipo `Archetype`
  - `lifePoints` deve retornar o tipo `number`;
  - `strength` deve retornar o tipo `number`;
  - `defense` deve retornar o tipo `number`;
  - `dexterity` deve retornar o tipo `number`;
  - `energy` deve retornar o tipo `Energy`.
    - `energy` é um objeto, portanto se você retornar ele diretamente o javascript permite que as propriedades desse objetos sejam alteradas, mesmo `energy` sendo privado. 
- A classe `Character` também deve implementar os métodos estendidos da `interface Fighter`;
  - **`receiveDamage`** este método recebe por parâmetro um valor (`attackPoints`) e as regras são:
    - Para calcular o dano recebido (`damage`), o valor da defesa (`defense`) do personagem deve ser subtraído do valor do ataque recebido (`attackPoints`);
    - Se o dano calculado (`damage`) for maior que `0`, você perde esse valor em pontos de vida (`lifePoints`). Se o dano calculado (`damage`) for igual ou menor a zero, você deve perder apenas `1` ponto de vida (`lifePoints`);
    - Ao receber o ataque e perder pontos de vida (`lifePoints`), e se sua vida chegar a `0` ou menos, você deve fixá-la com o valor `-1`;
    - Ao final sempre retorne o valor atualizado de seus pontos de vida.
  - **`attack`** este método recebe por parâmetro uma pessoa inimiga (`enemy`) e as regras são:
    - Toda vez que acontecer um ataque, o inimigo recebido por parâmetro recebe um dano;
    - Este dano deve ser equivalente a força (`strength`) de quem ataca.
  - **`levelUp`** este método não recebe parâmetro e as regras são:
    - Sempre que este método for chamado os atributos `maxLifePoints`, `strength`, `dexterity` e `defense` terão um incremento de no mínimo 1 e no máximo 10 pontos;
    - Assim como os atributos anteriores o montante de energia (`amount` dentro de `energy`) deve ser alterado também, ele deve ficar cheio, valendo exatamente `10`;
    - O atributo `maxLifePoints` do Character **nunca poderá ser maior** que o `maxLifePoints` de sua raça (`race`). Se, ao incrementar o valor de `maxLifePoints` do Character esse valor ficar maior do que o `maxLifePoints` da raça, ele deve receber o valor igual ao do da raça. Exemplo: se o `maxLifePoints`da raça é 100, e o do Character é 95, e ao fazer o levelUp ele ficaria 8 pontos maior, isso daria 103, que é maior do que o da raça, portanto você deveria deixar em 100.
    - Ao final, o atributo `lifePoints` também deve ser atualizado, recebendo o novo valor de `maxLifePoints` (de acordo com as regras anteriores).

---

### 8 - Crie a interface `SimpleFighter`

Uau, o nosso universo de T&D está ficando fabuloso! No entanto, nem todo mundo que luta possui capacidades avançadas, como ter uma defesa ou realizar ataques especiais. Dito isto, vamos para mais uma *quest*: **criar a interface lutador simples**

As dicas para completar essa *quest* são:

- Crie uma `interface` chamada `SimpleFighter`;
- O arquivo `SimpleFighter.ts` deve ser criado no diretório `src/Fighter/`.
- A interface deverá possuir os atributos:
  - `lifePoints`, do tipo `number`;
  - `strength`, do tipo `number`.
- A interface deverá possuir os métodos:
  - `attack()` que recebe um `enemy` do tipo `SimpleFighter` como parâmetro e não possui retorno (`void`);
  - `receiveDamage()` que recebe um `attackPoints` do tipo `number` como parâmetro e retorne um `number`;

---

### 9 - Crie a classe `Monster`

Se existem seres que implementam a `interface Fighter`, deve existir seres que implementam a `interface SimpleFighter` também, não é ? Estes são os `Monsters`, criaturas bestiais que apenas atacam outros seres. Então, sua próxima *quest* é: **criar a classe Monster**!

O que você deve saber para seguir em frente:

- O arquivo deve ser criado na raiz do diretório `src/` e chamar `Monster.ts`;
- A classe deve implementar a interface `SimpleFighter`;
- A classe `Monster` deve ter os atributos privados `lifePoints` e `strength`, ambos inicializados em seu **construtor**:
  - Os atributos `lifePoints` e `strength` devem ser do tipo `number`;
  - Devem ser inicializados no construtor:
    - `lifePoints` por padrão com o valor de `85`;
    - `strength` por padrão com o valor de `63`.
- Os atributos da classe `Monster` podem ser lidos mas não podem ser alterados:
  - `lifePoints` e `strength` devem retornar o tipo `number`.
- A classe `Monster` também deve implementar os métodos estendidos da `interface SimpleFighter`:
  - **`receiveDamage`** este método recebe por parâmetro um valor (`attackPoints`) e as regras são:
    - Este valor deve ser decrescido de seus pontos de vida (`lifePoints`), assim causando um dano (`damage`);
    - Ao receber o ataque, sua vida nunca poderá chegar a `0`, se isto acontecer seus `lifePoints` devem valer `-1`;
    - Ao final o método deve retornar o valor atualizado dos pontos de vida.
  - **`attack`** este método recebe por parâmetro uma pessoa inimiga (`enemy`) e as regras são:
    - Toda vez que acontecer um ataque, o inimigo recebido por parâmetro recebe um dano;
    - Este dano deve ser calculado a partir de `attackPoints` equivalentes à força (`strength`) de quem ataca.

---

### 10 - Crie a classe `PVP`

A ideia do mundo de T&D ser completamente pacífico provavelmente já deve ter desaparecido da sua mente depois das suas últimas *quests*. 
Nesse mundo, existem lutas, muitas delas inclusive épicas, denominadas `Battles` (batalhas). Sua representação geral/abstrata já foi fornecida anteriormente, entretanto, existem tipos específicos de batalhas. Uma dessas batalhas chamamos de `PVP`, batalhas entre personagens (ou *player versus player*), que só podem acontecer entre personagens lutadores (`Fighters`).

Sua *quest* agora é justamente **criar a classe PVP**, então, você que lute !
Brincadeira! Estamos aqui para te ajudar e por isso trazemos abaixo algumas dicas preciosas para garantir a sua vitória neste requisito:

- O arquivo deve ser criado no diretório `src/Battle/` e se chamar `PVP.ts`;
- A classe `PVP` deve herdar de `Battle`;
- A classe `Battle` já esta criada, dê uma espiada nela;
- Na criação de uma instância de `PVP` é esperado que em seu construtor sejam recebidos dois `Characters` lutadores, ambos inicializados lá;

---

### 11 - Criar a classe `PVE`

Nem todas as batalhas são entre personagens lutadoras (`Character`), afinal, há perigos à solta que espreitam ao escurecer, em densas florestas ou em calabouços profundos.

Monstros representam alguns destes perigos, assim, temos as batalhas do tipo `PVE`(*player versus environment*), em que personagens (sempre do tipo `Fighter`) podem lutar contra um ou mais monstros assustadores (`SimpleFighter`). Parece interessante, não é? Tornar isso possível é a sua próxima *quest*!
- O arquivo deve ser criado no diretório `src/Battle/` e se chamar `PVE.ts`;
- Lembre-se a classe `Battle` já esta criada;
- Na criação de uma instância de `PVE.ts` é esperado que em seu construtor seja recebido uma pessoa personagem lutadora (`Character Fighter`) e um *array* com pelo menos um monstro (`Monster`), ambos inicializados no **construtor**;
  - Como estamos falando de uma batalha *player versus environment*, este *array* de monstros também aceita instâncias de pessoas personagens lutadoras sendo elas simples ou não; (`Fighter`, `SimpleFighter`)
- Não se esqueça de fazer a sobrescrita (`override`) do(s) método(s) necessário(s);
  - Como na "Dica de mestre" do requisito anterior (`PVP`), não esqueça de implementar uma lógica de luta para este requisito também;
  - Lembre-se, aqui a luta é de uma personagem contra apenas um oponete ou uma legião deles. Logo, para a batalha ser finalizada, a personagem principal, ou seus oponentes, deverão ter perdido os seus respectivos pontos de vida (`lifePoints`).

---

### 12 - Crie a classe `Dragon`

Seria muito estranho se esse mundo se chamasse Trybers and Dragons e não existissem `Dragons`, não é mesmo?
Estes seres magníficos são representados como monstros aqui, mas com a característica especial de possuírem elevados valores de pontos de vida.

Nesta *quest*, você deve **criar a classe `Dragon`**, cuidando para garantir que:

- O arquivo deve ser criado na raiz de `src/` e se chamar `Dragon.ts`;
- A classe `Dragon` deve herdar de `Monster`;
- Como citado acima, um Dragão tem elevados valores de pontos de vida, então em seu construtor defina o valor de `_lifePoints` sendo igual a 999;

---

### 13 - Crie objetos no arquivo `index`

Você já modelou todo o mundo de T&D, maravilha!

Agora repare que, por mais que a gente saiba o que são `Monster`, `Character`, `Dragon`, `PVE`, etc, nenhum desses foi visto em ação. Então a sua última *quest* para completar essa aventura é dar vida às suas personagens e criar algumas instâncias das classes criadas anteriormente.

Algumas dicas se fazem necessárias para completar sua última missão no mundo de T&D. Elas são:

- O arquivo deve ser criado na raiz de `src/` e se chamar `index.ts`;
- Crie `3` objetos do tipo `Character`:
  - As variáveis devem-se chamar `player1`, `player2` e `player3`;
  - Execute algumas vezes o método `levelUp` do `player1`;
  - Ao final do arquivo `index.ts` exporte `player1`, `player2` e `player3`.
- Crie `2` objetos do tipo `Monster`:
  - As variáveis devem se chamar `monster1` e `monster2`;
  - `monster1` deve ser um `Monster` e `monster2` deve ser um `Dragon`;
  - Ao final do arquivo `index.ts` exporte `monster1` e `monster2`.
- Crie um objeto do tipo `PVP`:
  - A variável deve se chamar `pvp`;
  - Como parâmetro do construtor passe `player2` e `player3`;
  - Ao final do arquivo `index.ts` exporte `pvp`.
  - **NÃO execute o método `pvp.fight`**;
- Crie um objeto do tipo `PVE`:
  - A variável deve se chamar `pve`;
  - Como parâmetro do construtor passe `player1` e um array contendo `monster1` e `monster2`;
  - Ao final do arquivo `index.ts` exporte `pve`.
  - **NÃO execute o método `pve.fight`**;
- Crie uma função chamada `runBattles`:
  - A função recebe por parâmetro um *array* de batalhas (`battles`) e este *array* é do tipo `Battle`;
  - Dentro da função, crie uma repetição percorrendo este array e chame o método `fight`;
  - Ao final do arquivo `index.ts` exporte `runBattles`.

---
