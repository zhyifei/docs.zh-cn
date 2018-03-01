---
title: "向前兼容的数据协定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], forward compatibility
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ffd4a09de508a2353af356863f9e4f41fc253e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="forward-compatible-data-contracts"></a><span data-ttu-id="69b57-102">向前兼容的数据协定</span><span class="sxs-lookup"><span data-stu-id="69b57-102">Forward-Compatible Data Contracts</span></span>
<span data-ttu-id="69b57-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 数据协定系统的一个特征是协定能够以不间断的方式随着时间而逐步演化。</span><span class="sxs-lookup"><span data-stu-id="69b57-103">A feature of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] data contract system is that contracts can evolve over time in nonbreaking ways.</span></span> <span data-ttu-id="69b57-104">也就是说，具有旧版本数据协定的客户端可以与具有相同数据协定的新版本的服务进行通信，或者具有新版本数据协定的客户端可以与相同数据协定的旧版本进行通信。</span><span class="sxs-lookup"><span data-stu-id="69b57-104">That is, a client with an older version of a data contract can communicate with a service with a newer version of the same data contract, or a client with a newer version of a data contract can communicate with an older version of the same data contract.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="69b57-105">[最佳做法： 数据协定版本管理](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="69b57-105"> [Best Practices: Data Contract Versioning](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).</span></span>  
  
 <span data-ttu-id="69b57-106">如果创建了现有数据协定的新版本，您可以根据需要来应用大多数版本管理功能。</span><span class="sxs-lookup"><span data-stu-id="69b57-106">You can apply most of the versioning features on an as-needed basis when new versions of an existing data contract are created.</span></span> <span data-ttu-id="69b57-107">但是，一个版本管理功能，*往返*，必须生成为的类型中的第一个版本才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="69b57-107">However, one versioning feature, *round-tripping*, must be built into the type from the first version in order to work properly.</span></span>  
  
## <a name="round-tripping"></a><span data-ttu-id="69b57-108">往返</span><span class="sxs-lookup"><span data-stu-id="69b57-108">Round-Tripping</span></span>  
 <span data-ttu-id="69b57-109">当数据从数据协定的新版本传递到旧版本，然后传递回新版本时，就发生了往返。</span><span class="sxs-lookup"><span data-stu-id="69b57-109">Round-tripping occurs when data passes from a new version to an old version and back to the new version of a data contract.</span></span> <span data-ttu-id="69b57-110">往返保证了数据不会丢失。</span><span class="sxs-lookup"><span data-stu-id="69b57-110">Round-tripping guarantees that no data is lost.</span></span> <span data-ttu-id="69b57-111">如果启用往返功能，则可以使类型向前兼容于数据协定版本管理模型所支持的任何未来更改。</span><span class="sxs-lookup"><span data-stu-id="69b57-111">Enabling round-tripping makes the type forward-compatible with any future changes supported by the data contract versioning model.</span></span>  
  
 <span data-ttu-id="69b57-112">若要对某一特定类型启用往返功能，该类型必须实现 <xref:System.Runtime.Serialization.IExtensibleDataObject> 接口。</span><span class="sxs-lookup"><span data-stu-id="69b57-112">To enable round-tripping for a particular type, the type must implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span> <span data-ttu-id="69b57-113">该接口包含一个属性，即 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>（由 <xref:System.Runtime.Serialization.ExtensionDataObject> 类型返回）。</span><span class="sxs-lookup"><span data-stu-id="69b57-113">The interface contains one property, <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> (returning the <xref:System.Runtime.Serialization.ExtensionDataObject> type).</span></span> <span data-ttu-id="69b57-114">该属性存储数据协定未来版本中对当前版本未知的所有数据。</span><span class="sxs-lookup"><span data-stu-id="69b57-114">The property stores any data from future versions of the data contract that is unknown to the current version.</span></span>  
  
### <a name="example"></a><span data-ttu-id="69b57-115">示例</span><span class="sxs-lookup"><span data-stu-id="69b57-115">Example</span></span>  
 <span data-ttu-id="69b57-116">下面的数据协定不向前兼容于未来的更改。</span><span class="sxs-lookup"><span data-stu-id="69b57-116">The following data contract is not forward-compatible with future changes.</span></span>  
  
 [!code-csharp[C_DataContract#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#7)]
 [!code-vb[C_DataContract#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#7)]  
  
 <span data-ttu-id="69b57-117">若要使该类型兼容于未来的更改（例如添加名为“phoneNumber”的新数据成员），应实现 <xref:System.Runtime.Serialization.IExtensibleDataObject> 接口。</span><span class="sxs-lookup"><span data-stu-id="69b57-117">To make the type compatible with future changes (such as adding a new data member named "phoneNumber"), implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span>  
  
 [!code-csharp[C_DataContract#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#8)]
 [!code-vb[C_DataContract#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#8)]  
  
 <span data-ttu-id="69b57-118">当 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 基础结构遇到不属于原始数据协定的数据时，该数据被存储在该属性中并保留下来。</span><span class="sxs-lookup"><span data-stu-id="69b57-118">When the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure encounters data that is not part of the original data contract, the data is stored in the property and preserved.</span></span> <span data-ttu-id="69b57-119">除非是临时存储，否则不会以任何其他方式处理该数据。</span><span class="sxs-lookup"><span data-stu-id="69b57-119">It is not processed in any other way except for temporary storage.</span></span> <span data-ttu-id="69b57-120">如果对象返回到它的起始位置，则原始（未知）数据也将返回。</span><span class="sxs-lookup"><span data-stu-id="69b57-120">If the object is returned back to where it originated, the original (unknown) data is also returned.</span></span> <span data-ttu-id="69b57-121">由此，数据完成了从起始终结点又回到起始终结点的往返过程而没有丢失。</span><span class="sxs-lookup"><span data-stu-id="69b57-121">Therefore, the data has made a round trip to and from the originating endpoint without loss.</span></span> <span data-ttu-id="69b57-122">但请注意，如果起始终结点要求处理数据，则不会满足这一期望，该终结点必须以某种方式检测并调整更改。</span><span class="sxs-lookup"><span data-stu-id="69b57-122">Note, however, that if the originating endpoint required the data to be processed, that expectation is unmet, and the endpoint must somehow detect and accommodate the change.</span></span>  
  
 <span data-ttu-id="69b57-123"><xref:System.Runtime.Serialization.ExtensionDataObject> 类型不包含公共方法或属性。</span><span class="sxs-lookup"><span data-stu-id="69b57-123">The <xref:System.Runtime.Serialization.ExtensionDataObject> type contains no public methods or properties.</span></span> <span data-ttu-id="69b57-124">因此，无法直接访问存储在 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> 属性内部的数据。</span><span class="sxs-lookup"><span data-stu-id="69b57-124">Thus, it is impossible to get direct access to the data stored inside the <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> property.</span></span>  
  
 <span data-ttu-id="69b57-125">通过在 `ignoreExtensionDataObject` 构造函数中将 `true` 设置为 <xref:System.Runtime.Serialization.DataContractSerializer>，或者在 <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> 中将 `true` 属性设置为 <xref:System.ServiceModel.ServiceBehaviorAttribute>，可以关闭往返功能。</span><span class="sxs-lookup"><span data-stu-id="69b57-125">The round-tripping feature may be turned off, either by setting `ignoreExtensionDataObject` to `true` in the <xref:System.Runtime.Serialization.DataContractSerializer> constructor or by setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> property to `true` on the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="69b57-126">当该功能关闭时，反序列化程序将不填充 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> 属性，序列化程序也不发出该属性的内容。</span><span class="sxs-lookup"><span data-stu-id="69b57-126">When this feature is off, the deserializer will not populate the <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> property, and the serializer will not emit the contents of the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b57-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="69b57-127">See Also</span></span>  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 <xref:System.Runtime.Serialization.ExtensionDataObject>  
 [<span data-ttu-id="69b57-128">数据协定版本控制</span><span class="sxs-lookup"><span data-stu-id="69b57-128">Data Contract Versioning</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)  
 [<span data-ttu-id="69b57-129">最佳做法：数据协定版本控制</span><span class="sxs-lookup"><span data-stu-id="69b57-129">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
