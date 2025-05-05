<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="3" :nextPage="61"/>
  </div>
  
  <div class="col-start-2 col-span-5">

# Adapter

### **Adding endpoints**

<div grid="~ cols-2 gap-4">
<div>

A new <a href="https://github.com/empathyco/x/blob/main/packages/x-adapter/README.md#adapters-factory-function-implementation">endpoint adapter</a> should be created:

```ts
export const dummyEndpointAdapter = endpointAdapterFactory({
  endpoint: 'https://dummyjson.com/users/search',
  defaultRequestOptions: {
    id: 'dummy-search'
    // Rest of options
  },
  requestMapper: schemaMapperFactory<OwnAppRequestType, ApiRequestType>({
    q: 'query'
  }),
  responseMapper: schemaMapperFactory<ApiResponseType, OwnAppResponseType>({
    people: ({ users }) =>
    users.map(user => {
      return {
        id: user.id.toString(),
        name: user.firstName
      };
    })
    // Rest of mapping
});
```
</div>

<div>

And added in our adapter to be included:

```ts
import { platformAdapter } from '@empathyco/x-adapter-platform';

export const adapter = platformAdapter;
adapter.dummySearch = dummyEndpointAdapter;
```

<div class="description mt-8">* Additionally it should also be declared as part of the <a href="https://github.com/empathyco/x-archetype/blob/main/src/shims-x-components.d.ts"><code>XComponentsAdapter</code> interface</a> as follows:</div>

```ts
import { EndpointAdapter } from '@empathyco/x-adapter';

declare module '@empathyco/x-types' {
  export interface XComponentsAdapter {
    dummy: EndpointAdapter;
  }
}
```
</div>

</div>
</div>
</div>
---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="3" :nextPage="62"/>
  </div>
  
  <div class="col-start-2 col-span-5">

### **Extending platform adapter endpoints**

An adapter can be extended when we can reuse most of the stuff, but we need to change some other, for example, the endpoint and the response mapper.

```ts
platformAdapter.search = searchEndpointAdapter.extends({
  endpoint: 'https://dummyjson.com/users/search',
  responseMapper: searchResponseMapper
});
```

<br/>

### **Overriding or extending schemas**
X Platform Adapter's schemas are created using a [`MutableSchema`](https://github.com/empathyco/x/blob/main/packages/x-adapter/README.md#using-a-mutable-schema), that means their source and targets can be modified (extended, overriden, replaced) to suit our needs.

<div grid="~ cols-2 gap-4">
<div>

```ts
// Faked mapping for the purpose
resultSchema.$override<DummyResult, Partial<Result>>({
  id: 'product_id',
  name: 'product_name',
  // ... Rest of the fields
});
```
<p class="description !mt-0">* The override strategy enables us to modify some predefined platform API models to our own use case.</p>
</div>

<div>

```ts
export interface DummyResult extends PlatformResult {
  active_price: number;
  app_price: number;
// ... Rest of fields
}
```
<p class=" description !mt-0">* The <code>DummyResult</code> has been declared extending the Empathy's <a href="https://github.com/empathyco/x/blob/main/packages/x-adapter-platform/src/types/models/result.model.ts#L8"><code>PlatformResult</code></a>, so we can keep what is defined in the original model and evolve it to suit our needs.</p>
</div>
</div>

</div>
</div>
