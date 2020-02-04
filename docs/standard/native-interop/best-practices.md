---
title: 本机互操作性最佳做法 - .NET
description: 了解与 .NET 中的本机组件交互的最佳做法。
ms.date: 01/18/2019
ms.openlocfilehash: 9486256b815856c0c283f5fe231be3d35d6e8f00
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742746"
---
# <a name="native-interoperability-best-practices"></a>本机互操作性最佳做法

.NET 提供了多种方式来自定义本机互操作性代码。 本文包括 Microsoft .NET 团队为实现本机互操作性而遵循的指南。

## <a name="general-guidance"></a>一般指南

本部分中的指南适用于所有互操作方案。

- ✔️对方法和参数使用与要调用的本机方法相同的命名和大写。
- ✔️考虑对常数值使用相同的命名和大写。
- ✔️使用最接近本机类型的 .NET 类型。 例如，在 C# 中，当本机类型为 `uint` 时使用 `unsigned int`。
- 当所需的行为不同于默认行为时，✔️仅使用 `[In]` 和 `[Out]` 特性。
- ✔️考虑使用 <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> 来池本机数组缓冲区。
- ✔️考虑将您的 P/Invoke 声明包装在与本机库具有相同名称和大小写的类中。
  - 这允许 `[DllImport]` 属性使用 C# `nameof` 语言功能传入本机库的名称，并确保本机库的名称拼写正确。

## <a name="dllimport-attribute-settings"></a>DllImport 属性设置

| 设置 | 默认 | 建议 | 详细信息 |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  保留默认设置  | 将其显式设置为 False 时，失败的 HRESULT 返回值将变为异常（因此，定义中的返回值将变为 Null）。|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | 取决于 API  | 如果 API 使用 GetLastError，并使用 Marshal.GetLastWin32Error 获取值，则将其设置为 True。 如果 API 设置一个表示其有错误的条件，则在进行其他调用之前获取错误以避免无意覆盖该错误。|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | `CharSet.None`，这会退回到 `CharSet.Ansi` 行为  | 定义中存在字符串或字符时显式使用 `CharSet.Unicode` 或 `CharSet.Ansi` | 这将指定字符串的封送行为以及为 `ExactSpelling` 时 `false` 的操作。 请注意，`CharSet.Ansi` 在 Unix 上实际为 UTF8。 大部分时间，Windows 使用 Unicode，而 Unix 使用 UTF8。 有关更多信息，请查看[有关字符集的文档](./charset.md)。 |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | 将其设置为 True 并在运行时获得些许性能优势不会查找后缀为“A”或“W”的备用函数名称，具体取决于 `CharSet` 设置的值（“A”用于 `CharSet.Ansi`，“W”用于 `CharSet.Unicode`）。 |

## <a name="string-parameters"></a>字符串参数

当字符集为 Unicode 或将参数显式标记为 `[MarshalAs(UnmanagedType.LPWSTR)]`_并且_通过值（而不是 `ref` 或 `out`）传递字符串时，字符串将固定并直接由本机代码（而不是复制）使用。

除非明确想要对字符串进行 ANSI 处理，否则请务必将 `[DllImport]` 标记为 `Charset.Unicode`。

❌ 不使用 `[Out] string` 参数。 如果该字符串为暂存的字符串，则通过包含 `[Out]` 属性的值传递的字符串参数可能使运行时变得不稳定。 请在 <xref:System.String.Intern%2A?displayProperty=nameWithType> 的文档中查看有关字符串暂存的详细信息。

❌ 避免 `StringBuilder` 参数。 `StringBuilder` 封送*始终*创建本机缓冲区副本。 因此，该操作的效率可能非常低。 采取调用带有字符串的 Windows API 的典型方案：

1. 创建所需容量的 SB（分配托管容量） **{1}**
2. 调用
   1. 分配本机缓冲区 **{2}**
   2. 如果 `[In]`，则复制内容 _（`StringBuilder` 参数的默认值）_
   3. 如果 `[Out]` **{3}** _（也是 `StringBuilder`的默认值）_ ，则将本机缓冲区复制到新分配的托管数组
3. `ToString()` 分配其他托管数组 **** **

这是 *{4}* 分配，可从本机代码中获取字符串。 可用来限制此操作的最佳方法是在其他调用中重用 `StringBuilder`，但这仍只能保存 1 个分配。 最好从 `ArrayPool` 使用并缓存字符缓冲区 - 然后可以在后续调用中直接获得 `ToString()` 的分配。

`StringBuilder` 的另一个问题是它始终会将返回缓冲区备份复制到第一个 Null。 如果传递的返回字符串未终止或为双 Null 终止字符串，则 P/Invoke 很可能不正确。

如果使用 `StringBuilder`，则最后一个问题是容量确实不会包括隐藏的 Null，该值始终计入互操作。 人们常常会犯这个错误，因为大多数 API 希望缓冲区的大小包括 Null。 这可能会导致产生浪费/不必要的分配。 此外，此问题会阻止运行时通过优化 `StringBuilder` 封送来最大限度地减少副本。

✔️考虑从 `ArrayPool`使用 `char[]`。

有关字符串封送的详细信息，请参阅[字符串的默认封送](../../framework/interop/default-marshaling-for-strings.md)和[自定义字符串封送](customize-parameter-marshaling.md#customizing-string-parameters)。

> __Windows 专用__对于 `[Out]` 字符串，CLR 将默认使用 `CoTaskMemFree`，以便为标记为 `UnmanagedType.BSTR`的字符串自由字符串或 `SysStringFree`。
> **对于包含输出字符串缓冲区的大多数 api：** 传入的字符计数必须包含 null。 如果返回的值小于传入的字符计数，则调用成功，并且该值是不带尾随 Null 的字符数。 否则，该计数是包括 Null 字符的缓冲区的所需大小。
>
> - 传入5，get 4：字符串长度为4个字符，尾随 null。
> - Pass 5，get 6：字符串长度为5个字符，需要6个字符的缓冲区来容纳 null。
> [字符串的 Windows 数据类型](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a>布尔参数和字段

布尔值很容易混淆。 默认情况下，将 .NET `bool` 封送到 Windows `BOOL`，它在其中为包含 4 个字节的值。 但是，C 和 C++ 中的 `_Bool` 和 `bool` 类型是单字节。 这可能会导致难以跟踪 bug，因为一半的返回值将被丢弃，这样可能只会更改结果。 有关将 .NET `bool` 值封送到 C 或 C++ `bool` 类型的详细信息，请参阅有关[自定义布尔字段封送](customize-struct-marshaling.md#customizing-boolean-field-marshaling)的文档。

## <a name="guids"></a>GUID

GUID 可在签名中直接使用。 许多 Windows API 使用 `GUID&` 类型别名（例如，`REFIID`）。 通过引用传递时，可以通过 `ref` 或使用 `[MarshalAs(UnmanagedType.LPStruct)]` 属性传递。

| GUID | 通过引用传递的 GUID |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

对于 `ref` GUID 参数外的任何内容，❌ 不要使用 `[MarshalAs(UnmanagedType.LPStruct)]`。

## <a name="blittable-types"></a>Blittable 类型

Blittable 类型是托管代码和本机代码中具有相同位级别表示形式的类型。 因此，无需将这些类型转换为其他格式即可往返本机代码进行封送，而且由于这样可以提高性能，应首选这些类型。

**：**

- `byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`
- Blittable 类型的非嵌套一维数组（例如，`int[]`）
- 具有实例字段只有 blittable 值类型的固定布局的结构和类
  - 固定的布局需要 `[StructLayout(LayoutKind.Sequential)]` 或 `[StructLayout(LayoutKind.Explicit)]`
  - 默认情况下结构为 `LayoutKind.Sequential`，类为 `LayoutKind.Auto`

**不是 blittable：**

- `bool`

**有时为 blittable：**

- `char`、`string`

通过引用传递 blittable 类型时，这些类型只会被封送处理程序固定，而不会复制到中间缓冲区。 （类在本质上通过引用传递，结构在与 `ref` 或 `out` 结合使用时会通过引用传递。）

如果 `char` 位于一维数组中，或者如果它是包含使用 `[StructLayout]` 的 `CharSet = CharSet.Unicode` 显式标记的类型的一部分，则该类型为 blittable。

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

如果 `string` 不包含在其他类型中，并且作为使用 `[MarshalAs(UnmanagedType.LPWStr)]` 标记的参数传递或 `[DllImport]` 已设置 `CharSet = CharSet.Unicode`，则该类型为 blittable。

可以通过尝试创建固定的 `GCHandle` 来查看类型是否为 blittable。 如果该类型不是字符串或被视为 blittable，则 `GCHandle.Alloc` 将引发 `ArgumentException`。

✔️尽可能使结构成为可复制的。

有关详细信息，请参阅：

- [可直接复制到本机结构中的类型和非直接复制到本机结构中的类型](../../framework/interop/blittable-and-non-blittable-types.md)
- [类型封送](type-marshaling.md)

## <a name="keeping-managed-objects-alive"></a>使托管对象保持活动状态

`GC.KeepAlive()` 将确保对象保持在作用域内，直到采用 KeepAlive 方法。

[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) 允许封送处理程序在 P/Invoke 的持续时间内使对象保持活动状态。 方法签名中可以使用该类型，而不是 `IntPtr`。 `SafeHandle` 可有效地替换此类，应改为使用此类型。

[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) 允许固定托管对象和获取指向该类型的本机指针。 基本模式是：

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

固定不是 `GCHandle` 的默认设置。 其他主要模式是通过本机代码将引用传递到托管对象并返回到托管代码（通常使用回调）。 模式如下：

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

请务必注意需要显式释放 `GCHandle` 以避免内存泄漏。

## <a name="common-windows-data-types"></a>常见的 Windows 数据类型

下面是 Windows API 中常用的数据类型列表以及调用 Windows 代码时要使用的 C# 类型。

以下类型在 32 位和 64 位 Windows 上具有相同大小，而不管其名称为何。

| 宽度 | Windows          | C (Windows)          | C#       | 替代项                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| 32    | `BOOL`           | `int`                | `int`    | `bool`                               |
| 8     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| 8     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| 8     | `CHAR`           | `char`               | `sbyte`  |                                      |
| 8     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| 16    | `SHORT`          | `short`              | `short`  |                                      |
| 16    | `CSHORT`         | `short`              | `short`  |                                      |
| 16    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| 16    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| 16    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| 32    | `INT`            | `int`                | `int`    |                                      |
| 32    | `LONG`           | `long`               | `int`    |                                      |
| 32    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| 32    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| 64    | `QWORD`          | `long long`          | `long`   |                                      |
| 64    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| 64    | `LONGLONG`       | `long long`          | `long`   |                                      |
| 64    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| 64    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| 32    | `HRESULT`        | `long`               | `int`    |                                      |
| 32    | `NTSTATUS`       | `long`               | `int`    |                                      |

以下类型（指针）遵循平台的宽度。 对其使用 `IntPtr`/`UIntPtr`。

| 已签名的指针类型（使用 `IntPtr`） | 未签名的指针类型（使用 `UIntPtr`） |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

Windows `PVOID`，这是一个 C `void*`，可以作为 `IntPtr` 或 `UIntPtr` 进行封送，但在可能的情况下更倾向于 `void*`。

[Windows 数据类型](/windows/desktop/WinProg/windows-data-types)

[数据类型范围](/cpp/cpp/data-type-ranges)

## <a name="structs"></a>结构

托管结构是在堆栈上创建的，在返回方法之前不会将其删除。 按照定义，它们是“固定的”（不会被 GC 移动）。 如果本机代码不会在当前方法末尾之外使用指针，则也可以使用不安全代码块中的地址。

Blittable 结构的性能更好，因为它们可以由封送层直接使用。 尝试使结构为 blittable（例如，避免 `bool`）。 有关详细信息，请参阅 [Blittable 类型](#blittable-types)部分。

如果结构为 blittable，请使用 `sizeof()` 而不是 `Marshal.SizeOf<MyStruct>()`，以获得更好的性能。 如上所述，可以通过尝试创建固定的 `GCHandle` 来验证该类型是否为 blittable。 如果该类型不是字符串或被视为 blittable，则 `GCHandle.Alloc` 将引发 `ArgumentException`。

指向定义中的结构的指针必须通过 `ref` 传递或使用 `unsafe` 和 `*`。

✔️将托管结构尽可能与正式平台文档或标头中使用的形状和名称相匹配。

✔️使用C# `sizeof()` 而不是 `Marshal.SizeOf<MyStruct>()` 来实现直接复制的结构，从而提高性能。

`INT_PTR Reserved1[2]` 等数组必须封送到两个 `IntPtr` 字段（`Reserved1a` 和 `Reserved1b`）。 当本机数组为基元类型时，可以使用 `fixed` 关键字更明确地进行编写。 例如，`SYSTEM_PROCESS_INFORMATION` 在本机标头中类似如下内容：

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

可以在 C# 中编写如下内容：

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

但是，固定的缓冲区有一些问题。 非 blittable 类型的固定缓冲区不会正确封送，因此，就地数组需要扩大到多个单独字段。 此外，在早于 3.0 的 .NET Framework 和 .NET Core 中，如果包含固定缓冲区字段的结构嵌套在非 blittable 结构中，则不会将固定缓冲区字段正确封送到本机代码。
