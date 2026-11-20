# Atendimento Acessível · USF Covelo

Protótipo de um posto de atendimento acessível para a USF Covelo (ULS São João), para pessoas surdas ou com dificuldades auditivas e para pessoas cegas ou com baixa visão.

**Abrir a aplicação:** https://carolinapinto06235.github.io/atendimento-acessivel-usf-covelo/

Projeto desenvolvido no âmbito do estágio em Saúde Digital e Inovação Biomédica. O plano de implementação para a ULS São João está em [PLANO.md](PLANO.md).

## Como está organizada

Ao abrir, escolhe-se o que o computador vai ser:

### Ecrã tátil (posto na entrada da USF)

**Pessoas surdas.** No ecrã inicial há um botão: *Não oiço ou oiço com dificuldade*. A partir daí, cada ecrã tem os botões **← Voltar** e **⌂ Início** e um indicador de onde a pessoa está.

1. **Língua Gestual**: o vídeo do intérprete (ou a pré-visualização) e as perguntas frequentes:
   - Como fazer o check-in na consulta
   - Que documentos tenho de trazer
   - Onde ficam os consultórios
   - Horário da USF
2. **Falar com alguém**, três opções:
   - **Escrever ao secretariado**: conversa escrita em tempo real, com teclado grande, sugestões de palavras e frases rápidas.
   - **Falar com um intérprete**: videochamada em LGP.
   - **Dar entrada na consulta**: passo a passo (nome, número de utente, telemóvel para SMS opcional, confirmar).

**Pessoas cegas.** O telefone com teclado Braille, ao lado do ecrã, funciona à parte. Ao atender:

- Ouve-se a mensagem de boas-vindas da USF.
- **1, 2, 3**: como fazer o check-in, que documentos trazer, onde fica a sala da consulta.
- **4**: dar entrada na consulta. O assistente pede o nome (dito em voz alta), repete-o para confirmar, pede o número de utente (marcado no teclado), repete o nome e o número, pergunta se quer SMS (telemóvel opcional) e transfere a chamada para o secretariado, que já recebe o nome e o número de utente.
- **Ajuda**: passa a chamada para o secretariado em qualquer momento.
- **\*** repete, **#** confirma.

### Secretariado (computador do balcão)

- Estado do **ecrã tátil** e do **telefone**, em separado (em uso, o que a pessoa está a fazer).
- **Conversa escrita** com as pessoas surdas, com notificação e som.
- **Chamadas e pedidos**: videochamadas com intérprete, chamadas do telefone e chamadas transferidas depois da entrada na consulta.
- **Entradas na consulta**: nome, número de utente e telemóvel; botão «Médico pronto» que envia a SMS (simulada) ou indica que é preciso ir buscar a pessoa.

### Sala de espera (opcional)

Mostra a senha chamada em grande.

## Experimentar num só computador

Abra o link em dois separadores do mesmo navegador (Chrome ou Edge): num escolha **Ecrã tátil**, no outro **Secretariado**. Os dois comunicam entre si.

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
