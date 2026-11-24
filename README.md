# Garagem

App para registar abastecimentos e carregamentos, leituras de km e calcular consumos e poupança mensal. Funciona no iPhone como app instalada no ecrã principal (Safari → Partilhar → Adicionar ao Ecrã Principal).

Os dados ficam no telemóvel (localStorage) e, opcionalmente, são copiados para uma folha Google Sheets na tua conta.

## Configurar a sincronização com Google Sheets (uma vez)

1. Entra em [console.cloud.google.com](https://console.cloud.google.com) e cria um projeto (ex.: `garagem`).
2. Ativa a API **Google Sheets API** em *APIs e serviços → Biblioteca*.
3. Em *APIs e serviços → Ecrã de consentimento OAuth*, configura como **Externo**, preenche o nome da app e adiciona o teu email como utilizador de teste.
4. Em *APIs e serviços → Credenciais → Criar credenciais → ID do cliente OAuth*:
   - Tipo: **Aplicação Web**
   - **Origens JavaScript autorizadas**: `https://raduarte22.github.io`
5. Copia o **Client ID** (termina em `.apps.googleusercontent.com`).
6. Na app: **Definições → Google Sheets**, cola o Client ID, toca em **Guardar Client ID** e depois em **Ligar ao Google**.

A app cria uma folha "Garagem" com os separadores Veiculos, Registos e Km, e atualiza-a sempre que guardas alterações.

## Publicar no GitHub Pages

O repositório é `raduarte22/gastos-carro` (ou o nome que escolheres). Depois do primeiro `git push`:

- Em *Settings → Pages*, escolhe **Deploy from a branch**, branch `main`, pasta `/ (root)`.
- A app fica em `https://raduarte22.github.io/<nome-do-repositorio>/`.

## Privacidade

- Não há servidor: a app corre inteiramente no teu browser.
- A sincronização só pede acesso ao Google Sheets e só a folhas criadas pela própria app.
