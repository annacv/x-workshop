<div grid="~ cols-6 gap-4">

  <div class="col-start-1 col-span-1">
  <ContentIndex
        :title="{ text: 'Middleware', anchor: 48 }"
        :currentItem="1"
        :nextPage="51"
        :items="[
        { text: 'adapter', anchor: 48 },
        { text: 'platform adapter', anchor: 50 }
        ]"
    />
  </div>
  
  <div class="col-start-2 col-span-5">

## [X Platform Adapter](https://github.com/empathyco/x/tree/main/packages/x-adapter-platform)

The X Platform Adapter is a pre-built X Adapter with all the adapter endpoints configured to work with Empathy's backend.

```ts
export const platformAdapter: PlatformAdapter = {
  search: searchEndpointAdapter,
  popularSearches: popularSearchesEndpointAdapter,
  recommendations: recommendationsEndpointAdapter,
  nextQueries: nextQueriesEndpointAdapter,
  querySuggestions: querySuggestionsEndpointAdapter,
  relatedTags: relatedTagsEndpointAdapter,
  identifierResults: identifierResultsEndpointAdapter,
  tagging: taggingEndpointAdapter
};
```

The X Adapter allows [overriding](https://github.com/empathyco/x/tree/main/packages/x-adapter-platform#modifying-the-x-platform-adapter) of the mappers and schemas, so the idea of the X Platform Adapter is to have something working with an existing endpoint out of the box and override the configurations as needed.

The alternative to using the X Platform Adapter is to create a new X Adapter form scratch.
  </div>
</div>
