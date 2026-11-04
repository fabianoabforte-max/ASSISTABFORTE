# Assistência Técnica

App para a assistência técnica pós-obra: chamados de garantia, visitas e agenda.
Arquivo único, funciona offline, instala no celular e no PC. Os dados ficam no
navegador e, se você conectar, no seu Google Drive (arquivo `assistencia.json` +
pasta com as fotos, dentro de uma pasta "Assistência Técnica").

Endereço: https://fabianoabforte-max.github.io/ASSISTABFORTE/

## Conectar ao Google Drive (uma vez só)

Precisa de um "Client ID" — é uma chave que diz ao Google qual app está pedindo
acesso ao Drive. É grátis e leva uns 10 minutos.

1. Entre em https://console.cloud.google.com com a sua conta Google.
2. No topo, clique no seletor de projeto → **Novo projeto** → nome
   `Assistencia` → **Criar**. Espere e selecione o projeto.
3. Menu ☰ → **APIs e serviços** → **Biblioteca** → procure
   **Google Drive API** → **Ativar**.
4. Menu ☰ → **APIs e serviços** → **Tela de permissão OAuth** (pode aparecer
   como "Google Auth Platform"):
   - Tipo de usuário: **Externo** → Criar.
   - Nome do app: `Assistência Técnica`; e-mail de suporte: o seu. Salvar.
   - Em **Público-alvo** (ou "Usuários de teste"): **Adicionar usuários** →
     o seu e-mail. Salvar. O app fica em modo "teste", que é o suficiente
     para uso próprio — não precisa publicar nem verificar.
5. Menu ☰ → **APIs e serviços** → **Credenciais** → **Criar credenciais** →
   **ID do cliente OAuth**:
   - Tipo: **Aplicativo da Web**.
   - Nome: `assistencia`.
   - **Origens JavaScript autorizadas** → Adicionar URI:
     `https://fabianoabforte-max.github.io`
   - Criar. Copie o **ID do cliente** (termina em `.apps.googleusercontent.com`).
6. No app: **Ajustes → Google Drive** → cole o Client ID → **Salvar ajustes**
   → **Conectar e sincronizar**. Autorize na janela do Google.

Depois disso o ícone de nuvem no topo mostra o estado. A conexão vale por
uma hora de uso; quando expirar, é só tocar na nuvem de novo.

## Como funciona a sincronização

- Ao abrir o app e 3 segundos depois de cada alteração, ele compara com o
  Drive: a versão mais recente ganha.
- É feito pra uma pessoa só. Se editar no celular e no PC sem sincronizar
  entre um e outro, a alteração mais antiga se perde.
- As fotos sobem uma por uma e só baixam quando você abre o chamado.
- O backup manual (Ajustes → Exportar) continua existindo como plano B —
  mas ele não leva as fotos.

## Testar

Abrir `index.html?teste=1` roda os testes das regras (garantia, status,
atrasadas, calendário).
