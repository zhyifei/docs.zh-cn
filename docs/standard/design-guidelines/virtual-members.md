---
title: 虚成员
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa4227fc4476b86f07216650b22fccc25af7dd98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="virtual-members"></a>虚成员
虚拟成员可以被重写，因此更改行为的子类。 它们是非常类似于在它们提供的可扩展性方面的回调，但它们可以在执行性能和内存消耗方面获得更好。 此外，虚拟成员感觉需要创建一个特殊类型的现有类型 （专用） 的方案中更自然。  
  
 虚拟成员执行性能优于回调和事件，但不是比非虚拟方法的更好地执行。  
  
 虚拟成员的主要缺点是在编译时中的虚拟成员的行为可以仅能修改。 在运行时，可以对回调的行为进行修改。  
  
 虚拟成员，例如回调 （和可能有多个回调），是用于设计、 测试和维护，因为对虚拟成员的任何调用可以在无法预测的方式中重写，并且能够执行任意代码的成本。 此外，更多工作量通常要求以明确定义的虚拟成员的协定，使设计和记录它们的成本较高。  
  
 **X 不**虚成员，除非你有理由这样做，并且注意与设计、 测试和维护虚拟成员相关的所有成本。  
  
 虚拟成员是较少 forgiving 哪些可以对它们进行而不会破坏兼容性的更改。 此外，它们是低于非虚拟成员，主要是因为对虚拟成员的调用不内联。  
  
 **请考虑 ✓**限制只将绝对必要的扩展性。  
  
 **✓ 执行**首选受保护的辅助功能的虚拟成员，而公共可访问性。 公共成员应通过调用受保护的虚拟成员提供扩展性 （如果需要）。  
  
 类的公共成员应为该类的直接使用者提供正确的功能集。 旨在子类，在中重写虚拟成员和受保护的可访问性是作用域以用于其中的所有虚拟扩展性点的好办法。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
