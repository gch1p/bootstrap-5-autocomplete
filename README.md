# bootstrap-5-autocomplete

This is a rewrite of https://github.com/Honatas/bootstrap-4-autocomplete for bootstrap v5.

### Example

```js
const ac = new Autocomplete(field, {
    data: [{label: "I'm a label", value: 42}],
    maximumItems: 5,
    onSelectItem: ({label, value}) => {
        console.log("user selected:", label, value);
    }
});

// later, when you need to change the dataset

ac.setData([
    {label: 'New York JFK', value: 'JFK'},
    {label: 'Moscow SVO', value: 'SVO'},
]);
```


Or use custom label/value keys:
```js
const ac = new Autocomplete(field, {
    data: [{name: "entry1", text: "The first entry"}, {name: "entry2", text: "The second entry"}],
    label: "name",
    value: "text",
    onSelectItem: ({label, value}) => {
        console.log("user selected:", label, value);
    }
});
```

Or use a simple object instead of an array of objects:
```js
const ac = new Autocomplete(field, {
    data: {entry1: "The first entry", entry2: "The second entry"},
    label: null,
    value: null,
    onSelectItem: ({label, value}) => {
        console.log("user selected:", label, value);
    }
});
```

### Options

Options is a JSON object with the following attributes (in alphabetical order):

**data**:  
The data from where autocomplete will lookup items to show. This data can be a simple object or an array of JSON objects. By default the format for every object in the array is as following, but you can also change the name of the label and value keys (see below):

    {"label": "This is a text", "value": 42}

**dropdownOptions**:  
It's the same options from Bootstrap's Dropdown, documented [here](https://getbootstrap.com/docs/5.0/components/dropdowns/#options).

**dropdownClass**:  
The class of the dropdown-menu element, which is the box that is displayed. Can take a string or an array of strings.

**highlightClass**:  
The class to use when highlighting typed text on items. Only used when highlightTyped is true. Default is text-primary. Can take a string or an array of strings.

**highlightTyped**:  
Whether to highlight (style) typed text on items. Default is true.

**label**:  
The name of the `label` key in your data. The label is what will be shown on each item in the autocomplete list.

**maximumItems**:  
How many items you want to show when the autocomplete is displayed. Default is 5. Set to 0 to display all available items.

**onInput**:  
A callback function to execute on user input.

**onSelectItem**:  
A callback that is fired every time an item is selected. It receives an object in following format:
    
    {label: <label>, value: <value>}

**showValue**:  
If set to true, will display the value of the entry after the label in the dropdown list.

**showValueBeforeLabel**:  
If set to true and `showValue` also set to true, the value will be displayed before the label.

**threshold**:  
The number of characters that need to be typed on the input in order to trigger the autocomplete. Default is 4.

**value**:  
The name of the `value` key in your data.

### License

MIT
