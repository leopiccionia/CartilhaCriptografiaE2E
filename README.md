    Atenção: trabalho em andamento. Pode conter erros banais.

#Uma introdução à criptografia ponta a ponta
Essa cartilha pretende auxiliar leigos, das mais diversas áreas de atuação – direito, jornalismo, ativismo, etc. – a entender os conceitos gerais e o funcionamento básico dos esquemas de criptografia ponta a ponta, usados, por exemplo, pelo WhatsApp (desde abril de 2016).

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
* **Não-repúdio das mensagens**: garantia, *com valor jurídico*, de que apenas o rementente poderia ter enviado a mensagem.
  * Perceba que alguns esquemas de criptografia, como aquele usado pelo WhatsApp, substituem-no tal mecanismo por um que não permite a verificação da autenticidade da mensagem por terceiros, conhecido como **negação plausível**.

Como visto acima, a comunicação entre remetente e destinatário requer informações ou mecanismos aos quais apenas eles tenham acesso, denominados **segredos**.

Matemática pode ser usada para se comprovar a inviabilidade de quebra dos esquemas de criptografia. Mas a matemática por trás dessas provas vai muito além do escopo dessa cartilha.

##O que é criptografia ponta a ponta?
Nos meios digitais, a comunicação entre remetente e destinatário passa por um intermediário – por exemplo, um servidor de e-mails ou um servidor do WhatsApp.

Num esquema de criptografia que não seja criptografado ponta a ponta, o transporte das mensagens passa, resumidamente, pelas seguintes etapas:

1. Rementente criptografa a mensagem com um segredo compartilhado com o intermediário;
2. Remetente envia a mensagem para o intermediário, informando o destinatário;
3. Intermediário descriptografa a mensagem;
4. Intermediário criptografa a mensagem com um segredo compartilhado com o destinatário;
5. Intermediário envia a mensagem para o destinatário;
6. Destinatário descriptografa a mensagem, e a lê.
 
Perceba que, entre os passos 3 e 4, o intermediário teria acesso ao conteúdo da mensagem, que poderia ser armazenado e repassado, por exemplo, por ordem judicial. No entanto, o armazenamento de altos volumes de comunicações por empresas privadas configuram, além de ameaça à privacidade dos usuários, uma isca formidável para *hackers* com interesses maliciosos.

Por isso, desenvolveu-se um esquema de criptografia alternativo. Resumidamente, num sistema de **criptografia ponta a ponta**, o transporte das mensagens passa pelas seguintes etapas:

1. Remetente criptografa a mensagem com um segredo compartilhado com o destinatário;
2. Remetente envia a mensagem para o intermediário, informando o destinatário;
3. Intermediário repassa a mensagem para o destinatário;
4. Destinatário descriptografa a mensagem, e a lê.

Perceba que, nesse esquema, mesmo que o intermediário armazenasse as mensagens, ele não conseguiria ler o conteúdo das mesmas, pois ele não tem acesso ao segredo utilizado. Possíveis vulnerabilidades – como o envio dos segredos para o intermediário, ou uma forma de se descriptografar as mensagens sem o conhecimento dos mesmos – poderiam ser utilizadas por *hackers* mal-intencionados.

Por isso, é importante que detalhes dos esquemas de criptografia utilizados sejam públicos, como forma de se detectar e corrigir prematuramente possíveis vulnerabilidades. Mais informações sobre a criptografia do WhatsApp, por exemplos, podem ser obtidas [aqui](https://www.whatsapp.com/security/WhatsApp-Security-Whitepaper.pdf) (em inglês).
