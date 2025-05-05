---
title: Overlay vs X Components
---

# Overlay vs X Components

<div grid="~ cols-6 gap-2">
  <div class="col-span-5">

### **Mantainability**
<p class="description">Overlay was created as a stop-gap and with little time for planning how to scale the application.</p>

### **Scalability**
<p class="description">X Components had more time to plan and design the architecture, so we were able to have scalability in mind this time around.</p>

### **Modular**
<p class="description">We moved from config files to a more developer-friendly approach of modular components.</p>

### **Lightweight**
<p class="description">The main friction point with Overlay and previous frontend solutions was the bundle size and the initial loading times of the pages. Thanks to being modular, X Components allows customization of which components are used and added to the bundle.</p>

### **Tree Shaking**
<p class="description">Better tools allow X Components to remove from the bundle code that is not used in the setups, saving more loading time.</p>

### **Faster development**
<p class="description">With a new Design System, better testing and a more developer-friendly project, the setups for the clients are done much quicker.</p>
</div>



<div v-click="1">

### **Tech Stack**
<v-clicks :every="4">

#### Development
##### · Typescript
##### · Vue 3
##### · Tailwind

#### Bundling
##### · Rollup
##### · Vite
##### · Webpack

#### Testing
##### · Jest
##### · Cypress
  
</v-clicks>

  </div>
</div>

<style>
h4 {
  margin: 16px 0 0;
  color: #878787;
}
.description {
  color: #4A4A4A;
  font-size: 12px;
  margin: 8px 0 16px;
  line-height: 1.8;
}
</style>
