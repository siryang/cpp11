
#### 基本锁类型

`std::lock_guard`
`std::unique_lock`

#### 常量
* `std::adopt_lock`
* `std::defer_lock`
* `std::defer_lock`

#### class Mutex

##### BasicLockable
支持`lock()`/`unlock()`两种操作。

    std::mutex
    std::recursive_mutex
    std::timed_mutex
    std::recursive_timed_mutex

##### Lockable
增加了`try_lock()`。

##### TimedLockable
增加了`try_lock_for`/`try_lock_until`两种操作。


#### lock_guard
##### 声明：`template <class Mutex> class lock_guard;`  

    lock_guard的构造函数需要传入Mutex。
    lock_guard的声明周期内，它所管理的对象会一直保持上锁状态。
    程序抛出异常后，能保证Mutex可以被正常unlock。方便处理异常。

##### 构造
* `lock_guard(mutex_type& m)`:构造时对m上锁。
* `lock_guard(mutex_type& m, adopt_lock_t tag)`: m已被上锁，析构时解锁。

#### unique_lock
