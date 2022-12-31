---
title: Criar um Blog com o Jekyll no Github
date: 2022-12-15 21:55:00 -0300
categories: [Procedimento, Jekyll blog]
tags: [blog, github, gitpage, jekyll]
pin: false
---

## Pré-requisitos

Siga as instruções no [Jekyll Docs](https://jekyllrb.com/docs/installation/) para concluir a instalação do `Ruby`, `RubyGems`, `Jekyll`, e `Bundler`. Além disso, o [Git](https://git-scm.com/) também, lembre-se que só precisa fazer isso se for executar e testar no seu equipamento.

## Instalação

### Criando um novo site usando o Chirpy Starter

Crie um novo repositório a partir do [**Chirpy Starter**][use-starter] e de o nome de `<GH_USERNAME>.github.io`, onde `GH_USERNAME` representa o nome de usuário do GitHub.

### Configurando

Editar o arquivo `_config.yml`{: .filepath} e alterar as variaveis de acordo com a sua necessidade. Os principais campos são esses:

- `url`
- `avatar`
- `timezone`
- `lang`

### Customizing Stylesheet

If you need to customize the stylesheet, copy the theme's `assets/css/style.scss`{: .filepath} to the same path on your Jekyll site, and then add the custom style at the end of the style file.

Starting from [`v4.1.0`][chirpy-4.1.0], if you want to overwrite the SASS variables defined in `_sass/addon/variables.scss`{: .filepath}, create a new file `_sass/variables-hook.scss`{: .filepath} and assign new values to the target variable in it.

### Customing Static Assets

Static assets configuration was introduced in version `5.1.0`. The CDN of the static assets is defined by file `_data/assets/cross_origin.yml`{: .filepath }, and you can replace some of them according to the network conditions in the region where your website is published.

Also, if you'd like to self-host the static assets, please refer to the [_chirpy-static-assets_](https://github.com/cotes2020/chirpy-static-assets#readme).

### Executando o servidor local

Se você quiser testar o site antes de publicar, basta executar o comando abaixo:

```console
$ bundle exec jekyll s
```

Executando o servidor local

```console
$ docker run -it --rm \
    --volume="$PWD:/srv/jekyll" \
    -p 4000:4000 jekyll/jekyll \
    jekyll serve
```

Depois de um tempo, o serviço local será publicado em _<http://127.0.0.1:4000>_.


[starter]: https://github.com/cotes2020/chirpy-starter
[use-starter]: https://github.com/cotes2020/chirpy-starter/generate
[workflow]: https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/.github/workflows/pages-deploy.yml.hook
[chirpy-4.1.0]: https://github.com/cotes2020/jekyll-theme-chirpy/releases/tag/v4.1.0
[pages-workflow-src]: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow
[latest-tag]: https://github.com/cotes2020/jekyll-theme-chirpy/tags
