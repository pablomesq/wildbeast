# Projeto Bikcraft
> Este projeto foi desenvolvido durante o curso da Origamid. Nele, exploramos diversas ferramentas de desenvolvimento web front-end as quais podemos destacar: JavaScript(Puro), CSS3 e HTML5.

## Home

![](/img/readme/home.png)

## CSS Grid Layout
```CSS

/* GRID GERAL */

.estrutura {
  display: grid;
  grid-template-columns: minmax(160px, 1fr) 3fr 300px;
  grid-template-areas:
    'header header header'
    'sidenav content anuncios'
    'footer footer footer';
}

```


![](/img/readme/grid2.png)

## Responsividade

```CSS

/* Media Query */

@media (max-width: 1200px) {
  .estrutura {
    grid-template-areas:
      'header header header'
      'sidenav content content'
      'sidenav anuncios anuncios'
      'footer footer footer';
  }
}

@media (max-width: 760px) {
  .estrutura {
    grid-template-columns: 100%;
    grid-template-areas:
      'header'
      'sidenav'
      'content'
      'anuncios'
      'footer';
  }
}

```

![](/img/readme/respon2.png)







