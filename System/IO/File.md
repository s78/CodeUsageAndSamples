###### System.IO.File
## File

Remove 'ReadOnly' attribute
``` csharp
static void RemoveReadOnlyAttribute(string path)
{
    var attributes = File.GetAttributes(path);

    if (attributes.HasFlag(FileAttributes.ReadOnly))
    {
        File.SetAttributes(path, attributes & ~FileAttributes.ReadOnly);
    }
}
```

Change LastWriteTime ('Modified' in Explorer)
``` csharp
File.SetLastWriteTime(@"c:\text.txt", DateTime.Now.AddDays(-7));
```

'Created' in Explorer
``` csharp
File.GetCreationTime(@"c:\text.txt");
```

> NOTE: This is an expensive call.


'Accessed' in Explorer
``` csharp
File.GetLastAccessTime(@"c:\text.txt");
```
> NOTE: This is an expensive call.
