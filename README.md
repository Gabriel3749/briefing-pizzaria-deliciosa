# briefing pizzaria deliciosa

## 1) Contexto e objetivo
**Objetivo do produto:** Plataforma web/mobile para pedidos de pizza com entreha ou retirada, pagamento online e rastreamento do pedido.
**Proposta de valor:** Reduzir tempo médio de pedido, diminuir erros de comunicações e aumentar ticket médio via combos/cupons.

## 2) Público alvo e personas
- **Cliente Final(João):** Realiza 3-4 pedidos/mês, busca praticidade e cupons.
- **Atendente:** Monitora a fila, resolve exceções.
- **Gestor:** Acompanha vendas, tempo de preparo e satisfação
- **Entregador:** Recebe rota e registra comprovação de entrega

## 3) Processo atual e dores 
Pedido é feito por whatsapp/telefone -> erros de sabor/endereço/troco, fila em picos, nenhuma visibilidade de status, checkout demorado.

##4) Escopo MVP
Catálogo (sabores, tamanos, adicionais), Carrinho, Checkout (Endereço + pagamento), Pedidos(Status), Cupons, Admin básico(cardápiom horários, preços, cupons, taxa por zona(perímetro).
**Fora do escopo MVP:** Fidelidade, multiçojas, multi-idioma

##5) Regras de Negócio
1. Pedido finalizado apenas com **endereço válido** (CEP+Número)
2. **Área de entrega por zona:** (Z1/Z3) com taxas diferentes
3. **Horário de funcionamento:** Aceita pedidos apenas no intervalo configurado
4. **Tamanho:** (P/M/G) altera preço e tempo de forno
5. **Adicionais:** Borda recheada soma R$8,00 por pizza
6. **Cupons:** Não cumulativos; "PIZZA10" aplica 10% ao subtotal
7. **Tempo estimado** = preparo + fila + entrega por zona (exibir ao cliente)
8. **Pagamento online:** captura imediata, **PIX** confirmção automática
9. **Estoque crítico:** Falta de ingredientes torna sabor indisponível
10. **Pedido mínimo:** Para entrega(ex.R$30,00)
11. **Retirada no balcão:** Sem taxa; exigir **código de retirada**
12. **Cancelamento:** Até 2 min após pagamento é automático; depois, via atendente

## 6) Requisitos funcionais
**Pedidos:** Status, Recebido -> Em preparo -> Saiu para entrega -> Entregue
**Catálogo:** Listar sabores, tamanhos, combos, busca por ingredientes
**Carrinho:** Alterar quantidades, adicionais, observações
**Endereço:** CEP auto-preenchido, multiplos endereços salvos
**Pagamento:** Cartão(Gateway) e **PIX** (QR + Confrimação), pagar na retirada
**Cupons:** Validação, cálculo e auditoria de uso
**Admin:** Cardápio, preçoes, horários, cupons, taxas por zona, fila de pedidos 
**Notificações:** e-mail/whatsapp ao mudar de status

## 7) Requisitos não funcionais
**Performace:** Resposta < 1s, pico de **100 pedidos/min** em promções 
**Segurança:** LGPD (Consentimento/privacidade)
**Disponibilidade:** 99.5% no horário de funcionamento; **backup diário**
**Compatibilidade:** Responsivo (mobile-first), navegadores modernos
**Observabilidade:** Logs de auditoria (pagamentos, cupons)

## 8) Integrações 
Pagamentos (gateway + **PIX**), CEP/Mapas (validação e zona), mensageria(whatsapp/smtp)
## Cronograma
- **Sprint 1(2 sem.):** Catálogo + Carrinho
- **Sprint 2(2 sem.):** Checkout+ Pagamento
- **Sprint 3(2 sem.):** Pedidos + Admin + Métricas
- **Go-live** (soft launch)

  ## Backlog inicial
  1. Como cliente **Listar pedidos**
  2. Como cliente **Filtrar pizzas**
  3. Como cliente **Adicionar/Remover pizzas**
  4. Como cliente **Aplicar cupom**
  5. Como cliente **Calcular taxa/tempo por zona**
  6. Como cliente **Salvar endereço**
  7. Como cliente **Pagar com pix**
  8. Como cliente **Acompanhar status**
  9. Como admin **Gerenciar cardápio**
  10. Como admin **Definir taxa por zona**
  11. Como admin **Criar cupons**
  12. Como atendente **Cancelar pedido**
