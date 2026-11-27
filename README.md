# Atendimento Acessível · USF Covelo

Protótipo de um posto de atendimento acessível para a USF Covelo (ULS São João), para pessoas surdas ou com dificuldades auditivas e para pessoas cegas ou com baixa visão.

**Abrir a aplicação:** https://carolinapinto06235.github.io/atendimento-acessivel-usf-covelo/

Projeto desenvolvido no âmbito do estágio em Saúde Digital e Inovação Biomédica. O plano de implementação para a ULS São João está em [PLANO.md](PLANO.md).

## Como está organizada

Ao abrir, escolhe-se o que o computador vai ser:

### Ecrã tátil dos utentes (na entrada da USF)

Segue a estrutura e as cores do site [usf-covelo.github.io](https://usf-covelo.github.io): barra com horário, telefone e e-mail, logótipo e acesso rápido.

**Informação para todas as pessoas** (aba «Informação»), em resumo:

- O que trazer para a consulta
- Como dar entrada na consulta (com a opção de dar entrada no próprio ecrã)
- Horário e onde ser atendido quando a USF está fechada
- Contactos telefónicos e eletrónicos
- O que oferecemos
- Marcar consulta e renovar medicação

Todos os ecrãs têm **← Voltar** e **⌂ Início**.

**Pessoas com dificuldade auditiva** (botão «Tenho dificuldade em ouvir» ou aba «Dificuldade auditiva · LGP»):

1. Vídeo do intérprete (ou pré-visualização) com legendas e 4 perguntas frequentes: como dar entrada, o que trazer, onde ficam os consultórios, horário.
2. **Escrever ao secretariado** em tempo real, **Falar com um intérprete** por videochamada e **Dar entrada na consulta** (nome, n.º de utente, telemóvel para SMS).

**Pessoas cegas ou com dificuldade motora.** Não há botão no ecrã: o atendimento por voz é ativado ao **pegar no telefone** ao lado do ecrã. O ecrã mostra então, em letra grande, o que o assistente está a dizer. Ao pousar o telefone, o ecrã volta ao que estava.

- Mensagem de boas-vindas da USF; teclas **1, 2, 3** com as respostas pré-definidas.
- **4**: dar entrada na consulta. O assistente pede o nome (dito em voz alta), repete-o, pede o n.º de utente (teclado), repete o nome e o número, pergunta pelo telemóvel para SMS e transfere a chamada para o secretariado com estes dados.
- **Ajuda** passa a chamada ao secretariado; **\*** repete; **#** confirma.

### Secretariado (computador do balcão)

- Estado do **ecrã tátil** e do **telefone**, em separado (em uso, o que a pessoa está a fazer).
- **Conversa escrita** com as pessoas surdas, com notificação e som.
- **Chamadas e pedidos**: videochamadas com intérprete, chamadas do telefone e chamadas transferidas depois da entrada na consulta.
- **Entradas na consulta**: nome, número de utente e telemóvel; botão «Médico pronto» que envia a SMS (simulada) ou indica que é preciso ir buscar a pessoa.

### Sala de espera (opcional)

Mostra a senha chamada em grande.

## Experimentar num só computador

Abra o link em dois separadores do mesmo navegador (Chrome ou Edge): num escolha **Ecrã tátil dos utentes**, no outro **Secretariado**. Os dois comunicam entre si.

No telefone, para o nome é preciso microfone. Sem microfone, abra «Testar sem microfone» e escreva o nome. A voz usa a do sistema: instale uma voz de português de Portugal no Windows para ouvir com o sotaque certo.

## Vídeos em LGP

As respostas devem ser gravadas por um intérprete de LGP fluente e validadas pela comunidade surda. Coloque os vídeos MP4 na pasta `videos/` com estes nomes:

| Ficheiro | Conteúdo |
| --- | --- |
| `videos/saudacao.mp4` | Saudação inicial |
| `videos/checkin.mp4` | Como fazer o check-in na consulta |
| `videos/docs.mp4` | Que documentos tenho de trazer |
| `videos/consultorios.mp4` | Onde ficam os consultórios |
| `videos/horario.mp4` | Horário da USF |
| `videos/interprete.mp4` | Vídeo da videochamada (opcional) |

Enquanto um vídeo não existir, aparece uma pré-visualização ilustrada, que não é LGP validada.

## Limitações do protótipo

- A videochamada com intérprete, a transferência de chamadas do telefone e o envio de SMS são simulados.
- No GitHub Pages, a comunicação em tempo real só funciona entre separadores do mesmo navegador. Para ligar o ecrã tátil e o computador do secretariado em máquinas diferentes é preciso um pequeno servidor alojado pela ULS.
- Não guarda dados em servidor. Uma versão real precisa de parecer do Encarregado de Proteção de Dados da ULS.
