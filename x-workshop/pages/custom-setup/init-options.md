<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="0" :nextPage="54"/>
  </div>
  
  <div class="col-start-2 col-span-5">

  # Snippet Config
It is a global config object for the X Components setup.

This JSON object is passed in the <code>initX</code> object of the <code>window</code> and by default it takes the values from the URL (without using the URL module).
These configurations will affect the whole app.

```js
window.initX = {
  instance: popFromURLParameters('instance') || 'empathy',
  env: getEnv(),
  scope: popFromURLParameters('scope') || 'desktop',
  lang: popFromURLParameters('lang') || 'en',
  device: popFromURLParameters('device') || 'mobile',
  uiLang: popFromURLParameters('uiLang') || lang,
  currency: popFromURLParameters('currency') || 'EUR',
  consent: popFromURLParameters('consent') !== 'false'
  [...]
}
```

<p class="description !mt-0">
  *The whole list of parameters to receive through the <code>SnippetConfig</code> are defined in the X Components library's section 
  <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/x-installer/api/api.types.ts">x-installer.</a>
</p>

</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="0" :nextPage="55"/>
  </div>

  <div class="col-start-2 col-span-5">

### **Adding new parameters**
<p>
  All params defined in the <code>SnippetConfig</code> object are treated as <code>ExtraParams</code>, and, <b>unless it is not specified</b>, they will be attached to all the requests by default. If we want to avoid this, we just have to pass the <b>whole</b> list of the excluded extra parameters to the <code>SnippetConfigExtraParams</code> component when we use it in our <code>App.vue</code> file.
</p>
<p>
  Finally, the new param should be added to the <code>SnippetConfig</code> interface using the <a href="https://github.com/empathyco/x-archetype/blob/main/src/shims-x-components.d.ts"><code>shims-x-components.d.ts</code></a> file.
</p>

``` ts
<SnippetConfigExtraParams :excludedExtraParams="excludedExtraParams" />

const excludedExtraParams = [
  'callbacks',
  'uiLang',
  'consent',
  'documentDirection',
  'currency',
  'filters',
  'isolate',
  'queriesPreview',
  'cart',
  'wishlist'
];

// Extend type
declare module '@empathyco/x-components' {
  export interface SnippetConfig {
    wishlist: Result['id'][];
  }
}
```

</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="0" :nextPage="56"/>
  </div>
  
  <div class="col-start-2 col-span-5">

# [XPluginOptions](https://github.com/empathyco/x/blob/main/packages/x-components/src/plugins/x-plugin.types.ts#L35)
Initializing the `XPlugin` and apply it to the Vue instance.

The [`XPlugin`](https://github.com/empathyco/x/blob/main/packages/x-components/src/plugins/x-plugin.ts) is used to add the basics the X Component need to work, like the adapter and the store, but can be used to override things like the modules stores and the wiring.

On top of these options, there are install options, specified when installing the X in a Vue app and,
aside of the plugin options, adds things like installing extra plugins with access to the snippet config for the initialization.

```ts
    async installExtraPlugins({ app, snippet }) {
      const i18n = await I18n.create({
        locale: snippet.uiLang,
        device: (snippet.device as string) ?? device.deviceName.value,
        fallbackLocale: 'en',
        messages
      });
    
      app.use(i18n);
      app.config.globalProperties.$setLocale = i18n.setLocale.bind(i18n);
      app.config.globalProperties.$setLocaleDevice = i18n.setDevice.bind(i18n);
    
      return {
        i18n: i18n.vueI18n
      };
    }
```

</div>
</div>
