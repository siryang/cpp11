
##### std::shared_ptr

##### std::weak_ptr

##### std::unique_ptr

##### xxx_pointer_cast
`static_pointer_cast`, `dynamic_pointer_cast`, `const_pointer_cast`
`xxx_cast`的`shared_ptr`版本。

```
class A: B {
};

std::shared_ptr<A> a = std::make_shared<A>();
std::shared_ptr<B> b = a;
std::shared_ptr<A> c = std::static_pointer_cast<A>(b);
```

##### enable_shared_from_this

用`shared_ptr`包装`this`时，this指针会被这个`shared_ptr`会认为自己独占`this`，
当`shared_ptr`被销毁时，也会销毁`this`。
```
class A
{
public:
        shared_ptr<A> Get()
        {
             return shared_ptr<A>(this);
        }
}

shared_ptr<A> pA(new A());
shared_ptr<A> pB = pA->Get();
```

为了避免这个问题，引入了`enable_shared_from_this`
```
class A ：public enable_shared_from_this<A>
{
public:
        shared_ptr<A> Get()
        {
             return shared_from_this();
        }
}
```