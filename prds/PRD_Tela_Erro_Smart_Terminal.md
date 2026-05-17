# PRD — Tela de Erro Smart do Terminal PagBank
**Iniciativa 1 de 4 | Hackathon PagBank — Desafio 4**
**Status:** Proposta · Hackathon  
**Equipe:** Bruno (Dados), Faustino (Tecnologia), Cristiana / Nat (Design), Victor, Luan, Hermano (Tecnologia)

---

## 1. Contexto e Problema

Hoje, quando uma maquininha PagBank apresenta qualquer falha — de conectividade, ativação, hardware ou chip — o lojista se depara com uma tela amarela genérica exibindo apenas um código de erro (ex: M5000, A001, X000) e um botão "Sair".

Esse padrão gera três consequências diretas:

- **Venda perdida imediata:** o lojista não sabe o que fazer, paralisa a operação e perde a venda no balcão.
- **Chamado na central:** sem orientação, o único caminho percebido é ligar para o suporte — contribuindo para os ~10.395 contatos/dia registrados.
- **Frustração e erosão de confiança:** a experiência de erro é o momento de maior stress do lojista. Uma resposta fria e opaca piora o NPS (NPS Vendedor: 24, o mais crítico do parque).

---

## 2. Objetivo

Transformar a tela de erro do terminal — hoje um beco sem saída — em um ponto de triagem inteligente que:

1. **Educa** o lojista sobre o erro de forma humana e acionável.
2. **Oferece resolução imediata** via autoatendimento no app ou web.
3. **Garante continuidade das vendas** com uma alternativa de contingência contextualizada ao perfil do lojista.

---

## 3. Solução: Tela de Erro Smart

### Arquitetura da tela (3 seções)

```
┌─────────────────────────────────┐
│  [Seção 1] Identificação        │
│  Código de erro + mensagem      │
│  humanizada                     │
├─────────────────────────────────┤
│  [Seção 2] Troubleshoot         │
│  QR Code + URL curta + CTA      │
│  para app ou web chat           │
├─────────────────────────────────┤
│  [Seção 3] Fallback de Vendas   │
│  Mensagem contextual por perfil │
│  (Tap On / Link de Pagamento)   │
└─────────────────────────────────┘
```

---

### Seção 1 — Identificação do Erro

**Componentes:**
- Código do erro visível (ex: `M5000`)
- Título em linguagem humana (ex: *"Sua maquininha não conseguiu ativar"*)
- Subtexto explicativo curto (1–2 linhas), sem jargão técnico

**Exemplo de tradução:**

| Código | Mensagem atual | Mensagem proposta |
|--------|---------------|-------------------|
| M5000 | Leitor ou código de ativação inválido | "O código de ativação não corresponde a esta conta. Veja como resolver." |
| A001 | — | "A ativação foi cancelada. Tente novamente ou acesse o suporte." |
| M5007 | Código incorreto | "Código digitado incorretamente 3 vezes. Aguarde 30 min ou use o QR Code abaixo." |

---

### Seção 2 — Troubleshoot (Autoatendimento)

**Objetivo:** direcionar o lojista para resolução sem precisar ligar para a central.

**Componentes:**
- **QR Code dinâmico** gerado com metadados do terminal e do usuário embutidos na URL
- **URL curta** como fallback para quem não consegue escanear (ex: `pgbk.app/erro`)
- **CTA textual:** *"Escaneie para resolver agora"* ou *"Acesse no seu celular"*

**Comportamento do QR Code:**

```
Usuário escaneia o QR Code
        │
        ├── App PagBank instalado?
        │       └── SIM → Abre app direto na tela "Minhas Maquininhas"
        │                  com contexto do erro pré-carregado
        │
        └── App NÃO instalado
                └── Abre página web com chat de suporte
                    (metadados já preenchidos — sem pedir dados novamente)
```

**Metadados passados via URL / deep link:**
- `terminal_id` — identificador da maquininha
- `error_code` — código do erro atual
- `account_id` — identificador da conta do lojista (se disponível no contexto da máquina)
- `tap_on_status` — disponibilidade e ativação do Tap On (para personalizar Seção 3)

> **Impacto esperado:** elimina o atrito de identificação no atendimento — o agente (ou chatbot) já sabe quem é o cliente, qual máquina e qual o problema, sem perguntar nada.

---

### Seção 3 — Fallback de Vendas (Contingência)

**Objetivo:** garantir que o lojista não perca a venda enquanto o problema é resolvido.

**Lógica de exibição — 3 estados possíveis:**

| Estado | Condição | Mensagem exibida |
|--------|----------|-----------------|
| **A** | Tap On disponível e ativado | *"Precisa vender agora? Utilize o Tap On no seu celular pelo app do PagBank."* |
| **B** | Tap On disponível, mas não ativado | *"Precisa vender agora? Seu celular tem o Tap On disponível. Ative no app do PagBank e faça suas vendas."* |
| **C** | Tap On não disponível no perfil | *"Precisa vender agora? Utilize o Link de Pagamento no seu celular pelo app do PagBank."* |

**Requisito técnico:** o terminal precisa consultar o perfil do lojista (via cache local ou chamada leve à API) para determinar o estado correto antes de renderizar a seção.

---

## 4. Requisitos Técnicos

| Requisito | Detalhe |
|-----------|---------|
| Geração do QR Code | Dinâmica, com metadados embutidos na URL |
| Deep link para app | Suporte a Universal Links (iOS) e App Links (Android) com fallback web |
| Página web de fallback | Chat responsivo, pré-populado com dados do terminal |
| Cache de perfil do lojista | Terminal precisa armazenar localmente: tap_on_status, account_id |
| Mapeamento de erros | Banco de mensagens humanizadas para cada código conhecido |
| Compatibilidade | Todos os modelos Moderninha (Pro, Smart, Plus, Wifi, X) |

---

## 5. Métricas de Sucesso

| Métrica | Baseline atual | Meta pós-implementação |
|---------|---------------|----------------------|
| Chamados originados por erros de terminal | ~10.395/dia (total central) | Redução de 15–25% nos chamados por erro de máquina |
| Taxa de autoatendimento via QR/app | 0% (não existe hoje) | ≥ 30% dos usuários que veem a tela de erro |
| Venda perdida por indisponibilidade | Não mensurado hoje | Redução mensurável via TPV comparativo |
| NPS Vendedor | 24 | Melhoria incremental (baseline pós-lançamento) |

---

## 6. O Que Não Está no Escopo (Hackathon)

- Implementação real do firmware nos terminais
- Integração completa com sistemas de produção
- Suporte a todos os ~247 códigos de erro mapeados (foco nos top 6: A001, M3021, M5000, M5004, M5005, M5007)
- Analytics avançado de uso da tela

**Para o hackathon:** protótipo da tela (Figma ou HTML), simulação do fluxo de QR Code e demonstração da lógica dos 3 estados de fallback com dados mockados.

---

## 7. Dependências e Perguntas em Aberto

| # | Questão | Para quem |
|---|---------|-----------|
| 1 | O terminal tem capacidade de armazenar cache do perfil do lojista localmente? | Faustino |
| 2 | A API de perfil do lojista é consultável de dentro do firmware? Qual o tempo de resposta? | Faustino + Bruno |
| 3 | Quais são os 6 erros mais frequentes com maior volume de chamados gerados? | Bruno (Dados) |
| 4 | Existe mapeamento de erros → mensagem amigável já feito em algum lugar? | Nat / Cristiana |
| 5 | O deep link para "Minhas Maquininhas" já existe no app? | Faustino |

---

*Documento gerado para alinhamento interno do Time 4 — Hackathon PagBank, maio/2026.*
