<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ComponentsIndex :currentItem="2" :nextPage="10"/>
  </div>

  <div class="col-start-2 col-span-5">
  
### [**Icons**](https://docs.empathy.co/develop-empathy-platform/ui-reference/components/base-components/icons/)
Are set up as Vue functional components and follow a specific structure to work with the X Tailwind Design System. The package [`x-svg-converter`](https://github.com/empathyco/x/tree/main/packages/x-svg-converter) has a utility to convert from SVG to a X Components-ready Vue component. 

```html {all|1|3|5|10,17}
<template functional>
  <svg
    :class="['x-icon'].concat(data.staticClass, data.class)"
    viewBox="0 0 8 8"
    fill="none"
    xmlns="http://www.w3.org/2000/svg" 
  >
    <path 
      d="M1.5 4H6.24683"
      stroke="currentColor"
      stroke-width="0.4"
      stroke-linecap="round"
      stroke-linejoin="round"
    />
    <path 
      d="M4 6.5L6.5 4L4 1.5"
      stroke="currentColor"
      stroke-width="0.4"
      stroke-linecap="round"
      stroke-linejoin="round"
    />
  </svg>
</template>
```

  </div>
</div>

<!--
Clicks:
* Adds the x-icon class and the classes passed to it
* Specifies the fills to none by default
* Stroke and fills that are specified are set to currentColor
-->