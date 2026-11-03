# Sobrado Vila das Palmeiras — código-fonte do site

Pacote isolado da página pública do imóvel. Não contém painel da obra, planilhas, credenciais, senhas nem acesso ao servidor original.

## Estrutura

- `index.html`: página principal
- `maquete.html`: maquete 3D navegável
- `conteudo.txt`: textos editáveis da página
- `renders/`: imagens, plantas e `lista.json`

## Como visualizar

O site precisa ser servido por HTTP porque `index.html` carrega `conteudo.txt` e `renders/lista.json` com fetch.

Exemplo local: `python3 -m http.server 8080`. Depois, abra `http://localhost:8080`.

## Como publicar

É um site estático, sem etapa de build. Pode ser publicado no Vercel, Netlify, Cloudflare Pages ou hospedagem equivalente usando esta pasta como raiz e sem comando de build.

## Integração de leads/webhook

O site entregue ainda não possui formulário. Para receber leads, adicione o formulário em `index.html` e envie os dados para uma função de backend/serverless, por exemplo `/api/lead`.

Não coloque URL privada, token ou segredo do webhook diretamente no JavaScript do navegador. Guarde o webhook em variável de ambiente no provedor e faça a função serverless encaminhar os dados. Valide os campos, aplique limite de requisições e proteção antispam.

Campos mínimos recomendados: nome, WhatsApp, interesse e consentimento de contato.

## Conteúdo

Os textos comerciais estão em `conteudo.txt`. As imagens são ilustrativas e o aviso legal já aparece no rodapé.
