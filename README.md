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
<script src="./simplePagination/jquery.simplePagination.min.js"></script>
```

CSS

```html
<link rel="stylesheet" href="./simplePagination/simplePagination.min.css">
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

```js
$(document).ready(function () {
    var pageContent = $('#pagination-container > div')
    var pagination = $('#pagination')
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
    function changePage(pageNumber) {
        for (var page of pageContent) {
            $(page).addClass('hidden');
        }
        var currentPage = $('.row.page-' + pageNumber);
        currentPage.removeClass('hidden');
    }
});
```









