#Emmet
## Nummeret indhold

Add $ to the end

  Type abbreviation as 'div>p#foo$*3>a' and type '<C-y>,'.
>
  <div>
      <p id="foo1">
          <a href=""></a>
      </p>
      <p id="foo2">
          <a href=""></a>
      </p>
      <p id="foo3">
          <a href=""></a>
      </p>
  </div>

## Add class to tag

ctrl+y+u

  The begining of tags '<div>' on below
>
  <div>foo</div>
<
  Type '<C-y>u' request 'Enter Abbreviation:'. Then type
>
  .global
<
  This will be expanded like:
>
  <div class="global">foo</div>

## Wrap line

Vælg et element og benyt emmet.

  mike <- ctrl-y-,

  <p>mike</p>

  Write as below.
>
  test1
  test2
  test3
<
  Then do visual select (line wise) and type '<C-y>,'.
  If you request 'Tag:', then type
>
  ul>li*
<
  Result:
>
  <ul>
      <li>test1</li>
      <li>test2</li>
      <li>test3</li>
  </ul>
<
  If you type tag name, for example
>
  blockquote
<
  then you'll see as following:
>
  <blockquote>
      test1
      test2
      test3
  </blockquote>

## Image size

 Type '<C-y>i' on '<img>' tag

## Remove tag

Ctrl + y + k

## Make anchor from URL

  Move cursor to URL
>
  http://www.google.com/
<
  Type '<C-y>a'
>
  <a href="http://www.google.com/">Google</a>

## Nesting Operators

|Operator|Description   |Link ~      |
|--------|--------------|------------|
|>       |Child         |emmet->     |
|+       |Sibling       |emmet-+     |
|^       |Climb-up      |emmet-^     |
|*       |Multiplication|emmet-star  |
|()      |Grouping      |emmet-()    |

## Operators

|Operator|Description                |Link ~  |
|--------|---------------------------|--------|
|.       |Attribute 'class'          |emmet-. |
|#       |Attribute 'id'             |emmet-# |
|[]      |Custom attributes          |emmet-[]|
|$       |Number                     |emmet-$ |
|@       |Number origin and direction|emmet-@ |

## ID and Class

  span.class1          ->   <span class="class1"></span>
  span.class1.class2   ->   <span class="class1 class2"></span>
  div#wrapper          ->   <div id="wrapper"></div>
  div#wrapper.content  ->   <div id="wrapper" class="content"></div>

