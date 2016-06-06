# Page Scroll

To automatically scroll a page to the content on load (for small and medium breakpoints), simply put a class of `js-scroll-past-header-sm-md` somewhere on the page. On load, it will scroll to the last instance of `.pageHeader, #bodyContainer, .page-content` that it finds on the page.

## Category & Search Pages

To automatically scroll to a product or section on these pages, add the `scrollTo` URL parameter:

 `&scrollTo=product-{product number}`

 i.e. `http://www.gapfactory.com/browse/category.do?cid=1049456&scrollTo=product-541435211`

or

 `&scrollTo={headingname}` (replace special characters with '')

 i.e. `http://www.gapfactory.com/browse/category.do?cid=1049456&scrollTo=teestops`
