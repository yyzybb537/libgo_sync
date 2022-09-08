#libgo_sync
一套通用的协程同步组件(mutex/shared_mutex/condition_variable/channel)

一套同时支持多种协程+线程的同步组件, 可以帮助c++协程库完善生态.

接口兼容标准库风格, 可以和标准库提供的一些工具类配合使用.(例如: std::unique_lock)

在某些不得不同时使用多套协程库的特殊场景下, 可以用这种通用组件打破协程库间的壁垒, 让多种协程库合作.

example目录下是libgo集成这个库的例子.

```cpp
    #include "mutex.h"
    #include "shared_mutex.h"
    #include "condition_variable.h"
    #include "channel.h"

    int main()
    {
        libgo::Mutex mtx;                   // 锁
        libgo::SharedMutex smtx;            // 读写锁
        libgo::ConditionVariable cv;        // 条件变量
        libgo::Channel<int> ch;             // golang风格的channel
    }
```
