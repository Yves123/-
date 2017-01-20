# Chai.js

> BDD

- expect和should是BDD风格的，二者使用相同的链式语言来组织断言，但不同在于他们初始化断言的方式：
  expect使用构造函数来创建断言对象实例，而should通过为Object.prototype新增方法来实现断言（所以should不支持IE）；
  expect直接指向chai.expect，而should则是chai.should()。

~~~
  - 语言库
    
    to be been is that which and has have with at of same

    var chai = require('chai') ,
    expect = chai.expect ,
    should = chai.should()
~~~

## .not

   - 对断言取反

~~~
   expect(foo).to.not.equal('bar')
   expect(goodFn).to.not.throw(Error)
   expect({foo:'baz'}).to.have.property('foo')
         .and.not.equal('bar')
~~~

## deep

   -设置deep标记，然后使用equal和property断言。该标记可以让
    其后的断言不是比较对象本身，而是递归比较对象的键值对

~~~
   expect(foo).to.deep.equal({bar:'baz'})
   expect({foo:{bar:{baz:'quux'}}})
         .to.have.deep.property('foo.bar.baz','quux')
~~~