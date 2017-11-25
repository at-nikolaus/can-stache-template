# can-stache-template
A CanJS can-stache-template WebComponent that is able to Render Stache Templates to it self or Replaces it Self and saves the template to var

## types
if no <template> gets used
- append
- replace-inner (default)
- replace-outer
- replace-outer-varname for backup placed on the document fragment 
  - enables conditional rerendering
if <template> gets used automatic behavier
  - type=template if from
  - template gets attached to template 
  - template and inner content gets replaced by resulting render of template
    - allows to show content under <template> for ssr

## Scope
>Lets u supply the scope for your stache template like
>"document.viewModel" simply requests that var as scope
>this allows direct access you also can easy create a scope like
>document.viewModel = defineMap({})
>you can also use a webcomponent as viewModel via document
import ViewModel from './my-define-map'
const ViewModel = customElements.get('my-app'); // where my-app is a can-element for example
const ViewModel = customElements.get('my-app'); // where my-app is a can-element for example
// Init
const viewModel = new ViewModel; // pass ctor values like so.
> or use <can-import export-as="viewModel">

## Use



```html
<steal></steal>
<can-stache-template from="url?" type="replace-inner">{{message}}</can-stache-template>
<can-stache-template from="url?" type="replace-outer">{{message}}</can-stache-template>
<!-- if from type template is possible to allow auto behavier like that -->
<can-stache-template from="url?" type="template"></can-stache-template>
<can-stache-template>{{message}}</can-stache-template>
```
