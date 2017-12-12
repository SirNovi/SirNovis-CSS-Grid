# SirNovis Grid

A Responsive Grid that's based on inline-block and has:

- high flexibility
- robustness
- a small footprint
- sensible and timesaving defaults
- easy and unlimited nesting
- pushing and pulling
- vertical alignment options
- classes for hiding on certain views
- no float clearing
- no last-item classes

It works practically everywhere and is easy to learn. The only small caveat you need to work around when using inline-block for grids is the white-space issue. There are different ways around it and it's up to you, which way you take. I've been using the HTML-Comment method since years and it's only a small bother and absolutely bullet-proof.
(https://css-tricks.com/fighting-the-space-between-inline-block-elements/ ,  
https://davidwalsh.name/remove-whitespace-inline-block)

This is how it might look like:

```	
<div class="grid-wrap">
  <div class="grid">
     <div class="span-2"></div><!--
  --><div class="span-4"></div><!--		
  --><div class="span-6"></div>
  </div>
</div>
```

When ommiting `.grid-wrap` you'll have a full-width fluid grid and with the wrapper it'll be fluid up to 780px and then use fixed-width layouts to always have some white space on the sides and save quite some time when building sites.

## Views (Media-Queries)

You can control the width of every grid item in each view (media-query). But you don't have to because we're using sensible conventions. Every grid element need's a `.span-` class, for example `.span-7`. This determines the width of the item from 780px upwards -- below 780px it will default to 100% width. If you don't want this to happen you can (in this example) add a `.s-7` to force the element to keep the same relative width below 780px browser-width.

If you set a S-class it will control the S and XS-view and if you set a L-Class it will control the L and XL-view. But you still have the ability to set XS- and XL-classes to set individual element-widths for those views. This gives you the convenience and flexibilty of having 5(!) different views without actually having to set them all individually and without losing control. 
For example: If you still want the element to be full width in the xs-view after you set a s-class you can simply add a `.xs-12` to override it. 

## Nesting

Grids can be nested without any extra steps. Just pack a `.grid` in any `.span-` . They won't break.

## Push- & Pull / Source-Order

Pushing and Pulling works with `.push-` and `.pull-` and there are classes for every view like `.xs-push-` or `.l-pull-` . Because every grid-element is taking full width in the S- and XS-view (if not specified otherwise) you need to use the classes `.s-push-` `.s-pull-` if you want to move or reorder elements in the S View.

## Centering

Add `.center` to `.grid` to center all enclosed grid items.

## Vertical Alignment

You can use the classes .va-middle and .va-bottom on the elements to change the vertical alignment of elements. Or just do it via css yourself.

## Show & Hide

Add `.hide-` + xs/s/m/l/xl to any element to `display:none` it in a specific view. Add `.show-` + xs/s/m/l/xl to any grid element to only show it in a certain view and hide it in all others. You can combine these classes: `.show-xs .show-xl` will hide an element in all Views except the XS- and XL-View and `.hide-xs .hide-xl` will do the opposite.

## Gutter

### Turn off the gutter

Add .no-gutter to `.grid` to remove the gutter. 
(Note that there is no vertical Gap between the rows by default. You need to add that yourself if it's needed.)

Regular gutters are variable. They get larger as the Browser get's larger - from 10 pixel in the xs view up to 30px in xl.