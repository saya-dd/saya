---
published: true
subtitle:
date: 2024-06-30
tags: computação segurança
foam_template:
  filepath: '_journal/2024-06-descrição-das-diretrizes-de-senhas-do-nist.md'
  name: Journal Entry
---

# Descrição das Diretrizes de Senhas do NIST

## Introdução

Em junho de 2017, o Instituto Nacional de Padrões e Tecnologia do Departamento de Comércio dos EUA emitiu discretamente uma revisão de sua publicação [Diretrizes de Identidade Digital](https://web.archive.org/web/20181223021935/https://pages.nist.gov/800-63-3/sp800-63b.html) que forneceu as diretrizes de autenticação por senha a serem seguidas por agências federais.

Destacadas por seu aconselhamento saliente que contradiz o dogma contemporâneo prejudicial — a saber: requisitos de complexidade, autenticação baseada em conhecimento, dicas de senha e troca periódica forçada — as diretrizes atualizadas representam um padrão eficaz a ser seguido para o processo de registro e autenticação de senhas de qualquer site voltado para o consumidor.

Incapaz de encontrar um resumo abrangente das seções relevantes da publicação do NIST (5.1.1 - 5.1.2), foi fornecido um aqui. As diretrizes listadas devem ser consideradas melhores práticas a serem seguidas para qualquer serviço web padrão que requeira autenticação básica por senha.

---

## Níveis de Recomendação

É importante entender que o NIST delineia quatro padrões graduados de recomendação:

- **DEVE/ NÃO DEVE**: Requisitos a serem rigorosamente seguidos e dos quais não é permitido desviar.
- **DEVERIA/ NÃO DEVERIA**: Recomendações consideradas particularmente adequadas, mas não especificamente em exclusão de alternativas, ou que um determinado curso de ação é preferido/desencorajado, mas não necessariamente exigido/proibido.
- **PODE/ NÃO PRECISA**: Cursos de ação permitidos no que diz respeito às Diretrizes do NIST, mas não necessariamente recomendados.
- **PODER/ NÃO PODER**: Qualquer coisa que seja ou não possível.

NIST também delineia [três níveis de garantia de autenticador](#nivel-de-garantia-de-autenticador) que exigem vários níveis de autenticação, bem como muitos tipos diferentes de protocolos de autenticação. No entanto, para os propósitos deste artigo, nos concentraremos apenas no AAL1, o nível mais baixo, e na autenticação por segredo memorizado (doravante, senha).

*Nota: (NIST SP 800-63-3, Notação e Convenções de Requisitos)*

---

## Padrões de Autenticação por Senha

### Restrições

1. Uma senha DEVE ter pelo menos 8 caracteres de comprimento.
2. Todas as senhas DEVEM ser comparadas com uma [lista negra de senhas comprometidas](https://github.com/danielmiessler/seclists/tree/master/Passwords), que PODE incluir, mas não se limita a:
    - Senhas obtidas em [corpora de violações](https://haveibeenpwned.com/Passwords).
    - [Palavras comuns do dicionário](http://world.std.com/~reinhold/dicewarewordlist.pdf).
    - [Caracteres repetitivos ou sequenciais](http://www.aaaaaaaa.com).
    - [Palavras específicas do contexto](https://rpubs.com/iPhuoc/NIST_guidelines).
3. Se a senha for encontrada na lista, o verificador DEVE fornecer o motivo da rejeição e o usuário DEVE ser obrigado a selecionar uma senha diferente.
4. Nenhum outro requisito de complexidade DEVE ser imposto.

### Permissões

1. Uma senha DEVERIA ter permissão para ter até 64 caracteres de comprimento.
2. Todos os caracteres ASCII, Unicode e o espaço DEVERIAM ser permitidos.
3. O usuário DEVERIA ter permissão para usar a funcionalidade de colar ao inserir uma senha, para facilitar o uso de [gerenciadores de senhas](https://en.wikipedia.org/wiki/Password_manager).
4. As senhas NÃO DEVEM ser exigidas a serem alteradas arbitrariamente (por exemplo, periodicamente). No entanto, as senhas DEVEM ser forçadas a mudar se houver evidências de comprometimento.
5. O usuário DEVERIA ser oferecido a opção de exibir a senha, em vez de uma série de pontos ou asteriscos, para facilitar a inserção da senha.
6. O usuário PODE ter permissão para a opção de o dispositivo do usuário exibir caracteres individuais à medida que são inseridos, para facilitar dispositivos móveis.
7. O usuário DEVERIA receber orientações para ajudar a escolher uma senha forte, como um medidor de força de senha.
8. O usuário NÃO DEVE ser permitido fornecer uma "dica" acessível ao público.
9. O usuário NÃO DEVE ser solicitado a usar [Autenticação Baseada em Conhecimento](http://archive.is/gCv9n) (por exemplo, "Qual era o nome do seu primeiro animal de estimação?") para autenticação ou recuperação de senha.

*Nota: (NIST SP 800-63-3, 5.1.1 - 5.1.2)*

---

## Comentário

A lista resolutamente curta de restrições contrasta fortemente com a política equivocada e negativa para o usuário de complexidade forçada extensiva (por exemplo, 1 letra maiúscula, 1 número, 1 caractere especial, etc.) e mudança arbitrária (por exemplo, periódica) que encontramos comum hoje (ironicamente, em grande parte devido às [diretrizes anteriores do NIST](http://archive.is/4xffa)). Os autores oferecem uma justificativa firme para suas recomendações em um [apêndice](https://pages.nist.gov/800-63-3/sp800-63b.html#appendix-astrength-of-memorized-secrets) altamente legível.

Em resumo, os requisitos de complexidade são contraproducentes. Forçar os usuários a alterar senhas fornecidas para serem mais complexas [resulta em modificações previsíveis](http://www.cs.umd.edu/~jkatz/security/downloads/passwords_revealed-weir.pdf) de suas senhas vulneráveis existentes, um conceito conhecido como [munging](https://web.archive.org/web/20150615165058/http://www.catb.org/jargon/html/M/mung.html). E está bem documentado que [senhas mungadas são facilmente quebradas](http://archive.is/s62ms) e uma consideração padrão de [qualquer hacker](https://arstechnica.com/information-technology/2013/05/how-crackers-make-minced-meat-out-of-your-passwords/). Resulta em uma falsa sensação de segurança, especialmente porque tende a receber uma [classificação erroneamente alta por maioria dos medidores de força de senha](http://ieeexplore.ieee.org/iel5/6233637/6234400/06234434.pdf).

Do próprio artigo:

> Humanos... têm apenas uma capacidade limitada de memorizar segredos complexos e arbitrários, então eles frequentemente escolhem senhas que podem ser facilmente adivinhadas. Para abordar as preocupações resultantes de segurança, serviços online introduziram regras com o objetivo de aumentar a complexidade desses segredos memorizados. A forma mais notável dessas é as regras de composição, que exigem que o usuário escolha senhas construídas usando uma mistura de tipos de caracteres, como pelo menos um dígito, letra maiúscula e símbolo. No entanto, análises de bancos de dados de senhas violadas revelam que o benefício dessas regras não é tão significativo quanto inicialmente pensado, embora o impacto na usabilidade e memorização seja severo. [Ver mais](https://www.explainxkcd.com/wiki/index.php/936:_Password_Strength).

Em contraste, [comprimento](https://blog.renditioninfosec.com/2017/09/password-length-or-complexity-math-says-length/), [listas negras](https://github.com/jonathanong/password-blacklist) e uma [criptografia server-side](#cryptography) adequada são mais do que suficientes para mitigar ataques de força bruta.

Os autores resumem sua posição sucintamente no final do apêndice referenciado:

> Requisitos de comprimento e complexidade além daqueles recomendados aqui aumentam significativamente a dificuldade dos segredos memorizados e aumentam a frustração do usuário. Como resultado, os usuários frequentemente contornam essas restrições de uma forma que é contraproducente. Além disso, outras mitigação como listas negras, armazenamento hash seguro e limitação de taxa são mais eficazes na prevenção de ataques de força bruta modernos. Portanto, nenhum requisito adicional de complexidade é imposto.

*Nota: (NIST SP 800-63-3, A.5)*


### Nível de Garantia de Autenticador

O NIST delineia três níveis de garantia de autenticador:

- **Nível de Garantia de Autenticador 1**: AAL1 fornece "alguma garantia," exigindo autenticação de um ou múltiplos fatores que requerem que o reclamante prove a posse e controle

 do autenticador através de um protocolo de autenticação segura.
- **Nível de Garantia de Autenticador 2**: AAL2 fornece "alta confiança," exigindo prova de posse e controle de dois fatores de autenticação diferentes através de protocolos de autenticação seguros. Técnicas criptográficas aprovadas são exigidas no AAL2 e acima.
- **Nível de Garantia de Autenticador 3**: AAL3 fornece "muita alta confiança," exigindo prova de posse de uma chave via um autenticador baseado em hardware e autenticador que fornece resistência à falsificação de verificador, e prova de posse e controle de dois fatores de autenticação distintos.

*Nota: (NIST SP 800-63-3, 2)*

---

### Diretrizes Omitidas

Algumas diretrizes incluídas na Seção 5.1.2 foram omitidas das [Diretrizes de Senha](#padroes-de-autenticacao-por-senha) devido ao comprimento e irrelevância para os objetivos deste artigo. Elas estão incluídas na íntegra abaixo:

#### Sobre Formatação de Texto

> Se caracteres Unicode forem aceitos em segredos memorizados, o verificador DEVE aplicar o Processo de Normalização para Strings Estabilizadas usando a normalização NFKC ou NFKD. Esse processo é aplicado antes de hash o byte string que representa o segredo memorizado. Assinantes que escolhem segredos memorizados contendo caracteres Unicode DEVEM ser avisados de que alguns caracteres podem ser representados de forma diferente por alguns endpoints, o que pode afetar sua capacidade de autenticar com sucesso.
> O verificador PODE substituir múltiplos caracteres de espaço consecutivos por um único caractere de espaço para fazer concessões para erros de digitação, desde que o resultado tenha pelo menos 8 caracteres. No entanto, a truncação da própria senha NÃO DEVE ser realizada.

*Nota: (NIST SP 800-63-3, 5.1.2)*

---

#### Sobre Segurança Server-side

> O verificador DEVE usar criptografia aprovada e um canal protegido autenticado ao solicitar segredos memorizados para proteger contra ataques de eavesdropping e MitM.
> Verificadores DEVEM armazenar segredos memorizados em uma forma que seja resistente a ataques offline. Segredos memorizados DEVEM ser salteados e hash usando uma função de derivação de chave unidirecional adequada. Funções de derivação de chave tomam uma senha, um sal e um fator de custo como entradas e geram um hash de senha. Seu propósito é tornar cada tentativa de adivinhação de senha por um atacante que obteve um arquivo de hash de senha cara e, portanto, o custo de um ataque de adivinhação alto ou proibitivo. Exemplos de funções de derivação de chave adequadas incluem Password-based Key Derivation Function 2 (PBKDF2) e Balloon. Uma função de memória rígida DEVE ser usada porque aumenta o custo de um ataque. A função de derivação de chave DEVE usar uma função unidirecional aprovada, como Keyed Hash Message Authentication Code (HMAC), qualquer função hash aprovada no SP 800-107, Secure Hash Algorithm 3 (SHA-3), CMAC ou Keccak Message Authentication Code (KMAC), Customizable SHAKE (cSHAKE) ou ParallelHash. O comprimento de saída escolhido da função de derivação de chave DEVE ser o mesmo que o comprimento da saída da função unidirecional subjacente.

> O sal DEVE ter pelo menos 32 bits de comprimento e ser escolhido arbitrariamente para minimizar colisões de valores de sal entre hashes armazenados. Tanto o valor do sal quanto o hash resultante DEVEM ser armazenados para cada assinante usando um autenticador de segredo memorizado.

> Para PBKDF2, o fator de custo é uma contagem de iterações: quanto mais vezes a função PBKDF2 é iterada, mais tempo leva para calcular o hash da senha. Portanto, a contagem de iterações DEVE ser tão grande quanto o desempenho do servidor de verificação permitir, tipicamente pelo menos 10.000 iterações.

> Além disso, verificadores DEVERIAM realizar uma iteração adicional de uma função de derivação de chave usando um valor de sal que é secreto e conhecido apenas pelo verificador. Este valor de sal, se usado, DEVE ser gerado por um gerador de bits aleatórios aprovado e fornecer pelo menos a força mínima de segurança especificada na revisão mais recente do SP 800-131A (112 bits na data desta publicação). O valor de sal secreto DEVE ser armazenado separadamente dos segredos memorizados hash (por exemplo, em um dispositivo especializado como um módulo de segurança de hardware). Com esta iteração adicional, ataques de força bruta nos segredos memorizados hash são impraticáveis enquanto o valor do sal secreto permanecer secreto.

*Nota: (NIST SP 800-63-3, 5.1.2)*


## Leitura Complementar

### Artigos Relacionados

- [[Gerenciadores de Senhas Recomendados]]
- [[Complexidade Forçada de Senhas Considerada Prejudicial]]

### Estudos de Apoio

- [Of Passwords and People: Measuring the Effect of Password-Composition Policies](http://wp.internetsociety.org/ndss/wp-content/uploads/sites/25/2017/09/usec2017_01_3_Habib_paper.pdf)
- [Testing Metrics for Password Creation Policies by Attacking Large Sets of Revealed Passwords](http://www.cs.umd.edu/~jkatz/security/downloads/passwords_revealed-weir.pdf)
- [From Very Weak to Very Strong: Analyzing Password-Strength Meters](http://www.internetsociety.org/sites/default/files/06_3_1.pdf)
- [Testing Metrics for Password Creation Policies by Attacking Large Sets of Revealed Passwords](http://www.cs.umd.edu/~jkatz/security/downloads/passwords_revealed-weir.pdf)

### Sobre o NIST 800-63-3

- [Complying with NIST Guidelines for Stolen Passwords](https://blog.shapesecurity.com/2018/03/01/complying-with-nist-guidelines-for-stolen-passwords/)
- [Bad passwords and the NIST guidelines](https://rpubs.com/iPhuoc/NIST_guidelines)
- [Don't Pass on the New NIST Password Guidelines](https://auth0.com/blog/dont-pass-on-the-new-nist-password-guidelines/)


[//begin]: # "Autogenerated link references for markdown compatibility"
[2024-06-gerenciadores-de-senhas-recomendados]: 2024-06-gerenciadores-de-senhas-recomendados "Gerenciadores de Senhas recomendados"
[2024-06-complexidade-forçada-de-senhas-considerada-prejudicial]: 2024-06-complexidade-for%C3%A7ada-de-senhas-considerada-prejudicial "Complexidade Forçada de Senhas Considerada Prejudicial"
[//end]: # "Autogenerated link references"