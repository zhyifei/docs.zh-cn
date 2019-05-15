---
title: 用户定义的函数
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: fb55a8b248b085275f83d47b1f452cd07bd8dcb1
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582651"
---
# <a name="user-defined-functions"></a>用户定义的函数
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 在您的对象模型中使用方法来表示用户定义的函数。 您可以通过应用 <xref:System.Data.Linq.Mapping.FunctionAttribute> 属性和 <xref:System.Data.Linq.Mapping.ParameterAttribute> 属性（如果需要）将方法指定为函数。 有关详细信息，请参阅[LINQ to SQL 对象模型](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)。  
  
 为避免出现 <xref:System.InvalidOperationException>，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中用户定义的函数必须采用以下形式之一：  
  
- 包装为具有正确映射属性的方法调用的函数。 有关详细信息，请参阅[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)。  
  
- 特定于 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的静态 SQL 方法。  
  
- 支持的.NET Framework 方法的函数。  
  
 本节中的主题说明了在您自行编写代码的情况下，如何在您的应用程序中构建和调用这些方法。 使用 Visual Studio 的开发人员通常会使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]来映射用户定义的函数。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：使用标量值用户定义函数](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 介绍如何实现返回标量值的函数。  
  
 [如何：使用用户定义表值函数](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 介绍如何实现返回表值的函数。  
  
 [如何：内联调用用户定义的函数](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 介绍如何对函数进行内联调用，以及进行内联调用时在执行方面的差异。
