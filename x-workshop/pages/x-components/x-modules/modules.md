# [X Modules](https://github.com/empathyco/x/tree/main/packages/x-components/src/x-modules)

#### The X Modules are the core functionalities of the project. They are composed by:
<div class="mt-4">

### **Store**
### **Components**
### **Wiring**

<h5 class="mt-8"> * The <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/wiring/wiring.types.ts#L116"><b>wiring</b></a> is the event system that the X Modules use to communicate between each other & the app.</h5>

<h5 class="mt-4"> * They also communicate with the <b>endpoints</b> by calling an <a href="https://github.com/empathyco/x/blob/main/packages/x-adapter/src/endpoint-adapter/types.ts"><b>endpoint adapter service</b></a>, and set the <b>store</b> values commiting data.</h5>

<h5 class="mt-4"> * An <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/x-modules/x-modules.types.ts#L64"><b>X Module</b></a> is <b>registered</b> when it's going to be used, usually when the components that render its data are mounted. But this behavior can be customized if needed, as it is coupled to the application <a href="https://github.com/empathyco/x/blob/main/packages/x-components/src/plugins/x-plugin.types.ts#L46"><b>init options</b></a>.</h5>
</div>