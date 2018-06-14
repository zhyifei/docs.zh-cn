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
ms.openlocfilehash: 8bb05b825113c025781a790dc206d500633a3b08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573576"
---
# <a name="choosing-between-class-and-struct"></a>在类和结构之间选择
每个框架设计器将面向的基本设计决策之一是要设计一个类型作为类 （引用类型） 或结构 （值类型）。 熟悉的引用类型和值类型的行为差异在进行此选择至关重要。  
  
 第一个引用类型和值类型，我们将考虑是引用类型在堆上分配和垃圾回收，而是在堆栈上分配值类型或内联在包含类型，并释放时之间堆栈差异展开或其包含的类型获取释放时。 因此，分配和释放的值类型是通常价格低于分配和释放的引用类型。  
  
 接下来，引用类型的数组分配行，这意味着的数组元素的堆上驻留的引用类型的实例的只是引用。 值类型数组分配内联，这意味着数组元素值类型的实际实例。 因此，分配和释放的值类型数组将更廉价比分配和释放的引用类型数组。 此外，在大多数情况下值类型数组表现出多更好的引用地址。  
  
 下一个差异与内存使用量。 值类型获取装箱当强制转换为引用类型或它们实现的接口之一。 它们获取未装箱当强制转换回值类型。 因为框是堆上分配和垃圾回收、 过多装箱和取消装箱的对象可以对堆、 垃圾回收器，并最终应用程序的性能有负面影响。  与此相反，如引用类型强制转换，则会发生没有此类值类型装箱。  
  
 接下来，引用类型分配将该引用，而值类型分配复制整个值复制。 因此，大型引用类型的分配的价格低于较大的值类型的分配。  
  
 最后，引用类型通过引用进行传递，而通过值传递值类型。 一个引用类型的实例的更改会影响指向实例的所有引用。 将通过值传递它们时复制值类型实例。 当更改值类型的实例时，它是当然的不会影响任何其副本。 由于副本未由用户在显式创建，而隐式创建的自变量传递或返回返回值时，可以更改的值类型可以给许多用户造成混淆。 因此，值类型应是不可变。  
  
 作为一条经验法则，大多数框架中的类型应类。 一些，但是，某些情况下在其中的值类型的特征使其更适合使用结构。  
  
 **请考虑 ✓**定义而不是类结构，如果该类型的实例很小，通常生存期较短或嵌入其他对象。  
  
 **请避免 x**定义一个结构，除非该类型具有所有以下特征：  
  
-   它逻辑上表示的单个值，类似于基元类型 (`int`，`double`等。)。  
  
-   它具有实例大小小于 16 字节。  
  
-   不可变。  
  
-   它不需要频繁进行装箱。  
  
 在所有其他情况下，应为类定义你的类型。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
