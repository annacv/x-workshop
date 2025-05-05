
<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="1" :nextPage="18"/>
  </div>

  <div class="col-start-2 col-span-5">

### **Extra Params**

#### This module contains a collection of params that will be sent in all the requests. They can be set via snippet config or programatically.

Sometimes requests to the endpoints require extra data that doesn't fit in the regular **requests parameters**. This module allows this data to be provided: the components in this module propagate the extra params to the rest of the application and stores.

A renderless component that sets the values of the Extra Params is the main component of the module:

`extra-params.vue`
```ts {all|1-4|5-7}
values: {
  type: Object as PropType<Dictionary<unknown>>,
  required: true
}
// Events to update the store
$x.emit('ExtraParamsInitialized', { ...props.values });
$x.emit('ExtraParamsProvided', { ...props.values, ...params.value });
```

</div>
</div>
