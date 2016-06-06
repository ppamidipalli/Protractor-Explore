# Universal Modal

There are 2 ways that modal can be invoked, one is by adding a class such as `toggle-universal-modal` to the element that will trigger an openModal on click. The other is by making a function call to `publishModal`

In either case, [Javascript](#javascript) is necessary.

## JavaScript function call

```
gap.universalModal.publishModal({
  template: 'modal-example-template',
  modalSize: 'mini',
  actionSheet: 'large',
  title: 'Example Modal Title'
})
```

### Options

#### template
Type: `string`
Default: `modal-iframe-template`

#### actionSheet
Type: `string`
Default: `medium`

Actionsheet is the breakpoint at which modal becomes actionsheet. If modal should never be actionsheet, pass in an empty string to actionSheet. The options available for actionsheet are:

* small
* medium
* large
* x-large

#### closeWhen
type: `function`

Function to be called that will programatically close the open modal.

#### modalSize
Type: `string` or `number`
Default: `standard`

`modalSize` corresponds to the desired width of the modal. Number values will be set as a `max-width`. The modal will fill the screen until it reaches the `max-width`.

**String Options**
* mini
* standard
* max

#### url
Type: `string`
Default: `http://www.gap.com/browse/sizeChart.do?cid=&mdts=true`

`url` is the link to the page or content that you want to populate the iframe.

#### title
Type: `string`
Default: `Example Size Guide`

`title` is the content you want to fill the modal header with.

#### headerBackground
Type: `boolean`
Default: `true`

`headerBackground` setting this option to false allows you to remove the default light gray background in the modal header. 

## Modal open trigger element

#### modalHeight
Type: `string`
Default: `percentage`

`modalHeight` corresponds to the desired height of the modal.

* percentage: the modal's height will be based on a percentage of the window's height;
* auto: the modal's height will fit the modal's content height.
* natural: the modal's height will fit the modal's content height in addition to being aligned at the top and scrollable.

## HTML

In this case, you have the option of adding the options for modal via the javascript as an object literal when binding the addModal function or as a data attribute in the markup.

```
gap.universalModal.addModal('modal-class-name-here'[, options]);
```

### Data Attributes

* data-url
* data-title
* data-modal-size (Determines which size modal to use. See [modalSize](#modalSize) for accepted values.)
* data-modal-height (Determines which modal height to use. See [modalHeight](#modalHeight) for accepted values.)
* data-action-sheet (Determines at which size themodal will take over the screen)

```
<button class="button_secondary toggle-universal-modal" data-title="Access Information" data-url="http://www.gap.com" data-modal-size="mini" data-action-sheet="small">Find It Now</button>
```


## Templates

To add an additional template, include it in the universal-modal.hbs file and give it an id that can be called when initiating the addModal function.

```
<script type="template/handlebars" id="unique-modal-template-name">
  // modal content goes here
</script>
```
