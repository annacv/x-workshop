<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="4" :nextPage="63"/>
  </div>
  
  <div class="col-start-2 col-span-5">
  
  # Modules
  ### **Adding a new module**

As seen in the x-modules section, a module will have a store, components, and ist own wiring. It should be declared and registered, and also be added to the [`XModulesTree` interface](https://github.com/empathyco/x-archetype/blob/main/src/shims-x-components.d.ts): 

```ts
export const dummySearchXModule: DummySearchXModule = {
  name: 'dummySearch',
  storeModule: dummySearchXStoreModule,
  storeEmitters: dummySearchEmitters, // * Not all the modules will have emitters, they should be declared as a type requirement, but can be left as an empty object.
  wiring: dummySearchWiring
};

XPlugin.registerXModule(dummySearchXModule);
```
  
The store will include the module's state, getters, mutations and actions, and they should be typed accordingly.

```ts
export const dummySearchXStoreModule: DummySearchXStoreModule = {
  state: () => ({}),
  getters: {},
  mutations: {},
  actions: {}
};
```

</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="4" :nextPage="64"/>
  </div>
  
  <div class="col-start-2 col-span-5">

### **Initializing modules**
As seen before, modules will be effectively registered as soon as the components that are using them are mounted, or, if necessary, this can be done as soon as the application is initialized.

```ts
/**
   * XModules that will be registered on init.
   *
   * - dummySearchXModule is loaded on init to have info available to render
   * stuff before any search is done.
   */
  initialXModules: [dummySearchXModule]
```

<br/>
This should be done carefully, as will increment the loading app size on init. <b>So it is not recommended to do it with all the modules.</b>

</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="4" :nextPage="65"/>
  </div>
  
  <div class="col-start-2 col-span-5">

### **Extending an existing module**
Use case: adding wiring for the `UserModifiedAdd2cart` event.

<div grid="~ cols-3 gap-4">
<div class="col-span-2">
This behavior is defined as a module option:

```ts
  import { namespacedWireCommit, XModuleOptions } from '@empathyco/x-components';
  import { Result } from '@empathyco/x-types';
  
  const updateResultOutOfStock = namespacedWireCommit('search')(
    'updateResult',
    ({ eventPayload: result }: { eventPayload: Result }) => {
      return {
        id: result.id,
        isOutOfStock: result.isOutOfStock
      };
    }
  );

  // Configuration options for installing the search XModule.
  export const searchInstallOptions: XModuleOptions<'search'> = {
    wiring: {
      UserModifiedAdd2cart: {
        updateResultOutOfStock
      }
    }
  };
```
</div>

<div>

And set in the [xModule's install options](https://github.com/empathyco/x-archetype/blob/main/src/x-components/plugin.options.ts):

```ts
 import { searchInstallOptions } from '../x-modules/search.options';

  xModules: {
    search: searchInstallOptions
  }
```
</div>
</div>
</div>
</div>
