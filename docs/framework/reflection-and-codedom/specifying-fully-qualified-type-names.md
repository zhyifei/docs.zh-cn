---
title: "指定完全限定的类型名称 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "程序集 [.NET Framework], 名称"
  - "Backus-Naur 格式"
  - "BNF"
  - "完全限定的类型名"
  - "IDENTIFIER"
  - "语言, BNF 语法"
  - "名称 [.NET Framework], 程序集"
  - "名称 [.NET Framework], 完全限定的类型名"
  - "反射, 完全限定的类型名"
  - "特殊字符"
  - "标记"
  - "类型名称"
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 指定完全限定的类型名称
要为各种反射操作提供有效的输入，必须指定类型名称。  完全限定的类型名称包含程序集名称说明、命名空间说明和类型名称。  类型名称说明由 <xref:System.Type.GetType%2A?displayProperty=fullName>、<xref:System.Reflection.Module.GetType%2A?displayProperty=fullName>、<xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=fullName> 和 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> 等方法使用。  
  
## 类型名称的 Backus\-Naur 形式语法  
 Backus\-Naur 形式 \(BNF\) 定义正式语言的语法。  下表中列出的 BNF 词法规则说明如何识别有效的输入。  最终元素（无法再减小的元素）全部以大写字母显示。  非最终元素（可以再减小的元素）则显示为大小写混合或带单引号的字符串，但单引号 \('\) 不是语法本身的一部分。  竖线 \(&#124;\) 表示具有子规则的规则。  
  
|完全限定类型名称的 BNF 语法|  
|----------------------|  
|TypeSpec                          :\=   ReferenceTypeSpec<br /><br /> &#124;     SimpleTypeSpec|  
|ReferenceTypeSpec            :\=   SimpleTypeSpec '&'|  
|SimpleTypeSpec                :\=   PointerTypeSpec<br /><br /> &#124;     ArrayTypeSpec<br /><br /> &#124;     TypeName|  
|PointerTypeSpec                :\=   SimpleTypeSpec '\*'|  
|ArrayTypeSpec                  :\=   SimpleTypeSpec '\[ReflectionDimension\]'<br /><br /> &#124;     SimpleTypeSpec '\[ReflectionEmitDimension\]'|  
|ReflectionDimension           :\=   '\*'<br /><br /> &#124;     ReflectionDimension ',' ReflectionDimension<br /><br /> &#124;     NOTOKEN|  
|ReflectionEmitDimension    :\=   '\*'<br /><br /> &#124;     Number '..'数字<br /><br /> &#124;     Number '…'<br /><br /> &#124;     ReflectionDimension ',' ReflectionDimension<br /><br /> &#124;     NOTOKEN|  
|Number                            :\=   \[0\-9\]\+|  
|TypeName                         :\=   NamespaceTypeName<br /><br /> &#124;     NamespaceTypeName ',' AssemblyNameSpec|  
|NamespaceTypeName        :\=   NestedTypeName<br /><br /> &#124;     NamespaceSpec '.'NestedTypeName|  
|NestedTypeName               :\=   IDENTIFIER<br /><br /> &#124;     NestedTypeName '\+' IDENTIFIER|  
|NamespaceSpec                 :\=   IDENTIFIER<br /><br /> &#124;     NamespaceSpec '.'IDENTIFIER|  
|AssemblyNameSpec           :\=   IDENTIFIER<br /><br /> &#124;     IDENTIFIER ',' AssemblyProperties|  
|AssemblyProperties            :\=   AssemblyProperty<br /><br /> &#124;     AssemblyProperties ',' AssemblyProperty|  
|AssemblyProperty              :\=   AssemblyPropertyName '\=' AssemblyPropertyValue|  
  
## 指定特殊字符  
 在类型名称中，IDENTIFIER 是语言规则确定的任何有效名称。  
  
 反斜杠 \(\\\) 可用作转义符来分隔以下用作 IDENTIFIER 一部分的标记。  
  
|标记|含义|  
|--------|--------|  
|\\,|程序集分隔符。|  
|\\\+|嵌套类型分隔符。|  
|\\&|引用类型。|  
|\\\*|指针类型。|  
|\\\[|数组维度分隔符。|  
|\\\]|数组维度分隔符。|  
|\\.|只有在数组说明中使用句点时，才应在句点前使用反斜杠。  NamespaceSpec 中的句点不采用反斜杠。|  
|\\\\|用作字符串的反斜杠。|  
  
 请注意，在除 AssemblyNameSpec 之外的所有 TypeSpec 组成部分中，空格都是相关的。  在 AssemblyNameSpec 中，“,”分隔符之前的空格相关，但“,”分隔符之后的空格将被忽略。  
  
 反射类（如 <xref:System.Type.FullName%2A?displayProperty=fullName>）返回改变后的名称，以便使返回的名称可以在对 <xref:System.Type.GetType%2A> 的调用中（如同在 `MyType.GetType(myType.FullName)` 中一样）使用。  
  
 例如，某个类型的完全限定名称可能是 `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`。  
  
 如果命名空间为 `Ozzy.Out+Back`，则必须在加号前加反斜杠。  否则，分析器会将其解释为嵌套分隔符。  反射会将该字符串当作 `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly` 发出。  
  
## 指定程序集名称  
 程序集名称说明所需的最少信息是程序集的文本名称 \(IDENTIFIER\)。  您可以在 IDENTIFIER 后添加下表所述的逗号分隔属性\/值对列表。  IDENTIFIER 命名应遵循文件命名的规则。  IDENTIFIER 不区分大小写。  
  
|属性名称|说明|允许值|  
|----------|--------|---------|  
|**版本**|程序集版本号|*Major.Minor.Build.Revision*，其中 *Major*、*Minor*、*Build* 和 *Revision* 是 0 和 65535 之间（含 0 和 65535）的整数。|  
|**PublicKey**|完全公钥|完全公钥的十六进制字符串值。  指定 null 引用（在 Visual Basic 中为 **Nothing**）以显式指示私有程序集。|  
|**PublicKeyToken**|公钥标记（完全公钥的 8 字节哈希）|公钥标记的十六进制字符串值。  指定 null 引用（在 Visual Basic 中为 **Nothing**）以显式指示私有程序集。|  
|**区域性**|程序集区域性|程序集的 RFC\-1766 格式区域性，或者对于独立于语言（非附属）的程序集为“非特定”。|  
|**自定义**|自定义的二进制大对象 \(BLOB\)。  它当前仅用于由[本机图像生成器 \(Ngen\)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) 生成的程序集。|自定义的字符串，由本机图像生成器工具用来向程序集缓存通知所安装的程序集为本机图像，因此将安装在本机图像缓存中。  也称作 Zap 字符串。|  
  
 下面的示例演示具有默认区域性的简单命名程序集的 **AssemblyName**。  
  
```csharp  
com.microsoft.crypto, Culture=""   
```  
  
 下面的示例演示区域性为“en”的强命名程序集的完全限定引用。  
  
```csharp  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0   
```  
  
 下面的示例演示部分指定的 **AssemblyName**，它可以由具有强名称或简单名称的程序集来满足。  
  
```csharp  
com.microsoft.crypto  
com.microsoft.crypto, Culture=""  
com.microsoft.crypto, Culture=en   
```  
  
 下面的示例都演示一个部分指定的 **AssemblyName**，它必须由具有简单名称的程序集来满足。  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=null   
com.microsoft.crypto, Culture=en, PublicKeyToken=null  
```  
  
 下面的示例都显示一个部分指定的 **AssemblyName**，它必须由具有强名称的程序集来满足。  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0  
```  
  
## 指定指针  
 SimpleTypeSpec\* 表示非托管指针。  例如，要获取指向 MyType 类型的指针，请使用 `Type.GetType("MyType*")`。  要获取指向 MyType 类型指针的指针，请使用 `Type.GetType("MyType**")`。  
  
## 指定引用  
 SimpleTypeSpec &表示托管指针或引用。  例如，要获取对 MyType 类型的引用，请使用 `Type.GetType("MyType &")`。  请注意，与指针不同，引用仅限于一个级别。  
  
## 指定数组  
 在 BNF 语法中，ReflectionEmitDimension 仅适用于使用 <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=fullName> 检索的不完整类型定义。  不完整的类型定义是使用[Reflection.Emit](frlrfSystemReflectionEmit)构造但没有对它们调用<xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=fullName>的<xref:System.Reflection.Emit.TypeBuilder> 对象。  ReflectionDimension 可用于检索任何已完成的类型定义，即已加载的类型。  
  
 通过指定数组的秩，可以访问反射中的数组：  
  
-   `Type.GetType("MyArray[]")` 获取下限为 0 的单维数组。  
  
-   `Type.GetType("MyArray[*]")` 获取下限未知的单维数组。  
  
-   `Type.GetType("MyArray[][]")` 获取二维数组的数组。  
  
-   `Type.GetType("MyArray[*,*]")` 和 `Type.GetType("MyArray[,]")` 获取下限未知的矩形二维数组。  
  
 请注意，从运行时的角度来看，`MyArray[] != MyArray[*]`，但对于多维数组而言，这两种表示是等效的。  也就是说，`Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` 的计算结果为 **true**。  
  
 对于 **ModuleBuilder.GetType**, `MyArray[0..5]` 指示大小为 6 下限为 0 的单维数组。 `MyArray[4…]` 指示大小未知下限为 4 的单维数组。  
  
## 请参阅  
 <xref:System.Reflection.AssemblyName>   
 <xref:System.Reflection.Emit.ModuleBuilder>   
 <xref:System.Reflection.Emit.TypeBuilder>   
 <xref:System.Type.FullName%2A?displayProperty=fullName>   
 <xref:System.Type.GetType%2A?displayProperty=fullName>   
 <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName>   
 [查看类型信息](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)