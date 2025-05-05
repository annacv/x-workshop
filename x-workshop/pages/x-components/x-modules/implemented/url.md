<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="12" :nextPage="40"/>
  </div>

  <div class="col-start-2 col-span-5">
  
  ### **Url**

#### Manages the browser URL parameters to preserve them through reloads and history navigations.

The module is based on a **renderless component** called [`url-handler`](https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/url/components/url-handler.vue) that parses the URL parameters and emits the events to update the stores of the modules. The component handles various logics and edge cases, like navigating with the browser back button or coming from Product Page.

##### · Stores url parameters that are relevant in case of a url reload (sorting, facets, query, etc.). 
##### · Listens to events that impact on that relevant parameters for the url and updates the URL if needed.
##### · Restores the X Components store status when loading from URL.

<p class="description !mt-6 !mb-0">* There's no special usage for this module, just placing the <code>url-handler</code> component in the root component of the setup is enough.</p>

</div>
</div>

