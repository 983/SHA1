# SHA1

```cpp
void example(){
    const char *text = "quick brown fox jumps over the lazy dog";

    // constructor can be empty or take a const char*
    sha1 s = sha1("The ").
        // can be chained
        // can add single chars
        add(text[0]).
        // number of bytes
        add(&text[1], 4).
        // 0-terminated const char*
        add(&text[5]).
        // finalize must be called, otherwise the hash is not valid
        finalize();

    printf("The SHA1 hash of \"The %s\" is:\n", text);
    // after finalize is called, .hex contains a 0-terminated SHA1 hash
    puts(s.hex);
}
```
