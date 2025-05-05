<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="5" :nextPage="66"/>
  </div>

  <div class="col-start-2 col-span-5">

# Event Handling

### **Listening and reacting to X events**
Depending on the purpose, this can be done by **extending some module's wiring**, as seen before; but also **accessing to the x events' bus**.

##### **Extend a module's wiring**
###
```ts
export const installXOptions: InstallXOptions = {
 //...
  xModules: {
    search: {
      wiring: {
        UserModifiedAdd2cart: { updateResultOutOfStock }
      }
    }
  }
};
```

<div grid="~ cols-2 gap-4" class="mt-4">
<div>

##### **Accessing to the x-bus to react to an event**
###

<div class="description">Use the x-component's <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/composables/use-x-bus.ts"> <code>useXBus()</code> composable</a> to access to its `on` function.</div>

```ts
const xBus = useXBus();
xBus.on('UserClickedAdd2Cart', false).subscribe(setAdd2CartResult);
```
</div>

<div>

##### **Accessing to the x-bus to emit an event**
###

<div class="description">Use the <code>useXBus()</code> composable to access to its `emit` function.</div>

```ts
if (hasStock === null) {
  await xBus.emit('UserModifiedAdd2cart', {
    id: (payload.payload as Result).id,
    isOutOfStock: true
  });
}
```
</div>
</div>




</div>
</div>
---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="5" :nextPage="67"/>
  </div>

  <div class="col-start-2 col-span-5">

### **Callbacks**
Callbacks are functions defined in the client side that will be called when the specified events happen.
Defined in the `SnippetConfig` under the [`callbacks` key](https://github.com/empathyco/x/blob/main/packages/x-components/src/x-installer/api/api.types.ts#L129),
they are used to react to events in the X Components from outside.

The example below shows a common use case: listening to the add to cart related events to update the cart and keep the search layer and customer's website synced.

![snippet-callbacks-example.png](../../../../images/snippet-callbacks-example.png)

</div>
</div>
---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="5" :nextPage="68"/>
  </div>

  <div class="col-start-2 col-span-5">

#### Callbacks are integrated in the X-Archetype's `App.vue` file by importing its dedicated component.

[`snippet-callbacks-vue`](https://github.com/empathyco/x/blob/main/packages/x-components/src/components/snippet-callbacks.vue)
```ts {all|2|4-14|all}
const eventListeners = computed<XEventListeners>(() => {
  const callbacks = snippetConfig?.callbacks;
  return callbacks
    ? map(callbacks, (eventName, callback) => {
        return (payload: unknown, metadata: WireMetadata) => {
          const callbackReturn = callback(payload as never, metadata);
          xBus.emit('SnippetCallbackExecuted', {
            event: eventName,
            callbackReturn,
            payload: payload as never,
            metadata
          });
        };
      })
    : ({} as XEventListeners);
  });
  return { eventListeners };
}
```
<v-click at="0"><div class="description !mb-0">1. Getting the callbacks from the snippet config.</div></v-click>
<v-click at="1"><div class="description !mb-0">2. Iterating and setting up the callback.</div></v-click>

</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="5" :nextPage="69"/>
  </div>

  <div class="col-start-2 col-span-5">

### **Creating a new X Event**
When a new event is needed, it can be created by extending the `XEventsTypes` interface to have it available in the `XBus`. This way we can keep consistency and take advantage of the whole library ecosystem.

##### **Steps to follow:**
###
<h5>· Use the <code>BaseEventButton</code> component. This component is ready to receive an <code>XEvent</code> by <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/components/base-event-button.vue#L27">prop</a> and will use the <code>xBus</code> to emit it.</h5>
<h5> · Extend the <code>XEventsTypes</code> interface using the <a href="https://github.com/empathyco/x-archetype/blob/main/src/shims-x-components.d.ts"><code>shims-x-components.d.ts</code></a> file.</h5>
<br/>

``` ts 
<BaseEventButton
  class="x-button x-button-tight x-h-24 x-w-24 x-text-lead-50 hover:x-button-lead"
  :class="{ 'x-button-lead': isWishListed }"
  :events="wishlistEvents"
>
  <HeartIcon class="x-icon-lg" />
</BaseEventButton>

// XEvent and payload
const wishlistEvents = { UserClickedResultWishlist: props.result }

// Extend type
declare module '@empathyco/x-components' {
  interface XEventsTypes {
    UserClickedResultWishlist: Result;
  }
}
```

</div>
</div>
