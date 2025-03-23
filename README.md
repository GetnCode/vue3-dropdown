# Vue 3 Dropdown Component

A flexible and customizable dropdown component for Vue 3, utilizing Floating UI for precise positioning.

## Features

- **Customizable:** Offers a wide range of props for styling and behavior.
- **Flexible:** Can be triggered by any element via slots.
- **Accurate Positioning:** Uses Floating UI to ensure the dropdown is always positioned correctly, even in complex layouts.
- **Transitions:** Includes smooth slide-in/slide-out animations.

## Installation

```bash
npm install @floating-ui/dom
# or
yarn add @floating-ui/dom
```

Copy the `dropdown.vue` component into your project.

## Usage

Here's a basic example of how to use the dropdown component:

```vue
<template>
  <Dropdown>
    <template #trigger="{ toggle }">
      <button @click="toggle">Open Dropdown</button>
    </template>
    <div class="dropdown-item">Item 1</div>
    <div class="dropdown-item">Item 2</div>
    <div class="dropdown-item">Item 3</div>
  </Dropdown>
</template>

<script>
import Dropdown from "./components/Dropdown.vue";

export default {
  components: {
    Dropdown,
  },
};
</script>
```

This example uses a button to trigger the dropdown. The content of the dropdown is defined using the default slot.

### Triggering Element

The component uses a scoped slot named `trigger` to define the element that triggers the dropdown. The slot provides a `toggle` function that you can use to open and close the dropdown.

```vue
<Dropdown>
  <template #trigger="{ toggle }">
    <button @click="toggle">Open Dropdown</button>
  </template>
  <!-- Dropdown content -->
</Dropdown>
```

### Dropdown Content

The content of the dropdown is defined using the default slot. You can put any HTML content inside the dropdown. The slot also provides a `toggle` function that you can use to close the dropdown from within the content.

```vue
<Dropdown>
  <template #trigger="{ toggle }">
    <button @click="toggle">Open Dropdown</button>
  </template>
  <div class="dropdown-item" @click="toggle">Item 1</div>
  <div class="dropdown-item" @click="toggle">Item 2</div>
  <div class="dropdown-item" @click="toggle">Item 3</div>
</Dropdown>
```

## Props

| Prop                | Type                        | Default       | Description                                                                                           |
| ------------------- | --------------------------- | ------------- | ----------------------------------------------------------------------------------------------------- |
| `variant`           | `String`                    | `"secondary"` | The color variant of the button.                                                                      |
| `size`              | `String`                    | `"md"`        | The size of the button.                                                                               |
| `outline`           | `Boolean`                   | `false`       | Whether the button is outlined.                                                                       |
| `label`             | `String`                    | `"Dropdown"`  | The label of the button.                                                                              |
| `placement`         | `String`                    | `"bottom"`    | The placement of the dropdown relative to the button. Accepts any of Floating UI's placement options. |
| `alignment`         | `String`                    | `"center"`    | The alignment of the dropdown. Accepts `"left"`, `"center"`, or `"right"`.                            |
| `dropdownMenuClass` | `String`                    | `""`          | A custom CSS class to apply to the dropdown menu.                                                     |
| `btnStyle`          | `Object \| String`          | `undefined`   | Custom CSS styles to apply to the button.                                                             |
| `btnClass`          | `String \| Object \| Array` | `""`          | Custom CSS classes to apply to the button.                                                            |
| `ghosted`           | `Boolean`                   | `false`       | Whether the button is ghosted.                                                                        |
| `flat`              | `Boolean`                   | `false`       | Whether the button is flat.                                                                           |
| `buttonId`          | `String`                    | `""`          | The ID of the button.                                                                                 |
| `tooltipMessage`    | `String`                    | `""`          | A tooltip message to display on hover.                                                                |
| `offset`            | `Number`                    | `26`          | The offset of the dropdown from the button, in pixels.                                                |

## Styling

The dropdown component is styled using CSS. You can customize the styling by overriding the default CSS classes or by providing your own CSS classes via the `dropdownMenuClass` and `btnClass` props.

## Dependencies

- [Floating UI](https://floating-ui.com/): for positioning the dropdown menu.

## License

MIT
