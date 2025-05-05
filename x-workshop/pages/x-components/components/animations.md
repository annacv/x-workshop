
<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ComponentsIndex :currentItem="0" :nextPage="8"/>
  </div>

  <div class="col-start-2 col-span-5">

### [**Animations**](https://docs.empathy.co/develop-empathy-platform/ui-reference/components/base-components/animations/)

Animations are components that just render their slot wrapped by a Vue `transition` and apply the animation styles to it. Some components accept Animation components as props.

```html {all|1|2-3|all}
<transition v-on="$listeners" name="x-animation-" v-bind="$attrs">
  <!-- @slot (Required) Transition content -->
  <slot />
</transition>
```

#### Usage with a dynamic component:

```html {all|1,6|all}
<component :is="animation">
  <div
    v-show="isOpen && hasContent">
  // ...
  </div>
</component>
```

  </div>
</div>

<!--
Clicks:
* The transition setting up the listeners, attributes and the name
* Content that will be wrapped

* Usage with a dynamic component
* Transition trigger
-->