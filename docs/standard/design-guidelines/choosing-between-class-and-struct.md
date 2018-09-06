---
title: 在类和结构之间选择
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06661cb2c34d1da9085fa2129cb0c3307b99097e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865548"
---
# <a name="choosing-between-class-and-struct"></a>在类和结构之间选择
每个框架设计器的人脸的基本设计决策之一是要设计一种类型作为类 （引用类型） 或结构 （值类型）。 熟悉的引用类型和值类型的行为差异是在进行此选择中至关重要的。  
  
 第一个差别引用类型和值类型，我们将考虑是引用类型是在堆上分配和垃圾回收，而是在堆栈上分配值类型或包含中的以内联方式类型，并且已解除分配时堆栈展开时或当其包含类型会被解除分配。 因此，分配和释放的值类型是通常比分配和释放的引用类型成本更低。  
  
 接下来，引用类型的数组分配行，这意味着元素的数组只是对驻留在堆上的引用类型的实例。 值类型数组分配内联，这意味着数组元素值类型的实际实例。 因此，分配和释放的值类型数组将比分配和释放的引用类型数组更便宜。 此外，在大多数情况下值类型数组表现出多更好的引用地址。  
  
 下一个差异与内存使用量。 获取装箱值类型，当强制转换为引用类型或它们实现的接口之一。 他们会收到未装箱时强制转换回值类型。 因为框是在堆上分配和垃圾回收、 过多装箱和取消装箱的对象可以对堆、 垃圾回收器，并最终应用程序性能的负面影响。  与此相反，没有此类值类型装箱会出现引用类型转换。  
  
 接下来，引用类型分配将引用，而值类型分配复制的整个值复制。 因此，大型的引用类型的分配是大值类型的分配比更便宜。  
  
 最后，引用类型是通过引用传递，而按值传递值类型。 引用类型的实例的更改会影响所有指向实例的引用。 按值传递值类型实例进行复制。 当更改值类型的实例时，它当然不会影响任何其副本。 因为副本不由用户显式创建，但会隐式创建参数传递或返回值返回时，可以更改的值类型可以是给许多用户造成混淆。 因此，值类型应为不可变。  
  
 根据经验，大部分的框架中的类型应为类。 有，但是，某些情况下，在其中一个值类型的特性使其更适合使用结构。  
  
 **✓ CONSIDER** 定义而不是类结构，如果该类型的实例很小，通常生存期较短或嵌入其他对象。  
  
 **X AVOID** 定义一个结构，除非该类型具有所有以下特征：  
  
-   它逻辑上表示的单个值，类似于基元类型 (`int`， `double`，等等。)。  
  
-   它的实例大小小于 16 字节。  
  
-   它是不可变。  
  
-   它不会频繁装箱。  
  
 在所有其他情况下，应将您的类型定义为类。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
