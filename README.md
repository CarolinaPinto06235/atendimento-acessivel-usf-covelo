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
| `videos/checkin.mp4` | Como dar entrada na consulta (LGP; `checkin-en.mp4` em BSL, `checkin-es.mp4` em LSE, `checkin-ar.mp4` em língua gestual árabe) |
| `videos/docs.mp4` | Que documentos tenho de trazer |
| `videos/consultorios.mp4` | Onde ficam os consultórios |
| `videos/horario.mp4` | Horário da USF |
| `videos/interprete.mp4` | Vídeo da videochamada (opcional) |

Enquanto um vídeo não existir, aparece uma pré-visualização ilustrada, que não é LGP validada.

## Limitações do protótipo

- A videochamada com intérprete, a transferência de chamadas do telefone e o envio de SMS são simulados.
- No GitHub Pages, a comunicação em tempo real só funciona entre separadores do mesmo navegador. Para ligar o ecrã tátil e o computador do secretariado em máquinas diferentes é preciso um pequeno servidor alojado pela ULS.
- Não guarda dados em servidor. Uma versão real precisa de parecer do Encarregado de Proteção de Dados da ULS.

## Entrar e bloqueio do ecrã tátil

Cada função (ecrã tátil e secretariado) pede um código antes de abrir. Os códigos não estão escritos no repositório: só está guardado o seu resumo SHA-256, em `const ACCESS` no `index.html`. O ecrã da sala de espera usa o código do ecrã tátil.

- Depois de entrar no **ecrã tátil**, o computador fica bloqueado nesse modo: não há botão para sair, o logótipo só volta ao início do ecrã, mudar o endereço (`#secretariado`, `#inicio`) não tem efeito e recarregar a página mantém o bloqueio.
- **Para sair (funcionários):** toque 5 vezes seguidas no logótipo «USF Covelo» dentro do ecrã (na sala de espera, no relógio) e introduza o código do ecrã tátil.
- O **secretariado** tem o botão «Terminar sessão»; a sessão termina sozinha ao fim de 12 horas.
- Após 5 códigos errados, é preciso esperar 1 minuto.

**Mudar os códigos:** calcule o novo resumo e substitua o valor correspondente em `const ACCESS`:

```bash
python3 -c "import hashlib;print(hashlib.sha256(b'usf-covelo-atendimento:ecra:NOVOCODIGO').hexdigest())"
python3 -c "import hashlib;print(hashlib.sha256(b'usf-covelo-atendimento:secretariado:NOVAPASSE').hexdigest())"
```

> Limite: o site é estático e o repositório é público, por isso estes códigos impedem que os utentes saiam do ecrã ou abram o secretariado, mas não são um login seguro. Na versão para a ULS, o secretariado deve usar contas reais (por exemplo o Firebase Authentication que o site da USF já tem) e o ecrã tátil deve correr em modo quiosque do sistema (Chrome `--kiosk` ou «Acesso guiado» no tablet), para que também não se possa fechar o navegador.

## Línguas do ecrã tátil

O ecrã tátil tem um seletor de língua no topo: **Português** (por omissão), **English**, **Español** e **العربية** (em árabe o ecrã passa a ler-se da direita para a esquerda).

- Tudo o que o utente lê no ecrã é traduzido: informação, aba de dificuldade auditiva (legendas das frases), conversa escrita, videochamada e dar entrada na consulta. 
- Ao fim de 3 minutos sem uso, e quando um funcionário desbloqueia o ecrã, volta ao português.
- **Secretariado:** fica sempre em português. Vê a língua do utente no estado do ecrã, nas mensagens («escreveu em inglês») e nas entradas («Fala inglês»). As frases rápidas do utente chegam já em português; as respostas rápidas do secretariado seguem também traduzidas para a língua do utente; o texto escrito à mão segue como está. A SMS simulada vai na língua do utente.
- O telefone para pessoas cegas continua só em português de Portugal.
- **Língua gestual de cada língua:** português → LGP (Língua Gestual Portuguesa), inglês → BSL (Língua Gestual Britânica), espanhol → LSE (Língua Gestual Espanhola), árabe → Língua Gestual Árabe unificada. A aba, a videochamada e o pedido de intérprete que chega ao secretariado indicam a língua gestual certa.
- **Vídeos:** `videos/<frase>.mp4` é LGP; para as outras línguas gestuais acrescenta-se `-en`, `-es` ou `-ar` (por exemplo `videos/checkin-en.mp4` em BSL). Se faltar o vídeo de uma língua gestual, o ecrã mostra o vídeo em LGP e avisa. O avatar só faz uma aproximação de LGP, e isso também é indicado ao utente.
- Os textos estão em `TR`, `QP`, `DQ` e `INFO_TR` no `index.html`. As traduções devem ser revistas por um falante nativo antes de usar com utentes.

## Proteção de dados

- Depois de cada entrada, o nome, o número de utente e o telemóvel são apagados do ecrã; o ecrã final volta ao início ao fim de 20 segundos. No telefone, os dados apagam-se ao pousar.
- A conversa escrita é apagada (no ecrã e no secretariado) quando o utente sai do ecrã ou ao fim de 3 minutos sem uso.
- A SMS só é possível com consentimento: no ecrã, uma caixa a marcar; no telefone, a mensagem de voz explica-o antes de marcar o número.
- Quando o secretariado carrega em «Médico pronto», os dados pessoais da entrada são apagados; fica só a senha e o gabinete.
- **Mensagem ao secretariado:** cada entrada no ecrã tátil envia uma mensagem para «Mensagens, chamadas e pedidos», com a senha, o nome, o número de utente, se autorizou SMS e a língua. As entradas pelo telefone já chegam com a transferência da chamada.
- O que a ULS tem de fazer (Encarregado de Proteção de Dados, avaliação de impacto, prazos) está no `PLANO.md`, secção «Proteção de dados (RGPD)».

## Antes de apresentar

A aplicação começa vazia: não há casos de exemplo e a primeira senha é A001. Os casos são criados por quem apresenta, no ecrã tátil e no telefone.
No secretariado, o botão **Recomeçar** (tocar duas vezes) apaga mensagens, pedidos, entradas e senhas, para recomeçar entre ensaios.

## Acessibilidade digital (Decreto-Lei 83/2018 · WCAG 2.1 AA)

As aplicações de organismos públicos têm de cumprir o Decreto-Lei 83/2018 (norma EN 301 549, que corresponde ao nível AA das WCAG 2.1) e publicar uma declaração de acessibilidade.

- **Avaliação feita (27/11/2026):** testes automáticos em todos os ecrãs (contraste, nomes dos botões, etiquetas, língua, ids, ecrã de 320 px) e verificação manual (teclado, foco, tempo, mensagens de estado).
- **Correções:** verde e laranja mais escuros (contraste de 4,5:1), contorno dos campos mais visível, ligação «Saltar para o conteúdo», aviso «Ainda está aí?» com 20 segundos para pedir mais tempo antes de o ecrã voltar ao início, consentimento explicado por texto e não só por cor, ecrã a funcionar em 320 px de largura.
- **Declaração:** `acessibilidade.html` (rascunho com a estrutura do modelo oficial, «parcialmente conforme», com as limitações conhecidas). Está ligada no rodapé, exceto no ecrã tátil e na sala de espera.
- **Para a declaração oficial:** avaliar o endereço final no AccessMonitor (accessmonitor.acessibilidade.gov.pt), fazer testes com utilizadores e preencher a declaração no Gerador da ARTE (acessibilidade.gov.pt/gerador).
