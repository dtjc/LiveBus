# LiveBus
Event bus for Android, base on LiveData

* lifecycle aware, which means no need to unregister
* light weight

# Usage

#### Normal event
```
LiveBus.get(Event.class).observe(this, event -> {
  //TODO
});
//or
LiveBus.get(Event.class).observeForever(event -> {
  //TODO
});
  
LiveBus.sendEvent(new Event());
```

#### Sticky event
```
LiveBus.setEventSticky(Event.class);
LiveBus.sendEvent(new Event());

LiveBus.get(Event.class).observeSticky(this,event -> {
    //TODO
})
//or
LiveBus.get(Event.class).observeForeverSticky(event -> {
    //TODO
});

//if you don't need sticky event any more, remove it
LiveBus.removeStickyEvent(Event.class);
```

<br>

关于本项目的博客地址: https://blog.csdn.net/dnntjc/article/details/86039006

# License
[Apache License 2.0](https://github.com/zhoujucheng/LiveBus/blob/master/LICENSE)
