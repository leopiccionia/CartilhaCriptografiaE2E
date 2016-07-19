    Atenção: trabalho em andamento. Pode conter erros banais.

#Uma introdução à criptografia ponta a ponta
Essa cartilha pretende auxiliar leigos, das mais diversas áreas de atuação – direito, jornalismo, ativismo, etc. – a entender os conceitos gerais e o funcionamento básico dos sistemas de criptografia ponta a ponta, usados, por exemplo, pelo WhatsApp (desde abril de 2016).

##O que é criptografia?
Segundo o dicionário [Michaelis](http://michaelis.uol.com.br/busca?r=0&f=0&t=0&palavra=criptografia), **criptografia** pode ser entendida como:
> Arte ou processo de escrever em caracteres secretos ou em cifras; esteganografia.

Eu não gosto dessa definição. Considero-a vaga e até imprecisa (ao associá-la à esteganografia).

Eu prefiro a definição dada pelo [Wikicionário](https://en.wiktionary.org/wiki/cryptography) (em minha tradução):
> A disciplina que se ocupa da segurança da comunicação (ex: confidencialidade da mensagens, integridade das mensagens, autenticação dos remetentes, não-repúdio das mensagens, e muitos outros assuntos relacionados), indepentemente do meio usado, como papel e lápis ou computadores.

A partir dessa definição, podemos extrair alguns conceitos úteis para a criptografia moderna:
* **Confidencialidade das mensagens**: remetente e destinatário se comunicam de maneira sigilosa (isso é, sem que terceiros tenham acesso ao conteúdo das mensagens), mesmo quando usam um meio de comunicação inseguro (por exemplo, grampeado).
* **Integridade das mensagens**: o destinatário tem fortes razões para crer que a mensagem não foi modificada (teve trechos adicionados, substituídos ou removidos) depois do envio por parte do remetente.
* **Autenticação dos remetentes**: garantia *técnica*, por parte do destinatário, de que apenas o remetente poderia ter enviado a mensagem.
* **Não-repúdio da mensagem**: garantia, *com valor jurídica*, de que apenas o rementente poderia ter enviado a mensagem.
  * Perceba que alguns sistemas de criptografia, como o usado pelo WhatsApp, substituem-no tal mecanismo por um que não permite a verificação da autenticidade da mensagem por terceiros, conhecido como **negação plausível**.
