---
title: "如何：创建类或结构的基本数据协定"
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
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6241df0fd5a0b6ee532691eee2279f618be25a56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a>如何：创建类或结构的基本数据协定
本主题演示使用类或结构创建数据协定的基本步骤。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]数据协定以及如何使用它们，请参阅[使用数据协定](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)。  
  
 有关演练创建一个基本的步骤的教程[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]服务和客户端，请参阅[入门教程](../../../../docs/framework/wcf/getting-started-tutorial.md)。 有关工作示例应用程序，它包含基本服务和客户端，请参阅[基本数据协定](../../../../docs/framework/wcf/samples/basic-data-contract.md)。  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a>创建类或结构的基本数据协定  
  
1.  通过将 <xref:System.Runtime.Serialization.DataContractAttribute> 属性应用于类来声明该类型具有数据协定。 请注意，包括不带属性的公共类型在内的所有公共类型都是可序列化的。 如果不存在 <xref:System.Runtime.Serialization.DataContractSerializer> 属性，<xref:System.Runtime.Serialization.DataContractAttribute> 将推断出一个数据协定。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][可序列化类型](../../../../docs/framework/wcf/feature-details/serializable-types.md)。  
  
2.  通过将 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性 (Attribute) 应用于每个成员来定义要序列化的成员（属性 (Property)、字段或事件）。 这些成员称为数据成员。 默认情况下，所有公共类型都是可序列化的。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][可序列化类型](../../../../docs/framework/wcf/feature-details/serializable-types.md)。  
  
    > [!NOTE]
    >  您可以将 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性应用于私有字段，这会导致向其他人公开此数据。 请确保成员不包含敏感数据。  
  
## <a name="example"></a>示例  
 下面的示例演示如何通过将 `Person` 和 <xref:System.Runtime.Serialization.DataContractAttribute> 属性应用于类及其成员来创建 <xref:System.Runtime.Serialization.DataMemberAttribute> 类型的数据协定。  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [使用数据协定](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [入门教程](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)
