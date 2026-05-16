ERROS DE CHIP E COMUNICAÇÃO — MAQUININHAS PAGBANK
==================================================

USE ESTE DOCUMENTO quando o cliente relatar que a máquina não consegue fazer vendas
por falta de sinal, erro de chip, ou mensagens de "falha na comunicação".

IMPORTANTE — REGRA DA BATERIA:
A bateria deve estar com pelo menos 20% de carga para a máquina funcionar corretamente.
Bateria baixa é uma causa comum de erros de comunicação falsos.
SEMPRE verifique o nível de bateria antes de prosseguir com qualquer diagnóstico de chip.


PASSO INICIAL — DIAGNÓSTICO RÁPIDO DE CHIP
-------------------------------------------
Antes de identificar o código de erro específico, faça estas perguntas ao cliente:

1. "Qual o nível de bateria da máquina agora?" — se abaixo de 20%, peça para carregar.
2. "A máquina está com Wi-Fi ou chip?" — para testar chip, peça para desligar o Wi-Fi.
3. "O chip está inserido corretamente?" — peça para retirar e recolocar o chip.
4. "Reiniciou a máquina recentemente?" — se não, peça para reiniciar agora.


ERROS A011/T011, A012/T012, A014/T014, A016/T016 — OPERADORA DE TELEFONIA INDISPONÍVEL
----------------------------------------------------------------------------------------
Na tela aparece: "Operadora de telefonia indisponível. Tente novamente."
Quando ocorre: instabilidade momentânea da operadora de telefonia.

Passos:
1. Peça ao cliente para desligar o Wi-Fi da maquininha (para testar só pelo chip).
2. Peça para reiniciar a máquina.
3. Oriente a aguardar pelo menos 4 horas — normalmente é instabilidade temporária da operadora.
4. Certifique-se de que a bateria está com pelo menos 20% de carga.
5. Se persistir após 4 horas: inicie o Fluxo de Chip (descrito abaixo).

Escalação: se após 4 horas e reinicialização o erro continuar, abra ticket para
análise do chip junto à operadora.


ERRO A017/T017 — MÁQUINA NÃO REGISTRADA NA REDE GPRS
------------------------------------------------------
Na tela aparece: "Problema na comunicação GPRS. Contate a central de suporte."
Quando ocorre: a máquina não está registrada na rede GPRS (chip não reconhecido pela rede).

Passos:
1. Confirme que a bateria está acima de 20%.
2. Verifique se o chip está inserido corretamente — peça para retirar e recolocar.
3. Peça para a máquina ficar carregando por pelo menos 8 horas consecutivas.
4. Após recarregar, reinicie e teste a conexão.

Escalação: se o erro persistir após recarga total, o chip pode estar com problema
físico — abra ticket para análise e possível substituição do chip.


ERRO A018/T018 — FALHA NA AUTENTICAÇÃO GPRS
--------------------------------------------
Na tela aparece: "Falha na autenticação. Contate a central de suporte."
Quando ocorre: problema ao se conectar com a rede GPRS.

Passos:
1. Confirme que a bateria está acima de 20%.
2. Reinicie a máquina.
3. Aguarde 4 horas e teste novamente.
4. Verifique se o chip está cancelado ou suspenso (consulte o status do chip).

Escalação: se o chip estiver suspenso ou cancelado, siga o Fluxo de Chip Suspenso/Cancelado.


ERROS A019/T019, A025/T025, A028/T028, A034/T034 — PROBLEMAS GERAIS DE COMUNICAÇÃO
-------------------------------------------------------------------------------------
Na tela aparece: variações de "Problema na comunicação", "Erro na comunicação",
"Erro de chip", "O chip ainda não respondeu. Aguarde."

Passos gerais:
1. Verifique se a bateria está acima de 20%.
2. Desligar o Wi-Fi e testar apenas pelo chip.
3. Verificar se o chip está inserido corretamente.
4. Reiniciar a máquina.
5. Aguardar pelo menos 4 horas (instabilidade da operadora).

Se o chip estiver cancelado/suspenso (A025):
- Confirme junto ao cliente se o chip foi cancelado ou se há alguma pendência
  com a operadora de telefonia.
- Siga o Fluxo de Chip Suspenso ou Cancelado.

Escalação: se após 4 horas o erro persistir, abra ticket para análise do chip.


ERROS A034/T034 — MÁQUINA SEM CONEXÃO WI-FI E SEM GPRS
---------------------------------------------------------
Na tela aparece: "Erro de conexão. Veja o chip e sua rede Wi-Fi."
Quando ocorre: a máquina está sem nenhuma conexão (nem Wi-Fi nem chip).

Passos:
1. Tente reconectar ao Wi-Fi: Menu > Configurações > Wi-Fi > Selecione a rede.
2. Se o Wi-Fi não conectar, verifique se a senha está correta.
3. Para testar o chip, desligue o Wi-Fi e reinicie.
4. Aguarde 4 horas e teste novamente.

Escalação: se nenhuma das conexões funcionar após reinicialização e espera,
abra ticket para substituição — pode ser problema de hardware na antena.


ERROS A069, A070, A071, A072, A073, A074 — ERRO DE SIMCARD / OPERADORA INDISPONÍVEL
--------------------------------------------------------------------------------------
Na tela aparece: "Erro de SIMCARD", "Erro de SIM Card", "Operadora indisponível."
Quando ocorre: problema de comunicação entre a máquina e o chip físico,
ou a máquina não identifica o chip.

Passos:
1. Peça ao cliente para carregar a máquina por 8 horas consecutivas diretamente
   na tomada (não em carregadores USB de computador).
2. Faça o teste de conexão após a recarga:
   Menu > Configurações > Teste de Conexão.
3. Se o erro persistir, verifique se o chip está encaixado corretamente
   (retire e recoloque com cuidado).

Escalação: se após recarga total e reencaixe o erro continuar, abra ticket
para substituição do chip ou da máquina (pode ser defeito no leitor de chip).


FLUXO PARA CHIP SUSPENSO OU CANCELADO
---------------------------------------
Se o cliente informa que o chip foi cancelado ou suspenso:
1. Verifique no sistema se o chip está ativo ou não.
2. Se suspenso por inatividade: o chip pode ser reativado pelo App PagBank.
   App > Gerenciar Vendas > Maquininhas > Gerenciar Chips > Reativar.
3. Se cancelado definitivamente: o cliente precisará de um novo chip — abra
   ticket para solicitação de novo chip/substituição de máquina.


ORIENTAÇÕES GERAIS PARA PROBLEMAS DE COMUNICAÇÃO
--------------------------------------------------
- Erros de chip (série A0XX e T0XX) têm a mesma instrução geral: reiniciar,
  aguardar 4 horas, verificar bateria, verificar chip.
- Modelos com "T" no código (T011, T019, etc.) seguem o mesmo procedimento
  que os modelos com "A" equivalentes.
- A maioria dos erros de comunicação são instabilidades temporárias da operadora
  e se resolvem com reinicialização e espera de 4 horas.
- Se o cliente precisar vender com urgência e o chip não funcionar:
  oriente a conectar ao Wi-Fi como solução temporária.
