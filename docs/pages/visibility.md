---
title: Visibility Classes
description: Visibility classes let you show or hide elements based on screen size or device orientation. You can also use visibility classes to control which elements users see depending on their browsing environment.
sass: scss/components/_visibility.scss
---

## Show by Screen Size

In this example, we use the `.show` visibility classes to show certain strings of text based on the device on which users view a page. If their browser meets the class's conditions, the element will be shown. If not, it will be hidden.

```html_example
<p>You are on a small screen or larger.</p>
<p class="show-for-medium">You are on a medium screen or larger.</p>
<p class="show-for-large">You are on a large screen or larger.</p>
```

These classes automatically hide the element on screen sizes *below* what's specified in the class. So `.show-for-medium` will hide the element on small, and show it on medium and larger.

A separate set of classes allow you to show content *only* on a certain screen size. Just add `-only` to the end of the class.

```html_example
<p class="show-for-small-only">You are <em>definitely</em> on a small screen.</p>
<p class="show-for-medium-only">You are <em>definitely</em> on a medium screen.</p>
<p class="show-for-large-only">You are <em>definitely</em> on a large screen.</p>
```

---

## Hide by Screen Size

This example shows the opposite: It uses the `.hide` visibility classes to state which elements should disappear based on the device's screen size.

```html_example
<p class="hide-for-medium">You are <em>not</em> on a medium screen or larger.</p>
<p class="hide-for-large">You are <em>not</em> on a small screen or larger.</p>
```

Like with `.show`, these classes also have `-only` versions.

```html_example
<p class="hide-for-small-only">You are <em>definitely not</em> on a small screen.</p>
<p class="hide-for-medium-only">You are <em>definitely not</em> on a medium screen.</p>
<p class="hide-for-large-only">You are <em>definitely not</em> on a large screen.</p>
```

---

## Orientation Detection

This straightforward example shows how two strings of text determine whether or not an element is visible in different orientations. This will change on mobile devices when you rotate the device. On desktop, the orientation is almost always reported as landscape.

```html_example
<p class="show-for-landscape">You are in landscape orientation.</p>
<p class="show-for-portrait">You are in portrait orientation.</p>
```

---

## Touch Detection

There are also visibility classes to hide or show content based on whether a device supports touch. We use the Modernizr JavaScript library to detech a touch device.

```html_example
<p class="show-for-touch">You are on a touch-enabled device.</p>
<p class="hide-for-touch">You are not on a touch-enabled device.</p>
```

---

## Accessibility

Adding `display: none` to an element will prevent screen readers from reading it. However, there are techniques to hide content while still making it readable by screen readers.

### Show for Screen Readers Only

To visually hide content, while still allowing assistive technology to read it, add the class show-for-sr.

```html_example
<p class="show-for-sr">This text can only be read by a screen reader.</p>
<p>There's a line of text above this one, you just can't see it.</p>
```

### Hide for Screen Readers Only

To hide text from assistive technology, while still keeping it visible, add the attribute `aria-hidden="true"`. This doesn't affect how the element looks, but screen readers will skip over it.

```html_example
<p aria-hidden="true">This text can be seen, but won't be read by a screen reader.</p>
```

### Creating Skip Links

If your site has a lot of navigation, a screen reader will have to read through the entire navigation to get to your site's content. To remedy this, you can add a *skip link* at the very top of your page, which will send the user farther down the page, past the navigation when clicked on.

Use the class `.show-on-focus` to hide an element, except when it has focus.

```html_example
<p><a class="show-on-focus" href="#mainContent">Skip to Content</a></p>
<div id="mainContent"></div>
```