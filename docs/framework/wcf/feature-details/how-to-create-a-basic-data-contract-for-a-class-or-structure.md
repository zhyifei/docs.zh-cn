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
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="d39a1-102">如何：创建类或结构的基本数据协定</span><span class="sxs-lookup"><span data-stu-id="d39a1-102">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="d39a1-103">本主题演示使用类或结构创建数据协定的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="d39a1-103">This topic shows the basic steps to create a data contract using a class or structure.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d39a1-104">数据协定以及如何使用它们，请参阅[使用数据协定](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="d39a1-104"> data contracts and how they are used, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="d39a1-105">有关演练创建一个基本的步骤的教程[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]服务和客户端，请参阅[入门教程](../../../../docs/framework/wcf/getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="d39a1-105">For a tutorial that walks through the steps of creating a basic [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client, see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="d39a1-106">有关工作示例应用程序，它包含基本服务和客户端，请参阅[基本数据协定](../../../../docs/framework/wcf/samples/basic-data-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="d39a1-106">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="d39a1-107">创建类或结构的基本数据协定</span><span class="sxs-lookup"><span data-stu-id="d39a1-107">To create a basic data contract for a class or structure</span></span>  
  
1.  <span data-ttu-id="d39a1-108">通过将 <xref:System.Runtime.Serialization.DataContractAttribute> 属性应用于类来声明该类型具有数据协定。</span><span class="sxs-lookup"><span data-stu-id="d39a1-108">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="d39a1-109">请注意，包括不带属性的公共类型在内的所有公共类型都是可序列化的。</span><span class="sxs-lookup"><span data-stu-id="d39a1-109">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="d39a1-110">如果不存在 <xref:System.Runtime.Serialization.DataContractSerializer> 属性，<xref:System.Runtime.Serialization.DataContractAttribute> 将推断出一个数据协定。</span><span class="sxs-lookup"><span data-stu-id="d39a1-110">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="d39a1-111">[可序列化类型](../../../../docs/framework/wcf/feature-details/serializable-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d39a1-111"> [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
2.  <span data-ttu-id="d39a1-112">通过将 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性 (Attribute) 应用于每个成员来定义要序列化的成员（属性 (Property)、字段或事件）。</span><span class="sxs-lookup"><span data-stu-id="d39a1-112">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="d39a1-113">这些成员称为数据成员。</span><span class="sxs-lookup"><span data-stu-id="d39a1-113">These members are called data members.</span></span> <span data-ttu-id="d39a1-114">默认情况下，所有公共类型都是可序列化的。</span><span class="sxs-lookup"><span data-stu-id="d39a1-114">By default, all public types are serializable.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="d39a1-115">[可序列化类型](../../../../docs/framework/wcf/feature-details/serializable-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d39a1-115"> [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d39a1-116">您可以将 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性应用于私有字段，这会导致向其他人公开此数据。</span><span class="sxs-lookup"><span data-stu-id="d39a1-116">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="d39a1-117">请确保成员不包含敏感数据。</span><span class="sxs-lookup"><span data-stu-id="d39a1-117">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d39a1-118">示例</span><span class="sxs-lookup"><span data-stu-id="d39a1-118">Example</span></span>  
 <span data-ttu-id="d39a1-119">下面的示例演示如何通过将 `Person` 和 <xref:System.Runtime.Serialization.DataContractAttribute> 属性应用于类及其成员来创建 <xref:System.Runtime.Serialization.DataMemberAttribute> 类型的数据协定。</span><span class="sxs-lookup"><span data-stu-id="d39a1-119">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d39a1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d39a1-120">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="d39a1-121">使用数据协定</span><span class="sxs-lookup"><span data-stu-id="d39a1-121">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="d39a1-122">入门教程</span><span class="sxs-lookup"><span data-stu-id="d39a1-122">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="d39a1-123">入门</span><span class="sxs-lookup"><span data-stu-id="d39a1-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
