# Elitte Barber: sistema (visual novo)

Este é o sistema da Muniz Studio com o visual da **Elitte Barber**. O **Anderson Lucas** é o único barbeiro.
Os endereços dos webhooks, os dados enviados e as regras de cálculo **são os mesmos** do sistema da Muniz.

## Páginas

| Página | Para quem | O que faz |
|---|---|---|
| `link.html` | Cliente | Agendamento online (serviços, data, horário e "Meus agendamentos") |
| `index.html` | Admin (senha `km12873`) | Divisão de lucros |
| `financeiro.html` | Admin | Caixa e frente de loja |
| `barbeiros.html` | Admin | Acesso ao painel do Anderson Lucas |
| `agenda.html` | Admin | Agenda geral |
| `clientes.html` | Admin | Clientes regulares |
| `qrcode.html` | Admin | Conectar o WhatsApp (Evolution) |
| `anderson.html` | Anderson (senha `2027anderson`) | Painel completo: agenda, pagamento, editar e cancelar |
| `tarefas.html` | Anderson | Atendimentos passados que ainda não foram pagos |
| `clientes-barbeiro.html` | Anderson | Clientes regulares |
| `caixa_barbeiros.html` | Anderson | Caixa do barbeiro |

Imagens: `logo.png` (selo do perfil), `logo-completo.png` (carrossel), `anderson.png` (foto), `image.png` (ícone do app e favicon). Também vai um `manifest.json` novo.

## O que mudou além do visual

- **Painel do Anderson:** agora usa o painel completo, que era o do Igor, com confirmação de pagamento, tarefas atrasadas e financeiro. Ele envia `ag-barbeiro: 'anderson'`, o mesmo valor que o painel antigo do Anderson já usava. O `igor.html` saiu do sistema.
- **Página do cliente:** só aparece o Anderson Lucas, e ele já vem selecionado. O agendamento continua sendo enviado com `ag-barbeiro: 'Anderson'`.
- **Dashboard:** os nomes passaram a ser "Repasse Barbeiro Anderson Lucas", "Sócio 1" e "Sócio 2". O cálculo continua o mesmo.
- **Menu lateral do barbeiro:** as páginas `anderson.html`, `tarefas.html`, `clientes-barbeiro.html` e `caixa_barbeiros.html` agora têm links entre si. Antes, algumas levavam para as páginas do admin.
- **Nome do arquivo:** `caixa barbeiros.html` (com espaço) passou a se chamar `caixa_barbeiros.html`, e os links foram ajustados.
- **Sino do celular:** no painel, ele agora abre a página de tarefas. Antes, mostrava "Página em construção".
- **`qrcode.html`:** os links do menu apontavam para `dashboard.html` e `whatsapp.html`, que não existem. Agora apontam para `index.html` e `qrcode.html`.

## Para preencher em `link.html`

Procure por `EDITE AQUI` no arquivo:

1. Endereço e telefone (estão destacados em amarelo na página).
2. Mapa: está desativado até você colocar o endereço.
3. Horário de funcionamento: foi copiado da Muniz, confira.
4. Texto da aba "Sobre".

## Atenção: n8n compartilhado

Todos os webhooks continuam apontando para `n8n-n8n.njqmsx.easypanel.host`, os mesmos da Muniz. Se as duas barbearias usarem esses endereços, agenda, caixa e clientes vão se misturar. Para separar, duplique os fluxos no n8n com outros caminhos e troque as URLs nas constantes no começo de cada `<script>`.
