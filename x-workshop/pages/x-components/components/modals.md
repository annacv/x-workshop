<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ComponentsIndex :currentItem="3" :nextPage="11"/>
  </div>

  <div class="col-start-2 col-span-5">
  
### [**Modals**](https://docs.empathy.co/develop-empathy-platform/ui-reference/components/base-components/modals/)
Modals are panels with overlays that will overlap the page when opened to show its content. They can listen to events for opening and closing from anywhere within the app.

`base-events-modal.vue`

<div grid="~ cols-2 gap-4">
<div>
```html {all|9|4,6|5|2-3|all}
<BaseModal
  @click:overlay="emitBodyClickEvent"
  @focusin:body="emitBodyClickEvent"
  :animation="animation"
  :open="isOpen"
  v-bind="$attrs"
  ref="baseModalEl" 
>
  <slot />
</BaseModal>
```
</div>

<div>
<div class="description mb-0 mt-0">Props for events to open and close:</div>
```ts {all|1-4|5-7|all}
eventsToOpenModal: {
  type: Array as PropType<XEvent[]>,
  default: (): XEvent[] => ['UserClickedOpenEventsModal']
},
eventsToCloseModal: {
  type: Array as PropType<XEvent[]>,
  default: (): XEvent[] => ['UserClickedCloseEventsModal', 'UserClickedOutOfEventsModal']
}
```
</div>
</div>

<div class="description mb-0">Listening events to open:</div>
```ts {1-8}
props.eventsToOpenModal?.forEach(event =>
  $x.on(event, true).subscribe(({ metadata }) => {
    if (!isOpen.value) {
      openerElement.value = metadata.target;
      isOpen.value = true;
    }
  })
);
```

  </div>
</div>

<!--
 example
Clicks:
* Slot for the content in the modal
* Animation as prop and binding of attributes
* isOpen, controlled by the events
* Emit events for actions of click and focus
* Prop for events to open
* Prop for events to close
* Example Listening events to open
-->