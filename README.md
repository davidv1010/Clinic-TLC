# TLC Clinic | Landing Page

Landing page de alta conversão da **TLC Clinic** (Estética e Harmonização Facial), focada em levar o visitante ao agendamento pelo WhatsApp.

Site estático (HTML, CSS e JavaScript puros), sem build e sem dependências. Responsivo, com SEO básico e zoom nas fotos.

## Estrutura

```
index.html          página
css/style.css       estilos
js/config.js        configurações editáveis (número do WhatsApp)
js/main.js          WhatsApp, animações de entrada e zoom das fotos
assets/img/         fotos da clínica
.github/workflows/  deploy automático no GitHub Pages
.github/ISSUE_TEMPLATE/  modelos de issue (tarefa e problema)
scripts/criar-issues.sh  cria as issues de pendências de uma vez
```

## Rodar localmente

Abra o `index.html` direto no navegador, ou use um servidor local:

```bash
python -m http.server 3000
# acesse http://localhost:3000
```

## Editar o WhatsApp

Altere o número em `js/config.js` (55 + DDD + número, só dígitos). Todos os botões da página usam esse valor.

## Publicar no GitHub Pages

1. Crie um repositório no GitHub e envie o código:
   ```bash
   git init
   git add .
   git commit -m "Landing page TLC Clinic"
   git branch -M main
   git remote add origin https://github.com/SEU-USUARIO/NOME-DO-REPOSITORIO.git
   git push -u origin main
   ```
2. No GitHub, vá em **Settings → Pages → Build and deployment → Source** e escolha **GitHub Actions**.
3. A cada `push` na branch `main`, o site é publicado em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

Para usar domínio próprio, configure em **Settings → Pages → Custom domain**.

## Pendências antes de ir ao ar

- Preencher a biografia e o nome da profissional (seção "Sobre a profissional").
- Informar o responsável técnico com registro profissional no rodapé.
- Confirmar endereço e horário de atendimento na seção de contato.
- Substituir os marcadores restantes por fotos reais (seção de resultados).
- Adicionar depoimentos reais e autorizados.
- Confirmar a autorização das pacientes para o uso das imagens e se o formato antes e depois é permitido pelas normas do conselho profissional.
- Opcional: definir `og:image` e `canonical` com a URL final do site.

## Criar as issues de pendências

Depois de enviar o código ao GitHub, instale o [GitHub CLI](https://cli.github.com), faça login com `gh auth login` e rode, dentro da pasta do repositório:

```bash
bash scripts/criar-issues.sh
```

Isso cria os marcadores (labels) e as 11 issues de pendências, cada uma com checklist.

## Criar as issues das pendências

Com o [GitHub CLI](https://cli.github.com) instalado e logado (`gh auth login`), rode na pasta do repositório (já enviado ao GitHub):

```bash
bash scripts/criar-issues.sh
```

O script cria os rótulos e uma issue para cada pendência acima. No Windows, use o Git Bash.
