---
layout: post
title: Páginas em alta velocidade com AMP
---

Nos dias de hoje, onde todas as pessoas estão sempre conectadas nos seus smartphones, há uma necessidade crescente de consumir conteúdo rapidamente. Notícias sendo lançadas à todo momento, em tempo real. A velocidade das informações aumenta a cada dia. Um estudo divulgado Compuware revela que sete em cada dez usuários de celulares no mundo aguardam no máximo cinco segundos para que um site abra.

Com o propósito de tornar as páginas web consideravelmente mais rápidas, para saciar essa necessidade das pessoas, o Google criou um projeto open source chamado AMP (Accelerated Mobile Pages). 

<amp-img width="600" height="400" layout="responsive" src="/assets/images/posts/paginas-em-alta-velociade-com-amp/logo.jpg"></amp-img>

## Então, o que é AMP ?

AMP é basicamente uma página web estática muito otimizada para exibição, principalmente no mobile, que também utiliza um CDN (Content Delivery Network) do Google para entregar seu conteúdo quase instantaneamente. Qualquer componente externo dentro de uma página AMP, obrigatoriamente precisa ser carregado de forma assíncrona, não bloqueando de forma alguma o carregamento da página. 

Para uma página ser reconhecida como AMP, ela é dividida em alguns componentes, são eles: 

**AMP HTML** - Código HTML normal, apenas com algumas restrições. Algumas tags são substituídas por componentes AMP. 

**AMP JS** - Componentes responsáveis por carregar conteúdo externo em uma página AMP, como imagens vídeos e etc. 

**AMP Cache (Opcional)** - Armazena as páginas AMP em um cache do google e distribui pela CDN, tornando a exibição da página quase instantânea. Quando a sua página AMP é indexada no Google, *no mobile*, ela fica marcada com o símbolo caraterístico e, ao ser clicada, obtém o conteúdo do cache do Google e exibe rapidamente. 

Caso seu site tenha duas versões de página, uma normal e uma utilizando o AMP, é necessário que no HTML da página normal, faça referência à página AMP, utilizando a seguinte tag: 

```
<link rel=”amphtml” href=”http://www.example.com/post-example/amp/”>
```
Além disso, é necessário que na página AMP tenha uma tag canonical indicando o link do artigo original. 
```
<link rel="canonical" href="http://www.example.com/post-example/">
```
É recomendável que utilizemos um json-ld para descrever alguns metadados do site:

```
<script type="application/ld+json">
{  
   "@context":"http://schema.org",
   "@type":"NewsArticle",
   "mainEntityOfPage":"https://azeredogab.com/",
   "headline":"AzeredoGab",
   "datePublished":"2017-05-04T18:40:38+00:00",
   "dateModified":"2017-05-04T18:40:38+00:00",
   "description":"Arquitetura e Desenvolvimento de software, PHP, .NET, Javascript, Gestão de Projetos, Café, Cerveja... tem de tudo.",
   "author":{  
      "@type":"Person",
      "name":"Gabriel Azeredo"
   },
   "publisher":{  
      "@type":"Organization",
      "name":"AzeredoGab",
      "logo":{  
         "@type":"ImageObject",
         "url":"https://azeredogab.com/assets/images/logo.jpg",
         "width":"60",
         "height":"60"
      }
   },
   "image":{  
      "@type":"ImageObject",
      "url":"https://azeredogab.com/assets/images/logo.jpg",
      "height":"60",
      "width":"60"
   }
}

    </script>
```

## Validando uma página AMP

Existem ferramentas que tornam muito simples a validação de páginas AMP. O próprio site do projeto te dá [uma página](https://validator.ampproject.org/), onde você consegue colar seu código AMP e ele é validado. Outra opção é utilizar a [extensão do Google Chrome AMP Validator](https://chrome.google.com/webstore/detail/amp-validator/nmoffdblmcmgeicmolmhobpoocbbmknc)


# Começando com AMP de uma forma rápida

Se você tem um blog pessoal (como eu) ou quer simplesmente testar uma página AMP de forma mais rápida, sem muito trabalho, meu conselho é utilizar algum template pronto. [Existem vários templates legais! ](https://amptemplates.com/).Para criar esse blog, utilizei o [amplify](https://github.com/ageitgey/amplify). **Nos próximos posts vou tentar falar um pouco sobre como hospedar uma página AMP no github pages, para criar um blog pessoal sem nenhum custo de hospedagem.**

## Conclusão

Para fazer a web melhor e mais rápida (e também para concorrer com ferramentas de exibição de notícias, como o [https://instantarticles.fb.com/](Facebook Instant Articles), por exemplo), o projeto AMP foi um projeto sensacional e tenho certeza que irá avançar muito ainda. Acredito que daqui a um tempo, todos os tipos de páginas web estarão utilizando essa tecnologia, mas até lá, vamos torcer pra pelo menos os nossos portais de conteúdo favoritos esteja utilizando AMP rs. 

Grande Abraço! :) 



**Fontes:**
https://tecnologia.uol.com.br/ultimas-noticias/redacao/2011/07/27/internautas-moveis-esperam-so-5-segundos-pelo-carregamento-de-um-site-diz-pesquisa.jhtm

http://resultadosdigitais.com.br/blog/google-amp-accelerated-mobile-pages/