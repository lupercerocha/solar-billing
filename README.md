# ☀️ Solar Billing — Cultivve Gestão

Sistema de cobrança mensal de energia solar para clientes que compartilham a geração distribuída.

**[Acessar o sistema →](https://lupercerocha.github.io/solar-billing/)**

---

## O que faz

Calcula automaticamente o valor mensal a cobrar de um cliente que consome energia de uma usina solar compartilhada (GD-II), considerando consumo instantâneo, energia injetada na rede e desconto sobre o preço da concessionária.

### Fluxo mensal

1. **Upload do PDF** da conta Energisa do cliente (casa)
2. O sistema extrai automaticamente: mês, consumo kWh, energia injetada e preço por kWh
3. Você preenche a **Energia Produzida** (dado do inversor solar)
4. O sistema calcula tudo e gera a **mensagem para WhatsApp**
5. Copiar → Colar no WhatsApp → Salvar no histórico

### Cálculo

```
Consumo Instantâneo = Energia Produzida − Energia Injetada
Consumo Total       = Consumo da Conta + Consumo Instantâneo
Preço kWh           = (Consumo × Tarifa com tributos + COSIP + Bandeira) ÷ Consumo
Valor Bruto         = Consumo Total × Preço kWh
Desconto            = Valor Bruto × 15%
Total a Pagar       = Valor Bruto − Desconto
```

---

## Funcionalidades

- **Leitura automática de PDF** — extrai dados da conta Energisa via PDF.js local, com fallback para IA
- **Cálculo do preço efetivo por kWh** — inclui tarifa com tributos, COSIP e bandeira tarifária
- **Mensagem WhatsApp** pronta para copiar com todos os dados formatados
- **Histórico mensal** persistente com detalhes de cada cobrança
- **PWA** — funciona como app no iPhone (adicionar à tela inicial via Safari)
- **Dados do PIX** configuráveis e salvos automaticamente
- **Limpeza automática** dos campos após salvar, pronto para o próximo mês

---

## Instalação no iPhone

1. Abra o link do sistema no **Safari**
2. Toque no ícone de **compartilhar** (quadrado com seta para cima)
3. Toque em **"Adicionar à Tela de Início"**
4. Confirme

O app abre em tela cheia, sem barra do navegador.

---

## Stack

- HTML + CSS + JavaScript puro (arquivo único, sem build)
- [PDF.js](https://mozilla.github.io/pdf.js/) para leitura local de PDFs
- [Anthropic API](https://docs.anthropic.com/) como fallback para extração via IA
- LocalStorage para persistência de dados
- PWA com manifest para instalação mobile

---

## Identidade visual

Cores da **Cultivve Gestão** — Simplicidade, Eficácia e Resultado

| Cor | Hex | Uso |
|-----|-----|-----|
| Azul escuro | `#172334` | Header, cards escuros |
| Verde azulado | `#3AA094` | Acentos, botões, destaques |
| Cinza claro | `#F2F1F1` | Background |

---

Desenvolvido por **Cultivve Gestão** · João Pessoa/PB
