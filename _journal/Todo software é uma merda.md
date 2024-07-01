---
published: true
subtitle: 
date: 2024-06-29
tags: computação segurança software
---

#  Todo software é uma merda

> “E pessoal, sejamos honestos. Sturgeon era um otimista. Muito mais de 90% do código é lixo.” – Al Viro

> “Existem duas maneiras de construir um design de software: Uma maneira é torná-lo tão simples que obviamente não há deficiências e a outra maneira é torná-lo tão complicado que não há deficiências óbvias.” – C.A.R. Hoare, Palestra do Prêmio Turing de 1980

> “Um dos meus dias mais produtivos foi quando joguei fora 1000 linhas de código.” – Ken Thompson

> “..A princípio, eu esperava que um projeto tecnicamente tão falho colapsasse, mas logo percebi que ele estava condenado ao sucesso. Quase qualquer coisa em software pode ser implementada, vendida e até usada, dado o suficiente de determinação. Não há nada que um mero cientista possa dizer que se oponha à maré de cem milhões de dólares. Mas há uma qualidade que não pode ser comprada dessa maneira - e essa é a confiabilidade. O preço da confiabilidade é a busca da máxima simplicidade. É um preço que os muito ricos acham mais difícil de pagar.” – C.A.R. Hoare

> “É uma coisa curiosa sobre nossa indústria: não só não aprendemos com nossos erros, como também não aprendemos com nossos sucessos.” – Keith Braithwaite

## Mais citações sobre software e programação

## Coisas prejudiciais

*Este é um trabalho em andamento, muito está faltando.*

| Coisas prejudiciais | Alternativas menos prejudiciais |
| --- | --- |
| SGML, XML, YAML | JSON, CSV, ndb(6), texto simples (UTF-8). |
| NFS, SMB, AFS, WebDAV | 9p. |
| C++, Java, Vala, D, Python, Ruby | C, Go, Limbo. |
| pthreads (threads PoSix) | Concorrência estilo CSP: Go, libthread, libtask, Limbo, Erlang, ... |
| Perl, Ruby | rc, awk. |
| PCRE | Expressões Regulares Estruturais ou regexps clássicas/estendidas simples (como usado em awk, sed, grep, etc.). |
| Bash, tcsh, zsh | rc, pdksh do OpenBSD, ash/dash. |
| GNU Coreutils | Plan 9 from User Space. |
| GNU Screen | tmux. |
| GNU info | Páginas man. |
| GCC | 8c, tcc. |
| glibc | musl, ucLibc, DietLibc. |
| GNU autoconf/automake, CMake, imake, scons, waf | mk, ou makefiles portáveis antigos simples. |
| Glib | libc (veja acima), bibliotecas C do p9p. |
| GTK, Qt, VxWindows | Tk, interfaces textuais. |
| Vim, Emacs, nano, Eclipse, ... | Acme, Sam, ed. |
| UTF-16, UTF-32, Latin-1, outras codificações | UTF-8. |
| iSCSI, FCoE | AoE (ATA over Ethernet). |
| PAM (Módulos de Autenticação Plugáveis) | Factotum. |
| Jabber e XMPP | IRC (para IM), STOMP (para mensagens distribuídas em geral). |
| IMAP | SMAP (Protocolo Simples de Acesso a Email). |
| Bancos de dados SQL | Tutorial D, pq, BigTable, sistemas de arquivos hierárquicos simples. |
| Subversion, também conhecido como svn | Git, Mercurial (também conhecido como hg); inferno, até mesmo CVS ou tarballs simples antigos seriam melhores que svn. |
| FreeBSD, NetBSD, Solaris | OpenBSD. |
| Apache, lighttpd | thttpd, fork do apache 1.3 do OpenBSD, nginx, ou melhor de todos: não use HTTP. |
| SVG | PS (PostScript) |
| PDF | PS (PostScript), DjVu. |
| EPUB | DjVu. |
| ALSA | OSS4 |
| GPL, LGPL, Licença de Software Apache, MPL, CC | ISC, MIT/X, BSD, CC0, domínio público. |
| head | sed 11q |

### Coisas prejudiciais que são tão supérfluas e inúteis que não requerem alternativa:

- Unicode BoM em UTF-8.
- IDN.
- Linkagem dinâmica, em particular em sistemas Unix.
- Locales PoSix.
- Adobe Flash.
- GNOME e KDE.
- Boost.
- UML.

*Nota: No momento, uma justificativa detalhada não é fornecida para a maioria disso, então descobrir por que algumas coisas são consideradas mais ou menos prejudiciais do que outras é deixado como exercício para o leitor. Aqui está uma dica: complexidade é a praga de todo software, simplicidade é a qualidade mais importante. Veja também: [Pior é Melhor (INGLÊS)](http://dreamsongs.com/WorseIsBetter.html) por Richard Gabriel.*

## Funcionalidades

> Lei do Envelopamento de Software de JWZ: "Todo programa tenta se expandir até que possa ler e-mails. Aqueles programas que não podem se expandir para isso são substituídos por aqueles que podem."

A maioria das chamadas 'funcionalidades' são ou inúteis ou piores do que inúteis.

* [Não Implementar Funcionalidades é Difícil - Por Robert O'Callahan (INGLÊS)](https://robert.ocallahan.org/2011/11/not-implementing-features-is-hard.html).

## Frameworks

* [Por Que Eu Odeio Frameworks - Por Benji Smith (INGLÊS)](https://medium.com/@benjiwheeler/why-i-hate-frameworks-692c9cc1c312).
