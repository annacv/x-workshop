
<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="5" :nextPage="28"/>
  </div>

  <div class="col-start-2 col-span-5">

### **Popular Searches**

#### Popular searches are the most searched terms, likely to be clicked by the user.

Popular searches are requested to their own endpoint, this can be done at any time as they don't depend on the current query. The wiring handles when to request them and the module stores them.

Once again, a pair of components, [`popular-search`](https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/popular-searches/components/popular-search.vue) and [`popular-searches`](https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/popular-searches/components/popular-searches.vue), based on `base-suggestions` and `base-suggestion`, are enough to render the information in this module.

<div class="mb-1 mt-0">In the X-Archetype they are used to be rendered as a list of queries inside the predictive layer (empathize) when the search input is focused without a query, but they also can be displayed in the main grid zone as a pre-search strategy.</div>

![popular-searches.png](../../../../images/popular-searches.png)

</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="5" :nextPage="29"/>
  </div>

  <div class="col-start-2 col-span-5">

  <h4 class="mt-0">Popular searches shown as main page content before user starts searching.</h4>

  <div class="description">Each popular searched query is used to be rendered with preview of its results inside a sliding panel.</div> 

  ![popular-searches-pre-search.png](../../../../images/popular-searches-pre-search.png)
  </div>

</div>
