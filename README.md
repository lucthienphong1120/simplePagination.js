# SimplePagination.js

A simple jQuery pagination plugin and 3 CSS themes.

[Read Full Documentation](https://flaviusmatis.github.io/simplePagination.js/)

## Quick start

Jquery

```html
<script src="https://code.jquery.com/jquery-3.6.3.min.js"></script>
```

JS

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/simplePagination.js/1.4/jquery.simplePagination.min.js" integrity="sha512-J4OD+6Nca5l8HwpKlxiZZ5iF79e9sgRGSf0GxLsL1W55HHdg48AEiKCXqvQCNtA1NOMOVrw15DXnVuPpBm2mPg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/simplePagination.js/1.4/jquery.simplePagination.js" integrity="sha512-D8ZYpkcpCShIdi/rxpVjyKIo4+cos46+lUaPOn2RXe8Wl5geuxwmFoP+0Aj6wiZghAphh4LNxnPDiW4B802rjQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
```

CSS

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/simplePagination.js/1.4/simplePagination.css" integrity="sha512-emkhkASXU1wKqnSDVZiYpSKjYEPP8RRG2lgIxDFVI4f/twjijBnDItdaRh7j+VRKFs4YzrAcV17JeFqX+3NVig==" crossorigin="anonymous" referrerpolicy="no-referrer" />
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/simplePagination.js/1.4/simplePagination.min.css" integrity="sha512-85KEMf8eFSgiFrs/gGSVg0S6JqrmCtvVcA+s1PTMl/qtqH0ucmhrYrAFXock7iSjCaVcCMUNgCEF+sdQBUp7pA==" crossorigin="anonymous" referrerpolicy="no-referrer" />
```

## How to use

HTMl

```html
<!-- container -->
<div id="pagination-container">
  <div class="page-1">Content here</div>
  <div class="page-1">Content here</div>
  <div class="page-1">Content here</div>
  <div class="page-1">Content here</div>
</div>
<!-- pagination -->
  <div id="pagination"></div>
```

JS

```
var pageContent = $('#pagination-container > div')
var pagination = $('#pagination')

$(function () {
    pagination.pagination({
        pages: 10,
        cssStyle: 'dark-theme',
        onInit: function () {
            var pageNumber = pagination.pagination('getCurrentPage');
            changePage(pageNumber);
        },
        onPageClick(pageNumber, event) {
            changePage(pageNumber);
            
        }
    });
});

function changePage(pageNumber) {
    for (var page of pageContent) {
        $(page).addClass('hidden');
    }
    var currentPage = $('.row.page-' + pageNumber);
    currentPage.removeClass('hidden');
}
```









