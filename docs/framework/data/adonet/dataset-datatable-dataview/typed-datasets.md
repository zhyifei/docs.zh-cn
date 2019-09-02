---
title: 类型化数据集
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 33876cb9f614a93cab2fa3fd9d056f94dd1e9038
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203150"
---
# <a name="typed-datasets"></a>类型化数据集
在允许通过弱类型化变量对值进行后期绑定访问的同时，<xref:System.Data.DataSet> 还允许通过强类型化比喻对数据进行访问。 可以使用用户友好名称和强类型化变量来访问作为**数据集**一部分的表和列。  
  
 类型化**数据集**是从**数据集**派生的类。 因此, 它继承了**数据集**的所有方法、事件和属性。 此外, 类型化**数据集**提供强类型化的方法、事件和属性。 这意味着可以按名称（而不是使用基于集合的方法）访问表和列。 除了提高代码的可读性之外, 类型化**数据集**还允许 Visual Studio .net 代码编辑器在你键入时自动完成行。  
  
 此外, 强类型化**数据集**还可在编译时访问值作为正确的类型。 使用强类型化**数据集**时, 将在编译代码时 (而不是在运行时) 捕获类型不匹配错误。  
  
## <a name="in-this-section"></a>本节内容  
 [生成强类型化数据集](generating-strongly-typed-datasets.md)  
 介绍如何创建和使用强类型化**数据集**。  
  
 [为类型化的数据集进行注释](annotating-typed-datasets.md)  
 介绍如何为用于生成强类型化**数据集**的 XML 架构定义语言 (XSD) 架构添加批注, 以便在不更改基础架构的情况下为**DataSet**元素指定友好名称。  
  
## <a name="see-also"></a>请参阅

- [数据集、数据表和数据视图](index.md)
- [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
