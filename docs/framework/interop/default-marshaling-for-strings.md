---
title: "字符串的默认封送处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d219ad68d125e2b90197fc7703ccfc0a1c857d2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="ef4d4-102">字符串的默认封送处理</span><span class="sxs-lookup"><span data-stu-id="ef4d4-102">Default Marshaling for Strings</span></span>
<span data-ttu-id="ef4d4-103"><xref:System.String?displayProperty=nameWithType> 和 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 类均具有类似的封送处理行为。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>  
  
 <span data-ttu-id="ef4d4-104">字符串以 COM 样式 `BSTR` 类型或以 null 结尾的字符串（以 null 字符结尾的字符数组）进行封送。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="ef4d4-105">字符串中的字符可以采用 Unicode（Windows 系统上的默认值）或 ANSI 进行封送。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>  
  
 <span data-ttu-id="ef4d4-106">本主题提供字符串类型封送处理的以下信息：</span><span class="sxs-lookup"><span data-stu-id="ef4d4-106">This topic provides the following information on marshaling string types:</span></span>  
  
-   [<span data-ttu-id="ef4d4-107">在接口中使用的字符串</span><span class="sxs-lookup"><span data-stu-id="ef4d4-107">Strings Used in Interfaces</span></span>](#cpcondefaultmarshalingforstringsanchor1)  
  
-   [<span data-ttu-id="ef4d4-108">在平台调用中使用的字符串</span><span class="sxs-lookup"><span data-stu-id="ef4d4-108">Strings Used in Platform Invoke</span></span>](#cpcondefaultmarshalingforstringsanchor5)  
  
-   [<span data-ttu-id="ef4d4-109">在结构中使用的字符串</span><span class="sxs-lookup"><span data-stu-id="ef4d4-109">Strings Used in Structures</span></span>](#cpcondefaultmarshalingforstringsanchor2)  
  
-   [<span data-ttu-id="ef4d4-110">定长字符串缓冲区</span><span class="sxs-lookup"><span data-stu-id="ef4d4-110">Fixed-Length String Buffers</span></span>](#cpcondefaultmarshalingforstringsanchor3)  
  
<a name="cpcondefaultmarshalingforstringsanchor1"></a>   
## <a name="strings-used-in-interfaces"></a><span data-ttu-id="ef4d4-111">在接口中使用的字符串</span><span class="sxs-lookup"><span data-stu-id="ef4d4-111">Strings Used in Interfaces</span></span>  
 <span data-ttu-id="ef4d4-112">下表显示以非托管代码的方法参数封送字符串数据类型时的封送处理选项。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-112">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="ef4d4-113"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性向 COM 接口的封送字符串提供若干个 <xref:System.Runtime.InteropServices.UnmanagedType> 枚举值。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-113">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>  
  
|<span data-ttu-id="ef4d4-114">枚举类型</span><span class="sxs-lookup"><span data-stu-id="ef4d4-114">Enumeration type</span></span>|<span data-ttu-id="ef4d4-115">非托管格式说明</span><span class="sxs-lookup"><span data-stu-id="ef4d4-115">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="ef4d4-116">`UnmanagedType.BStr`（默认值）</span><span class="sxs-lookup"><span data-stu-id="ef4d4-116">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="ef4d4-117">具有预先固定长度和 Unicode 字符的 COM 样式 `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-117">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="ef4d4-118">指向以 null 终止的 ANSI 字符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-118">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="ef4d4-119">指向以 null 终止的 Unicode 字符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-119">A pointer to a null-terminated array of Unicode characters.</span></span>|  
  
 <span data-ttu-id="ef4d4-120">此表适用于字符串。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-120">This table applies to strings.</span></span> <span data-ttu-id="ef4d4-121">但是，对于 <xref:System.Text.StringBuilder>，仅允许 `UnmanagedType.LPStr` 和 `UnmanagedType.LPWStr` 两个选项。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-121">However, for <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>  
  
 <span data-ttu-id="ef4d4-122">以下示例演示在 `IStringWorker` 接口中声明的字符串。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-122">The following example shows strings declared in the `IStringWorker` interface.</span></span>  
  
```cpp  
public interface IStringWorker {  
void PassString1(String s);  
void PassString2([MarshalAs(UnmanagedType.BStr)]String s);  
void PassString3([MarshalAs(UnmanagedType.LPStr)]String s);  
void PassString4([MarshalAs(UnmanagedType.LPWStr)]String s);  
void PassStringRef1(ref String s);  
void PassStringRef2([MarshalAs(UnmanagedType.BStr)]ref String s);  
void PassStringRef3([MarshalAs(UnmanagedType.LPStr)]ref String s);  
void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)]ref String s);  
);  
```  
  
 <span data-ttu-id="ef4d4-123">以下示例演示类型库中描述的相应接口。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-123">The following example shows the corresponding interface described in a type library.</span></span>  
  
```  
[…]  
interface IStringWorker : IDispatch {  
HRESULT PassString1([in] BSTR s);  
HRESULT PassString2([in] BSTR s);  
HRESULT PassString3([in] LPStr s);  
HRESULT PassString4([in] LPWStr s);  
HRESULT PassStringRef1([in, out] BSTR *s);  
HRESULT PassStringRef2([in, out] BSTR *s);  
HRESULT PassStringRef3([in, out] LPStr *s);  
HRESULT PassStringRef4([in, out] LPWStr *s);  
);  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor5"></a>   
## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="ef4d4-124">在平台调用中使用的字符串</span><span class="sxs-lookup"><span data-stu-id="ef4d4-124">Strings Used in Platform Invoke</span></span>  
 <span data-ttu-id="ef4d4-125">平台调用复制字符串参数，将其从.NET Framework 格式 (Unicode) 转换为平台非托管格式。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-125">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="ef4d4-126">当调用返回时，字符串固定不变，且不会从非托管内存复制回托管内存。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-126">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>  
  
 <span data-ttu-id="ef4d4-127">下表列出以平台调用的方法参数封送字符串时的封送处理选项。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-127">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="ef4d4-128"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性向封送字符串提供若干个 <xref:System.Runtime.InteropServices.UnmanagedType> 枚举值。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-128">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>  
  
|<span data-ttu-id="ef4d4-129">枚举类型</span><span class="sxs-lookup"><span data-stu-id="ef4d4-129">Enumeration type</span></span>|<span data-ttu-id="ef4d4-130">非托管格式说明</span><span class="sxs-lookup"><span data-stu-id="ef4d4-130">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="ef4d4-131">具有预先固定长度和 ANSI 字符的 COM 样式 `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-131">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|  
|`UnmanagedType.BStr`|<span data-ttu-id="ef4d4-132">具有预先固定长度和 Unicode 字符的 COM 样式 `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-132">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="ef4d4-133">指向以 null 终止的 ANSI 字符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-133">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="ef4d4-134">指向以 null 终止的平台相关字符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-134">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="ef4d4-135">指向以 null 终止的 Unicode 字符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-135">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.TBStr`|<span data-ttu-id="ef4d4-136">具有预先固定长度和平台相关字符的 COM 样式 `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-136">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|  
|`VBByRefStr`|<span data-ttu-id="ef4d4-137">使 Visual Basic .NET 能够在非托管代码中更改字符串，并在托管代码中反映出结果的值。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-137">A value that enables Visual Basic .NET to change a string in unmanaged code, and have the results reflected in managed code.</span></span> <span data-ttu-id="ef4d4-138">此值仅支持用于平台调用。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-138">This value is supported only for platform invoke.</span></span> <span data-ttu-id="ef4d4-139">这是 `ByVal` 字符串在 Visual Basic 中的默认值。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-139">This is default value in Visual Basic for `ByVal` strings.</span></span>|  
  
 <span data-ttu-id="ef4d4-140">此表适用于字符串。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-140">This table applies to strings.</span></span> <span data-ttu-id="ef4d4-141">但是，对于 <xref:System.Text.StringBuilder>，仅允许 `LPStr`、`LPTStr` 和 `LPWStr` 三个选项。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-141">However, for <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>  
  
 <span data-ttu-id="ef4d4-142">以下类型定义演示 `MarshalAsAttribute` 平台调用的正确用法。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-142">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>  
  
```vb  
Class StringLibAPI      
Public Declare Auto Sub PassLPStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPStr)> s As String)      
Public Declare Auto Sub PassLPWStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPWStr)> s As String)      
Public Declare Auto Sub PassLPTStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPTStr)> s As String)      
Public Declare Auto Sub PassBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.BStr)> s As String)      
Public Declare Auto Sub PassAnsiBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.AnsiBStr)> s As String)      
Public Declare Auto Sub PassTBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.TBStr)> s As String)  
End Class  
```  
  
```csharp  
class StringLibAPI {  
[DllImport("StringLib.Dll")]  
public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPWStr([MarshalAs(UnmanagedType.LPWStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPTStr([MarshalAs(UnmanagedType.LPTStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)]  
String s);  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor2"></a>   
## <a name="strings-used-in-structures"></a><span data-ttu-id="ef4d4-143">在结构中使用的字符串</span><span class="sxs-lookup"><span data-stu-id="ef4d4-143">Strings Used in Structures</span></span>  
 <span data-ttu-id="ef4d4-144">字符串是结构的有效成员，但是 <xref:System.Text.StringBuilder> 缓冲区在结构中无效。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-144">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="ef4d4-145">下表显示以字段封送字符串数据类型时的封送处理选项。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-145">The following table shows the marshaling options for the string data type when the type is marshaled as a field.</span></span> <span data-ttu-id="ef4d4-146"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性向字段的封送字符串提供若干个 <xref:System.Runtime.InteropServices.UnmanagedType> 枚举值。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-146">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>  
  
|<span data-ttu-id="ef4d4-147">枚举类型</span><span class="sxs-lookup"><span data-stu-id="ef4d4-147">Enumeration type</span></span>|<span data-ttu-id="ef4d4-148">非托管格式说明</span><span class="sxs-lookup"><span data-stu-id="ef4d4-148">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`|<span data-ttu-id="ef4d4-149">具有预先固定长度和 Unicode 字符的 COM 样式 `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-149">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="ef4d4-150">指向以 null 终止的 ANSI 字符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-150">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="ef4d4-151">指向以 null 终止的平台相关字符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-151">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="ef4d4-152">指向以 null 终止的 Unicode 字符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-152">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.ByValTStr`|<span data-ttu-id="ef4d4-153">定长字符数组；数组的类型由包含结构的字符集确定。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-153">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|  
  
 <span data-ttu-id="ef4d4-154">`ByValTStr` 类型用于结构中出现的内联定长字符数组。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-154">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="ef4d4-155">其他类型适用于包含指向字符串的指针的结构中包含的字符串引用。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-155">Other types apply to string references contained within structures that contain pointers to strings.</span></span>  
  
 <span data-ttu-id="ef4d4-156">应用于包含结构的 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 特性的 `CharSet` 参数确定结构中字符串的字符格式。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-156">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="ef4d4-157">以下示例结构包含字符串引用和内联字符串，以及 ANSI、Unicode 和平台相关字符。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-157">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span>  
  
### <a name="type-library-representation"></a><span data-ttu-id="ef4d4-158">类型库表示形式</span><span class="sxs-lookup"><span data-stu-id="ef4d4-158">Type Library Representation</span></span>  
  
```  
struct StringInfoA {  
   char *    f1;  
   char      f2[256];  
};  
struct StringInfoW {  
   WCHAR *   f1;  
   WCHAR     f2[256];  
   BSTR      f3;  
};  
struct StringInfoT {  
   TCHAR *   f1;  
   TCHAR     f2[256];  
};  
```  
  
 <span data-ttu-id="ef4d4-159">以下代码示例演示如何使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性以不同的格式定义相同的结构。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-159">The following code example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to define the same structure in different formats.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _  
Structure StringInfoA  
<MarshalAs(UnmanagedType.LPStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _  
Structure StringInfoW  
<MarshalAs(UnmanagedType.LPWStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
<MarshalAs(UnmanagedType.BStr)> Public f3 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _  
Structure StringInfoT  
<MarshalAs(UnmanagedType.LPTStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Ansi)]  
struct StringInfoA {  
   [MarshalAs(UnmanagedType.LPStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Unicode)]  
struct StringInfoW {  
   [MarshalAs(UnmanagedType.LPWStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
   [MarshalAs(UnmanagedType.BStr)] public String f3;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Auto)]  
struct StringInfoT {  
   [MarshalAs(UnmanagedType.LPTStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor3"></a>   
## <a name="fixed-length-string-buffers"></a><span data-ttu-id="ef4d4-160">定长字符串缓冲区</span><span class="sxs-lookup"><span data-stu-id="ef4d4-160">Fixed-Length String Buffers</span></span>  
 <span data-ttu-id="ef4d4-161">在某些情况下，必须将定长字符缓冲区传递到要操作的非托管代码中。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-161">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="ef4d4-162">在这种情况下，只传递字符串将不起作用，因为被调用方不能修改所传递缓冲区的内容。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-162">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="ef4d4-163">即使通过引用传递字符串，仍无法将缓冲区初始化为给定大小。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-163">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>  
  
 <span data-ttu-id="ef4d4-164">解决方法是将 <xref:System.Text.StringBuilder> 缓冲区作为参数而非字符串进行传递。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-164">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a string.</span></span> <span data-ttu-id="ef4d4-165">被调用方可以取消引用和修改 `StringBuilder`，前提是不超过 `StringBuilder` 的容量。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-165">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="ef4d4-166">还可以初始化为固定长度。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-166">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="ef4d4-167">例如，如果将 `StringBuilder` 缓冲区初始化为 `N` 容量，则封送处理程序提供大小为 (`N`+ 1) 个字符的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-167">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="ef4d4-168">+1 解释了非托管字符串具有 null 终止符而帐户 `StringBuilder` 却不具有这一事实。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-168">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>  
  
 <span data-ttu-id="ef4d4-169">例如，Microsoft Win32 API `GetWindowText` 函数（在 Windows.h 中定义）是一个定长字符缓冲区，必须传递到要操作的非托管代码中。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-169">For example, the Microsoft Win32 API `GetWindowText` function (defined in Windows.h) is a fixed-length character buffer that must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="ef4d4-170">`LpString` 指向调用方分配的大小为 `nMaxCount` 的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-170">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="ef4d4-171">调用方应分配缓冲区，并将 `nMaxCount` 参数设置为已分配缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-171">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="ef4d4-172">以下代码演示 `GetWindowText` 函数声明，如 Windows.h 中所定义。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-172">The following code shows the `GetWindowText` function declaration as defined in Windows.h.</span></span>  
  
```  
int GetWindowText(  
HWND hWnd,        // Handle to window or control.  
LPTStr lpString,  // Text buffer.  
int nMaxCount     // Maximum number of characters to copy.  
);  
```  
  
 <span data-ttu-id="ef4d4-173">被调用方可以取消引用和修改 `StringBuilder`，前提是不超过 `StringBuilder` 的容量。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-173">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="ef4d4-174">下面的代码示例演示如何将 `StringBuilder` 初始化为固定长度。</span><span class="sxs-lookup"><span data-stu-id="ef4d4-174">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>  
  
```vb  
Public Class Win32API  
Public Declare Auto Sub GetWindowText Lib "User32.Dll" _  
(h As Integer, s As StringBuilder, nMaxCount As Integer)  
End Class  
Public Class Window  
   Friend h As Integer ' Friend handle to Window.  
   Public Function GetText() As String  
      Dim sb As New StringBuilder(256)  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1)  
   Return sb.ToString()  
   End Function  
End Class  
```  
  
```csharp  
public class Win32API {  
[DllImport("User32.Dll")]  
public static extern void GetWindowText(int h, StringBuilder s,   
int nMaxCount);  
}  
public class Window {  
   internal int h;        // Internal handle to Window.  
   public String GetText() {  
      StringBuilder sb = new StringBuilder(256);  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1);  
   return sb.ToString();  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef4d4-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef4d4-175">See Also</span></span>  
 [<span data-ttu-id="ef4d4-176">默认封送处理行为</span><span class="sxs-lookup"><span data-stu-id="ef4d4-176">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)  
 [<span data-ttu-id="ef4d4-177">可直接复制到本机结构中的类型和非直接复制到本机结构中的类型</span><span class="sxs-lookup"><span data-stu-id="ef4d4-177">Blittable and Non-Blittable Types</span></span>](../../../docs/framework/interop/blittable-and-non-blittable-types.md)  
 [<span data-ttu-id="ef4d4-178">方向特性</span><span class="sxs-lookup"><span data-stu-id="ef4d4-178">Directional Attributes</span></span>](http://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2)  
 [<span data-ttu-id="ef4d4-179">复制和锁定</span><span class="sxs-lookup"><span data-stu-id="ef4d4-179">Copying and Pinning</span></span>](../../../docs/framework/interop/copying-and-pinning.md)
