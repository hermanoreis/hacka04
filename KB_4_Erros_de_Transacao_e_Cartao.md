ERROS DE TRANSAÇÃO E CARTÃO — MAQUININHAS PAGBANK
==================================================

USE ESTE DOCUMENTO quando o cliente relatar que a máquina está funcionando
(com sinal e ligada), mas as vendas estão sendo recusadas, falhando ou
exibindo erros ao passar o cartão.


DIAGNÓSTICO RÁPIDO — TRANSAÇÃO NÃO PASSA
------------------------------------------
Antes de identificar o código de erro, pergunte ao cliente:
1. "O erro apareceu no cartão do cliente (comprador) ou na máquina?"
2. "Qual bandeira é o cartão? Visa, Mastercard, Elo, Amex, Hipercard?"
3. "O cliente tem outro cartão para testar?" — ajuda a isolar se é o cartão ou a máquina.
4. "O erro tem algum código na tela? Me informe o número."


ERRO A008 — CARTÃO INVÁLIDO (BANDEIRA NÃO RECONHECIDA)
--------------------------------------------------------
Na tela aparece: A008 — Cartão inválido.
Quando ocorre: problema no mapeamento do cartão — a processadora da venda não foi encontrada.

Passos:
1. Verifique se a bandeira do cartão é aceita pelo PagBank.
   Bandeiras aceitas: Visa, Mastercard, Elo, Amex, Hipercard, Cabal.
2. Se a bandeira NÃO for aceita: informe ao cliente (comprador) que o PagBank não
   processa aquela bandeira.
3. Se a bandeira FOR aceita, o problema pode ser de tabela de transações:
   - Para Moderninhas: realize o procedimento de "Forçar Carga de Tabelas"
     (Menu > Suporte > Atualizar Tabelas).
   - Para Minizinha Chip: faça a desativação e reativação da máquina pelo gerenciador.
   - Para Leitores (Minizinha sem chip): desinstale e reinstale o app PagBank e
     refaça o pareamento.

Escalação: se o erro persistir após a carga de tabelas, abra ticket com WF de
erros não mapeados.


ERROS C060, C061 — CARTÃO COM ERRO OU MAL INSERIDO
----------------------------------------------------
Na tela aparece: C060 / C061 — Cartão com erro ou mal inserido.
Quando ocorre: o cartão não responde, o chip não está presente, ou há erro na
leitura do chip.

Passos:
1. Peça ao cliente (comprador) para retirar o cartão e reinseri-lo com cuidado,
   certificando-se de que o chip dourado está virado para cima.
2. Tente limpar suavemente o chip do cartão com um pano seco.
3. Se o erro persistir, tente passar o cartão pela tarja magnética (se disponível).
4. Teste com outro cartão do cliente para verificar se o problema é o cartão ou o leitor.

Escalação: se múltiplos cartões apresentarem o mesmo erro, o leitor de cartão
da máquina pode estar com defeito — abra ticket para substituição.


ERRO A205 — CARTÃO MAU INSERIDO
---------------------------------
Na tela aparece: A205.
Quando ocorre: o cartão não está inserido corretamente.

Passos:
1. Peça ao cliente para retirar o cartão e tentar novamente a transação.
2. Insira o cartão completamente até o fim do slot, com o chip virado para cima.


ERRO M0510 — FUNÇÃO INDISPONÍVEL / CANCELE PELO SITE
------------------------------------------------------
Na tela aparece: M0510 — Função indisponível no momento. Cancele pelo site PagBank.
Quando ocorre: o cliente está tentando cancelar uma venda diretamente pela máquina
em uma situação onde isso não é possível.

Passos:
1. Informe ao cliente que o cancelamento desta venda deve ser feito pelo site
   ou aplicativo PagBank, não pela máquina.
2. Oriente: App PagBank > Extrato > Localizar a venda > Cancelar / Estornar.

Escalação: se o cancelamento não aparecer no extrato, abra ticket para análise da transação.


ERRO M0815 — TRANSAÇÃO NÃO AUTORIZADA (BLOQUEIO PAGBANK)
----------------------------------------------------------
Na tela aparece: M0815 — Transação não autorizada PagBank.
Quando ocorre: por questões de segurança, o PagBank negou a venda.

Passos:
1. Informe ao cliente (lojista) que a transação foi bloqueada por segurança.
2. Oriente a verificar se há alguma pendência ou restrição na conta PagBank.
3. O cliente pode verificar no App PagBank > Conta > Notificações ou Suporte.

Escalação: se o bloqueio não for explicado no app, abra ticket para análise
pela equipe de segurança — não tente reverter sem análise.


ERRO M0826 — DISPOSITIVO BLOQUEADO POR FURTO OU ROUBO
-------------------------------------------------------
Na tela aparece: M0826 — Transação não autorizada PagBank.
Quando ocorre: o dispositivo foi bloqueado por furto/roubo ou identificado
como dispositivo em situação irregular.

AÇÃO IMEDIATA: Escale imediatamente.
Não tente realizar nenhum procedimento de desbloqueio.
Informe ao cliente que o caso será analisado pela equipe de segurança.
Abra ticket urgente com as informações do cliente e do dispositivo.


ERRO M2017 — ERRO AO ESTORNAR TRANSAÇÃO
-----------------------------------------
Na tela aparece: M2017 — Erro ao estornar transação. Por favor, tente novamente mais tarde.
Quando ocorre: o código de confirmação do estorno está incorreto ou houve falha no processo.

Passos:
1. Aguarde alguns minutos e tente realizar o estorno novamente.
2. Verifique se o código de confirmação digitado está correto.
3. Tente realizar o estorno pelo App PagBank em vez da máquina.

Escalação: se o estorno continuar falhando, abra ticket com os dados da transação.


ERRO M3005 — PRAZO DE ESTORNO EXCEDIDO
----------------------------------------
Na tela aparece: M3005 — Data máxima para estorno da transação foi excedida.
Quando ocorre: a venda só pode ser estornada dentro de um prazo máximo (geralmente
até 90 dias após a venda, dependendo da bandeira).

Passos:
1. Informe ao cliente que o prazo legal para estorno dessa venda já expirou.
2. Para resolver o problema com o comprador, oriente o lojista a tentar
   uma outra solução direta com o comprador (devolução manual, voucher, etc.).

Escalação: se o cliente contestar o prazo, abra ticket para análise da data da transação.


ERROS DE ATUALIZAÇÃO — M2021, M2069
-------------------------------------
Na tela aparece: M2021 — "Atualize o aplicativo para continuar vendendo."
Na tela aparece: M2069 — "Para voltar a vender, atualize o aplicativo."
Quando ocorre: a versão do aplicativo ou do sistema da máquina está desatualizada.

Passos:
1. Para Moderninhas Smart: acesse o Menu da máquina > Atualizações.
   Aguarde a atualização e reinicie.
2. Para Leitores: peça ao cliente para atualizar o aplicativo PagBank no celular
   (Google Play ou App Store).
3. Após a atualização, teste a máquina fazendo uma venda teste de R$ 1,00.

Escalação: se a atualização falhar ou não aparecer, abra ticket de suporte técnico.


ERROS DE CANCELAMENTO DE VENDA — M3001
---------------------------------------
Na tela aparece: M3001 — Aplicação móvel desconhecida / Não foi possível localizar a aplicação.
Quando ocorre: o aplicativo não está reconhecido pelo sistema da máquina.

Passos para Leitores:
1. Peça ao cliente para desinstalar o aplicativo PagBank no celular.
2. Reinstale o aplicativo pelo Google Play ou App Store.
3. Refaça o pareamento da máquina com o celular.

Escalação: se o pareamento falhar repetidamente, abra ticket de suporte.
