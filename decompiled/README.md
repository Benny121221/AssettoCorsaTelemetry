Most of the methods in AcSdk.dll can be read with a decompiler (I personally use this one: http://devextras.com/decompiler/)

Any files which cannot be I have decompliled by hand and put them in this directory. Some MSIL code is interleaved through it, this is mostly as a reference so I can find lines in the MSIL easier. Some statements like `rethrow` are left as is. There are a few reasons.

    a) I'm lazy
    b) It's more clear

The normal C# user would rethrow like this:
```cs
catch(Exception e){
    throw e;
}
```

However, this removes the callstack, so the compiler does something like this:

```cs
catch{
    throw;
}
```

Most users don't even know that is legal, and what's more the compiler doesn't *really* do this, it has its own opcode. But the compiler's opcode can be produced by the above C#.
