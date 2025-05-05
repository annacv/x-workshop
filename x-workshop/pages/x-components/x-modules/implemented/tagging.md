<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="11" :nextPage="39"/>
  </div>

  <div class="col-start-2 col-span-5">
  
  ### **Tagging**

#### This module is in charge of sending the requests to track some user actions, but also makes sure that no tracking is done before the user actually accepts it.

A [**renderless component**](https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/tagging/components/tagging.vue) enables the tracking.

Specific actions then make a tracking request, for example, when a result is clicked. The tagging request sends properties like **location** and **feature**, which can vary depending on where the result is located and why it is displayed. 

Typically, this information is **provided** and **injected** to pass data to the events that the module [wiring](https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/tagging/wiring.ts#L283) uses to make the requests.


<h4>Usage Example:</h4>
```html {all}
<Tagging :consent="true" />
<LocationProvider location="predictive_layer">
  <Result
    :item="result"
  />
</LocationProvider>
```

<div class="description ml-2 mb-1 mt-0">* The <code>constent</code> prop is set to true to enable tracking. This is usually set in the app init object.</div>
<div class="description ml-2 mb-0 mt-0">* The result will send a tagging request with a location equal to <code>'predictive_layer'</code>.</div>

</div>
</div>
