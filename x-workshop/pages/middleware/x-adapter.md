<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ContentIndex
        :title="{ text: 'Middleware', anchor: 48 }"
        :currentItem="0"
        :nextPage="49"
        :items="[
        { text: 'adapter', anchor: 48 },
        { text: 'platform adapter', anchor: 50 }
        ]"
    />
  </div>
  
  <div class="col-start-2 col-span-5">

# [X Adapter](https://github.com/empathyco/x/tree/main/packages/x-adapter)
The adapter is the middleman between the backend endpoints and the X Components.

The X Components modules call a specific **adapter** to request the information and map the response. The modules will request to the endpoint with a format and expect the response with a specific structure, the adapter has the task of convert the request to something that the endpoint understands and to map the response into something the module expects.

Roughly speaking, each adapter consists of 3 parts that would need to be configured. The **endpoint** that will be called, the **request mapper** and the **response mapper**

The endpoint is very straightforward, it's just the URL that will be called.

The request and response mappers are functions called before the request and after the response respectively. They are the ones that will adapt the formats to the needs of each part of the requests, and they do so with **Schemas**.

</div>
</div>

---

<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ContentIndex
        :title="{ text: 'Middleware', anchor: 48 }"
        :currentItem="0"
        :nextPage="50"
        :items="[
        { text: 'adapter', anchor: 48 },
        { text: 'platform adapter', anchor: 50 }
        ]"
    />
  </div>
  
  <div class="col-start-2 col-span-5">

## Schemas

A Schema is a dictionary that indicates what values from an object should be mapped to what field from another. They are used by the mappers to know how to map requests and responses.

Imagine you have a search requests where the endpoint expects the query value to be `keyword` but the X Components are sending it as `query`. You can create a schema for the request mapper that maps the requests as the endpoint expects it:

```ts
const searchRequestSchema = {
  keyword: 'query',
}
```

In the same way you can use a schema to map the response from the endpoint to the format that the X Components expect:

```ts
const searchResponseSchema = {
  images: ({imageStrings}) => imageStrings.split(','),
}
```
  </div>
</div>
