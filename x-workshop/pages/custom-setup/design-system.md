
<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="1" :nextPage="57"/>
  </div>

  <div class="col-start-2 col-span-5">

# [X Design System](https://github.com/empathyco/x/tree/main/packages/x-tailwindcss)

Based in the [Tailwind CSS](https://tailwindcss.com/) framework and exported as a plugin, it provides:

<div grid="~ cols-2 gap-8">
<div>

### [**The XDS Theme**](https://github.com/empathyco/x/blob/main/packages/x-tailwindcss/src/x-tailwind-plugin/theme.ts)
<div class="description">A set of colors, fonts, spacings, and other properties that the base utilities of Tailwind use, as well as the components.</div>

### [**Custom components' styles**](https://github.com/empathyco/x/tree/main/packages/x-tailwindcss/src/x-tailwind-plugin/components)
<div class="description">The custom components are bundles of styles that modify the look and feel of the X Components when applied to those elements. Things like <code>x-button</code>, <code>x-suggestion</code> and <code>x-icon</code> are used throughout the customer's setup.
There are also different variants designed to be combined: variants such as color, size, style (outlined, ghosted...), and focused on user experience (disabled, selected, checked...).</div>

### **XDS Showcase**
<div class="description">It can be run locally to see the whole design system components and variants, thus click-copy each item's classes to implement them in a setup quickly.</div>
</div>

<div>

![XDS-showcase.png](../../../../images/XDS-showcase.png)
</div>

</div>

</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="1" :nextPage="58"/>
  </div>

  <div class="col-start-2 col-span-5">
<div grid="~ cols-2 gap-8">
<div>

### **Changing theme & component's styles**
####
##### The theme is defined in the [plugin-options.js](https://github.com/empathyco/x-archetype/blob/main/src/tailwind/plugin-options.js) file. The XDS automatically generates classes to implement theme colors or other properties that can be extended.

```js
module.exports = {
  theme: {
    colors: {
      newColor: {
        50: '#FFCD4C'
      }
    },
    extend: {
      // The `x-shadow-empathize` class will be available in the project and apply the values defined below.
      boxShadow: {
        'empathize': '0 0 10px 0 rgba(0, 0, 0, 0.1)'
      }
    }
  },
  components: ({ theme }) => ({
    // Classes applied in components can be overriden
    '.picture': {
      aspectRatio: '1/1'
    },
  })
};
```

</div>

<div>

### **Changing config options or adding plugins**
####
##### [`tailwind.config.js`](https://github.com/empathyco/x-archetype/blob/main/tailwind.config.js) file can be found in the root of the project. There you can modify some configuration options, such as the prefix used to apply in CSS generated classes, add custom plugins or [more features that are still not available in the core of framework](https://tailwindcss.com/docs/plugins#official-plugins).

![x-tailwind-config.png](../../../../images/x-tailwind-config.png)
</div>

</div>

</div>
</div>

