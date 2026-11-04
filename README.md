# Assistência Técnica

App para a assistência técnica pós-obra: chamados de garantia, visitas e agenda.
Arquivo único, funciona offline, instala no celular e no PC. Os dados ficam no
aparelho e, para quem entra com e-mail e senha, sincronizam com o banco da
empresa (Supabase).

Endereço: https://fabianoabforte-max.github.io/ASSISTABFORTE/

## Conta e sincronização (Supabase)

Os dados ficam no aparelho e, estando logado, sobem para o banco da empresa.
O app continua funcionando offline; sincroniza sozinho alguns segundos depois
de cada alteração e ao abrir.

Perfis, definidos no banco:

- **admin** — vê e altera tudo, e libera os outros;
- **registrador** — abre chamado, agenda e conclui visita, encerra, nas obras liberadas;
- **leitor** — só visualiza.

Quem decide o que cada um enxerga é o banco (regras por linha), não a tela.
A primeira conta criada vira admin automaticamente.

Estrutura do banco: ver o arquivo SQL entregue na implantação.

## Como funciona a sincronização

- Ao abrir o app e alguns segundos depois de cada alteração, ele envia o que
  mudou aqui e baixa o que os outros mudaram — registro a registro.
- Só sobe o que realmente mudou, comparando uma assinatura de cada registro.
- Exclusões também viajam: o registro é marcado como excluído no banco.
- **As fotos ainda ficam só no aparelho** — vão para a nuvem numa próxima etapa.
- O backup manual (Ajustes → Exportar) continua existindo como plano B.

## Testar

Abrir `index.html?teste=1` roda os testes das regras (garantia, status,
atrasadas, calendário).
