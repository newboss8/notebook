# [jQuery pagination plugin (bootstrap powered)](http://esimakin.github.io/twbs-pagination/)

### Basic usage ###

Plugin requires jQuery (required - 1.7.0 or higher).

You can use Bootstrap CSS styles and markup (or use your own).

The following code shows call the function on `<ul>` tag (it can be also `<div>` tag).

```javascript
$('#pagination-demo').twbsPagination({
  totalPages: 35,
  visiblePages: 7,
  onPageClick: function (event, page) {
    $('#page-content').text('Page ' + page);
  }
});
```

## Contributing
For development use grunt build to make minified file.
To use grunt install packages by using: npm install

## Demo and Docs
For more information see [docs on github pages](http://esimakin.github.io/twbs-pagination/)



$('#digg').twbsPagination({
			        totalPages: 50,
			        startPage: 1,
			        visiblePages: 5,
			        initiateStartPageClick: true,
			        href: false,
			        hrefVariable: '{{number}}',
			        first: '第一页',
			        prev: '上一页',
			        next: '下一页',
			        last: '最后页',
			        loop: false,
			        onPageClick: null,
			        paginationClass: 'pagination',
			        nextClass: 'next',
			        prevClass: 'prev',
			        lastClass: 'last',
			        firstClass: 'first',
			        pageClass: 'page',
			        activeClass: 'active',
			        disabledClass: 'disabled',
       				onPageClick :  function(event, page){	//回调 ajax像page页面请求数据
                                    //alert(page);
                                    NProgress.done();
                                    NProgress.start();
                                    $.post('http://localhost/ftp/index.php/index/test/test2', {'page': page}, function(data, textStatus, xhr) {
                                    	//alert(textStatus);
                                    	if (data) {
                                    		NProgress.done();
                                    		$('#pagecontent').html(data);
                                    	}
                                    });
                                }
    		});