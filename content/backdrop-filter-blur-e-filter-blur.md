---
title: "Backdrop Filter Blur e Filter Blur"
date: 2023-12-19T10:50:32-03:00
draft: false
type: "post"
layout: "post"
tags: ['css', 'blur', 'figma']
featured_image: "uploads/blur.webp"
---

<figure>
<img src="/uploads/blur.webp" alt="Backdrop Filter Blur e Blur" width="700" height="500">
</figure>

Assim como no figma, no css temos 2 propriedades pra aplicar o *blur* em elementos.
Apesar de aplicarem o mesmo efeito, eles tem diferenças nas aplicações.

## backdrop-filter: blur

Essa propriedade adiciona o blur no **background** do elemento. Os elementos que ficam dentro do elemento pai, não sofrem as alterações. Ele precisa ser transparente ou parcialmente transparente para surtir o efeito.

Sintaxe do css:

```css
.element {
	backdrop-filter: blur(10px);
}
```

No figma: 

```html
Effects > Background blur
```

## filter: blur

O `filter: blur` aplica o efeito em **todo** elemento juntamente com os elementos filhos. Geralmente é usado em imagens e em svg com a tag `<feGaussianBlur>`.

Sintaxe do css:

```css
img {
	filter: blur(10px);
	filter: url(#blur); /* embedded SVG */
	filter: url(folder/file.svg#blur); /* svg externo */
}
```

Em svg:

```html
<svg role="none">
	<filter id="blur">
		<feGaussianBlur stdDeviation="10" edgeMode="duplicate" />
	</filter>
</svg>
```

No figma:

```html
Effects > Layer Blur
```

Esses efeitos podem causar confusão na hora de fazer o hand-off do figma para o código. Usando elas da forma correta, você garante que não vai ter diferenças no elemento final.