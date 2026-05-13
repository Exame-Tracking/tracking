# Uso

Adicione os scripts dentro do `<head>` da página.

```html
<script>
  document.head.appendChild(Object.assign(document.createElement("script"), {
    src: `https://cdn.jsdelivr.net/gh/Exame-Tracking/tracking@1/pageview.min.js?cb=${Math.floor(Date.now() / 600000)}`,
  }));
  document.head.appendChild(Object.assign(document.createElement("script"), {
    src: `https://cdn.jsdelivr.net/gh/Exame-Tracking/tracking@1/lead.min.js?cb=${Math.floor(Date.now() / 600000)}`,
  }));
</script>
```

## Scripts

### `pageview.min.js`

Responsável pelo tracking automático de visualizações de página.

### `lead.min.js`

Responsável pelo tracking de leads e envios de formulário.

## Versionamento

Os arquivos são carregados via jsDelivr usando o repositório GitHub:

```txt
https://cdn.jsdelivr.net/gh/Exame-Tracking/tracking@1/
```

O `@1` representa a versão principal (`major version`) do projeto.

Exemplos:

```txt
@1     -> sempre última versão da série 1.x.x
@1.2   -> sempre última versão da série 1.2.x
@1.2.0 -> versão fixa exata
```

Isso permite atualizar scripts sem alterar a URL principal, mantendo controle de compatibilidade.

## Cache Busting

O parâmetro `cb` é atualizado automaticamente a cada 10 minutos:

```js
Math.floor(Date.now() / 600000)
```

Isso força a atualização do cache da CDN periodicamente, evitando que navegadores utilizem versões antigas dos arquivos por muito tempo.