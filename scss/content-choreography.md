## Cross-browser content choreography with Bourbon mixins

`.col-2` stands in-front of the `.col-1` despite the mark-up.

Especially useful within mobile media queries, as flexbox is almost fully supported by mobile browsers and allows to significantly change the layout for mobile devices. See [Can I Use](http://caniuse.com/#search=flex) for compatibility reference. 

Read more on [content choreography](http://trentwalton.com/2011/07/14/content-choreography) technique.

```html
<div class="summary">
     <div class="col-1">1</div>
     <div class="col-2">2</div>
</div>
```


```scss
@import "bourbon/bourbon";
.summary {

     @include display(flex);
     @include flex-direction(column);

     .col-1 {
          @include order(2);
     }

     .col-2 {
          @include order(1);
     }
}
```

[Source on Codepen](http://codepen.io/anon/pen/EaJJjW)
