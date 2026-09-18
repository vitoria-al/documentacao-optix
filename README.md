# Optix — Soluções Fotográficas

O projeto corresponde à nova interface web da Optix, criada para apresentar a plataforma de forma moderna, explicar seus serviços e permitir que o visitante encontre suas fotos e vídeos.




### Para acessar mais informações sobre a   [página inicial](docs/paginainicial.md)

# Descrição

A **Optix — Soluções Fotográficas** é uma plataforma voltada à gestão e entrega de registros fotográficos e audiovisuais produzidos em parques, atrações e experiências.
Nesta etapa do projeto, o foco acadêmico está principalmente na **interface da aplicação**, ou seja, naquilo que o usuário consegue ver e utilizar diretamente no navegador.

Isso inclui:

- página inicial;
- navegação;
- apresentação dos serviços;
- modo claro e escuro;
- adaptação para celular, tablet e computador;
- página de localização de arquivos;
- leitura de QR Code;
- visualização da galeria;
- orientações ao visitante;
- páginas de erro;
- termos de uso e privacidade.

> **IMPORTANTE SOBRE O BACKEND**
>
> O **backend**, ou seja, a parte interna responsável pelo processamento, servidor, organização das galerias, segurança, automações e comunicação com os arquivos, **não será detalhado na documentação pública deste projeto**.
>
> Ele existe e é necessário para o funcionamento completo da plataforma, porém seu desenvolvimento e sua documentação aprofundada fazem parte do **projeto do semestre seguinte**.
>
> Neste documento, o backend será citado apenas quando for necessário explicar o funcionamento geral da página, sem expor sua implementação interna.

### Resumindo de forma simples

O visitante entra na Optix, conhece a plataforma e, caso já tenha realizado uma experiência, pode utilizar seu código ou QR Code para chegar à sua galeria.

---






# Problema a ser resolvido

Operações fotográficas em parques, atrações e experiências produzem uma grande quantidade de fotos e vídeos durante o dia.

Sem uma interface organizada, o cliente pode enfrentar problemas como:

- não saber onde encontrar suas fotos;
- precisar falar com um atendente para localizar arquivos;
- digitar endereços ou informações complicadas;
- acessar páginas confusas;
- ter dificuldade para usar o site pelo celular;
- não saber se uma galeria ainda está disponível;
- não entender como baixar suas fotos;
- receber uma experiência visual diferente da identidade da empresa.

A nova página da Optix busca resolver esses problemas criando uma experiência única e simples.

Fluxo básico:

```text
Visitante entra no site
        |
        v
Conhece a Optix
        |
        v
Quer localizar seus arquivos?
        |
       SIM
        |
        v
Abre "Localizar meus arquivos"
        |
        +----> Digita o código
        |
        ou
        |
        +----> Escaneia o QR Code
        |
        v
Sistema verifica a galeria
        |
        v
Galeria é exibida
        |
        v
Visitante visualiza e baixa os arquivos
```

O objetivo é deixar a experiência mais rápida, intuitiva e padronizada.

---

# Requisitos operacionais

## Para visualizar a página

É recomendado utilizar um navegador moderno, por exemplo:

- Google Chrome;
- Microsoft Edge;
- Mozilla Firefox;
- Safari.

A página foi desenvolvida para funcionar em:

- computador;
- notebook;
- tablet;
- celular.

##  Para usar o leitor de QR Code

O dispositivo precisa possuir:

- câmera;
- permissão para o navegador acessar a câmera;
- navegador compatível com recursos modernos da web.

Em ambiente publicado, o acesso à câmera deve ocorrer utilizando conexão segura **HTTPS**.

##  Para executar o projeto em ambiente de desenvolvimento

O projeto utiliza tecnologias de front-end e também uma camada interna de servidor.

O ambiente utilizado no desenvolvimento possui:

```text
Windows
Python 3.10 ou superior
HTML5
CSS3
JavaScript
Flask
```

As dependências internas estão registradas no arquivo:

```text
requirements.txt
```

> A instalação, configuração e arquitetura completa do backend não são detalhadas nesta documentação pública, pois fazem parte da próxima etapa do projeto.

##  Arquivos necessários para a interface

Para compreender visualmente o projeto, os diretórios mais importantes são:

```text
templates/
static/
```

`templates/` contém as páginas HTML utilizadas pela aplicação.

`static/` contém estilos, JavaScript, imagens, vídeos, logos e outros recursos visuais.

---

# Ferramentas utilizadas

| Ferramenta / tecnologia | Para que foi utilizada |
|---|---|
| **HTML5** | Criação da estrutura das páginas |
| **CSS3** | Aparência, responsividade, temas e animações |
| **JavaScript** | Interações, menus, QR Code, efeitos e recursos da interface |
| **MediaDevices API** | Permissão e acesso à câmera do dispositivo |
| **BarcodeDetector API** | Leitura de QR Code em navegadores compatíveis |
| **jsQR** | Alternativa para leitura de QR Code |
| **LocalStorage** | Guarda a preferência de tema claro ou escuro |
| **SessionStorage** | Auxilia em comportamentos temporários durante a navegação |
| **Google Fonts** | Fontes utilizadas na identidade visual |
| **Animate.css** | Apoio a animações da interface |
| **TeleportHQ** | Utilizado como base em partes da estrutura visual |
| **Python / Flask** | Suporte interno para funcionamento da aplicação |
| **Outras ferramentas de servidor** | Utilizadas no backend e detalhadas somente no projeto do semestre seguinte |

---

#  Funcionalidades gerais

Esta seção apresenta apenas um resumo. As funcionalidades completas estão descritas no **[funcionalidades](docs/funcionalidades.md)**.

A versão atual possui:

- página inicial institucional;
- menu de navegação;
- menu hambúrguer;
- modo claro e escuro;
- seções explicativas sobre a Optix;
- apresentação de experiências;
- botão para localizar arquivos;
- busca por código;
- leitura de QR Code;
- galeria de fotos e vídeos;
- download de arquivos;
- orientações para diferentes dispositivos;
- Termos de Uso;
- Política de Privacidade e LGPD;
- páginas personalizadas de erro;
- adaptação para desktop, tablet e celular;
- botão para voltar ao topo.

---

#  Estrutura do projeto

## Como visualizar a estrutura com **tree**

No Windows, abra o terminal dentro da pasta do projeto e execute:

```bat
tree /F /A
```

O parâmetro `/F` mostra os arquivos existentes dentro das pastas.

O parâmetro `/A` utiliza caracteres simples, evitando problemas de exibição no terminal.

### Exemplo

```text
C:\Projeto\Optix Web> tree /F /A
```

## Estrutura simplificada

A árvore abaixo foi simplificada para mostrar as partes mais importantes do projeto público:

```text
Optix Web
|
|   README.md
|   requirements.txt
|
+---templates
|       index.html
|       localizar.html
|       galeria.html
|       403.html
|       404.html
|       500.html
|
+---static
|   |   style.css
|   |   index.css
|   |   localizar-meus-arquivos.css
|   |   galeria.css
|   |   qr-scanner.css
|   |   qr-scanner.js
|   |   legal.css
|   |   legal.js
|   |   button.css
|   |   download-button.html
|   |   error.css
|   |   403.css
|   |   404.css
|   |   500.css
|   |
|   +---public
|       |
|       +---img
|       |   +---branding
|       |   +---errors
|       |   +---momentos
|       |
|       +---media
|       |
|       +---video
|
+---Exportacao_demo
|   +---DEMO2026
|           arquivos de demonstração
|
+---HTML
|       versões/exportações históricas
|
+---Next
|       componentes/exportações históricas
|
+---UIDL
|       arquivo de estrutura exportada
|
+---BACKEND / INFRAESTRUTURA
        arquivos internos existentes no projeto,
        mas não detalhados publicamente nesta etapa
```

# Autores

Projeto desenvolvido pela equipe:

- **Kevin H. Z. Schirrmann**
- **Vitória Alves de Oliveira**
- **Paulo de Tarcío**
- **Deyvison Ranyeri**

Projeto relacionado ao desenvolvimento e redesign da plataforma **Optix — Soluções Fotográficas**.

---


