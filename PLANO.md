# Atendimento Acessível USF Covelo — Plano para a ULS São João

19 de novembro de 2026

## Resumo

Propõe-se um piloto de 6 meses na USF Covelo: um posto de atendimento acessível para pessoas surdas e cegas, com protótipo funcional já feito e equipamento comercial disponível. À ULS São João pede-se três coisas: autorização para o piloto, apoio dos serviços de sistemas de informação e de compras, e ligação a parceiros (equipa do PE2LGP e associações).

**O problema.** Na USF, o utente é chamado em voz alta e a informação está em cartazes e no balcão. Uma pessoa surda não ouve a chamada; uma pessoa cega não lê os cartazes nem encontra o balcão sem ajuda.

**A solução:**

- **Uma aplicação, duas funções.** Ao abrir, escolhe-se se o computador é o ecrã tátil ou o do secretariado. O secretariado vê em separado o estado do ecrã tátil e do telefone, e recebe notificação com som de cada mensagem, chamada e entrada na consulta.
- **Pessoas surdas ou com dificuldades auditivas.** Botão «Não oiço ou oiço com dificuldade»; depois, o vídeo do intérprete em LGP com legendas e quatro perguntas frequentes (como dar entrada na consulta, documentos, consultórios, horário). Navegação com Voltar e Início em todos os ecrãs.
- **Falar com alguém, três opções.** Escrever ao secretariado em tempo real (teclado grande, sugestões de palavras, frases rápidas); videochamada com um intérprete de LGP, como nas Lojas do Cidadão; dar entrada na consulta passo a passo (nome, número de utente e telemóvel opcional para SMS).
- **Pessoas cegas ou com baixa visão.** Piso podotátil até um telefone com teclado Braille de 0 a 9 e botão Ajuda, independente do ecrã. Ao atender, ouve-se a mensagem de boas-vindas da USF; as teclas 1 a 3 dão as respostas pré-definidas; a 4 dá entrada na consulta: o assistente pede o nome e o número de utente, repete-os para confirmar, pergunta pelo telemóvel para SMS e transfere a chamada para o secretariado, que já recebe estes dados.

**Protótipo funcional:** o ficheiro `index.html` deste repositório. Ao abrir, pergunta se o computador é o ecrã tátil dos utentes ou o do secretariado.

## Enquadramento

A proposta responde a obrigações legais que já estão em vigor e aproveita serviços do SNS que já existem.

- **ULS São João.** Desde 1 de janeiro de 2024, a ULS integra o Centro Hospitalar Universitário de São João e os ACeS Grande Porto III (Maia/Valongo) e Grande Porto VI (Porto Oriental), onde está a USF Covelo ([fonte](https://www.noticiasaominuto.com/pais/2479749/sns-reorganizado-em-unidades-locais-de-saude-saiba-os-pontos-essenciais)). Conselho de Administração: Alameda Prof. Hernani Monteiro, 4200-319 Porto, ca@chsj.min-saude.pt, 225 512 100 ([Diário da República](https://files.diariodarepublica.pt/cp_hora/2026/06/118/419964987.pdf)).
- **Ato Europeu de Acessibilidade.** O [Decreto-Lei n.º 82/2022](https://diariodarepublica.pt/dr/detalhe/decreto-lei/82-2022-204379872) e a Portaria n.º 220/2023 aplicam-se desde 28 de junho de 2025 aos terminais de autosserviço, incluindo máquinas de senhas e terminais interativos de informação ([Garrigues](https://www.garrigues.com/pt/pt-PT/news/primeiro-prazo-do-novo-regime-juridico-da-acessibilidade-termina-em-junho-2025-com-novas)). Um equipamento novo deve já nascer acessível.
- **Acessibilidade física.** O Decreto-Lei n.º 163/2006 é a referência para percursos acessíveis no edifício, incluindo o piso podotátil.
- **LGP no Estado.** O SNS 24 já permite videochamada entre uma pessoa surda e um intérprete de LGP ([DECO Proteste](https://www.deco.proteste.pt/saude/hospitais-servicos/noticias/saude-24-disponivel-24-horas-dia)), e as Lojas do Cidadão usam intérprete por videochamada ao balcão ([gov.pt](https://www.gov.pt/guias/atendimento-em-lingua-gestual-portuguesa-lgp)). O botão «Falar com um intérprete» deve ligar a um destes serviços.
- **Dados pessoais.** O telemóvel para SMS e as mensagens escritas são dados pessoais: o piloto precisa de parecer do Encarregado de Proteção de Dados da ULS.

## Melhorias ao protótipo antes de apresentar

1. **Gravar os vídeos do intérprete.** São 5 vídeos curtos: saudação e as 4 opções fixas, gravados por um intérprete de LGP fluente e validados por uma pessoa surda. Colocam-se na pasta `videos/`; até lá a aplicação mostra uma pré-visualização ilustrada.
2. **Ligar a videochamada a um serviço real.** No protótipo a chamada é simulada; na versão final liga ao serviço de interpretação do SNS 24 ou a um intérprete contratado.
3. **Ligar as SMS ao serviço de mensagens da ULS.** No protótipo, «Médico pronto: enviar SMS» mostra a mensagem mas não a envia.
4. **Testar com utilizadores reais.** 5 pessoas surdas e 5 pessoas cegas ou com baixa visão, com tarefas simples (saber os documentos, confirmar presença, pedir ajuda). Medir tarefas concluídas sem ajuda e a escala SUS.
5. **Voz pt-PT no equipamento.** Instalar uma voz de português de Portugal no sistema do ecrã tátil; a aplicação já a escolhe primeiro.
6. **Sair do ambiente de protótipo.** Alojar a aplicação num servidor da ULS, com ligação em tempo real entre o ecrã tátil e o secretariado e parecer do Encarregado de Proteção de Dados sobre os telemóveis e as mensagens.

Fica para uma 2.ª fase: identificar o utente pelo cartão de cidadão e mostrar o seu médico e sala, o que exige integração com os sistemas da SPMS.

## Equipamento: onde comprar

O caminho mais simples é pedir a um fabricante português de quiosques que integre os componentes acessíveis num só equipamento. Os preços são de referência, de lojas online, sem IVA nem instalação.

| Componente | Opção de referência | Onde | Preço de referência |
| --- | --- | --- | --- |
| Quiosque com ecrã tátil, caixa para teclado e telefone | Fabrico à medida, cumprindo o DL 82/2022 | [Partteam & OEMKiosks](https://oemkiosks.com/blog/partteam-oemkiosks-technical-excellence-innovation-high-level-support), Vila Nova de Famalicão | Pedir orçamento |
| Comando de navegação com tomada de auscultadores (alternativa) | [Storm AudioNav, 6 teclas](https://shop.storm-interface.com/audio-nav-6-key-white-mic-support.html): liga por USB e funciona como teclado | Loja Storm Interface ou [Mouser](https://www.mouser.com/new/storm-interface/storm-interface-ez-access/) | US$ 219,89 |
| Telefone (auscultador) blindado | [Auscultador com cabo blindado e ficha 3,5 mm](https://www.eddyselectronics.com/amp/product/10636433/black-euro-pc-handset-with-armored-cord) | Lojas de componentes para quiosques; o fabricante pode integrar | US$ 97,73 |
| Ecrã da sala de espera e senhas | Monitor grande ligado a um sistema de gestão de filas (ex.: [QMAGINE](https://www.pr.com/press-release/831798)) | Fabricante do quiosque ou o sistema de senhas que a USF já usa | Pedir orçamento |
| Piso podotátil (faixa-guia e zona de alerta) | [Placa podotátil em poliuretano, 750 mm](https://catalog.manutan.com/manutan-central/manutan-pt/2026/bb2026/catalogo-manutan-2026-pt/?Page=570) | Manutan Portugal ou empreiteiro da ULS | € 49,75 por placa |

**Notas para a compra:**

- **Telefone com teclado Braille 0–9.** O desenho escolhido é um auscultador com um teclado numérico de 12 teclas (0 a 9, asterisco e cardinal) com Braille e um botão Ajuda separado, de cor diferente. Pedir ao fabricante do quiosque que o integre; o teclado deve ligar por USB e funcionar como teclado de computador, porque a aplicação já responde às teclas 0–9, \*, # e A.
- O AudioNav liga-se por USB e é reconhecido como teclado ([Kiosk Group](https://www.kioskgroup.com/products/storm-audio-nav-tactile-navigation-keypad)), e a sua tomada aceita um auscultador ([Mouser](https://www.mouser.in/new/storm-interface/storm-interface-ez-access/)). É uma alternativa mais barata, mas tem setas em vez de números.
- A compra é feita pelo serviço de aprovisionamento da ULS. O papel do projeto é entregar especificações claras e orçamentos de referência.
- O traçado do piso podotátil deve ser desenhado com o serviço de instalações da ULS e validado pela ACAPO.

## LGP: com quem falar

Vale a pena contactar a Católica em conjunto com o Técnico: o avatar é de um projeto partilhado entre as duas instituições. O pedido mais realista é uma colaboração para animar só as cerca de 30 frases e gestos que a USF precisa.

- **Universidade Católica Portuguesa.** O projeto [Corpus Linguístico e Avatar da LGP](https://fcse.lisboa.ucp.pt/asset/4156/file) foi financiado pela FCT e coordenado por Ana Mineiro e Luísa Coheur, no Lang-Lab da Católica. Ana Mineiro: amineiro@ucp.pt ([artigo de 2026](https://repositorio.ucp.pt/bitstreams/caa842b9-4cfc-45d1-9eed-0689e76a4ac8/download)).
- **Instituto Superior Técnico / INESC-ID.** Luísa Coheur e Hugo Nicolau são autores do [PE2LGP Animator](https://aclweb.org/anthology/2020.signlang-1.6.pdf), a ferramenta que anima o avatar 3D.
- **O que pedir:** a transcrição dos gestos das frases fixas e a possibilidade de usar o avatar num piloto de saúde, com crédito ao projeto. Em troca, a USF oferece um caso real de uso e utilizadores para testes.
- **Associação de Surdos do Porto.** Parceira natural para gravar e validar os vídeos e recrutar pessoas surdas para os testes ([Festival DDD](https://www.festivalddd.com/en/participantes/joaquim-viana-associacao-de-surdos-do-porto/)).
- **ACAPO.** Associação dos Cegos e Amblíopes de Portugal, com sede em Lisboa e delegação no Porto: validação do atendimento por voz, do teclado e do traçado do piso podotátil.

Até haver resposta, os vídeos de intérprete resolvem o problema da compreensão; o avatar é uma evolução, não um requisito do piloto.

## Outras ideias para pessoas cegas

- **Acompanhamento até ao gabinete.** Quando uma pessoa cega dá entrada pela tecla 4, o secretariado vê «ir buscar à sala de espera» e um funcionário acompanha-a quando o médico estiver pronto. Já está na aplicação.
- **Entrada na consulta pelo telefone.** Depois da tecla 4, o assistente recolhe nome e número de utente, confirma-os em voz alta e transfere a chamada ao secretariado; a pessoa pode deixar o telemóvel para receber a SMS de chamada, que o leitor de ecrã lhe lê. Já está na aplicação.
- **Sinal sonoro de localização** junto ao telefone, no fim do piso podotátil.
- **Auscultador com controlo de volume e acoplamento indutivo** para aparelhos auditivos.
- **Braille e letra grande nas portas** dos gabinetes, à altura da mão.
- **Informação antes de sair de casa:** o site da USF pode explicar o percurso desde a paragem de autocarro até à entrada.

## Acessibilidade digital (Decreto-Lei 83/2018)

Como serviço de uma entidade pública, a aplicação tem de cumprir o Decreto-Lei n.º 83/2018, que transpõe a Diretiva (UE) 2016/2102. Na prática, isto quer dizer a norma europeia EN 301 549, equivalente ao nível AA das WCAG 2.1, e a publicação de uma declaração de acessibilidade.

- **Já feito no protótipo:** autoavaliação (testes automáticos em todos os ecrãs e verificação manual), correção dos problemas encontrados e rascunho da declaração (`acessibilidade.html`, «parcialmente conforme»).
- **A fazer pela ULS:**
  1. Avaliar o endereço final com o validador do Estado, o AccessMonitor.
  2. Fazer testes com utilizadores. O Selo de Usabilidade e Acessibilidade de nível Ouro pede pelo menos 6 participantes, 2 deles com necessidades específicas.
  3. Preencher a declaração oficial no Gerador da Declaração de Acessibilidade e Usabilidade (ARTE) e publicá-la com a aplicação.
  4. Opcionalmente, candidatar a aplicação ao Selo de Usabilidade e Acessibilidade, que é gratuito para entidades públicas.

## Proteção de dados (RGPD)

O ecrã tátil e o telefone recolhem o nome, o número de utente e, se a pessoa quiser, o telemóvel. São dados de saúde, uma categoria especial de dados pessoais (art. 9.º do RGPD), num equipamento que está numa sala pública. A proposta trata isto em duas partes.

**O que o protótipo já faz (proteção de dados desde a conceção, art. 25.º)**

- **Dados apagados do ecrã logo após cada entrada.** Assim que o utente confirma, o nome, o número de utente e o telemóvel desaparecem do ecrã e da memória do posto. O ecrã final mostra só a senha e o telemóvel mascarado (91• ••• •78), e volta ao início ao fim de 20 segundos. Se a pessoa sair a meio, os dados também são apagados. No telefone, os dados apagam-se quando a pessoa pousa o auscultador.
- **Sem histórico das conversas.** A conversa escrita com o secretariado é apagada, nos dois lados, quando o utente sai do ecrã ou ao fim de 3 minutos sem uso. O ecrã avisa disso. Nada fica guardado no navegador.
- **Consentimento para a SMS.** No ecrã, só é possível continuar com um número depois de marcar «Autorizo que a USF Covelo use este número só para me avisar desta consulta. O número é apagado depois do aviso.». No telefone, a mensagem de voz explica o mesmo antes de a pessoa marcar o número.
- **Minimização e conservação.** Quando o secretariado carrega em «Médico pronto», o nome, o número de utente e o telemóvel são apagados; fica só a senha e o gabinete, para o ecrã da sala de espera.
- **Informação ao utente (art. 13.º).** O ecrã inicial explica, em quatro línguas, para que servem os dados e a quem perguntar.
- **Acesso restrito.** O secretariado só abre com palavra-passe, e o ecrã tátil não deixa sair para outras funções.

**O que a ULS São João tem de fazer antes de usar com utentes**

1. **Envolver o Encarregado de Proteção de Dados (EPD) da ULS** desde o início. As entidades públicas são obrigadas a ter um EPD (art. 37.º do RGPD; Lei n.º 58/2019), e cabe-lhe aconselhar sobre este tipo de projeto.
2. **Fazer uma Avaliação de Impacto sobre a Proteção de Dados (AIPD, art. 35.º)**, com o EPD: dados de saúde, num ecrã em espaço público, com pessoas vulneráveis.
3. **Definir o fundamento jurídico:** a prestação de cuidados de saúde (art. 9.º, n.º 2, alínea h) para a entrada na consulta; o consentimento (art. 6.º e 7.º) para a SMS.
4. **Definir prazos de conservação** e confirmar que os registos de entrada ficam apenas no sistema clínico da USF, e não no equipamento do ecrã.
5. **Escolher fornecedores dentro da UE** para o servidor, o serviço de SMS e a videochamada com intérprete, com contrato de subcontratação (art. 28.º).
6. **Segurança do equipamento:** modo quiosque do sistema, atualizações, contas reais para o secretariado (em vez de um código partilhado) e ecrã virado de forma a que quem está na fila não o consiga ler.
7. **Pôr a informação de privacidade** também em papel, junto do ecrã, com o contacto do EPD.

## Próximos passos

O calendário é uma proposta; o passo que desbloqueia tudo é a aprovação da ULS em fevereiro.

| Fase | Quando | O quê |
| --- | --- | --- |
| 1. Preparar | dez 2026 – jan 2027 | Gravar vídeos LGP com a Associação de Surdos do Porto; testar com 10 pessoas; contactar Católica e Técnico |
| 2. Apresentar | fevereiro 2027 | Reunião com a ULS; parecer do EPD; orçamentos de referência — **decisão: aprovação da ULS** |
| 3. Instalar | março – maio 2027 | Compra pela ULS; ecrã tátil e telefone; piso podotátil; formar o secretariado |
| 4. Piloto | junho – novembro 2027 | 6 meses na USF; medir uso, tarefas sem ajuda e satisfação; relatório final — **decisão: alargar a outras USF** |

**Esta semana e na próxima:**

1. Mostrar o protótipo e este plano à orientadora e ao coordenador da USF Covelo, e pedir que sejam eles a encaminhar o pedido à ULS.
2. Enviar emails à Associação de Surdos do Porto, à ACAPO e à equipa da Católica e do Técnico.
3. Pedir orçamentos de referência à Partteam & OEMKiosks e a um distribuidor do teclado.
4. Preparar uma apresentação de 10 minutos para a ULS: problema, demonstração ao vivo, custos e calendário.
5. Incluir no relatório de estágio o plano e a declaração de uso de IA.

## Contactos

| Entidade | Para quê | Contacto |
| --- | --- | --- |
| ULS São João, Conselho de Administração | Autorização do piloto | ca@chsj.min-saude.pt · 225 512 100 |
| Universidade Católica, Ana Mineiro | Corpus e avatar de LGP | amineiro@ucp.pt |
| IST / INESC-ID, Luísa Coheur e Hugo Nicolau | PE2LGP Animator | [página do projeto](https://www.hlt.inesc-id.pt/w/PE2LGP_Avatar) |
| Associação de Surdos do Porto | Vídeos LGP, validação, testes | a confirmar |
| ACAPO, delegação do Porto | Atendimento por voz, teclado, piso | a confirmar |
| Storm Interface | Comando AudioNav | info@storm-interface.com |
| Partteam & OEMKiosks | Quiosque integrado | +351 304 501 710 |
