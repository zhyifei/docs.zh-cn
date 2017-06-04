---
title: "可直接复制到本机结构中的类型和非直接复制到本机结构中的类型 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "能直接复制到本机结构中的类型, 互操作封送处理"
  - "互操作封送处理, 能直接复制到本机结构中的类型"
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# 可直接复制到本机结构中的类型和非直接复制到本机结构中的类型
大多数数据类型在托管和非托管内存中都有公共的表示形式，而不需要 Interop 封送拆收器的特殊处理。  因为这些类型在托管和非托管代码之间传递时不需要转换，因此称为“可直接复制到本机结构中的类型”。  
  
 从平台调用返回的结构必须为可直接复制到本机结构中的类型。  平台调用不支持将非直接复制到本机结构中的结构作为返回类型。  
  
 下列来自 <xref:System> 命名空间的类型为可直接复制到本机结构中的类型：  
  
-   <xref:System.Byte?displayProperty=fullName>  
  
-   <xref:System.SByte?displayProperty=fullName>  
  
-   <xref:System.Int16?displayProperty=fullName>  
  
-   <xref:System.UInt16?displayProperty=fullName>  
  
-   <xref:System.Int32?displayProperty=fullName>  
  
-   <xref:System.UInt32?displayProperty=fullName>  
  
-   <xref:System.Int64?displayProperty=fullName>  
  
-   <xref:System.UInt64?displayProperty=fullName>  
  
-   <xref:System.IntPtr?displayProperty=fullName>  
  
-   <xref:System.UIntPtr?displayProperty=fullName>  
  
-   <xref:System.Single?displayProperty=fullName>  
  
-   <xref:System.Double?displayProperty=fullName>  
  
 下列复杂类型也是可直接复制到本机结构中的类型：  
  
-   可直接复制到本机结构中的类型的一维数组，如整数数组。  但是，包含可直接复制到本机结构中的类型的变量数组的类型本身不可直接复制到本机结构中。  
  
-   只包含可直接复制到本机结构中的类型（如果它们被作为格式化类型封送，则还包含类）的格式化值类型。  有关格式化值类型的更多信息，请参见[Default Marshaling for Value Types](http://msdn.microsoft.com/zh-cn/4d9a876c-e05a-40ba-bd85-bd22877f984a)。  
  
 对象引用不可直接复制到本机结构中。  其中包含一组对象引用，它们本身可直接复制到本机结构中。  例如，您可以定义一个可直接复制到本机结构中的结构，但是您不能定义包含对这些结构的一组引用的可直接复制到本机结构中的类型。  
  
 作为一种优化方式，在进行封送处理的过程中，可直接复制到本机结构中的类型的数组和只包含可直接复制到本机结构中的成员的类被[锁定](../../../docs/framework/interop/copying-and-pinning.md)，而不是被复制。  在调用方和被调用方位于同一单元中时，这些类型可能看上去是被作为 In\/Out 参数封送的。  但是，这些类型实际上是作为 In 形参封送的，而如果要将实参作为 In\/Out 形参封送，则必须应用 <xref:System.Runtime.InteropServices.InAttribute> 和 <xref:System.Runtime.InteropServices.OutAttribute> 特性。  
  
 某些托管数据类型在非托管环境中需要采用一种不同的表示形式。  必须将这些非直接复制到本机结构中的数据类型转换为可进行封送的格式。  例如，托管字符串是非直接复制到本机结构中的类型，这是因为它们必须转换为字符串对象才能进行封送。  
  
 下表列出了 <xref:System> 命名空间中的非直接复制到本机结构中的类型。  [委托](http://msdn.microsoft.com/zh-cn/d176ee76-f982-494b-b03d-92e4118896e2)（它是引用静态方法或类实例的数据结构）也是非直接复制到本机结构中的。  
  
|非直接复制到本机结构中的类型|说明|  
|--------------------|--------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|转换为 C 样式数组或 `SAFEARRAY`。|  
|[System.Boolean](http://msdn.microsoft.com/zh-cn/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|转换为 1、2 或 4 字节的值，值为 `true` 时为 1 或 \-1。|  
|[System.Char](http://msdn.microsoft.com/zh-cn/cecc87c1-075e-4cde-aa56-33d189f66feb)|转换为 Unicode 或 ANSI 字符。|  
|[System.Class](http://msdn.microsoft.com/zh-cn/fe334af5-0123-43d8-be84-26f6f023ddb6)|转换为类接口。|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|转换为变量或接口。|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|转换为 C 样式数组或 `SAFEARRAY`。|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|转换为以 null 引用或 BSTR 引用终止的字符串。|  
|[System.Valuetype](http://msdn.microsoft.com/zh-cn/4d9a876c-e05a-40ba-bd85-bd22877f984a)|转换为具有固定内存布局的结构。|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|转换为 C 样式数组或 `SAFEARRAY`。|  
  
 类和对象类型只受 COM 互操作支持。  有关 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]、C\# 和 C\+\+ 中的相应类型，请参见 [类库概述](../../../docs/standard/class-library-overview.md)。  
  
## 请参阅  
 [默认封送处理行为](../../../docs/framework/interop/default-marshaling-behavior.md)