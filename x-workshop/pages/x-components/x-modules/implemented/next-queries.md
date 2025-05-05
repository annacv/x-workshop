<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="4" :nextPage="25"/>
  </div>

  <div class="col-start-2 col-span-5">

### **Next Queries**

#### Module to handle terms usually searched by the users after the current query.

The next queries are requested to their own endpoint through the adapter, and the module stores the results. The <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/next-queries/components/next-queries.vue"><code>next-queries</code></a> and <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/next-queries/components/next-query.vue"><code>next-query</code></a> components follow a similar approach of using `base-suggestions` for the listing and `base-suggestion` for the individual elements that we saw previously.

#### They can be shown as:
A list of queries, inside the predictive layer:

![predictive-next-queries.png](../../../../images/predictive-next-queries.png)

</div>
</div>


---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="4" :nextPage="26"/>
  </div>

  <div class="col-start-2 col-span-5">

<p class="!mt-0">As a list of queries, scattered in the results grid:</p>

![next-queries-list.png](../../../../images/next-queries-list.png)

</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="4" :nextPage="27"/>
  </div>

  <div class="col-start-2 col-span-5">

<p class="!mt-0">Or even the module can also request and store a preview of the results of requesting that term, and display them as a sliding panel of results:</p>

![next-queries-preview.png](../../../../images/next-queries-preview.png)
<div class="description">*There is already a dedicated component called <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/next-queries/components/next-query-preview.vue"><code>next-query-preview</code></a> in the module for this.</div>
</div>
</div>
