---
title: x:Members 指令
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: 2c273fce1f15d9a5af72bc3f5a530d3c26dfc77e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564131"
---
# <a name="xmembers-directive"></a>x:Members 指令
包含一组在标记中，定义应用于父元素的 x： 类的成员。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`className`|XAML 生产的备用类或分部类的名称。 请参阅“备注”。|  
|`oneOrMoreMembers`|表示成员定义的一个或多个对象元素。 通常，这些都是`x:Property`对象元素。 请参阅“备注”。|  
  
## <a name="remarks"></a>备注  
 在.NET Framework XAML 服务实现中，没有备用类或基础成员实现`x:Members`。 `x:Members` 是特殊的 XAML 成员，它可以作为上任何类型的成员存在。 在 XAML 节点流中，`x:Members`表示名为的成员为`Members`，XAML 语言 XAML 命名空间。 成员`Members`包含的只读泛型列表`Member`对象。 在典型的标记中各个成员指定为`x:Property`属性元素。 `x:Property` 是专为类型的属性更精确的类型和可分配给`x:Member`。 有关详细信息，请参阅[X:property 指令](../../../docs/framework/xaml-services/x-property-directive.md)。  
  
 若要支持将 `x:Members` 实际用作一种在标记中指定成员定义的方法，成员必须与可修改的类相关联。 预期模型是 `x:Members` 作为指定 `x:Class` 的类型的成员存在。 但是，.NET Framework XAML 服务级别不支持用于关联类型和成员或用于生成动态成员定义的机制。 此功能由具有支持 XAML 的成员定义的应用程序模型的单个框架实现。 通常，需要 MSBUILD 生成操来支持此功能，这些操作以标记编译 XAML 并将其与隐藏代码相集成或者从 XMAL 生成纯程序集。  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>对于 Windows Workflow Foundation 的 x： 成员  
 对于 Windows Workflow Foundation，`x:Members`包含完全在 XAML 中或 XAML 中构成的自定义活动的成员-定义了与隐藏代码的活动设计器的动态成员。 此外，必须在 XAML 生产的根元素上指定 `x:Class`。 这不是 .NET Framework XAML 服务级别上的要求，但在一般情况下当支持自定义活动和 Windows Workflow Foundation XAML 的 MSBUILD 生成操作加载 XAML 生产时将成为一项要求。 `x:Members` 必须在声明的对象元素的标记中的第一个子元素`x:Class`。
