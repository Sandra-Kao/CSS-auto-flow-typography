# CSS-auto-flow-typography

Please see codepan:
https://codepen.io/K-SY/pen/JjWjPBB


``` scss

//COLOR
$color-darkgray:#777;
$color-dark:rgba(0, 0, 0, 0.2);
$color-white:#fff;
$color-white-opacity:#ffffff49;
$color-default:hsla(111, 55%, 64%, 0.8);
$color-default-darken:hsla(160, 64%, 43%, 0.8);
//GRID
$grid-width:114rem;
$gutter-vertical:8rem;
$gutter-horizontal:6rem;
@mixin clearfix {
    &::after {
        content: '';
        display: table;
        clear: both;
    }
}

@mixin baseCol {
    background-color: orangered;
    color: $color-white;
    float: left;
    padding: 2rem;
    &:not(:last-child) {
        margin-right: $gutter-horizontal;
    }
}

.grid-test{
    padding: 4rem;
    background: #ccc;
  
    .row {
        max-width: $grid-width;
        margin: 0 auto;
        &:not(:last-child) {
            margin-bottom: $gutter-vertical;
        }
        @include clearfix;
        .col-1-of-2 {
            width: calc((100% - #{$gutter-horizontal}) / 2);
            @include baseCol;
        }
        .col-1-of-3 {
            width: calc((100% - #{$gutter-horizontal} * 2) / 3);
            @include baseCol;
        }
        .col-2-of-3 {
            width: calc((100% - #{$gutter-horizontal} * 2) / 3 * 2 + #{$gutter-horizontal});
            @include baseCol;
        }
        .col-1-of-4 {
            width: calc((100% - #{$gutter-horizontal} * 3) / 4);
            @include baseCol;
        }
        .col-2-of-4 {
            width: calc((100% - #{$gutter-horizontal}) / 2);
            @include baseCol;
        }
        .col-3-of-4 {
            width: calc((100% - #{$gutter-horizontal} * 3) / 4 * 3 + #{$gutter-horizontal} * 2);
            @include baseCol;
        }
    }
}

```
