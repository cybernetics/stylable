# Compose CSS Class

Use `-st-compose` to apply CSS class to another CSS class or tag selector.

CSS API:
```css
@namespace "Comp";
.item {
    color: red;
}
.selected {
    -st-compose: item;
    color: green;
}
```

CSS OUTPUT:
```css
.Comp__item {
    color: red;
}
.Comp__selected.Comp__item {
    color: green;
}
```

## Multiple Classes

CSS API:
```css
@namespace "Comp";
.item {
    color: red;
}
.round {
    border-radius: 10px;
}
.selected {
    -st-compose: item, round; /* pass multiple classes */
    color: green;
}
```

CSS OUTPUT:
```css
.Comp__item {
    color: red;
}
.Comp__round {
    border-radius: 10px;
}
.Comp__selected.Comp__item.Comp__round {
    color: green;
}
```