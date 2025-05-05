
<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ComponentsIndex :currentItem="1" :nextPage="9"/>
  </div>

  <div class="col-start-2 col-span-5">

### [**Base**](https://docs.empathy.co/develop-empathy-platform/ui-reference/components/base-components/)

Minimal components aimed to be used as building blocks for more complex ones, although they can be imported and implemented by themselves too. They are used across all the modules and are not coupled to any of them.

`base-event-button.vue`

```html {all|2-3|1|all}
<button v-on="$listeners" @click="emitEvents">
  <!-- @slot (Required) Button content with a text, an icon or both -->
  <slot />
</button>
```

#### Example of usage:

`clear-filters.vue`

```html {all|9|6|2-4,5,7}
<BaseEventButton
  v-if="isVisible"
  class="x-clear-filters x-button"
  data-test="clear-filters"
  :disabled="!hasSelectedFilters"
  :events="events"
  :class="cssClasses"
>
  <slot :selectedFilters="selectedFilters">Clear Filters ({{ selectedFilters.length }})</slot>
</BaseEventButton>
```

  </div>
</div>

<!--
Clicks:
* Content of the button
* Action of the button, emitting events
* Example of usage: content = slot, the button will clear the selected filters
* Events that will be triggered
* Other properties normal of a button
-->