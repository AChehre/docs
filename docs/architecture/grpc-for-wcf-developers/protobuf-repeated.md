---
title: Repeated fields for lists and arrays - gRPC for WCF developers
description: Understand how Protobuf handles collections and how they relate to .NET collections.
ms.date: 09/09/2019
---

# Repeated fields for lists and arrays

You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword. The following example shows how to create a list:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.

The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format. It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>. So you can use LINQ queries or convert it to an array or a list easily.

>[!div class="step-by-step"]
>[Previous](protobuf-nested-types.md)
>[Next](protobuf-reserved.md)
