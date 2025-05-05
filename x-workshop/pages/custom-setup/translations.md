<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="2" :nextPage="59"/>
  </div>
  
  <div class="col-start-2 col-span-5">

  # Translations

  To handle the internalization for the customer's setups, X Archetype is integrated with the [vue-i18n](https://kazupon.github.io/vue-i18n/) package. It is imported as a plugin and [initialized as an extra plugin](https://github.com/empathyco/x-archetype/blob/main/src/x-components/plugin.options.ts). 

### **Setting a default locale**
The default locale, is taken from the `uiLang` value defined in the `SnippetConfig`.

![i18n-default-locale.png](../../../../images/i18n-default-locale.png)

<br/>

### **Adding locales**
Each locale has its [own language file](https://github.com/empathyco/x-archetype/tree/main/src/i18n/messages), so create one for the new language you want to add, and also add it to the [`index.ts`](https://github.com/empathyco/x-archetype/blob/main/src/i18n/messages/index.ts) file to get it lazy loaded.

![i18n-lazy-load.png](../../../../images/i18n-lazy-load.png)


</div>
</div>

---


<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <CustomizeIndex :currentItem="2" :nextPage="60"/>
  </div>
  
  <div class="col-start-2 col-span-5">

### **Adding more messages**
Language files are written in `JSON` format, and each entry is typed under a [`Messages`](https://github.com/empathyco/x-archetype/blob/main/src/i18n/messages.types.ts) interface to avoid forgetting them. So, to add a new message, add it to the `Messages` interface and then to all the `JSON` files.

The language files are **device-featured** so that we can specify different content for desktop or mobile devices. This works by adding a mobile object with the keys intended to be overwritten.

![i18n-per-device.png](../../../../images/i18n-per-device.png)

<p>* The <a href="https://github.com/empathyco/x/tree/main/packages/x-translations">X Translations</a> package aids to the creation of language files by converting from <code>.csv</code> files to the <code>JSON</code> format that the package uses and vice-versa.</p>

</div>
</div>
