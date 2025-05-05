<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ComponentsIndex :currentItem="4" :nextPage="12"/>
  </div>

  <div class="col-start-2 col-span-5">

### [**Results**](https://docs.empathy.co/develop-empathy-platform/ui-reference/components/base-components/result/)

There is no a pre-made result component in X-Components, but a couple of results-related base components that can be combined to configure what would be a result card. This allows more modularity and flexibility when approaching a setup.

#### Example of what a minimal result component could be:

```html {all|1,10|2,4|3|5,9|6|7-8}
<MainScrollItem>
  <BaseResultLink>
    <BaseResultImage />
  </BaseResultLink>
  <BaseResultLink>
    { result.description }
    <BaseResultCurrentPrice />
    <BaseResultPreviousPrice />
  </BaseResultLink>
</MainScrollItem>
```

  </div>
</div>

<!--
Clicks:
* Main scroll item to control the scroll on url load
* Result link (link to the product page)
* Image of the result
* Result link again
* The description
* The result prices for sale prices
-->