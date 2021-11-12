- Start Date: 2021-11-12)
- Target Major Version: 1.0
- Implementation PR: (leave this empty)

# Summary

Provide a function to access, query and configure the content of QPublisher.

# Basic example

````html
<template>
  <div v-for="item in items" :key="item.title">
    {{item.text}}
  </div>
</template>

<script setup>
    import { useQPublisherDSL } from 'vue'
    const options = {}
    const items = useQPublisherDSL(options).fetch()
</script>
````


# Motivation
The idea of this RFC is to  query content of different data types e.g .md or .yaml and 
show the content on the page.
A use case of this is for example simple blog with different sections.

This can improve Developer experience and flexibility.

# Detailed design

### Basic Usage

Creating accessing content:

```js
const items = useQPublisherDSL({}).fetch()
```

### Usage with dsl query
DSL (domain-specific language) query API:

Inspired by: [JOOQ DSL] 

[JOOQ DSL]: https://www.jooq.org/doc/3.9/manual-single-page/#select-statement

Query Api:
```js
var useQPublisherDSL = new function(options) {
    this.query = []
   this.limit = function(limit) {
       ...
       return this
   } 
   this.skip = function() {
        ...
       return this
   }
   this.orderBy = function() {
        ...
       return this
   }
   this.select = function() {
        ...
       return this
   }
   this.fetch = function() {
        return new ExecuteQuery(query)
   }
}
```

Creating accessing and query content:

```html
<template>
    <div v-for="item in items" :key="item.title">
        {{item.title}}: {{item.description}}
    </div>
</template>

<script setup>
const items = useQPublisherDSL({})
    .select('title', 'description')
    .where({draft: false})
    .orderBy(date)
    .limit(6)
    .skip(2)
    .fetch()
</script>
```

# Alternatives
For simplification, we can provide a template which uses internal the query dsl api.

````html
<template>
    <q-publisher
            :select="['title', 'description']"
            :orderBy="date"
            :where="{draft: true}"
            :skip="2"
            :limit="6"
    />
</template>
````


# Adoption strategy

This is a new API and should not affect the existing code.

# Drawbacks

None

# Unresolved questions

None
