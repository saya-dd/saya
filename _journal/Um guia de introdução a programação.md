---
published: true
subtitle: 
date: 2024-06-29
tags: 
---

# Um guia de introdução a programação

Como muitos, quando comecei, passei por uma fase de questionar qual seria a melhor maneira de aprender programação. Já superei essa fase, mas a questão ainda me interessa, porque muitos fazem a mesma pergunta. Acho que programação é a melhor maneira para NEETs de alto QI começarem a obter uma renda, então vou escrever aqui minhas opiniões sobre como começar a aprender.

Existem três caminhos possíveis que eu vou citar a seguir.

## 1. Começe de baixo pra cima

![](/images/animec.png)

Comece com C. Simples assim.

O primeiro caminho é C pois, quando você começa a aprender com C, os detalhes arquitetônicos da máquina te guiam de alguma forma sobre o que você pode e não pode fazer. Isso é frequentemente apresentado como um ponto negativo de começar com C, como se você se perdesse em detalhes desnecessários ao invés de focar na resolução de problemas, mas acredito que essa visão está errada: você não tem problemas reais para resolver quando está aprendendo a programar pela primeira vez, você está lidando com problemas artificiais, e se eles são artificiais para se adequar ao ensino de C também são para Python, JavaScript ou qualquer outra linguagem, isso não importa. A programação de baixo nível não bloqueia seu caminho para um conhecimento ideal de "resolução de problemas". C é uma linguagem simples que te faz entender alguns conceitos básicos que ocorrem por trás das cenas, por exemplo, que arrays são slots contínuos na memória, ou que variáveis têm um número específico de bits salvos, ou que letras ASCII são apenas números de 8 bits mostrados de maneira diferente, coisas assim que te dão alguns limites naturais sobre o que é possível.

## 2. QI < 160 = Filtrado. Se o seu for menor do que isso pode pular pra próxima

O segundo ponto é sobre programação funcional - LISP/Scheme especificamente. Concordo que a programação funcional tem valor pedagógico similar ao que mencionei acima: as "fundamentações logico-matemáticas da computação" em vez dos detalhes arquitetônicos são o que fornecem ao iniciante uma diretriz sobre como programar. O currículo funcional essencialmente introduz computação muito básica na forma de funções recursivas que fazem correspondência de padrões. Essa correspondência de padrões é aplicada a tipos de dados simples como listas. Então, estruturas de dados mais complexas como grafos/árvores são introduzidas, e as funções escritas para listas são naturalmente transferidas para essas. Então uma função filter() em uma lista se torna uma filter() em um tipo de árvore, e a progressão parece natural. Isso é contrário aos currículos imperativos onde tudo se torna possível após a introdução de loops, e muitos alunos ficam confusos.

Além disso: tipagem estática forte, correspondência de padrões e monads são alguns dos recursos que linguagens mainstream estão apenas agora implementando, muitas vezes de forma defeituosa, que outras linguagens já tinham há 40 anos. Então aprender uma linguagem funcional corretamente é um conhecimento valioso e transferível para outras linguagens. Entretanto, linguagens de programação funcional quase nunca são usadas na indústria, são um grande meme para indivíduos de alto QI. 

## 3. Se você não conseguiu usar nenhum dos dois caminhos acima, esta é a sua última esperança

Falam que python em si pode parecer simples, mas por trás das cenas é muito complicada e carece dos benefícios das duas abordagens anteriores que mencionei, nomeadamente ter algo em que se basear, seja a máquina ou fundamentos matemáticos. Mas ainda é uma boa alternativa se alguém tentar as anteriores e não gostar delas. O lado bom de Python, é que se você tem um problema, provavelmente existe alguma biblioteca que te faça trabalhar em algo com aplicações práticas de uma forma bem intuitiva e bem documentada. Você quer automatizar uma planilha do trabalho? Pandas. Automatizar uma ação no navegador? Selenium.

Tecnicamente é possível usar as duas anteriores para todas essas atividades também, mas essa aqui é a perfeita para os que foram filtrados pelas outras.

# Notas finais

Java e muitas outras linguagens não fornecem nenhum dos benefícios acima e adicionam muita complexidade inicial com os conceitos de OOP, então acho que não faz sentido começar com elas. JavaScript é inconsistente, às vezes é recomendado porque você pode ver imediatamente os resultados da programação no navegador, mas é uma abordagem muito contraproducente.

Não assista tutoriais. Leia documentações e livros. Brinque com APIs. Faça anotações. Faça boas perguntas. É mais simples do que parece. Se nada disso funcionou, infelizmente assinar o plano da Alura ou fazer faculdade de Ciência da Computação na Estácio não vai resolver. No melhor dos casos você vai ser só mais um macaco de código no mercado, esperando pelo [grande filtro](https://pt.wikipedia.org/wiki/Teoria_populacional_malthusiana).