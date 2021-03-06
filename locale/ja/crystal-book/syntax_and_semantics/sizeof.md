# sizeof

The `sizeof` expression returns an `Int32` with the size in bytes of a given type. 例をあげます。

```crystal
sizeof(Int32) # => 4
sizeof(Int64) # => 8
```

For [Reference](http://crystal-lang.org/api/Reference.html) types, the size is the same as the size of a pointer:

```crystal
# On a 64 bits machine
sizeof(Pointer(Int32)) # => 8
sizeof(String)         # => 8
```

この理由は、Reference のメモリはヒープに割り当てられ、渡されるのはそこを指すポインタになるためです。
To get the effective size of a class, use [instance_sizeof](instance_sizeof.html).

The argument to sizeof is a [type](type_grammar.html) and is often combined with [typeof](typeof.html):

```crystal
a = 1
sizeof(typeof(a)) # => 4
```
