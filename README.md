# Atendimento Acessível · USF Covelo

Protótipo de um posto de atendimento acessível para a USF Covelo (ULS São João), para pessoas surdas ou com dificuldades auditivas e para pessoas cegas ou com baixa visão.

Projeto desenvolvido no âmbito do estágio em Saúde Digital e Inovação Biomédica. O plano de implementação para a ULS São João está em [PLANO.md](PLANO.md).

## O que faz

Ao abrir, a aplicação pergunta para que vai ser usado o computador:

- **Ecrã tátil dos utentes**
  - *Não tenho capacidade auditiva ou tenho dificuldades auditivas*: quatro respostas fixas em Língua Gestual Portuguesa com legendas (como fazer o check-in, que documentos trazer, onde ficam os consultórios, quero fazer check-in), conversa escrita em tempo real com o secretariado, videochamada com intérprete de LGP e confirmação de presença com aviso por SMS.
  - *Telefone com teclado Braille (0–9, \*, # e Ajuda)*: ao atender, uma mensagem de boas-vindas em português de Portugal; as teclas 1 a 4 dão as respostas pré-definidas e a 4 regista a entrada na consulta.
- **Secretariado**: estado do ecrã tátil, mensagens e pedidos com notificação e som, presenças confirmadas e botão «Médico pronto».
- **Sala de espera** (opcional): mostra a senha chamada em grande.

## Como usar

Abra `index.html` num navegador (Chrome ou Edge recomendados).

Para publicar com GitHub Pages: *Settings → Pages → Branch: main / (root)*. O endereço fica `https://<utilizador>.github.io/<repositório>/`.

Para testar o fluxo completo num só computador, abra a página em dois separadores do mesmo navegador: um como «Ecrã tátil dos utentes» e outro como «Secretariado». Os dois comunicam entre si.

## Vídeos em LGP

As respostas devem ser gravadas por um intérprete de LGP fluente e validadas pela comunidade surda. Coloque os vídeos MP4 na pasta `videos/` com estes nomes:

| Ficheiro | Conteúdo |
| --- | --- |
| `videos/saudacao.mp4` | Saudação inicial |
| `videos/checkin.mp4` | Como fazer o check-in na consulta |
| `videos/docs.mp4` | Que documentos tenho de trazer |
| `videos/consultorios.mp4` | Onde ficam os consultórios |
| `videos/fazercheckin.mp4` | Quero fazer check-in |
| `videos/interprete.mp4` | Vídeo da videochamada (opcional) |

Enquanto um vídeo não existir, aparece uma pré-visualização ilustrada, que não é LGP validada.

## Limitações do protótipo

- A videochamada com intérprete e o envio de SMS são simulados.
- Fora do ambiente Claude, a comunicação em tempo real só funciona entre separadores do mesmo navegador. Para ligar o ecrã tátil e o computador do secretariado em máquinas diferentes é preciso um pequeno servidor (por exemplo, WebSocket) alojado pela ULS.
- A voz usa a síntese do sistema operativo: instale uma voz de português de Portugal no computador do ecrã tátil.
- Não guarda dados em servidor; os números de telemóvel ficam apenas na sessão. Uma versão real precisa de parecer do Encarregado de Proteção de Dados da ULS.
