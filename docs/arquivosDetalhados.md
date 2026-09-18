## Arquivos detalhados

> Este documento explica os principais arquivos **públicos e visuais** utilizados na nova página da Optix.

---

#  Antes de começar

O projeto possui arquivos de front-end e arquivos de backend.

Nesta documentação:

```text
FRONT-END
Será detalhado.

BACKEND
Será apenas identificado.
A implementação interna ficará para o projeto do semestre seguinte.
```

Isso é proposital.

Não significa que os arquivos de backend sejam desnecessários.

Significa apenas que eles não fazem parte do escopo público detalhado desta etapa acadêmica.

---

#  Como visualizar todos os arquivos

No Windows, abra o terminal dentro da pasta do projeto e execute:

```bat
tree /F /A
```

Explicação:

```text
tree = mostra a estrutura de pastas
/F   = inclui os arquivos
/A   = usa caracteres simples no terminal
```

Exemplo:

```text
C:\Optix Web> tree /F /A
```

---

# Pasta `templates`

A pasta:

```text
templates/
```

contém as páginas HTML utilizadas pela aplicação.

Pense nela como a pasta onde ficam os "esqueletos" das telas.

---

##  `templates/index.html`

É o arquivo principal da página inicial.

Responsável por organizar elementos como:

- cabeçalho;
- menu;
- hero;
- apresentação da Optix;
- Momentos Optix;
- seções de funcionamento;
- tecnologias;
- área para empresas;
- indicadores;
- contato;
- rodapé.

Em termos simples:

> se o usuário está vendo a página inicial, grande parte da estrutura dessa tela está neste arquivo.

---

##  `templates/localizar.html`

É a página utilizada para localizar uma galeria.

Ela apresenta recursos como:

- campo para digitar o código;
- botão de localização;
- acesso ao leitor de QR Code;
- mensagens ao usuário;
- elementos visuais da página de busca.

Essa página funciona como a ponte entre:

```text
Visitante
   |
   v
Código / QR Code
   |
   v
Galeria
```

A verificação interna do código é feita pelo backend e não será detalhada neste documento.

---

##  `templates/galeria.html`

É responsável pela estrutura visual da galeria.

Pode apresentar:

- fotos;
- vídeos;
- miniaturas;
- botões;
- controles de download;
- orientações para o visitante.

Em resumo:

> este é o arquivo que organiza a tela onde o visitante encontra seus registros.

---

##  `templates/403.html`

Página mostrada quando um acesso é recusado.

Mensagem geral:

> você não possui acesso a este recurso.

O motivo técnico da recusa é tratado internamente pelo backend.

---

##  `templates/404.html`

Página apresentada quando algo não foi encontrado.

Exemplo:

```text
Usuário tenta abrir uma página inexistente
        |
        v
404
```

---

## `templates/500.html`

Página apresentada quando ocorre uma falha interna.

Ela evita que o visitante receba apenas uma tela técnica ou uma mensagem sem identidade visual.

A causa e o tratamento técnico do erro pertencem ao backend e ficam fora do detalhamento público atual.

---

#  Pasta `static`

A pasta:

```text
static/
```

armazena arquivos utilizados pela interface.

Aqui ficam principalmente:

- CSS;
- JavaScript;
- imagens;
- vídeos;
- logos;
- recursos visuais.

---

##  `static/style.css`

É um dos principais arquivos de estilo global.

Pode controlar elementos compartilhados por várias partes da aplicação.

Exemplos:

- fontes;
- espaçamentos;
- cores;
- padrões visuais;
- elementos gerais;
- comportamentos responsivos.

Pense nele como uma das bases visuais da aplicação.

---

##  `static/index.css`

É utilizado principalmente na página inicial.

Responsável por estilos específicos de:

- hero;
- seções institucionais;
- cards;
- blocos;
- indicadores;
- áreas de apresentação;
- comportamento visual da Home.

Se algo está errado visualmente apenas na página inicial, este é um dos primeiros arquivos a verificar.

---

##  `static/localizar-meus-arquivos.css`

Controla a aparência da página utilizada para localizar galerias.

Pode estilizar:

- campo de código;
- botões;
- textos;
- área do QR Code;
- blocos de ajuda;
- responsividade da tela.

---

## `static/galeria.css`

Controla a aparência da galeria.

Responsável por organizar visualmente:

- fotos;
- vídeos;
- grade;
- botões;
- caixas;
- instruções;
- comportamento em celular e computador.

---

##  `static/qr-scanner.js`

É o principal JavaScript relacionado à leitura de QR Code.

Ele participa de ações como:

- abrir o leitor;
- solicitar câmera;
- iniciar a visualização;
- tentar identificar um QR Code;
- tratar o resultado;
- encerrar a câmera quando necessário.

### Atenção

Este arquivo controla o comportamento do leitor na interface.

A validação interna e o processamento posterior do código pertencem ao backend.

---

##  `static/qr-scanner.css`

Contém os estilos da interface do leitor de QR Code.

Pode controlar:

- área da câmera;
- moldura de leitura;
- textos;
- botões;
- estados visuais;
- adaptação para telas diferentes.

---

## `static/legal.js`

Controla comportamentos relacionados aos documentos legais apresentados na página.

Exemplos:

- abrir modal;
- fechar modal;
- alternar conteúdo;
- exibir Termos de Uso;
- exibir informações de Privacidade e LGPD.

---

##  `static/legal.css`

Controla a aparência dos componentes legais.

Exemplos:

- janela/modal;
- fundo;
- textos;
- títulos;
- rolagem;
- botões.

---

##  `static/button.css`

Arquivo de estilos utilizado em botões e efeitos específicos da interface.

Pode conter:

- animações;
- estados de hover;
- efeitos visuais;
- formas;
- tamanhos.

---

## `static/download-button.html`

Contém estrutura relacionada ao botão de download utilizado pela interface.

Serve como parte reutilizável ou referência para o comportamento visual do download.

---

##  `static/error.css`

É um arquivo de estilo compartilhado pelas páginas de erro.

Evita repetir o mesmo CSS em todas elas.

---

## `static/403.css`

Possui ajustes específicos da página de erro 403.

---

##  `static/404.css`

Possui ajustes específicos da página de erro 404.

---

## `static/500.css`

Possui ajustes específicos da página de erro 500.

---

#  Pasta `static/public`

A pasta:

```text
static/public/
```

contém recursos públicos utilizados visualmente pela página.

Ela possui imagens, vídeos e outros arquivos que o navegador pode precisar carregar.

---

##  `static/public/img/branding`

Contém arquivos relacionados à identidade visual.

Exemplos:

```text
optix-logo-dark-iris.png
optix-favicon-white-iris.png
```

Esses arquivos são utilizados para representar visualmente a marca.

---

## `static/public/img/errors`

Contém imagens utilizadas nas páginas de erro.

Exemplos:

```text
camera-403.png
camera-404.png
server-500.png
```

A função delas é tornar as mensagens de erro mais claras e coerentes com a identidade visual da Optix.

---

## `static/public/img/momentos`

Contém recursos da seção **Momentos Optix**.

Essa pasta é utilizada para organizar imagens apresentadas como exemplos das experiências.

Também pode conter arquivos auxiliares, como:

```text
NOMES_DAS_FOTOS.txt
```

---

## `static/public/media`

Armazena mídias utilizadas na apresentação institucional.

Pode conter:

- imagens;
- vídeos;
- materiais demonstrativos.

---

##  `static/public/video`

Contém vídeos utilizados diretamente pela interface.

Exemplos:

```text
localizar-hero.mp4
localizar-loading-loop.mp4
qr-transition-desktop.mp4
qr-transition-mobile.mp4
```

### `localizar-hero.mp4`

Vídeo utilizado na área principal da página de localização.

### `localizar-loading-loop.mp4`

Vídeo utilizado como elemento visual durante determinados estados de carregamento.

### `qr-transition-desktop.mp4`

Transição preparada para telas maiores.

### `qr-transition-mobile.mp4`

Transição preparada para dispositivos móveis.

---

#  `Exportacao_demo/DEMO2026`

A pasta:

```text
Exportacao_demo/
└── DEMO2026/
```

contém arquivos utilizados como demonstração.

Exemplos existentes no projeto:

```text
casal-praia-blue-park.jpg
flybike-bali-park.mp4
rio-lento-blue-park.jpg
super-maverick-blue-park.jpg
tirolesa-blue-park.jpg
```

Ela serve para testes e demonstrações sem depender de uma galeria real de cliente.

Código demonstrativo:

```text
DEMO2026
```

---

#  `requirements.txt`

O arquivo:

```text
requirements.txt
```

registra dependências Python utilizadas pelo projeto.

Ele está relacionado principalmente à camada interna da aplicação.

Como o backend será detalhado no próximo semestre, esta documentação não explica individualmente suas bibliotecas ou arquitetura.

---

# `.gitignore`

O arquivo:

```text
.gitignore
```

indica ao Git quais arquivos ou pastas não devem ser incluídos normalmente no repositório.

Ele pode ser usado para evitar o envio de:

- arquivos temporários;
- cache;
- dados locais;
- arquivos gerados automaticamente;
- informações que não devem fazer parte do código versionado.

---

#  Pastas históricas

O projeto possui pastas que foram mantidas como histórico ou referência.

Elas não representam necessariamente a versão que está sendo executada atualmente.

---

##  `HTML/`

Contém versões e exportações HTML utilizadas durante etapas anteriores do desenvolvimento.

Pode servir como:

- referência;
- comparação;
- backup;
- histórico de alterações.

A aplicação atual utiliza principalmente:

```text
templates/
static/
```

---

##  `Next/`

Contém exportações ou componentes JavaScript gerados em etapas anteriores.

Pode incluir arquivos como:

```text
index.js
navigation.js
footer.js
component.js
```

Essa pasta é mantida como referência histórica.

---

##  `UIDL/`

Contém:

```text
uidl.json
```

Esse arquivo está relacionado à estrutura exportada utilizada durante o desenvolvimento visual.

Não é o ponto principal de manutenção da versão atual.

---

# Arquivos de documentação e histórico

O projeto possui diversos arquivos com nomes semelhantes a:

```text
ALTERACOES_*.txt
ATUALIZACAO_*.txt
AJUSTES_*.txt
```

Eles registram mudanças realizadas durante o desenvolvimento.

Servem como histórico.

Exemplos de informações que podem aparecer nesses arquivos:

- correções;
- mudanças visuais;
- ajustes mobile;
- revisão de botões;
- alterações na galeria;
- mudanças de identidade;
- ajustes de QR Code.

Eles não devem ser confundidos com os arquivos principais da aplicação.

---

# Arquivos de backup

Também podem existir arquivos com extensões ou nomes de backup.

Exemplo:

```text
arquivo.py.bak_...
```

ou pacotes:

```text
PATCH_*.zip
```

Eles são cópias ou pacotes utilizados durante manutenções anteriores.

Não representam necessariamente o arquivo atualmente utilizado pelo sistema.

---

# Backend — arquivos identificados, mas não detalhados publicamente

Os arquivos abaixo pertencem à camada interna do projeto.

Eles existem no pacote atual, porém sua lógica **não faz parte da documentação pública detalhada deste semestre**.

Entre eles estão:

```text
app.py
optix_config.py
manifest_store.py
manifest_worker.py
waitress_worker.py
iniciar_workers.py
gerar_caddyfile.py
iniciar_teste_celular.py
teste_carga_arquitetura.py
Caddyfile.generated
CONFIGURACAO_MEDUSA.bat
INSTALAR_DEPENDENCIAS.bat
INDEXAR_GALERIAS_AGORA.bat
GERAR_CADDYFILE.bat
INICIAR_WORKER_MANIFESTOS.bat
INICIAR_WORKERS_WEB.bat
INICIAR_OPTIX_PRODUCAO.bat
```

Também existem diretórios internos relacionados ao funcionamento da aplicação, por exemplo:

```text
private/
media_cache/
logs/
documentacao_arquitetura/
```

### Por que eles não estão detalhados?

Porque o escopo atual concentra-se na nova página e em sua interface.

A explicação técnica desses arquivos envolve temas como:

- servidor;
- rotas;
- processamento;
- segurança;
- armazenamento;
- geração de arquivos auxiliares;
- infraestrutura;
- execução em produção;
- workers;
- balanceamento;
- cache;
- logs.

Esses assuntos serão tratados no **projeto do semestre seguinte**.

> "A aplicação já possui uma camada de backend responsável por dar suporte às funcionalidades da interface. Porém, como o escopo deste semestre está concentrado no desenvolvimento e redesign do front-end, a arquitetura interna do backend não será detalhada publicamente nesta etapa. Essa parte será aprofundada no projeto do semestre seguinte."

---

# Onde mexer dependendo do problema

Esta tabela serve como referência rápida.

| Quero alterar... | Primeiro arquivo/pasta para verificar |
|---|---|
| Página inicial | `templates/index.html` |
| Aparência geral | `static/style.css` |
| Aparência da Home | `static/index.css` |
| Página de localização | `templates/localizar.html` |
| Estilo da localização | `static/localizar-meus-arquivos.css` |
| Leitor de QR Code | `static/qr-scanner.js` |
| Aparência do leitor | `static/qr-scanner.css` |
| Página da galeria | `templates/galeria.html` |
| Aparência da galeria | `static/galeria.css` |
| Termos/LGPD | `static/legal.js` e `static/legal.css` |
| Página 403 | `templates/403.html` e `static/403.css` |
| Página 404 | `templates/404.html` e `static/404.css` |
| Página 500 | `templates/500.html` e `static/500.css` |
| Logo e identidade | `static/public/img/branding/` |
| Imagens de erro | `static/public/img/errors/` |
| Momentos Optix | `static/public/img/momentos/` |
| Vídeos da interface | `static/public/video/` |
| Backend | documentação do próximo semestre |

---

# Resumo para quem abriu a pasta pela primeira vez

Se você abriu o projeto e não sabe por onde começar:

```text
QUERO ENTENDER A HOME
→ templates/index.html
→ static/index.css
→ static/style.css

QUERO ENTENDER A BUSCA
→ templates/localizar.html
→ static/localizar-meus-arquivos.css

QUERO ENTENDER O QR CODE
→ static/qr-scanner.js
→ static/qr-scanner.css

QUERO ENTENDER A GALERIA
→ templates/galeria.html
→ static/galeria.css

QUERO ENTENDER TERMOS E LGPD
→ static/legal.js
→ static/legal.css

QUERO ENTENDER O BACKEND
→ não faz parte da documentação pública detalhada deste semestre
→ será aprofundado no projeto do semestre seguinte
```

---

# Resumo final

A divisão mais importante é:

```text
templates/
= estrutura das páginas

static/
= aparência, JavaScript, imagens e vídeos

Exportacao_demo/
= material utilizado para demonstração

HTML/, Next/, UIDL/
= histórico e referências de desenvolvimento

backend/
= existe e dá suporte à aplicação,
  mas será detalhado no próximo semestre
```

---

  

[Voltar para Página Inicial](../docs/paginainicial.md)


  ---
[Voltar para README](../README.md)

