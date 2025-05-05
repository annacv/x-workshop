
<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ModulesIndex :currentItem="8" :nextPage="33"/>
  </div>

  <div class="col-start-2 col-span-5">

### **Scroll**

#### Handles the state of the scroll, so stores all related data accordingly.

The Scroll Module tracks the id of the **current element** in the scroll's view, and so it can rely the information about its **position** relative to the start or the end of the **scrolling space**, its **direction**, and **restore** the position if necessary.

<p class="!mt-0">The <code>scroll</code> component is the backbone of the module. It uses the <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/components/scroll/base-scroll.vue"><code>base-scroll</code></a> component and it's the one which communicates with the module through <b>events</b>. To use it is enough to <b>wrap</b> the components that you want to apply the scroll to.</p>

`scroll.vue`
```html {all|1,11|2-9|all}
<BaseScroll
  @scroll="emitScroll"
  @scroll:direction-change="emitScrollDirectionChange"
  @scroll:at-start="emitScrollAtStart"
  @scroll:almost-at-end="emitScrollAlmostAtEnd"
  @scroll:at-end="emitScrollAtEnd"
  v-on="$listeners"
  :id="id"
  v-bind="$attrs">
  <slot />
</BaseScroll>
```
<v-click at="0"><div class="description ml-2 mb-0">1. Extends the <code>BaseScroll</code>.</div></v-click>
  <v-click at="1"><div class="description ml-2 mb-0 mt-0">2. Emits every scroll event so the module picks up the information and the `id` for the dictionary in the module slot.</div></v-click>



</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
 <ModulesIndex :currentItem="8" :nextPage="34"/>
  </div>

  <div class="col-start-2 col-span-5">
<p class="!mt-0">Aside from some utility components in the module, the other important ones are the <code>main-scroll</code> and the <code>main-scroll-item</code>. The <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/scroll/components/main-scroll.vue"><code>main-scroll</code></a> is an extended <code>scroll</code> component, it <b>tracks the current component</b> in view, so the scroll position can be restored if the page is loaded from the URL. The <code>main-scroll-item</code> adds the <b>ids and the tracking communication</b> to the components they wrap.</p>

<div grid="~ cols-3 gap-4">
<div class="col-span-2">

<p class="!mt-0"><code>main-scroll-item.vue</code></p>

```ts {all|1-2|4-7|8-15|all}
item: { type: Object as PropType<Identifiable>, required: true },
tag: { type: [String, Object] as PropType<string | typeof Vue>, default: 'div' }

const firstVisibleItemObserver = inject<Ref<ScrollVisibilityObserver> | null>(
  ScrollObserverKey as string,
  null
);
// Mounted does not guarantee that child components are mounted too
onMounted(() => {
  nextTick(() => {
    if (firstVisibleItemObserver) {
      watch(firstVisibleItemObserver, observeItem, { immediate: true });
    }
  });
});
```

<v-click at="0"><div class="description ml-2 mb-0 mt-0">1. Props: item with an <code>id</code> (usually the result), and the html <code>tag</code> for the component that will be wrapping the slot.</div></v-click>
  <v-click at="1"><div class="description ml-2 mb-0 mt-0">2. The observable coming from an scroll element. (<code>main-scroll</code>).</div></v-click>
<v-click at="2"><div class="description ml-2 mb-0 mt-0">3. Sets the observable that is tracking as the visible element in the scroll.</div></v-click>
</div>

<div>

<h4 class="mb-3 !mt-0">Usage:</h4>

```html {all}
<MainScroll>
  <Scroll id="main-scroll">
    <ResultsList>
      <MainScrollItem
        :item="result"
        tag="article"
      >
        <Result :item="result" />
      </MainScrollItem>
    </ResultsList>
  </Scroll>
</MainScroll>
```
</div>
</div>


</div>
</div>

