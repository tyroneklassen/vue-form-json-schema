### Module (`pkg.module`)

#### Installation

`npm install vue-form-json-schema`

Also include the core components if you don't want to include your own:

`npm install vue-form-json-core-components`

> If you use `webpack` or `rollup` this version will be used automatically.

#### Option 1

Import everything and use globally

```js
// Register and use globally
import VueFormJsonSchema from 'vue-form-json-schema';
import VueFormJsonSchemaCoreComponents from 'vue-form-json-schema-core-components';

Vue.component('vue-form-json-schema', VueFormJsonSchema);
Vue.use(VueFormJsonSchemaCoreComponents);
```

```html
<template>
    <vue-form-json-schema
      :model="model"
      :schema="schema"
      :ui-schema="uiSchema"
      :on-change="onChange"
    >
  </vue-form-json-schema>
</template>
```

#### Option 2

Import and use locally

```html
<script>
// Import vue-form-json-schema
import VueFormJsonSchema from 'vue-form-json-schema';

// Import all core components
import { VueFormJsonSchemaCoreComponents } from 'vue-form-json-schema-core-components';

// Or: Import only some core components
// import { vfjsSelect, vfjsTextarea } from 'vue-form-json-schema-core-components';
// const components = { vfjsSelect, vfjsTextarea };

// Include custom components
import MyCustomComponent from './my-custom-component';
const components = Object.assign({}, VueFormJsonSchemaCoreComponents, {
  MyCustomComponent
});

export default {
  components: {
    'vue-form-json-schema': VueFormJsonSchema
  },
  methods: {
    onChange(value) {
      console.log(value);
    }
  }
  ...
}

</script>
<template>
    <vue-form-json-schema
      :components="components"
      :model="model"
      :schema="schema"
      :ui-schema="uiSchema"
      :on-change="onChange"
    >
  </vue-form-json-schema>
</template>
```

There are two ways this package is distributed. Use whatever suits your requirements.

### UMD (`pkg.main`)

This is the way to go if you want to use the package with AMD/RequireJS or directly in the browser.