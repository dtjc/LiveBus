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
LiveBus.sendStickyEvent(new Event());
LiveBus.sendEvent(new Event()); //this event will be receive after observeSticky()

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
[Apache License 2.0](https://github.com/dtjc/LiveBus/blob/master/LICENSE)
