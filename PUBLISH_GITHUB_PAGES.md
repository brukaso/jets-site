# Publicar jetstech.com.br com GitHub Pages

Esta é uma opção simples, gratuita para repositório público e suficiente para uma landing page institucional.

## 1. Criar um repositório
No GitHub:
1. Crie um repositório, por exemplo `jets-site`.
2. Pode ser público. Não coloque nenhum segredo no repositório.
3. Faça upload de todos os arquivos desta pasta na raiz do repositório.
4. Confirme o commit.

## 2. Ativar GitHub Pages
No repositório:
1. `Settings`
2. `Pages`
3. Em **Build and deployment**, escolha **Deploy from a branch**.
4. Branch: `main`
5. Folder: `/ (root)`
6. Salve.

## 3. Definir o domínio no GitHub
Ainda em `Settings > Pages`:
1. Em **Custom domain**, digite `jetstech.com.br`.
2. Salve.
3. O arquivo `CNAME` desta pasta já contém `jetstech.com.br`.

Importante: configure o domínio no GitHub antes de apontar o DNS.

## 4. Configurar DNS no Registro.br
No painel do domínio `jetstech.com.br`, abra a edição da Zona DNS.

Para o domínio raiz, crie estes 4 registros A:

| Tipo | Nome | Valor |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

Para `www`, crie um CNAME:

| Tipo | Nome | Valor |
|---|---|---|
| CNAME | www | SEU_USUARIO_GITHUB.github.io |

Substitua `SEU_USUARIO_GITHUB` pelo seu usuário real do GitHub.

Não crie registro wildcard `*`.

## 5. Aguardar DNS
A propagação pode levar algum tempo e, em alguns casos, até 24 horas.

No Windows, você pode verificar:

```powershell
Resolve-DnsName jetstech.com.br -Type A
Resolve-DnsName www.jetstech.com.br -Type CNAME
```

O domínio raiz deve resolver para os IPs do GitHub Pages.

## 6. Habilitar HTTPS
Depois que o GitHub reconhecer o DNS:
1. Volte a `Settings > Pages`.
2. Aguarde o domínio ficar validado.
3. Marque **Enforce HTTPS** assim que a opção aparecer.

## 7. Teste final
Abra:
- https://jetstech.com.br
- https://jetstech.com.br/privacy.html
- https://jetstech.com.br/terms.html

Verifique no celular e no desktop.

## 8. Uso no TikTok Shop Partner Center
No campo Website, informe:

`https://jetstech.com.br`

Só faça isso depois que o domínio estiver abrindo normalmente com HTTPS.
