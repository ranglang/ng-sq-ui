# Introduction

## Another UI-kit? How is it different?

You've guessed right, folks - ng-sq-ui IS yet another UI-kit.
The intention behind it is to help Angular developers with their day-to-day work
by trying to offer a solution to the most widespread use-cases they have to handle. Without
being too opinionated on looks and without containing dozen of just "fancy" features. This,
with almost no additional dependencies. How cool is that?

## How do you determine the "most widespread" cases?

When we thought about what an initial version of the UI-kit should have,
we decided to simply ask other developers. We handed out a Google form
to different groups (Facebook groups and colleagues, included) and asked them what they mostly look for
when dealing with UI development. The most voted answer was "form elements",
and right after that - "modal dialogs". And these two types of components
are included in our first version of the kit.

We intend to keep the original idea of the UI-kit. We would like to ask the developers
what they need most for our next release! Don't hesitate to create a [feature request!](https://github.com/SQ-UI/ng-sq-ui/issues)

# Overview

You will find a description of the public API for each component. The components are grouped by modules.
Any properties you can see through code inspection that are left out from this documentation are for internal use and you should not rely on them.

Any types of public interfaces and services are also included here.

# FormElementsModule

The properties / methods listed under every component are specific to the UI-kit. All components support both <a href="https://angular.io/guide/reactive-forms">Model-Driven</a> and <a href="https://angular.io/guide/forms#template-driven-forms">Template-Driven</a> form approaches. The properties / methods exposed by either of the approaches are not documented as component-specific and are assumed to be familiar to the developer.

## sq-input

sq-input represents a thin wrapper over the native HTML `input` element.

### Component properties:

- **`@Input()` name:** `string` - Name of the input. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlId:** `string` - Id of the input. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlLabel:** `string` - Label of the input. Defaults to empty string.

- **`@Input()` controlPlaceholder:** `string` - Placeholder of the input. Defaults to empty string.

- **`@Input()` required:** `boolean` - When using the template-driven approach, this property determines if the input is required. Defaults to false.

- **`@Input()` pattern:** `any` - When using the template-driven approach, this property determines the pattern against which the input value is validated. Defaults to empty string.

- **`@Input()` disabled:** `boolean` - Enables/disables the component.

For template-driven and reactive-driven code examples, please refer to the examples page.

## sq-button

sq-button is thin wrapper over the native HTML `button` element.

### Component properties:

- **`@Input()` name:** `string` - Name of the input. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlId:** `string` - Id of the input. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlLabel:** `string` - Label of the inputcheckbox. Defaults to empty string.

- **`@Input()` controlPlaceholder:** `string` - Placeholder of the input. Defaults to empty string.

- **`@Input()` required:** `boolean` - When using the template-driven approach, this property determines if the input is required. Defaults to false.

- **`@Input()` pattern:** `any` - When using the template-driven approach, this property determines the pattern against which the input value is validated. Defaults to empty string.

- **`@Input()` disabled:** `boolean` - Enables/disables the component.

For template-driven and reactive-driven code examples, please refer to the examples page.

## sq-checkbox

sq-checkbox is a custom implementation using a wrapper over the native HTML `input[type="checkbox"]` element.

### Component properties:

- **`@Input()` name:** `string` - Name of the checkbox. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlId:** `string` - Id of the checkbox. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlLabel:** `string` - Label of the checkbox. Defaults to empty string.

- **`@Input()` required:** `boolean` - When using the template-driven approach, this property determines if the checkbox is required. Defaults to false.

- **`@Input()` isSelected:** `boolean` - Programatically select/deselect the checkbox.

- **`@Output()` isSelectedChange:** `EventEmitter<boolean>` - Callback invoked when the checkbox has been selected/deselected.

- **`@Input()` disabled:** `boolean` - Enables/disables the component.

For template-driven and reactive-driven code examples, please refer to the examples page.

## sq-dropdown

sq-dropdown is a custom implementation of a dropdown which emulates the behavior of the regular HTML `select` tag. Its model returns a **copy** of the selected object.

### Component properties:

- **`@Input()` name:** `string` - Name of the dropdown. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlId:** `string` - Id of the dropdown. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlLabel:** `string` - Label of the dropdown. Defaults to empty string.

- **`@Input()` controlPlaceholder:** `string` - Placeholder of the dropdown. Defaults to empty string.

- **`@Input()` required:** `boolean` - When using the template-driven approach, this property determines if the dropdown is required. Defaults to false.

- **`@Input()` pattern:** `any` - When using the template-driven approach, this property determines the pattern against which the dropdown value is validated. Defaults to empty string.dropdown

- **`@Input()` options:** `LabelValuePair[]` - The options for the dropdown.

- **`@Output()` onSelectItem:** `EventEmitter<LabelValuePair>` - Callback which is invoked when an item has been selected.

- **`@Input()` showOptions:** `boolean` - Programatically show/hide the dropdown list of options.

- **`@Input()` disabled:** `boolean` - Enables/disables the component.

### Component methods:

- **toggleOptionsDropdown():** `void` - Shows/hides the options dropdown.
- **selectOption(option: `LabelValuePair`):** `void` - Selects an option from the list.

For template-driven and reactive-driven code examples, please refer to the examples page.

## sq-form-group

sq-form-group is a visual representation of a group of related form elements. Uses content projection via `ng-content`.

### Component properties:

- **`@Input()` groupLabel:** `string` - Title of the group. Defaults to an empty string.

For code snippets, please refer to the examples page.

## sq-radiobutton

sq-radiobutton is a custom implementation using a wrapper over the native HTML `input[type="radio"]` element.

### Component properties:

- **`@Input()` name:** `string` - Name of the radiobutton. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`. If the radiobutton is part of a radiobutton group, all of the related radiobuttons should have the same value for **name**.

- **`@Input()` controlId:** `string` - Id of the radiobutton. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlLabel:** `string` - Label of the radiobutton. Defaults to empty string.

- **`@Input()` disabled:** `boolean` - Enables/disables the component.

- **`@Input()` radioValue:** `any` - Value of the radiobutton. Defaults to undefined.

- **`@Input()` isSelected:** `boolean` - Programatically select/deselect the radiobutton.

- **`@Output()` isSelectedChange:** `EventEmitter<boolean>` - Callback invoked when the radiobutton has been selected/deselected.

For template-driven and reactive-driven code examples, please refer to the examples page.

## sq-tags-input

sq-tags-input represents a collection of strings populated by the user through an input. Its model returns a **copy** of the string array.

### Component properties:

- **`@Input()` name:** `string` - Name of the tags-input. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlId:** `string` - Id of the tags-input. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlLabel:** `string` - Label of the tags-input. Defaults to empty string.

- **`@Input()` controlPlaceholder:** `string` - Placeholder of the tags-input. Defaults to empty string.

- **`@Input()` required:** `boolean` - When using the template-driven approach, this property determines if the tags-input is required. Defaults to false.

- **`@Input()` pattern:** `any` - When using the template-driven approach, this property determines the pattern against which the tags-input value is validated. Defaults to empty string.

- **`@Input()` disabled:** `boolean` - Enables/disables the component.

For template-driven and reactive-driven code examples, please refer to the examples page.

### Class properties:

- **newTagName:** `string` - The model for the input where the user types in a new tag.

### Component methods:

- **removeTag(tagIndex: `number`):** `void` - Removes a tag by given index.

## sq-typeahead

sq-typeahead represents a collection of items shown to the user after they have input query. Its model returns an array of `SearchResult` items the user has selected from the result list. The returned array consists of **copies** of the chosen items.

### Component properties:

- **`@Input()` name:** `string` - Name of the typeahead. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlId:** `string` - Id of the typeahead. If not provided, a generic name is generated, using the following pattern: `'sq-form-control' + new Date().getTime().toString()`.

- **`@Input()` controlLabel:** `string` - Label of the typeahead. Defaults to empty string.

- **`@Input()` controlPlaceholder:** `string` - Placeholder of the typeahead. Defaults to empty string.

- **`@Input()` required:** `boolean` - When using the template-driven approach, this property determines if the typeahead is required. Defaults to false.

- **`@Input()` pattern:** `any` - When using the template-driven approach, this property determines the pattern against which typeahead value is validated. Defaults to empty string.

- **`@Input()` disabled:** `boolean` - Enables/disables the component.

- **`@Output()` onUserInputEnd:** `EventEmitter<string>` - Callback invoked after the user has typed in a search `query`. Every new `query` is invoked with a delay (by default: 500ms).

- **`@Input()` delay:** `number` - The time in milliseconds to delay the **onUserInputEnd** emitter.

- **`@Input()` searchResults:** `SearchResult[]` - The list of results shown to the user after the last value which **onUserInputEnd** has emitted.

- **`@Input()` multiple:** `boolean` - Allow the user to choose multiple items from the search results list. Defaults to `false`.

### Class properties:

- **queryInputControl:** `FormControl` - The model for the input where the user types in a `query`.
- **isLoading:** `boolean` - A flag to show/hide the loadbar of the typeahead.
- **hideResults:** `boolean` - A flag to show/hide the search results list.

### Component methods:

- **selectSearchResult(result: `SearchResult`):** `void` - Selects a result.
- **removeSearchResult(itemIndex: `number`):** `void` - Remove a search item by given index.

For template-driven and reactive-driven code examples, please refer to the examples page.

# \> ModalModule

## sq-modal

sq-modal is a generic modal window with content projection.

### Component properties:

- **`@Input()` customCssAnimation:** `{ duration: number, entranceAnimation: string, exitAnimation: string }` - A configurational object which determines the CSS animation the modal uses. The duration of the animation is in milliseconds. The default values for each property are:
  `{ duration: 1000, entranceAnimation: 'flipInX', exitAnimation: flipOutX }`.

- **`@Input()` show:** `boolean` - Shows/hides the modal window. Defaults to `false`.

- **`@Output()` showChange:** `EventEmitter<boolean>` - Callback invoked whenever the modal is shown/hidden.

### Component methods:

- **close():** `void` - Closes the modal.

# \> Interfaces

```javascript
interface LabelValuePair {
  label: string;
  value: any;
}
```

```javascript
interface SearchResult {
  displayName: string;
  value: any;
}
```