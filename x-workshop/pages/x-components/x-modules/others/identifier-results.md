<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="14" :nextPage="43"/>
  </div>

  <div class="col-start-2 col-span-5">

### **Identifier Results**

#### Module containing the results of a search by product id.

Beside other common module configurations (e.g `maxItemsToRequest`), it requires the **regex expression** that provides the characters' match and activates the request to the **identifier search endpoint** through the adapter.

The response of that request is mapped and saved in the identifier results state module as `Results[]`. The components in the module are: the [`IdentifierResult`](https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/identifier-results/components/identifier-result.vue) item, with the identifier query and its matching part; and the  [`IdentifierResults`](https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/identifier-results/components/identifier-results.vue) list of items that are rendered inside the predictive layer.

<br/>

![sku.png](../../../../images/sku.png)

</div>
</div>
