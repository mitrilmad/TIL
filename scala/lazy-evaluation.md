## Lazy EVALUATION

```
object Stream {
  def cons[T](hd: T, **tl: => Stream[T]**) = new Stream[T] {
    def isEmpty = false
    def head = hd
    def tail = tl
    override def toString = "Stream(" + hd + ", ?)"
  }
  val empty = new Stream[Nothing] {
    def isEmpty = true
    def head = throw new NoSuchElementException("empty.head")
    def tail = throw new NoSuchElementException("empty.tail")
    override def toString = "Stream()"
  }
}
```

elements are only computed when they are needed, where “needed” means that someone calls tail on the stream. (call by name)

call by name : every formal parameter called , then real parameter is computed by
call by value : before calling function, computed subfunction value
