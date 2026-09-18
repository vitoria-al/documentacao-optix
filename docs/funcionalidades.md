# Funcionalidades

> Este documento explica **o que o usuário consegue fazer na nova página da Optix** e como cada funcionalidade se comporta do ponto de vista da interface.

---

# Observação sobre o backend

A plataforma possui uma parte interna responsável pelo processamento e comunicação com os arquivos.

Essa parte é chamada de **backend**.

Para evitar confusão:

```text
FRONT-END = aquilo que o usuário vê e utiliza
BACKEND   = aquilo que trabalha por trás da página
```

Exemplo:

```text
Usuário digita um código
        |
        v
FRONT-END envia a solicitação
        |
        v
BACKEND verifica as informações
        |
        v
FRONT-END mostra o resultado
```

Nesta etapa do projeto, a documentação pública apresenta detalhadamente o **front-end e o comportamento das funcionalidades**.

A arquitetura, código, automações, infraestrutura e processamento interno do backend serão detalhados apenas no **projeto do semestre seguinte**.

---

# Funcionalidades disponíveis

A nova página possui:

- página inicial institucional;
- menu de navegação;
- modo claro e escuro;
- adaptação para diferentes tamanhos de tela;
- acesso à página de localização;
- busca por código;
- leitura de QR Code;
- mensagens para diferentes estados da galeria;
- transição visual para a galeria;
- galeria de fotos;
- galeria de vídeos;
- miniaturas para facilitar a navegação;
- download individual;
- opção de baixar todos os arquivos;
- instruções de download;
- Termos de Uso;
- Política de Privacidade e LGPD;
- páginas personalizadas de erro;
- botão para voltar ao topo.

---

# Página "Localizar meus arquivos"

A página de localização é o ponto utilizado por quem já recebeu um código da operação.

Ela pode ser acessada pelo endereço interno:

```text
/localizar
```

Na tela, o usuário possui duas formas principais de localizar sua galeria:

```text
OPÇÃO 1
Digitar o código

OPÇÃO 2
Escanear o QR Code
```

---

# Busca manual por código

O visitante pode digitar o código recebido durante a experiência.

Exemplo:

```text
DEMO2026
```

Fluxo simplificado:

```text
Usuário digita o código
        |
        v
Pressiona o botão de localizar
        |
        v
Sistema verifica a solicitação
        |
        +----> Encontrou?
        |         |
        |        SIM
        |         |
        |         v
        |      Abre a galeria
        |
        +----> NÃO
                  |
                  v
             Mostra mensagem
```

A verificação técnica acontece no backend e não é detalhada publicamente neste semestre.

---

# Possíveis resultados da busca

Nem toda busca precisa terminar imediatamente em uma galeria.

A interface está preparada para diferentes situações.

## Galeria encontrada

Significa que a galeria está disponível.

O visitante pode prosseguir para seus arquivos.

## Galeria em processamento

Significa que os arquivos ainda estão sendo preparados.

O visitante recebe uma mensagem informando que a galeria ainda não está pronta.

## Galeria expirada

Significa que o período de disponibilidade terminou.

A interface informa ao visitante que aquele acesso não está mais disponível.

## Galeria não encontrada

Significa que o código informado não corresponde a uma galeria disponível.

Isso pode acontecer, por exemplo, quando:

- o código foi digitado errado;
- faltou algum caractere;
- o código não existe;
- o acesso já não está disponível.

---

# Leitor de QR Code

A página também permite utilizar a câmera do dispositivo.

O botão de QR Code abre uma área específica de leitura.

Arquivo principal da funcionalidade:

```text
static/qr-scanner.js
```

Estilo visual:

```text
static/qr-scanner.css
```

Fluxo:

```text
Usuário toca em "Escanear QR Code"
        |
        v
Página solicita acesso à câmera
        |
        v
Usuário permite
        |
        v
Câmera é aberta
        |
        v
QR Code entra na área de leitura
        |
        v
Código é identificado
        |
        v
Sistema verifica o conteúdo
        |
        v
Galeria é aberta
```

---

# Permissão da câmera

Por segurança, o navegador não pode simplesmente ligar a câmera sem autorização.

Por isso, o usuário precisa permitir o acesso.

Caso a permissão seja negada, a página não consegue realizar a leitura pela câmera.

Nesse caso, ainda existe a alternativa de digitar o código manualmente.

---

#  Compatibilidade do QR Code

A leitura pode utilizar recursos disponíveis no próprio navegador.

Quando necessário, a aplicação também possui uma alternativa em JavaScript.

Isso ajuda a aumentar a compatibilidade entre diferentes dispositivos e navegadores.

O objetivo é simples:

> permitir que o maior número possível de visitantes consiga escanear o código sem instalar outro aplicativo.

---

#  Transição para a galeria

Após uma leitura válida, a interface pode apresentar uma transição visual antes de abrir a galeria.

Isso evita uma mudança brusca de tela e mantém a identidade visual da Optix.

Existem recursos separados para diferentes formatos de tela.

Exemplo de arquivos utilizados:

```text
static/public/video/qr-transition-desktop.mp4
static/public/video/qr-transition-mobile.mp4
```

---

# Galeria

A galeria é a página onde os arquivos do visitante são apresentados.

Arquivo principal:

```text
templates/galeria.html
```

Estilo principal:

```text
static/galeria.css
```

Ela pode apresentar:

- fotos;
- vídeos;
- miniaturas;
- botões de download;
- orientações;
- controles adaptados para celular e computador.

---

# Miniaturas

Uma foto original pode ser grande demais para ser carregada várias vezes apenas para aparecer como prévia.

Por isso, a galeria pode utilizar versões menores para a visualização.

Exemplo:

```text
ARQUIVO ORIGINAL
foto_cliente.jpg
20 MB

        |
        v

MINIATURA
foto_cliente.webp
arquivo menor
```

Para o usuário, a vantagem é uma galeria mais leve e rápida.

A geração e o gerenciamento técnico dessas miniaturas pertencem ao backend e serão documentados no projeto do semestre seguinte.

---

# Exibição de fotos

As fotos aparecem organizadas na galeria.

O visitante pode visualizar seus registros sem precisar abrir cada arquivo diretamente pelo sistema operacional.

A interface é preparada para organizar vários itens de forma responsiva.

---

# Exibição de vídeos

Vídeos também podem aparecer na galeria.

A interface diferencia os tipos de mídia e permite ao visitante identificar quais itens são vídeos.

O processamento interno dos vídeos não faz parte da documentação pública atual.

---

# Download individual

Cada mídia pode possuir seu próprio botão de download.

Fluxo:

```text
Visitante encontra a foto
        |
        v
Toca em "Baixar"
        |
        v
Arquivo é solicitado
        |
        v
Navegador inicia o download
```

---

# Baixar todos os arquivos

A galeria também pode disponibilizar uma opção para baixar todos os arquivos.

Do ponto de vista do visitante:

```text
1. Pressiona "Baixar todos os arquivos"
2. A página inicia as solicitações necessárias
3. O navegador recebe os arquivos
```

O comportamento pode variar conforme o navegador e o sistema operacional.

Alguns navegadores podem solicitar autorização para múltiplos downloads.

---

# Orientações de download

A página possui orientações específicas porque o processo de salvar arquivos pode ser diferente em:

- iPhone;
- Android;
- computador.

Isso reduz dúvidas do visitante depois da compra.

---

# Tema claro e escuro

A interface oferece dois modos visuais:

```text
CLARO
ESCURO
```

O usuário pode alternar pelo botão localizado no cabeçalho.

A preferência pode ser guardada no próprio navegador.

Assim, a página tenta manter a escolha realizada anteriormente.

---

# Menu hambúrguer

O menu hambúrguer é representado pelo botão com linhas.

Ele é utilizado para abrir a navegação sem ocupar uma grande área da tela o tempo todo.

Fluxo:

```text
Botão do menu
      |
      v
Painel abre
      |
      v
Links ficam disponíveis
      |
      v
Usuário escolhe uma opção
```

---

# Responsividade

A página foi projetada para se adaptar ao tamanho da tela.

Isso significa que o mesmo conteúdo reorganiza sua aparência conforme o dispositivo.

Exemplo:

```text
DESKTOP
[ conteúdo lado a lado ]

CELULAR
[ conteúdo ]
[ um abaixo ]
[ do outro ]
```

Foram considerados:

- computador;
- notebook;
- tablet;
- celular.

---

# Vídeos e elementos visuais

A interface utiliza vídeos e imagens para reforçar a identidade visual.

Eles aparecem em áreas como:

- hero;
- localização;
- transições;
- apresentação das experiências.

Esses arquivos ficam principalmente dentro de:

```text
static/public/
```

---

# Botão "Voltar ao topo"

Em páginas longas, o visitante pode rolar bastante para baixo.

O botão de voltar ao topo permite retornar rapidamente ao início.

Fluxo:

```text
Usuário está no final da página
        |
        v
Toca no botão
        |
        v
Página volta para o topo
```

---

# Termos de Uso

A página possui acesso aos Termos de Uso.

A apresentação desses documentos utiliza:

```text
static/legal.js
static/legal.css
```

O objetivo é disponibilizar as informações legais sem obrigar o visitante a abandonar a página atual.

---

# Privacidade e LGPD

Também existe acesso às informações de Privacidade e LGPD.

Essa área explica ao visitante questões relacionadas ao tratamento de seus dados e registros.

A parte visual pertence ao front-end.

Os controles internos de segurança e armazenamento pertencem ao backend e não são detalhados publicamente nesta etapa.

---

# Páginas de erro

A aplicação possui páginas visuais próprias para erros.

Arquivos HTML:

```text
templates/403.html
templates/404.html
templates/500.html
```

Arquivos CSS relacionados:

```text
static/403.css
static/404.css
static/500.css
static/error.css
```

## Erro 403

Em termos simples:

> o acesso foi recusado.

## Erro 404

Em termos simples:

> a página ou recurso procurado não foi encontrado.

## Erro 500

Em termos simples:

> aconteceu um problema interno durante o processamento da solicitação.

A causa técnica de erros internos pertence à camada de backend e será tratada na documentação futura.

---

# Proteções gerais

A aplicação possui proteções internas para evitar comportamentos inadequados, acessos indevidos e uso abusivo.

Para esta documentação pública, basta compreender que existem mecanismos de proteção entre a interface e o servidor.

Detalhes como:

- regras internas de validação;
- limites;
- logs;
- filtros;
- servidores;
- processos;
- cabeçalhos;
- organização dos arquivos;
- infraestrutura de publicação;

não são expostos detalhadamente neste semestre.

---

# Experiência do usuário

As funcionalidades foram organizadas para que o visitante não precise compreender a tecnologia utilizada.

Ele precisa apenas saber:

```text
1. Entrar no site
2. Localizar seus arquivos
3. Digitar o código OU usar o QR Code
4. Abrir a galeria
5. Escolher seus arquivos
6. Baixar
```

Esse é o principal objetivo da interface.

---

# O que fica para o próximo semestre

A próxima etapa do projeto poderá documentar detalhadamente o backend.

Entre os assuntos reservados para essa etapa estão:

- arquitetura do servidor;
- processamento interno;
- geração e leitura de manifestos;
- cache;
- workers;
- preparação de miniaturas;
- expiração de galerias;
- logs;
- segurança de servidor;
- balanceamento;
- distribuição de arquivos;
- publicação;
- automações;
- integrações internas.

Nesta versão pública, esses recursos podem ser citados apenas para contextualizar o funcionamento da interface.

---

# Resumo das funcionalidades

> A nova página da Optix permite apresentar a plataforma, orientar o visitante, localizar galerias por código ou QR Code, visualizar fotos e vídeos e realizar downloads através de uma interface responsiva, moderna e preparada para diferentes dispositivos.

---



[Voltar para Página Inicial](../docs/paginainicial.md)
[Voltar para README](../README.md)
