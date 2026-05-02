# Booking → Planilha — Suplemento Outlook

Suplemento para extrair dados de confirmações de booking e atualizar o General Shipping automaticamente.

---

## Arquivos

| Arquivo | Descrição |
|---|---|
| `manifest.xml` | Registro do suplemento no Outlook |
| `taskpane.html` | Interface do painel lateral |
| `commands.html` | Arquivo auxiliar exigido pelo Outlook |

---

## Passo 1 — Publicar no Netlify

1. Acesse https://netlify.com e crie uma conta gratuita
2. Na página inicial, arraste a pasta `booking-addin` inteira para a área de deploy
3. O Netlify gera uma URL como `https://amazing-name-123.netlify.app`
4. **Copie essa URL**

---

## Passo 2 — Atualizar o manifest.xml

Substitua todas as ocorrências de:
```
https://booking-addin-placeholder.netlify.app
```
Pela URL real que o Netlify gerou, por exemplo:
```
https://amazing-name-123.netlify.app
```

Faça isso em 8 lugares no arquivo `manifest.xml` (use Localizar e Substituir no seu editor de texto).

Depois, **faça o deploy novamente** arrastando a pasta atualizada para o Netlify.

---

## Passo 3 — Instalar no Outlook (Mac)

1. Abra o **Outlook Desktop** no Mac
2. Abra qualquer e-mail
3. No menu superior, clique em **"..."** (reticências) ou **"Obter Suplementos"**
4. Selecione **"Meus suplementos"**
5. Role até o final e clique em **"Adicionar um suplemento personalizado"**
6. Escolha **"Adicionar a partir de arquivo..."**
7. Selecione o arquivo `manifest.xml`
8. Confirme a instalação

A partir daí, ao abrir qualquer e-mail, um botão **"Atualizar Planilha"** aparecerá na barra superior do Outlook.

---

## Passo 4 — Configurar a chave da API

Na primeira vez que abrir o painel:
1. Clique em **⚙ Configurações** no rodapé
2. Insira sua chave da API Claude (obtenha em https://console.anthropic.com)
3. Confirme o ID da planilha (já está preenchido com o General Shipping)

A chave fica salva localmente — você só precisa fazer isso uma vez.

---

## Como usar no dia a dia

1. Abra um e-mail de confirmação de booking
2. Clique em **"Atualizar Planilha"** na barra do Outlook
3. O painel abre com a PO já detectada (se estiver no assunto)
4. Confirme ou ajuste a referência do cliente
5. Clique em **"Extrair e atualizar planilha"**
6. Revise os dados extraídos
7. Clique em **"Confirmar atualização"**

Pronto — o General Shipping é atualizado automaticamente.
