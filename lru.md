采用STL::map做lru链，map::first是一个“虚时间”，表示访问某一个key的虚时间，map::second就是key值，同样另外一个map做cache缓存数据，first为key，second为（value，virtual_time)对，这样当读写一个key的数据时，可以快速定位到该数据，并且可以查找到它的上次访问时间，从而在lru链里面快速定位（树上的查找终究要快）并删除，再更新key的访问时间并插入到lru链中就可以了。

         当cache过大了，比如缓存最多100，那么就可以从lru链的头部开始淘汰了，（因为lru链first值越小，表示访问越久了）。代码贴在下面，欢迎批评指证。与上面文章里的相比，代码简化了给多，这样比较方便阅读，另外考虑到数据多是blob，所以cache中的value就采用stl::string了。

