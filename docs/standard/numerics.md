---
title: ".NET Framework 中的数字 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SIMD"
  - "系统数字向量"
  - "向量"
  - "科学计算"
  - "Complex"
  - "数字"
  - "BigInteger"
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# .NET Framework 中的数字
.NET Framework 支持标准数值整型和浮点型基元以及<xref:System.Numerics.BigInteger>，没有理论上限或下限的整数类型<xref:System.Numerics.Complex>表示复杂数字的类型和中的组启用了 SIMD 的矢量类型<xref:System.Numerics>命名空间。  
  
 此外，作为 NuGet 程序包发布 System.Numerics.Vectors，vectory 类型启用了 SIMD 的库。  
  
## <a name="integral-types"></a>整型  
 .NET Framework 支持长度为&1; -&8; 个字节的有符号和无符号整数。 下表列出了整数类型及其大小、指示它们有无符号，并记录了相应范围。 所有整数都是值类型。  
  
|类型|有符号/无符号|大小（字节）|最小值|最大值|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=fullName>|无符号|1|0|255|  
|<xref:System.Int16?displayProperty=fullName>|签名|2|-32,768|32,767|  
|<xref:System.Int32?displayProperty=fullName>|签名|4|-2,147,483,648|2,147,483,647|  
|<xref:System.Int64?displayProperty=fullName>|签名|8|-9,223,372,036,854,775,808|9,223,372,036,854,775,807|  
|<xref:System.SByte?displayProperty=fullName>|签名|1|-128|127|  
|<xref:System.UInt16?displayProperty=fullName>|无符号|2|0|65,535|  
|<xref:System.UInt32?displayProperty=fullName>|无符号|4|0|4,294,967,295|  
|<xref:System.UInt64?displayProperty=fullName>|无符号|8|0|18,446,744,073,709,551,615|  
  
 每个整数类型都支持一套标准的算术、比较、相等、显式转换和隐式转换运算符。 每个整数还包括执行相等比较和相对比较的方法，将数字的字符串表示形式转换为相应整数的方法，以及将整数转换为相应字符串表示形式的方法。 由标准运算符处理的之外其他数学运算，如舍入和确定两个整数的值的大小也可从<xref:System.Math>类。 您还可以使用一个整数值中的单个位使用<xref:System.BitConverter>类。  
  
 请注意无符号整数类型不符合 CLS。 有关详细信息，请参阅[语言独立性和与语言无关的组件](../../docs/standard/language-independence-and-language-independent-components.md)。  
  
## <a name="floating-point-types"></a>浮点类型  
 .NET Framework 包括三个基元浮点类型，如下表所列。  
  
|类型|大小（以字节为单位）|最低|最大值|  
|----------|-----------------------|-------------|-------------|  
|<xref:System.Double?displayProperty=fullName>|8|-1.79769313486232e308|1.79769313486232e308|  
|<xref:System.Single?displayProperty=fullName>|4|-3.402823e38|3.402823e38|  
|<xref:System.Decimal?displayProperty=fullName>|16|-79,228,162,514,264,337,593,543,950,335|79,228,162,514,264,337,593,543,950,335|  
  
 每个浮点类型都支持一套标准的算术、比较、相等、显式转换和隐式转换运算符。 每个浮点还包括执行相等比较和相对比较的方法，转换浮点数的字符串表示形式的方法，以及将浮点数转换为相应字符串表示形式的方法。 还可以从一些其他的数学、 代数和三角运算<xref:System.Math>类。 您还可以使用中的单个位<xref:System.Double>和<xref:System.Single>使用值<xref:System.BitConverter>类。 <xref:System.Decimal?displayProperty=fullName>结构有它自己的方法， <xref:System.Decimal.GetBits%2A?displayProperty=fullName>和[Decimal.Decimal (Int32\<xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29?displayProperty=fullName>、 使用十进制值的单个位为单位，以及其自己的用于执行一些其他数学运算方法集。  
  
 <xref:System.Double>和<xref:System.Single>类型旨在用于本质上不精确 （例如，太阳系中两颗行星之间的距离） 的值以及在其中高度精确和舍入误差小不是必需的应用程序。 应使用<xref:System.Decimal?displayProperty=fullName>中较高的用例的类型是必需的精度和无舍入误差并不可取，  
  
## <a name="biginteger"></a>BigInteger  
 <xref:System.Numerics.BigInteger?displayProperty=fullName> 是不可变类型，表示其值没有理论上限或下限的任意大整数。 方法<xref:System.Numerics.BigInteger>类型几乎其他整数类型。  
  
## <a name="complex"></a>Complex  
 <xref:System.Numerics.Complex>类型表示复数，即带实数部分和虚数部分的数字。 此类型支持一套标准的算术、比较、相等、显式转换和隐式转换运算符，以及数学、代数和三角方法。  
  
## <a name="simd-enabled-vector-types"></a>启用了 SIMD 的矢量类型  
 <xref:System.Numerics>命名空间包含启用了 SIMD 的矢量类型的一组适用于.NET Framework。 SIMD（单指令多数据运算）允许在硬件级别并行化某些操作，从而使通过向量执行计算的数学应用、科学应用和图形应用产生大幅性能提升。  
  
 .NET Framework 中启用了 SIMD 的矢量类型包括以下类型：  此外，System.Numerics.Vectors 包括一个 Plane 类型和一个 Quaternion 类型。  
  
-   <xref:System.Numerics.Vector2>， <xref:System.Numerics.Vector3>，和<xref:System.Numerics.Vector4>类型，它们是 2、 3 和 4 维向量类型的<xref:System.Single>。  
  
-   两个矩阵类型， <xref:System.Numerics.Matrix3x2>，它表示的 3 x 2 矩阵; 和<xref:System.Numerics.Matrix4x4>，这表示 4 x 4 矩阵。  
  
-   <xref:System.Numerics.Plane>和<xref:System.Numerics.Quaternion>类型。  
  
 启用了 SIMD 的矢量类型在 IL 中得到实现，这使其可以用于未启用 SIMD 的硬件和 JIT 编译器。 要利用 SIMD 指令，必须使用新的 64 位托管代码的 JIT 编译器编译你的 64 位应用，该编译器包含在 .NET Framework 4.6 中；它针对 x64 处理器添加了 SIMD 支持。  
  
 单指令多数据还可以下载作为[NuGet 程序包](http://www.nuget.org/packages/System.Numerics.Vectors)。  NuGET 包还包括一个泛型<xref:System.Numerics.Vector%601>结构，它允许您创建任何基元数值类型的向量。 (基元数值类型包括中的所有数字类型<xref:System>命名空间除外<xref:System.Decimal>。)此外，<xref:System.Numerics.Vector%601>结构提供了一个方便的方法，您可以使用向量时调用的库。  
  
## <a name="see-also"></a>另请参阅  
 [应用程序要点](../../docs/standard/application-essentials.md)