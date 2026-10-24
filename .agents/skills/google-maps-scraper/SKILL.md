---
name: google-maps-scraper
description: Use para prospectar empresas locais para a Vitria com o Google Maps Extractor da Omkar Cloud, configurar seu acesso ou organizar os resultados exportados.
---

# Prospecção no Google Maps para a Vitria

Leia o README.md da raiz para entender os serviços e o público da Vitria.
Esta é uma skill de integração criada para este projeto. O repositório de
referência não distribui uma skill Codex nem o código do extrator na versão
consultada. Este arquivo não instala o aplicativo ou disponibiliza uma API.

## Fontes

- Projeto: https://github.com/omkarcloud/google-maps-scraper
- Download oficial: https://www.omkar.cloud/google-maps-extractor/download
- Instalação em servidor: https://github.com/omkarcloud/google-maps-scraper/blob/master/server-deployment.md
- Uso avançado: https://github.com/omkarcloud/google-maps-scraper/blob/master/advanced.md
- Campos: https://github.com/omkarcloud/google-maps-scraper/blob/master/fields.md

Referência consultada em 24/10/2026, commit
`b83d79f3210977a31ff50bdd000b4d16b1f12365` do projeto de origem.
Confira as instruções atuais antes de instalar: requisitos e planos podem mudar.

## Preparar o acesso

1. Verifique se o aplicativo já está instalado e se existe uma API acessível
   neste ambiente. Não presuma que a instalação de outra sessão está disponível.
2. Em computador pessoal, use o instalador oficial adequado ao sistema.
   Em servidor Debian/Ubuntu, siga o guia oficial de implantação. Examine os
   scripts antes de executá-los e confira os requisitos do ambiente.
3. A implantação em servidor documentada pelo fornecedor exige autenticação
   Omkar Cloud. Configure os segredos pelo mecanismo do ambiente; nunca os
   escreva em arquivos versionados, comandos documentados ou mensagens.
4. Após a instalação, abra a documentação de API indicada pelo instalador.
   Descubra nela a URL, a autenticação e os endpoints reais. Não invente rotas,
   portas, parâmetros ou exemplos de API que não tenham sido verificados.
5. Verifique a conectividade com uma operação de leitura documentada antes
   de iniciar uma extração. Confirme o plano e os limites disponíveis.

Se o aplicativo ou o acesso estiver ausente, explique o requisito pendente.
Uma alternativa é o usuário executar o aplicativo e fornecer o CSV exportado.
Não declare a extração operacional apenas porque esta skill está no GitHub.

## Executar uma prospecção

1. Determine o segmento, cidade/região e quantidade desejada a partir do pedido.
   Se faltar uma informação que impeça a busca, solicite-a.
2. Use consultas concretas, por exemplo `oficinas em Campinas, SP`.
   O foco inicial da Vitria são comércios locais, prestadores de serviços,
   oficinas, clínicas e profissionais autônomos que possam precisar de sites.
3. Use a estratégia Detailed recomendada pelo fornecedor como ponto inicial,
   se disponível na versão instalada. Aplique filtros coerentes com o pedido.
4. Execute pela API documentada ou oriente a exportação pelo aplicativo.
   Registre a consulta, data, região, filtros e origem junto do resultado.
5. Preserve a exportação original localmente. Normalize os resultados em
   CSV UTF-8 sem substituir os campos originais. Campos úteis, quando presentes:
   nome, categoria, endereço, telefone, website, URL do Maps, place_id,
   nota e quantidade de avaliações.
6. Remova duplicados por place_id quando disponível; sem ele, compare nome,
   endereço e telefone. Não una empresas só porque têm nomes parecidos.
7. Para priorização, marque website ausente como oportunidade a verificar.
   Campo vazio não comprova que a empresa não possui site. Não atribua
   qualidade ruim a um site que não foi inspecionado.
8. Entregue a contagem encontrada, critérios de priorização, arquivo gerado e
   limitações. Diferencie dados coletados, verificações e hipóteses comerciais.

Enriquecimento de emails e outras funções podem exigir chave e créditos
separados. Não habilite recursos pagos sem autorização do usuário.
Prospecção e organização dos resultados não autorizam o envio de mensagens.

## Arquivos locais

Guarde exportações e resultados em `data/prospeccao/`, ignorada pelo Git.
Não adicione listas reais de contatos, credenciais ou arquivos `.env` aos commits.
Se um relatório precisar ser versionado, use dados agregados ou exemplos fictícios
claramente identificados. A skill é uma ferramenta interna de prospecção e não
exige mudanças no site estático da Vitria.
